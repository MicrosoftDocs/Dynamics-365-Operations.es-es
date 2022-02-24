---
title: Gestionar varias asignaciones derivadas para una única raíz de modelo
description: Este tema explica cómo administrar varias asignaciones derivadas que se configuraron para una única raíz de modelo.
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3116fe98f499637b3bc7f243ed1b5094853caa7e
ms.sourcegitcommit: 7cfe8931dd454e811a691f5118a4ecae7ba4b478
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2021
ms.locfileid: "4826118"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Gestionar varias asignaciones derivadas para una única raíz de modelo

[!include [banner](../includes/banner.md)]

Un componente de [Informes electrónicos (ER)](general-electronic-reporting.md) de [modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) de datos se utiliza en cada componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) ER configurado como fuente de datos para generar documentos salientes. Para describir un único dominio empresarial, configure un componente de modelo de datos que tenga muchas definiciones de raíz. 

Cada definición de raíz le permite representar los datos de ese dominio de la forma que mejor se adapte a los propósitos de informes específicos. Para cada definición de raíz, puede configurar un componente de [asignación de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) de ER como Microsoft Dynamics 365 Finance – implementación específica de su modelo de datos. De esta manera, describe cómo se completará su modelo de datos en tiempo de ejecución.

Los componentes de asignación del modelo ER pueden residir en las configuraciones de asignación del modelo ER y de las [configuraciones](general-electronic-reporting.md#Configuration) del modelo de datos de ER. Una única configuración de ER puede contener muchos componentes de asignación, cada uno de los cuales está configurado para una única definición de raíz. En alternativa, una única configuración de ER puede contener solo un componente de asignación que esté configurado para una única definición de raíz.

Muchos proveedores de configuración pueden ofrecer configuraciones de asignación de modelos de ER para el mismo modelo de datos de ER. Esas configuraciones de asignación de modelos pueden contener componentes de asignación para diferentes definiciones de raíz. Puede utilizar una asignación de modelo para una definición de raíz ofrecida por un [proveedor](general-electronic-reporting.md#Provider) y utilizar asignación de modelo para otra definición de raíz ofrecida por otro proveedor.

Los procedimientos de este tema explican cómo administrar múltiples configuraciones de asignación de modelos de ER de un modelo de datos de ER cuando contienen diferentes componentes de asignación de modelos configurados para la misma definición de raíz. 

Para completar los procedimientos en este tema, usted debe estar asignado al rol de Administrador del sistema o al de Desarrollador de informes electrónicos.

Todos los siguientes procedimientos se pueden hacer en el USMF de la empresa. No se requiere codificación.

## <a name="configure-the-er-framework"></a>Configurar el marco ER

Como usuario en el rol de Desarrollador de informes electrónicos, debe [configurar el conjunto mínimo](er-quick-start2-customize-report.md#ConfigureFramework) de parámetros de ER antes de comenzar a usar el marco de ER para generar documentos empresariales.

## <a name="import-the-standard-er-format-configurations"></a>Importar configuraciones del formato estándar de ER

Para agregar las configuraciones estándar de ER a su instancia actual de Finance, debe importarlas desde el repositorio de ER que se configuró para esa instancia. Siga los pasos en [Descargar las configuraciones de ER del repositorio global del servicio de configuración](er-download-configurations-global-repo.md) para importar las siguientes configuraciones de formato ER:

- **Factura de servicios (Excel)**, versión 220.106
- **Factura de proyecto (Excel)**, versión 226.27

## <a name="review-the-imported-er-configurations"></a>Revisar las configuraciones importadas de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura**.

    ![Revisión de las configuraciones importadas en la página Configuraciones](./media/er-multiple-model-mappings-image1.png)

4. Revise el formato **Factura de servicios (Excel)**:

    1. En el árbol de configuración del panel izquierdo, seleccione **Factura de servicios (Excel)**.
    2. En el panel de acciones, haga clic en **Diseñador**.
    3. En la página **Diseñador de formato**, en la pestaña **Asignación**, en la lista de origen de datos seleccione **Modelo**.
    4. Seleccione **Ver**.
    
       El formato ER actual está configurado para usar la definición de raíz **InvoiceCustomer** del **Modelo de factura**. Cuando se ejecuta este formato y se llama el origen de datos **Modelo**, la asignación del modelo que está configurado para la definición de raíz **InvoiceCustomer** se utiliza para acceder a los datos de la aplicación y completar el modelo de datos.

        ![Revisar el origen de datos del modelo en la página del diseñador de formato](./media/er-multiple-model-mappings-image2.png)

    6. Cierre la página **Diseñador de formato**.

5. Revise el contenido de la configuración de la **Asignación del modelo de factura**:

    1. En el árbol de configuración del panel izquierdo, seleccione **Asignación de modelo de factura**.
    2. En el panel de acciones, haga clic en **Diseñador**.
    3. En la página **Asignación de modelo a origen de datos**, observe que la configuración actual de la asignación del modelo de ER contiene varios componentes de la asignación del modelo:

        + La asignación del modelo **Factura del cliente** está configurada para la definición de raíz de **InvoiceCustomer** del **Modelo de factura**. Por lo tanto, cuando el formato de ER **Factura de servicios (Excel)** se ejecuta, la asignación de modelo de **Factura del cliente** de esta configuración de ER se puede elegir para acceder a los datos de la aplicación y completar el modelo de datos.
        + La asignación del modelo **Factura del proyecto** está configurada para la definición de raíz de **InvoiceProject** del **Modelo de factura**. Por lo tanto, cuando el formato de ER **Factura de proyecto (Excel)** se ejecuta, la asignación de modelo de **Factura del proyecto** de esta configuración de ER se puede elegir para acceder a los datos de la aplicación y completar el modelo de datos.

        ![Asignación del modelo de factura en la página de asignación de modelo a origen de datos](./media/er-multiple-model-mappings-image3.png)

    4. Cierre la página **Asignación de modelo a origen de datos**.
    5. En la ficha desplegable **Versiones**, seleccione **Eliminar** para eliminar todas las versiones de esta configuración de ER que sean posteriores a la versión 240.175.

6. Revise el contenido de la configuración de la **Asignación del modelo de factura de proyecto (RDP)**:

    1. En el árbol de configuración del panel izquierdo, seleccione **Asignación de modelo de factura de proyecto (RDP)**.
    2. En el panel de acciones, haga clic en **Diseñador**.
    3. En la página **Asignación de modelo a origen de datos**, observe que la configuración de asignación del modelo ER actual contiene la asignación del modelo **InvoiceProject** y que esta asignación de modelo está configurada para la definición de raíz **InvoiceProject** del **Modelo de factura**. Cuando el formato de ER **Factura de proyecto (Excel)** se ejecuta, seleccione la asignación de modelo **InvoiceProject** de esta configuración de ER para acceder a los datos de la aplicación y completar el modelo de datos.

        ![Asignación del modelo de factura de proyecto en la página de asignación de modelo a origen de datos](./media/er-multiple-model-mappings-image4.png)

    4. Cierre la página **Asignación de modelo a origen de datos**.
    5. En la ficha desplegable **Versiones**, seleccione **Eliminar** para eliminar todas las versiones de esta configuración de ER que sean posteriores a la versión 226.35.

## <a name="customize-the-imported-er-configurations"></a>Personalizar las configuraciones importadas de ER

Esta sección explica cómo [personalizar](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) las asignaciones de modelos que proporciona Microsoft. Por ejemplo, es posible que se requiera personalización para implementar su lógica personalizada o agregar enlaces faltantes.

### <a name="customize-the-invoice-model-mapping-configuration"></a>Personalizar la configuración de la asignación de modelo de factura

1. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Asignación de modelo de factura**.
2. En el panel de acciones, seleccione **Crear configuración**.
3. En el cuadro de diálogo desplegable **Crear configuración**, en el campo **Nuevo**, seleccione **Derivar del nombre: Asignación de modelo de factura, Microsoft**.
4. En el campo **Nombre**, escriba **Asignación de modelo de factura Litware**.
5. Seleccionar **Crear configuración**.
6. [Marque](er-quick-start2-customize-report.md#MarkFormatRunnable) la versión [borrador](general-electronic-reporting.md#component-versioning) de la asignación derivada como disponible para su uso en runtime:

    1. En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros avanzados**, seleccione **Parámetros del usuario**.
    2. En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.
    3. Seleccione **Editar** para hacer que la página sea editable, según sea necesario.
    4. Para la configuración de la **asignación del modelo de factura Litware** que está actualmente seleccionada en el árbol de configuración, establezca la opción **Ejecutar borrador** en **Sí**.

7. En el panel de acciones, seleccione **Diseñador** para revisar las asignaciones de modelos de esta configuración.

    ![Revisión de las asignaciones del modelo de factura en la página de asignación de modelo a origen de datos](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > Ahora puede abrir cualquiera de los componentes de asignación del modelo de ER de esta configuración ER en el diseñador para configurar su lógica personalizada. Para más información, consulte [Personalizar la configuración de la asignación del modelo](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Cierre la página **Asignación de modelo a origen de datos**.

Ahora dispone de las configuraciones **Asignación del modelo de factura** y **Asignación del modelo de factura Litware**, cada una de las cuales tiene una asignación de modelo que está configurada para la definición de raíz **InvoiceCustomer**. Asigne explícitamente una de las asignaciones de modelo como la asignación de modelo predeterminada que se utiliza en cualquiera de los formatos de ER, como el formato **Factura de servicios (Excel)**, que contiene una fuente de datos de modelo que tiene la definición de raíz **InvoiceCustomer**. De lo contrario, cuando ejecuta, edita o valida uno de los formatos de ER, se lanza la siguiente excepción para notificarle que no se ha asignado explícitamente ninguna asignación de modelo predeterminada:
 
> Existe más de una asignación de modelo para el modelo de datos '\<model name\> (\<root descriptor\>)' en las configuraciones \<configuration names separated by commas\>. Establezca una de las configuraciones como predeterminada.

![Abrir el formato para editar en la página Configuraciones](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>Personalizar la configuración de la asignación de modelo de factura de proyecto (RDP)

1. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Asignación de modelo de factura de proyecto (RDP)**.
2. En el panel de acciones, seleccione **Crear configuración**.
3. En el cuadro de diálogo **Crear configuración**, en el campo **Nuevo**, seleccione **Derivar del nombre: Asignación de modelo de factura de proyecto (RDP), Microsoft**.
4. En el campo **Nombre**, escriba **Asignación de modelo de factura de proyecto Litware**.
5. Seleccionar **Crear configuración**.
6. Para la configuración de la **Asignación del modelo de factura de proyecto Litware** que está actualmente seleccionada en el árbol de configuración, establezca la opción **Ejecutar borrador** en **Sí**.
7. En el panel de acciones, seleccione **Diseñador** para revisar las asignaciones de modelos de esta configuración.

    ![Revisión de las asignaciones del modelo de factura de proyecto personalizado en la página de asignación de modelo a origen de datos](./media/er-multiple-model-mappings-image7.png)

8. Cierre la página **Asignación de modelo a origen de datos**.

Ahora dispone de las configuraciones **Asignación de modelo de factura**, **Asignación de modelo de factura de proyecto (RDP)** y **Asignación de modelo de factura de proyecto Litware**. Cada una de estas configuraciones tiene una asignación de modelo configurada para la definición de raíz **InvoiceProject**. Asigne explícitamente una de las asignaciones de modelo como la asignación de modelo predeterminada que utiliza cualquiera de los formatos de ER. Por ejemplo, use el formato **Factura de proyecto (Excel)** que contiene un origen de datos modelo que tiene la definición de raíz **InvoiceProject**. De lo contrario, cuando ejecuta o edita uno de los formatos de ER, se lanza una excepción para notificarle que no se ha asignado explícitamente ninguna asignación de modelo predeterminada.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Seleccione la configuración de asignación de modelo de factura Litware derivada como la configuración que contiene asignaciones de modelo predeterminadas

1. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Asignación de modelo de factura Litware**.
2. Establezca la opción **Predeterminado para la asignación de modelo** a **Sí**.

    ![Establecer la asignación del modelo como asignación de modelo predeterminada en la página Configuraciones](./media/er-multiple-model-mappings-image8.png)

    Debido a esta configuración, la asignación de modelo **Copia de la factura del cliente** se usa cuando ejecuta, valida o edita la **Factura de servicios (Excel)**. La asignación de modelo **Factura de cliente** de la configuración **Asignación de modelo de factura** se ignora.

    Ahora puede abrir el formato **Factura de servicios (Excel)** para su revisión en el diseñador de formatos.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Seleccione la configuración de asignación de modelo de factura de proyecto Litware derivada como la configuración que contiene asignaciones de modelo predeterminadas

1. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Asignación de modelo de factura de proyecto Litware**.
2. Establezca la opción **Predeterminado para la asignación de modelo** a **Sí**.

    En este caso, a diferencia del caso que se describe para la configuración **Asignación del modelo de factura Litware** en la sección anterior, no puede empezar a utilizar la asignación de modelo **Copia de InvoiceProject** de la configuración de la **Asignación del modelo de factura del proyecto Litware**. Dos configuraciones que contienen una asignación de modelo para la definición de raíz **InvoiceProject** están actualmente marcadas como la configuración predeterminada. Por lo tanto, tienen la misma prioridad de uso. Para resolver este problema, complete los pasos restantes de este procedimiento.

3. En el árbol de configuración del panel izquierdo, seleccione **Asignación de modelo de factura Litware**.
4. En el panel de acciones, haga clic en **Diseñador**.
5. En la página **Asignación de modelo a origen de datos**, seleccione **Editar** para que la página sea editable, según sea necesario.
6. Seleccione la asignación de modelo **Copia de factura de proyecto** y luego seleccione la casilla de verificación **Eliminado** para ello.

    ![Establecer la asignación del modelo como eliminada virtualmente en la página Asignación de modelo a origen de datos](./media/er-multiple-model-mappings-image9.png)

    Debido a esta configuración, la configuración de **asignación del modelo de factura Litware** se trata como si no tuviera una asignación de modelo para la definición de raíz **InvoiceProject**. La asignación de modelo **Copia de InvoiceProject** se emite por defecto. La configuración, **asignación de modelo de factura de proyecto Litware**, que contiene la asignación de modelo, se marca como la configuración predeterminada. Debido a que está marcada como predeterminada, tiene una prioridad más alta que la asignación de modelo **InvoiceProject** de la configuración **Asignación del modelo de factura de proyecto (RDP)**.

## <a name="other-considerations"></a>Otras consideraciones

La asignación de modelo **Copia de InvoiceProject** de la configuración **Asignación del modelo de factura del proyecto Litware** está diseñada para utilizar el origen de datos **ReportDataProvider**. La fuente de datos es parte del tipo de *Objeto* que se refiere a la clase de aplicación **PsaProjInvoiceDP**. Esta clase se implementa como proveedor de datos para el informe de factura SQL Server Reporting Services (SSRS) del marco de gestión de impresión. Seleccione esta fuente de datos como el [punto de integración](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents) de ER. La implementación actual de ER para los informes de gestión de impresión tiene en cuenta esta configuración. Para obtener más detalles, revise el código fuente de la clase de aplicación **ERPrintMgmtDataProviderReport**. Durante el tiempo de ejecución, la asignación del origen de datos **ReportDataProvider** como punto de integración de la asignación del modelo obliga a Finance a tratar este componente de asignación con una prioridad más alta que el componente de asignación **InvoiceProject** de la configuración **Asignación del modelo de factura del proyecto (RDP)**.

## <a name="see-also"></a>Consulte también

- [Gestionar la asignación de modelos de informes electrónicos en distintas configuraciones de informes electrónicos](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Configurar asignaciones de modelo de informes electrónicos dependientes del contexto del país](er-country-dependent-model-mapping.md)
- [Cambios en la API de marco de informes electrónicos](er-apis-app10-0-11.md)
