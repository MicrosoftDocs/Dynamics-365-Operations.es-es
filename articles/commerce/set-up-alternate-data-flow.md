---
title: Configurar un flujo de datos alternativo para recomendaciones
description: En este artículo se describe cómo configurar un entorno mediante un flujo de datos alternativo para proporcionar datos al servicio de recomendaciones.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460169"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Configurar un flujo de datos alternativo para recomendaciones

[!include [banner](includes/banner.md)]

En este artículo se describe cómo configurar un entorno mediante un flujo de datos alternativo para proporcionar datos al servicio de recomendaciones.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>Comparación del flujo de datos listo para usar con el flujo de datos alternativo

La siguiente ilustración muestra el flujo de datos listo para usar en un entorno.

![Flujo de datos listo para usar en un entorno](media/reco-out-of-the-box-dataflow-2.png)

La siguiente ilustración muestra un flujo de datos alternativo, donde el trabajo por lotes de sincronización del almacén de entidades se reemplaza con pasos de flujo de datos alternativos.

![Flujo de datos alternativo en un entorno](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Supuestos

- En este artículo se supone que ya ha habilitado el servicio de recomendaciones para su entorno. Para obtener más información, consulte [Habilitar recomendaciones de producto](enable-product-recommendations.md).
- Cuando trabaja con archivos y carpetas en la Cuenta de Microsoft Azure Data Lake Storage:

    - Puede usar la interfaz del portal web de Azure o la aplicación Explorador de Azure Storage.
    - Los puntos de partida para trabajar con archivos y carpetas se encuentran en el contenedor **dynamics365-financeandoperations** contenedor que se encuentra debajo de la carpeta cuyo nombre coincide con la URL de su entorno.
    - Si el nombre de su entorno de espacio aislado es **MyUAT**, la URL base del entorno será `myuat.sandbox.operations.dynamics.com`.
    - Si hay más de un entorno conectado a la misma cuenta de almacenamiento, cada entorno tendrá su propia carpeta raíz.

## <a name="prerequisites"></a>Requisitos previos

Debe cumplir los prerrequisitos siguientes antes de implementar el enfoque de flujo de datos alternativo.

### <a name="set-up-microsoft-power-platform"></a>Configurar Microsoft Power Platform

Para configurar Microsoft Power Platform, siga las instrucciones en [Habilitar la integración Microsoft Power Platform](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Instalar el complemento Exportar a Data Lake

Para instalar el complemento Exportar a Data Lake, siga las instrucciones en [Instalar el complemento Exportar a Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Tome nota de los valores de configuración, porque los necesitará para algunos de los pasos siguientes.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Configurar tablas para exportar en Dynamics 365

Sincronización de tablas de Dynamics 365 a Azure Data Lake Storage se gestiona en la página **Exportar a Data Lake**. Debido a que esa página actualmente no tiene un elemento de menú, solo los usuarios en el rol de seguridad **Administrador de sistema** pueden abrirlo.

Para configurar tablas para exportar en Dynamics 365, siga estos pasos.

1. Para abrir la página **Exportar a Data Lake**, agregue la cadena `?mi=DataFeedsDefinitionWorkspace` a la URL base del entorno, como se muestra en el siguiente ejemplo:

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. En la página **Exportar a Data Lake** y copie las tablas que se enumeran en la sección [Lista de tablas de cubo RetailSales](#list-of-retailsales-cube-tables) de este artículo.
1. En la columna **Nombre del sistema**, expanda la lista de opciones de filtro.
1. Para el tipo de filtro, seleccione **es uno de**. Luego coloque el cursor en el cuadro de texto y pegue la lista de tablas que copió de la página **Exportar a Data Lake**.
1. En la parte inferior de la lista de opciones de filtro, seleccione **Aplicar**.
1. Seleccione todas las filas de la cuadrícula y, a continuación, seleccione **Activar**.

> [!NOTE]
> Antes de pasar al siguiente paso, todas las filas deben actualizarse a un estado de **Ejecutando**. Resuelva los problemas y resuelva los errores según sea necesario.

### <a name="create-a-synapse-workspace"></a>Crear espacio de trabajo Synapse

Para crear un espacio de trabajo de Synapse si aún no tiene uno, siga las instrucciones en [Inicio rápido: crear un espacio de trabajo de Synapse](/azure/synapse-analytics/quickstart-create-workspace).

Para mantener sus recursos de Azure organizados, le recomendamos que coloque la cuenta de Data Lake Storage y el área de trabajo de Synapse juntos en un grupo de recursos en Azure. Puede reutilizar la cuenta de almacenamiento que creó cuando instalaba el complemento Exportar a Data Lake.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Cree una base de datos en Synapse para el procesamiento de datos de recomendación

Use la aplicación de consola de la utilidad Common Data Model (CDMUtil_ConsoleApp) para crear una base de datos en su espacio de trabajo de Synapse y llénela desde las tablas de Common Data Model en Data Lake Storage. Le recomendamos que utilice la utilidad Common Data Model con su base de datos en un entorno de desarrollo, en caso de que haya extensiones.

> [!NOTE]
> Los siguientes pasos asumen que no se agregan datos de extensión al cubo RetailSales.

Para crear una base de datos en Synapse, siga estos pasos.

1. Vaya a [Dynamics-365-FastTrack-Implementation-Assets GitHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app) y siga los pasos para descargar el archivo **CDMUtilConsoleApp.zip**.
1. Extraiga el archivo zip en una carpeta local.
1. Abra el archivo **CDMUtil_ConsoleApp.dll.config** en un editor de texto y actualice los siguientes valores:

    1. Establezca el valor **Id. de inquilino** (Id. de inquilino de Azure).
    1. Selecciona el valor **Clave de acceso** (la clave de acceso para la cuenta de Data Lake Storage).

        1. En Azure Portal, abra su cuenta de almacenamiento.
        1. En el menú del lado izquierdo de la página, seleccione **Teclas de acceso**.
        1. En la parte superior de la página, seleccione **Mostrar claves**.
        1. Seleccione el botón Copiar para uno de los dos campos clave y luego pegue el valor entre comillas dobles en el archivo de configuración.

    1. Establezca el valor **ManifestURL** a la URL de su archivo **Tables.manifest.cdm.json** en Azure Data Lake Storage. Para obtener la dirección URL, busque el archivo en Azure Portal, seleccione los puntos suspensivos (**...**) en el lado derecho de la vista y luego seleccione **Propiedades**. La URL es la primera propiedad que se muestra en la pestaña **Visión general**.
    1. Establezca el valor **TargetDbConnectionString** a la cadena de conexión para el grupo SQL sin servidor integrado de su espacio de trabajo de Synapse.

        1. En el espacio de trabajo de Synapse, seleccione la pestaña **Administrar**.
        1. En el submenú, seleccione **Grupos de SQL**.
        1. Seleccione el nombre **Incorporado** para ver las propiedades del grupo.
        1. En el cuadro de diálogo propiedades, seleccione el tipo de conexión ADO.NET que quiera usar. Luego copie el valor de la cadena de conexión y péguelo entre comillas dobles en el archivo de configuración.

        > [!NOTE]
        > Debe tener permiso para crear bases de datos. Para facilitar el uso, es posible que desee utilizar la cuenta de administrador integrada **sqladminuser**.

    1. Descomente el nodo **ProcessEntities** y establezca su valor en **true** (por ejemplo `<add key="ProcessEntities" value ="true"/>`).

1. Guarde y cierre el archivo **CDMUtil_ConsoleApp.dll.config**.
1. Copie el archivo **EntityList.json** al directorio **/Manifest**.
1. En una ventana del símbolo del sistema, ejecute **cdmutil_consoleapp.exe**.

> [!NOTE]
> Cuando revise el resultado, debe haber 35 entidades/vistas, al menos 75 tablas y ningún error.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Prepare el directorio de Mediciones agregadas RetailSales de Data Lake

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Realice una copia de seguridad de los datos del cubo RetailSales actual de Data Lake Storage

La forma más fácil de hacer una copia de seguridad de los datos del cubo RetailSales actual es cambiar el nombre del directorio **RetailSales** en Data Lake Storage a **RetailSales-backup** o algo similar. Este método conserva los datos existentes en caso de que se requiera una solución de problemas más adelante.

La carpeta del cubo **/RetailSales** se puede encontrar en la siguiente ubicación:

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Cree una nueva carpeta RetailSales y cargue el archivo del modelo

Para crear un nuevo directorio **RetailSales** y subir el archivo **model.json** a Data Lake Storage, siga estos pasos.

1. Cree un nuevo directorio vacío al mismo nivel que el directorio anterior y asígnele el nombre **RetailSales**.
1. Suba el archivo **model.json** al nuevo directorio.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Crear una canalización para copiar los datos del cubo RetailSales

La canalización leerá las vistas del cubo RetailSales y exportará los datos a archivos .csv en Data Lake Storage.

Para crear una canalización para copiar los datos del cubo RetailSales siga estos pasos.

1. En el espacio de trabajo de Synapse, seleccione la pestaña **Integrar**.
1. Seleccione el signo más (**+**), y luego seleccione **Importar desde plantilla de canalización**.
1. Descargar y luego seleccionar el [Archivo ExportRetailSalesCubeViews.zip](https://aka.ms/reco-alternate-dataflow-files).
1. Seleccione su servicio vinculado a la base de datos SQL.
1. Seleccione el servicio vinculado a su cuenta de almacenamiento.
1. Abra la herramienta **Copiar datos** y cambie la propiedad **Ruta de la carpeta** propiedad a **\<environment_name\>/...**.

### <a name="test-execution-of-the-pipeline"></a>Probar la ejecución de la canalización

Le recomendamos que pruebe la canalización utilizando solo una vista. La vista **RetailSales_RetailMediaTemplateView** funciona bien porque normalmente contiene menos de 10 filas.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>Programe la canalización para que se ejecute en un programa recurrente

Cada vez que se ejecuta la canalización, se produce el consumo de Azure. Le recomendamos que programe ejecuciones a intervalos de 48 horas o más. Siempre puede ejecutar la canalización manualmente si debe sincronizar los datos inmediatamente. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Lista de tablas para la sincronización de Dynamics 365 con Data Lake Storage

La siguiente lista de tablas es un subconjunto de todas las tablas necesarias para todo el cubo RetailSales. El servicio de recomendaciones utiliza solo 15 de las vistas en el cubo RetailSales y la lista de tablas requeridas se filtró en consecuencia.

### <a name="list-of-retailsales-cube-tables"></a>Lista de tablas de cubo RetailSales

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Catálogo
- CatalogProduct
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- LogisticsLocation
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>Ver la lista del parámetro para pasar a la canalización de Synapse

La siguiente lista separada por comas contiene las vistas del cubo RetailSales en las que la canalización realizará una operación de "selección". Luego copiará los resultados en Data Lake Storage.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView,RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> El parámetro de canalización debe ser una lista de nombres de vista separados por comas simples. No debe haber espacios ni saltos de línea.

## <a name="environment-specific-fixes"></a>Arreglos específicos del entorno

### <a name="retailchannelview-fix"></a>Corrección de RETAILCHANNELVIEW

La vista **RETAILCHANNELVIEW** contiene un entero codificado que representa una organización del tipo "canal minorista". El valor real del tipo puede cambiar de un entorno a otro o de un inquilino a otro.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

Para actualizar el entero codificado de forma rígida, siga estos pasos.

1. En Dynamics 365, busque el valor **ChannelID** para su canal en línea.
1. En una instancia de SQL Server Management Studio (SSMS) adjunta a la base de datos de Synapse, ejecute la siguiente consulta.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Copie el valor de la primera columna (**INSTANCERELATIONTYPE**) y péguelo en la definición de la vista.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="pipeline-task-fails"></a>La tarea de canalización falla

Debería haber 15 ejecuciones de tareas de canalización para la tarea **CopyData**. Si alguna ejecución falla, debe validar que existen todos los objetos SQL dependientes y que se ejecutan las consultas. La forma más fácil de llegar a todas las dependencias es usar SSMS para conectarse a la base de datos. A continuación, puede seleccionar y mantener (o hacer clic con el botón derecho) una vista y seleccionar **Generar CREAR como en una nueva ventana**.

El mensaje de error puede incluir el texto siguiente:

- Error: error ocurrido en el lado 'Fuente'
- Error al manejar el archivo externo: 'Número máximo de errores'.
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Supuesto de ejemplo

En este ejemplo, el **RetailSales_RetailProductCategory** la tarea falla y recibe un error de "Número máximo de errores".

Para depurar el error, siga estos pasos.

1. Abra el archivo **EntityList.json** en un editor de texto (por ejemplo, Visual Studio Code).
1. Encuentre la definición de vista para **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Esta vista depende solo de otra vista: **RetailProductCategoryView** _. Encuentre la definición de vista para _*RetailProductCategoryView**.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Esta vista depende de otras tres vistas: **RETAILPRODUCTCATEGORY**, **ECORESPRODUCTTRANSLATIONS**, y **RETAILCATEGORYEXPANDED**. Busque la definición de cada una de estas vistas y enumere sus dependencias. Continúe hasta que encuentre todas las vistas dependientes.

    Aquí está la lista completa en orden de árbol de dependencia. Se deben validar trece vistas.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. En Excel, cree las siguientes 13 declaraciones **seleccione contar(\*) de \<view_name\>**. Ejecute estas instrucciones en SSMS y envíe los resultados a texto. Luego desplácese por los resultados para ver si alguna de las vistas falló. El error inicial sugiere que al menos una de las vistas fallará.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. Una forma de validar lo que está viendo es crear una vista dependiente de la raíz para generar la definición de vista en SSMS. Luego verifique que haya una columna de archivo de Azure Data Lake que se llame **r.filepath**. La presencia de esta columna indicará que la vista que está inspeccionando está leyendo datos de Data Lake Storage.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
