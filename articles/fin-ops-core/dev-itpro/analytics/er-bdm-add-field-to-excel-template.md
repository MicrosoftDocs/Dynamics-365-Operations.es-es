---
title: Agregar nuevos campos a una plantilla de documento empresarial en Microsoft Excel
description: En este artículo se proporciona información acerca de cómo agregar nuevos campos a una plantilla de documento empresarial en Microsoft Excel mediante la característica de gestión de documentos empresariales.
author: kfend
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.custom: ''
ms.assetid: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
ms.openlocfilehash: c2d76997b2bb3f53c8341e4b747ba37631b3857d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285557"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Agregar nuevos campos a una plantilla de documento empresarial en Microsoft Excel

[!include[banner](../includes/banner.md)]

Puede agregar nuevos campos a una plantilla que se usa para generar documentos empresariales en formato Microsoft Excel. Estos campos se pueden agregar como marcadores de posición que se utilizan para rellenar documentos generados con la información necesaria de la aplicación. Para cada campo que agregue, también puede especificar un enlace a los orígenes de datos, a fin de especificar qué datos de la aplicación se introducirán en el campo cuando la plantilla se use para generar documentos empresariales.

Para obtener más información acerca de esta característica, complete el ejemplo de este artículo. Este ejemplo muestra cómo actualizar una plantilla para rellenar los campos en formularios de facturas de servicios que se generan.

## <a name="configure-business-document-management-to-edit-templates"></a>Configurar la gestión de documentos empresariales para editar plantillas

Puesto que la gestión de documentos empresariales (BDM) se basa en el marco [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md), debe configurar los parámetros necesarios de ER y BDM antes de poder empezar a trabajar con BDM.

1.  Inicie sesión en la instancia de Microsoft Dynamics 365 Finance como administrador del sistema.
2.  Complete los siguientes pasos del ejemplo en el artículo [Visión general de la gestión de documentos empresariales](er-business-document-management.md):

    1.  Configure los parámetros de ER.
    2.  Active BDM.

Ahora puede empezar a usar BDM para editar plantillas de documentos empresariales.

## <a name="import-er-solutions-that-contain-a-template"></a>Importar soluciones de ER que contienen una plantilla

El ejemplo de este procedimiento emplea la solución de ER publicada oficialmente. Debe importar las configuraciones de ER de esta solución en su instancia actual de Finance.

La configuración del formato de ER **Factura de servicios (Excel)** de esta solución contiene la plantilla de documento empresarial en formato Excel que se puede editar mediante BDM. Importe la última versión de esta configuración del formato de ER desde Microsoft Dynamics Lifecycle Service (LCS). El modelo de datos de ER correspondiente y las configuraciones de asignación de modelo de ER se importarán automáticamente.

Para obtener más información acerca de cómo importar configuraciones de ER, consulte [Gestionar el ciclo de vida de la configuración de ER](general-electronic-reporting-manage-configuration-lifecycle.md).

