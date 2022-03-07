---
title: Usar los orígenes de datos de JOIN del modelo ER asignaciones para recopilar datos de las tablas de la aplicación múltiple
description: En este tema se explica cómo puede usar orígenes de datos de tipo JOIN en informes electrónicos (ER).
author: NickSelin
ms.date: 04/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-03-01
ms.dyn365.ops.version: Release 10.0.1
ms.openlocfilehash: be5646eaf395310c8b34586ef1274a41b5b97029
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944736"
---
# <a name="use-join-data-sources-to-get-data-from-multiple-application-tables-in-electronic-reporting-er-model-mappings"></a>Usar los orígenes de datos de JOIN para obtener datos de varias tablas de aplicación múltiple en las asignaciones de modelo de informes electrónicos (ER)

[!include[banner](../includes/banner.md)]

A medida que configura las asignaciones o los formatos de modelos electrónicos (ER), puede [agregar](#review) los orígenes de datos requeridos del tipo **Unión**. En el tiempo de diseño, un origen datos **Unión** se configura como un conjunto de varios orígenes de datos que devuelve una lista de registros. Para cada origen de datos excepto la primera, es necesario definir condiciones necesarias para unir los registros de los orígenes de datos actual y anterior. En el tiempo de ejecución, un origen de datos tipo **Unión** [devuelve](#executeERformat) una sola lista de registros participada que contiene campos de los registros de orígenes de datos anidados.

Actualmente se admiten los siguientes tipos de uniones:

- Unión externa (izquierda):
    - Une a todos los registros del primer origen de datos (de más a la izquierda) y después cualquier coincidencia de acuerdo a las condiciones configuradas de los registros de la segunda fuente de datos (de más a la derecha).
- Unión interna (derecha):
    - Une solo los registros del primer origen de datos (de más a la izquierda) y solo los registros del segundo origen de datos (de más a la derecha) que coincidan según las condiciones configuradas.

En el origen de datos configurado **Unión**, cuando todos los orígenes de datos son del tipo **Tabla de registros**, la ejecución del origen de datos de la Unión puede [efectuarse en el nivel de la base de datos](#analyze) usando una sola instrucción SQL. Esta instrucción reduce el número de llamadas a la base de datos, lo que mejora el rendimiento del modelo de asignación. De lo contrario, la ejecución del origen **Unión de datos** se realiza en la memoria.

> [!NOTE]
> Usar la función **VALUEIN** en las expresiones de ER que especifican las condiciones para participar registra en orígenes de datos del tipo de combinación no se admite aún. Visite la página [Diseñador de fórmulas en informes electrónicos](general-electronic-reporting-formula-designer.md) para obtener más información sobre esta función.

Para obtener más información acerca de esta característica, complete el ejemplo de este tema.

## <a name="example-use-join-data-sources-in-er-model-mappings"></a>Ejemplo: Usar orígenes de datos JOIN en asignaciones de modelo de ER

Los pasos siguientes se explica cómo el administrador del sistema o el desarrollador del informe electrónico puede configurar un modelo de asignación de informe electrónico (ER) para obtener datos de varias tablas de aplicación a la vez usando fuentes de datos del tipo **Unión** para mejorar el rendimiento en el acceso a los datos. Estos pasos se pueden realizar por cualquier empresa de Dynamics 365 Finance o Regulatory Configuration Service (RCS).

### <a name="prerequisites"></a>Requisitos previos

Para completar los ejemplos de este tema, debe obtener acceso a uno de los siguientes en función de qué servicio se use para completar estos pasos:

**Acceso a Finance para uno de los roles siguientes:**

- Desarrollador de informes electrónicos
- Consultor funcional de informes electrónicos
- Administrador del sistema

**Acceso a RCS para uno de los roles siguientes:**

- Desarrollador de informes electrónicos
- Consultor funcional de informes electrónicos
- Administrador del sistema

También debe completar primero los pasos del procedimiento [Creación de un proveedor de configuraciones y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

De antemano, también debe descargar y guardar los siguientes archivos de configuración de ER de muestra:

| **Descripción del contenido**  | **Nombre de archivo**   |
|--------------------------|-----------------|
| Ejemplo de archivo de configuración de **Modelo de datos de ER**, que se usa como origen de datos para los ejemplos.| [Modelo para aprender fuentes de datos JOIN.version.1.1.xml](https://download.microsoft.com/download/5/c/1/5c1d8a57-6ebd-425b-bc5d-c71dde92c6af/ModeltolearnJOINdatasources.version.1.xml) |
| Ejemplo de archivo de configuración de **Asignación de modelo ER**, que implementa el modelo de datos ER para los ejemplos. | [Asignación para aprender fuentes de datos JOIN.version.1.1.xml](https://user-images.githubusercontent.com/19827601/115923048-86b10400-a432-11eb-9e57-c37a02effcb4.png)|
| Archivo de configuración de ejemplo del **Formato ER**. En este archivo se describen los datos para rellenar el componente del formato de ER para los ejemplos. | [Formato para aprender fuentes de datos JOIN.version.1.1.xml](https://download.microsoft.com/download/f/f/8/ff8f1b48-14d0-4c73-9145-bcdf8b5265bc/FormattolearnJOINdatasources.version.1.1.xml) |

### <a name="activate-a-configurations-provider"></a>Activar un proveedor de las configuraciones

1. Obtener acceso a Finance o al RCS en la primera sesión de su explorador Web.
2. Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.
3. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, compruebe que aparece el proveedor de la configuración para la empresa de ejemplo [Litware, Inc.](http://www.litware.com) y que se ha marcado como **Activo**. Si no ve a este proveedor de configuración, siga los pasos del procedimiento [Creación de un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![Espacio de trabajo de los informes electrónicos](./media/GER-JoinDS-ActiveProvider.PNG)

### <a name="import-sample-er-configuration-files"></a>Importar archivos de configuración del ejemplo ER.

1. Seleccione **Configuraciones de informes**.
2. Importar el archivo de configuración del modelo de datos de ER.
    1. Seleccione **Intercambiar**.
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Explorar** para encontrar el archivo **Modelo para aprender las fuentes de datos JOIN.version.1.1.xml**.
    4. Seleccione **Aceptar**.
3. Importar el archivo de asignación del modelo de datos de ER.
    1. Seleccione **Intercambiar**.
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Explorar** para encontrar el archivo **Asignación para aprender las fuentes de datos JOIN.version.1.1.xml**.
    4. Seleccione **Aceptar**.
4. Importar el archivo de formato de configuración ER.
    1. Seleccione **Intercambiar**.
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Explorar** para encontrar el archivo **Formato para aprender las fuentes de datos JOIN.version.1.1.xml**.
    4. Seleccione **Aceptar**.
5. En el árbol de las configuraciones, expanda el elemento **Modelo para aprender fuentes de datos JOIN** junto con otros elementos de modelo (si está disponible).
6. Observe la lista de la configuración de ER en los detalles del árbol además de la versión en la ficha desplegable **Versiones**, se usarán como origen de los datos del informe de ejemplo.

    ![Página de configuraciones de informes electrónicos](./media/GER-JoinDS-ConfigurationsTree.PNG)

### <a name="turn-on-execution-trace-options"></a>Active las opciones de seguimiento de la ejecución

1. Seleccione **CONFIGURACIONES**.
2. Seleccione **Parámetros del usuario**.
3. Establezca los parámetros de seguimiento de la ejecución como se muestra en la captura de pantalla continuación.

    ![Página de parámetros de informes electrónicos del usuario](./media/GER-JoinDS-Parameters.PNG)

    Con estos parámetros activados, para cada ejecución del archivo importado del formato de ER, se realizará el seguimiento de la ejecución. Usando los detalles de seguimiento generados de la ejecución, se puede analizar la ejecución de los componentes modelos del formato de ER y la asignación de ER. Visite la página [Ejecución de seguimiento del formato de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md) para obtener más información sobre la función de seguimiento de la ejecución de ER.

### <a name="review-er-model-mapping-part-1"></a>Revise la asignación del modelo de ER (parte 1)

Revise los valores del componente de asignación del modelo de ER. El componente está configurado para acceder a información sobre las versiones de configuraciones ER, detalles de las configuraciones y proveedores de configuración sin usar las fuentes de datos del tipo **Unión**.

1. Seleccione la configuración **Asignación para aprender fuentes de datos**
2. Seleccione **Diseñador** para abrir la lista de asignaciones.
3. Seleccione **Diseñador** para revisar los detalles de la asignación.
4. Seleccionar **Mostrar detalles**.
5. En el árbol de las configuraciones, expanda los artículos del modelo de datos **Set1** y **Set1.Details** :

    1. Enlazar **Detalles: Lista de registro = versiones** indica que el elemento **Set1.Details** está enlazado en el origen datos **Versiones** que devuelve los registros de la tabla **ERSolutionVersionTable** . Cada registro de esta tabla representa una única versión de una configuración de ER. El contenido de esta tabla se muestra en la ficha desplegable **Versiones**, en la página **Configuraciones**.
    2. Enlazar **ConfigurationVersion: String = @.PublicVersionNumber** significa que el valor de la versión pública de la versión de cada configuración de ER está tomado del campo **PublicVersionNumber** de la tabla **ERSolutionVersionTable** y se incluirán al elemento **ConfigurationVersion**.
    3. Enlazar **ConfigurationTitle: String = @.'>Relations'. Solution.Name** indica que el nombre de una configuración de ER está tomado del campo **Nombre** de la tabla **ERSolutionTable** que evalúa mediante la relación varios-a-uno (**'>Relations'**) entre **ERSolutionVersionTable** y las tablas **ERSolutionTable** . Los nombres de las configuraciones de ER de la instancia de aplicación actual se muestran en el árbol de las configuraciones de la página **Configuraciones**.
    4. Enlazar **@.'>Relations'.Solution.'>Relations'.SolutionVendor.Name** significa que el nombre del proveedor de configuración propietario de la configuración actual se toma del campo **Nombre** de la tabla **ERVendorTable** evaluando mediante la relación varios-a-uno entre las tablas **ERSolutionTable** y **ERVendorTable**. Los nombres de los proveedores de configuración de ER de la instancia de aplicación actual se muestran en el árbol de las configuraciones de la página **Configuraciones** en el encabezado de página de cada configuración. La lista completa de proveedores de la configuración del ER se puede encontrar en la página de la tabla **Administración de la organización \> Informes electrónicos \> Proveedor de configuración**.

    ![Página del diseñador de asignación de modelos de ER, lista de elementos del modelo de datos enazado](./media/GER-JoinDS-Set1Review.PNG)

6. En el árbol de las configuraciones, expanda los artículos del elemento de modelo de datos **Set1.Summary**:

    1. Enlazar **VersionsNumber: Integer = VersionsSummary.aggregated.VersionsNumber** indica que el elemento **Set1.Summary.VersionsNumber** está enlazado al campo del agregado **VersionsNumber** del origen de datos **VersionsSummary** del tipo **GroupBy** que se haya configurado devolver el número de registros de la tabla **ERSolutionVersionTable** mediante el origen de datos **Versiones**.

    ![Editar la página de parámetros 'Agrupar por'](./media/GER-JoinDS-Set1GroupByReview.PNG)

7. Cierre la página.

### <a name="review-er-model-mapping-part-2"></a><a name="review"></a> Revise la asignación del modelo de ER (parte 2)

Revise los valores del componente de asignación del modelo de ER. El componente está configurado para acceder a información sobre las versiones de configuraciones ER, detalles de las configuraciones y proveedores de configuración usando una fuente de datos del tipo **Unión**.

1. En el árbol de las configuraciones, expanda los artículos del modelo de datos **Set2** y **Set2.Details**. El enlace **Detalles: Registro enumerado = detalles** indica que el elemento **Set2.Details** está enlazado el origen de datos **Detalles** configurado como origen de datos del tipo **Unión**.

    ![Página del diseñador de asignación del modelo ER que muestra los elementos del modelo de datos Set2:Record](./media/GER-JoinDS-Set2Review.PNG)

    El origen de datos **Unión** se puede agregar seleccionando el origen de datos **Funciones\Unión**:

    ![Página del diseñador de asignación de modelo de ER, unirse al tipo de origen de datos](./media/GER-JoinDS-AddJoinDS.PNG)

2. Seleccionar **Detalle** s del origen de datos.
3. Seleccione **Editar** en el panel **Orígenes de datos**.
4. Seleccione **Editar unión**.
5. Seleccionar **Mostrar detalles**.

    ![Página de los parámetros del origen de datos de JOIN](./media/GER-JoinDS-JoinDSEditor.PNG)

    Esta página se utiliza para diseñar el origen de datos necesario **Tipo de unión**. En el tiempo de ejecución, este origen de datos creará una sola lista de registros participada de los orígenes de datos de la cuadrícula **Lista unida**. La Unión de registros empezará con el origen de datos **ConfigurationProviders** que se encuentra en la cuadrícula como primera (la columna **Tipo** está en blanco para ella). Los registros de cada otro origen de datos serán unidos por tanto a los registros del origen de datos principal basado en el pedido en la cuadrícula. Cada origen de datos que une se debe configurar como un origen de datos anidado bajo origen de datos de destino (el origen datos `1Versions` se anida bajo `1Configurations` ; uno el origen de datos `1Configurations` se anida bajo **ConfigurationProviders**). Cada origen de datos debe contener las condiciones para la unión. En el origen de datos de esta **Unión** concreta, se definen las uniones siguientes:

    - Cada registro del origen de datos **ConfigurationProviders** (referido a la tabla **ERVendorTable** ) se une con solo los registros de **1Configurations** (referida en la tabla **ERSolutionTable** ) con el mismo valor en los campos **SolutionVendor** y **RecId**. El tipo **Unión interna** se usa para esta unión junto con las siguientes condiciones para coincidir registros:

    FILTRO (Configuraciones, Configurations.SolutionVendor = ConfigurationProviders.RecId)

    - Cada registro del origen de datos **1Configurations** (referido a la tabla **ERSolutionTable** ) se une con solo los registros de **1Versions** (referida en la tabla **ERSolutionVersionTable** ) con el mismo valor en los campos **Solution** y **RecId**. El tipo **Unión interna** se usa para esta unión junto con las siguientes condiciones para coincidir registros:

    FILTRO (ConfigurationVersions, ConfigurationVersions.Solution = ConfigurationProviders.'1Configurations'.RecId)

    - La opción **Ejecutar** se configura como **Consulta** lo que significa que este origen de datos de la unión se ejecuta en el tiempo de ejecución en el nivel de la base de datos como llamada directa de SQL.

    Para unir los registros de los orígenes de datos que representan las tablas de la aplicación, puede especificar condiciones de combinación mediante par de campos con la excepción de unos que describan las relaciones AOT existentes entre estas tablas. Este tipo de unión puede estar configurado para ejecutarse también en el nivel de la base de datos.

6. Cierre la página.
7. Seleccione **Cancelar**.
8. En el árbol de las configuraciones, expanda los artículos del elemento de modelo de datos **Set2.Summary**:

    - Enlazar **VersionsNumber: Integer = DetailsSummary.aggregated.VersionsNumber** indica que el elemento **Set2.Summary.VersionsNumber** está enlazado al campo del agregado **VersionsNumber** del origen de datos **DetailsSummary** del tipo **GroupBy** que se haya configurado para devolver el número de registros unidos de la tabla **Detalles** mediante el origen de datos del tipo **Unión**.
    - La opción de ubicación **Ejecución** se configura como **Consulta** lo que significa que este origen de datos **GroupBy** se ejecutará en tiempo de ejecución como llamada SQL directa al nivel de base de datos. Este comportamiento es posible porque el origen de datos base **Detalles** del tipo **Unión** se configura según lo ejecutado en el nivel de la base de datos.

    ![Página de los parámetros del origen de datos de GROUPBY](./media/GER-JoinDS-Set2GroupByReview.PNG)

9. Cierre la página.
10. Seleccione **Cancelar**.

### <a name="execute-er-format"></a><a name="executeERformat"></a> Ejecutar formato ER

1. Acceda a Finance o al RCS en la segunda sesión del explorador web mediante las mismas credenciales y empresa que en la primera sesión.
2. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
3. Expanda la configuración **Modelo para aprender fuentes de datos JOIN**.
4. Seleccione la configuración **Formato para aprender fuentes de datos JOIN**.
5. Seleccione **Diseñador**.
6. Seleccionar **Mostrar detalles**.
7. Seleccione **Asignación**.
8. Seleccione **Expandir/Contraer**.

    Este formato están diseñado para rellenar un archivo de texto generado con una nueva línea para cada versión de una configuración ER (secuencia **Versión**). Cada línea generada contendrá el nombre de un proveedor de la configuración que posee la configuración actual, el nombre de la configuración y la versión de configuración separados por la marca del punto y coma. La línea final de archivo generado contendrá el número de versiones detectadas de las configuraciones de ER (secuencia **Resumen**).

    ![Página del diseñador de formato ER, pestaña Formato](./media/GER-JoinDS-FormatReview.PNG)

    Los orígenes de datos **Datos** y **Resumen** se usan para rellenar los detalles de la versión de la configuración al archivo generado:

    - La información del modelo de datos **Set1** se usa cuando elija **No** para el origen de datos **Selector** en el tiempo de ejecución en la página del cuadro de diálogo cuando ejecuta formato de ER.
    - La información del modelo de datos **Set2** se usa cuando elija **Sí** para el origen de datos **Selector** en el tiempo de ejecución en la página del cuadro de diálogo.

    ![Página del diseñador de formato de ER, pestaña Asignación](./media/GER-JoinDS-FormatMappingReview.PNG)

9. Seleccione **Ejecutar**.
10. En la página de diálogo, seleccione **No** en el campo **Usar origen de datos JOIN**.
11. Seleccione **Aceptar**.
12. Revisar el archivo generado.

    ![Archivo generado de parámetros de informe electrónico que no utiliza la fuente de datos JOIN](./media/GER-JoinDS-Set1Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a>Analizar el seguimiento de la ejecución del formato de ER

1. En la primera sesión de Finance o de RCS, seleccione **Diseñador**.
2. Seleccione **Seguimiento del rendimiento**.
3. En la cuadrícula **Seguimiento de rendimiento**, seleccione el registro superior del último seguimiento de la ejecución de un formato de ER que utilizó el componente modelo actual de la asignación.
4. Seleccione **Aceptar**.

    Las estadísticas de la ejecución le informan acerca de llamadas duplicadas a las tablas de la aplicación:

    - **ERSolutionTable** se ha llamado tantas veces que tiene registros de versión de la configuración de la tabla **ERSolutionVersionTable**, mientras que el número de tales llamadas se podría reducir para la mejora de rendimiento.
    - **ERVendorTable** se ha llamado dos por cada registro de versión de configuración que se encontró en la tabla **ERSolutionVersionTable**, mientras que el número de tales llamadas también se podría reducir.

    ![Estadísticas de ejecución en la página del diseñador de asignación de modelo de ER](./media/GER-JoinDS-Set1Run2.PNG)

5. Cierre la página.

### <a name="execute-er-format"></a>Ejecutar formato ER

1. Cambie a la ficha del explorador web con la segunda sesión de Finance o de RCS.
2. Seleccione **Ejecutar**.
3. En la página de diálogo, seleccione **Sí** en el campo **Usar origen de datos JOIN**.
4. Seleccione **Aceptar**.
5. Revisar el archivo generado.

    ![Archivo generado de parámetros de informes electrónicos que utiliza la fuente de datos JOIN](./media/GER-JoinDS-Set2Run.PNG)

#### <a name="analyze-er-format-execution-trace"></a><a name="analyze"></a> Analizar el seguimiento de la ejecución del formato de ER

1. En la primera sesión de Finance o de RCS, seleccione **Diseñador**.
2. Seleccione **Seguimiento del rendimiento**.
3. En la cuadrícula **Seguimiento de rendimiento**, seleccione el registro superior representando el último seguimiento de la ejecución de un formato de ER que utilizó el componente modelo actual de la asignación.
4. Seleccione **Aceptar**.

    Estadísticas le informa sobre lo siguiente:

    - La base de datos de aplicación se ha llamado una vez para conseguir los registros de las tablas **ERVendorTable**, **ERSolutionTable** y **ERSolutionVersionTable** para obtener el acceso a campos necesarios.

    ![Detalles de estadísticas de rendimiento en la página del diseñador de asignación de modelo de ER](./media/GER-JoinDS-Set2Run2.PNG)

    - La base de datos de aplicación se ha llamado una vez para calcular el número de versiones de la configuración mediante las uniones que se hayan configurado en el origen de datos **Detalles**.

    ![Página del diseñador de asignación del modelo ER que muestra las llamadas a la base de datos de aplicaciones](./media/GER-JoinDS-Set2Run3.PNG)

## <a name="limitations"></a>Limitaciones

Como puede ver en el ejemplo de este tema, el origen de datos **UNIRSE** se puede construir a partir de varias fuentes de datos que describen los conjuntos de datos individuales de los registros que eventualmente se deben unir. Puede configurar esos orígenes de datos utilizando la función ER incorporada [FILTRAR](er-functions-list-filter.md). Cuando configura el origen de datos para que se llame más allá del origen de datos **UNIRSE**, puede usar los rangos de empresas como parte de la condición para la selección de datos. La implementación inicial del origen de datos **UNIRSE** no admite fuentes de datos de este tipo. Por ejemplo, cuando llama a un origen de datos basado en [FILTRAR](er-functions-list-filter.md) dentro del alcance de la ejecución de un origen de datos **UNIRSE**, si el origen de datos llamado contiene rangos de empresas como parte de la condición para la selección de datos, se produce una excepción.

En Microsoft Dynamics 365 Finance, versión 10.0.12 (agosto de 2020), puede utilizar rangos de empresas como parte de la condición para la selección de datos en orígenes de datos basados en [FILTRAR](er-functions-list-filter.md) que se llaman dentro del alcance de la ejecución de un origen de datos **UNIRSE**. Debido a las limitaciones de la aplicación creadora de [consultas](../dev-ref/xpp-library-objects.md#query-object-model), los rangos de empresas solo se admiten para el primer origen de datos de un origen de datos **UNIRSE**.

### <a name="example"></a>Ejemplo

Por ejemplo, debe hacer una sola llamada a la base de datos de la aplicación para obtener la lista de transacciones de comercio exterior de varias compañías y los detalles del artículo de inventario al que se hace referencia en esas transacciones.

En este caso, configure los siguientes artefactos en su asignación de modelo ER:

- Origen de datos raíz **Intrastat** que representa la tabla **Intrastat**.
- Origen de datos raíz **Elementos** que representa la tabla **InventTable**.
- Origen de datos raíz **Empresas** que devuelve la lista de empresas (**DEMF** y **GBSI** en este ejemplo) donde se debe acceder a las transacciones. El código de empresa está disponible en el campo **Companies.Code**.
- Origen de datos raíz **X1** que tiene la expresión `FILTER (Intrastat, VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code))`. Como parte de la condición para la selección de datos, esta expresión contiene la definición de rangos de empresa `VALUEIN(Intrastat.dataAreaId, Companies, Companies.Code)`.
- Origen de datos **X2** como elemento anidado del origen de datos **X1**. Incluye la expresion `FILTER (Items, Items.ItemId = X1.ItemId)`.

Finalmente, puedes configurar un origen de datos **UNIRSE**, donde **X1** es el primer origen de datos y **X2** es la segunda fuente de datos. Puede especificar **Consulta** como opción de **Ejecutar** para forzar a ER a ejecutar este origen de datos en el nivel de la base de datos como una llamada directa de SQL.

Cuando el origen de datos configurado se ejecuta mientras la ejecución de ER se [rastrea](trace-execution-er-troubleshoot-perf.md), la siguiente declaración se muestra en el diseñador de asignación del modelo ER como parte de la traza de rendimiento ER.

`SELECT ... FROM INTRASTAT T1 CROSS JOIN INVENTTABLE T2 WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF',N'GBSI') )) AND ((T2.PARTITION=?) AND (T2.ITEMID=T1.ITEMID AND (T2.DATAAREAID = T1.DATAAREAID) AND (T2.PARTITION = T1.PARTITION))) ORDER BY T1.DISPATCHID,T1.SEQNUM`

> [!NOTE]
> Se produce un error si se ejecuta un origen de datos **UNIRSE** que se ha configurado para que contenga condiciones de selección de datos que tengan rangos de empresas para orígenes de datos adicionales de los orígenes de datos **UNIRSE** ejecutados.

## <a name="additional-resources"></a>Recursos adicionales

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Ejecución de seguimiento del formato de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