![Página Biblioteca de activos compartidos de LCS.](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Editar la plantilla de la solución de ER

1.  Inicie sesión como usuario que tiene acceso al espacio de trabajo de la **gestión de documentos empresariales**.
2.  Abra el espacio de trabajo de la **gestión de documentos empresariales**.

    ![Espacio de trabajo de la gestión de documentos empresariales.](./media/BDM-AddFldExcel-Workspace.png)

3.  En la cuadrícula, seleccione la plantilla **Factura de servicios (Excel)**.
4.  En el panel derecho, seleccione **Nueva plantilla** para crear una nueva plantilla basada en la plantilla seleccionada.
5.  En el campo **Título**, introduzca **Factura de servicios (Excel) Contoso** como título de la nueva plantilla.
6.  Seleccione **Aceptar** para confirmar el inicio del proceso de edición.

Aparece la página del editor de plantillas de BDM. Puede usar Microsoft 365 para editar en línea la plantilla seleccionada en el control incrustado.

![Página del editor de plantillas de BDM.](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Agregar la etiqueta para un nuevo campo a la plantilla

1.  En la página del editor de plantillas de BDM, en la cinta de opciones de Excel, en la pestaña **Ver**, seleccione las casillas **Encabezados y líneas de cuadrícula** para la plantilla de Excel editable.

    ![Casillas de encabezados y líneas de cuadrícula seleccionadas.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Seleccione las celdas **E8:F8**.
3.  En la cinta de opciones de Excel, en la pestaña **Inicio**, seleccione **Combinar y centrar** para combinar las celdas seleccionadas en una nueva celda **E8:F8** combinada.
4.  En la celda combinada **E8:F8**, introduzca la **URL**.
5.  Seleccione la celda combinada **E7:F7**, seleccione **Copiar formato** y luego seleccione la celda combinada **E8:F8** para aplicarle formato de la misma manera que la celda combinada **E7:F7**.

    ![Nuevo etiqueta de campo agregada a la plantilla.](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>Aplicar formato a la plantilla para reservar espacio para un nuevo campo

1.  En la página del editor de plantillas de BDM, seleccione la celda combinada **G8:H8**.
2.  En la cinta de opciones de Excel, en la pestaña **Inicio**, seleccione **Combinar y centrar** para combinar las celdas seleccionadas en una nueva celda **G8:H8** combinada.
3.  Seleccione la celda combinada **G7:H7**, seleccione **Copiar formato** y luego seleccione la celda combinada **G8:H8** para aplicarle formato de la misma manera que la celda combinada **G7:H7**.

    ![Espacio reservado para el nuevo campo.](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  En el campo **Nombre**, seleccione **CompanyInfo**.

    El intervalo **CompanyInfo** de la plantilla de Excel actual contiene todos los campos que se utilizan para rellenar el encabezado de un informe generado con los detalles de la empresa actual como parte vendedora.

    ![Intervalo CompanyInfo seleccionado.](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Agregar un nuevo campo a la plantilla

1.  En la página **Editor de plantilla de BDM**, en el panel de acciones, seleccione **Mostrar formato**.
2.  En el panel **Estructura de la plantilla**, seleccione **Agregar**.

    > [!NOTE]
    > Debe ajustar la sección de la plantilla que desea utilizar como un nuevo campo. Ya hizo este ajuste al aplicar formato a la celda combinada **G8:H8**.

    ![Agregando un nuevo campo a la plantilla.](./media/BDM-AddFldExcel-AddCell.png)

3.  Seleccione **Excel\Celda** para agregar un nuevo campo como celda en la plantilla.

    Puede seleccionar **Excel\Intervalo** si desea agregar un nuevo intervalo a la plantilla. El intervalo que se introduce puede contener múltiples celdas. Puede agregar estas celdas más adelante.
    
    Tenga en cuenta que el componente de la plantilla **CompanyInfo** se selecciona automáticamente en el panel **Estructura de la plantilla**, ya que es el componente principal más adecuado de la estructura de la plantilla actual para el campo que desea agregar.
    
4.  En el campo **Intervalo de Excel**, introduzca **CompanyURL_Value**.
5.  Seleccione **Aceptar**.

    ![Campo CompanyURL_Value agregado a la estructura de la plantilla.](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  En el panel **Estructura de la plantilla**, seleccione los puntos suspensivos (...) y, a continuación, seleccione **Mostrar enlaces**.

    ![Mostrar enlaces seleccionados.](./media/BDM-AddFldExcel-ShowBindings.png)

    El panel **Estructura de la plantilla** ahora muestra los orígenes de datos disponibles en el formato de ER subyacente.

7.  Seleccione **CompanyInfo_Value** como el campo que tiene previsto enlazar a un origen de datos del formato de ER subyacente.
8.  En la sección **Orígenes de datos** del panel **Estructura de la plantilla**, expanda **Modelo \> InvoiceBase \> CompanyInfo**.
9.  En **CompanyInfo**, seleccione el elemento **WebsiteURI**.

    ![Elemento WebsiteURI seleccionado.](./media/BDM-AddFldExcel-BindURL.png)

10. Seleccione **Enlazar**.
11. En el panel **Estructura de la plantilla**, seleccione **Guardar** y luego cierre la página del editor de la plantilla de BDM.

En el espacio de trabajo **Gestión de documentos empresariales**, la pestaña **Plantilla** en el panel derecho muestra la plantilla actualizada. En la cuadrícula, tenga en cuenta que el campo **Estado** para la plantilla editada se ha cambiado a **Borrador** y el campo **Revisión** dejará de estar en blanco. Estos cambios indican que se ha iniciado el proceso de edición de esta plantilla.

![Plantilla editada en el espacio de trabajo de Gestión de documentos empresariales.](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Revisar configuración de empresa

1.  Vaya a **Administración de la organización \> Organizaciones \> Entidades jurídicas**.
2.  En la ficha desplegable **Información de contacto**, compruebe que está introducida la dirección URL de la empresa.

![Dirección URL de la empresa introducida en la página de Entidades jurídicas.](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Generar documentos empresariales para probar la plantilla actualizada

1.  En la aplicación, cambie la empresa a **USMF** y vaya a **Clientes \> Facturas \> Todas las facturas de servicios**.
2.  Seleccione la factura **FTI-00000002** y, a continuación, seleccione **Gestión de impresión**.
3.  En el panel izquierdo, expanda **Módulo - Clientes \> Documentos \> Factura de servicios**.
4.  En **Factura de servicios**, seleccione el nivel **Documento original** para especificar el ámbito de las facturas para procesar.
5.  En el panel derecho, en el campo **Formato del informe**, seleccione la plantilla **Factura de servicios (Excel) Contoso** para el nivel del documento especificado.

    ![Plantilla Factura de servicio (Excel) Contoso seleccionada.](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Presione **Esc** para cerrar la página actual.
7.  Seleccionar **Impresión \> Seleccionada**.
8.  Descargue el documento generado y ábralo en Excel.

    ![Factura de servicios en Excel.](./media/BDM-AddFldExcel-PreviewReport.png)

La plantilla modificada se usa para generar el informe de facturas de servicios para el artículo seleccionado. Para analizar cómo este informe se ve afectado por los cambios que hace en la plantilla, ejecute el informe en una sesión de la aplicación inmediatamente después de cambiar la plantilla en otra sesión de la aplicación.

## <a name="related-links"></a>Vínculos relacionados

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Visión general de la gestión de documentos empresariales](er-business-document-management.md)

[Diseñar una configuración para generar informes en formato OPENXML](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
