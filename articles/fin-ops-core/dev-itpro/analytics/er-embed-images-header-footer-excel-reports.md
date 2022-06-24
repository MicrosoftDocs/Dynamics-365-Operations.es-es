---
title: Diseñe un formato ER para generar un informe en formato Excel con imágenes incrustadas en encabezados o pies de página
description: En este artículo se explica cómo utilizar informes electrónicos (ER) para generar documentos empresariales que tienen imágenes y formas incrustadas en los encabezados o pies de página.
author: NickSelin
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1cfde60459e440c851edb97276321216b1654e40
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854854"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>Diseñe un formato ER para generar un informe en formato Excel con imágenes incrustadas en encabezados o pies de página

[!include[banner](../includes/banner.md)]

Este artículo explica cómo un usuario con el rol de administrador del sistema o consultor funcional de informes electrónicos puede realizar estas tareas:

- Configurar los parámetros para el marco de [informes electrónicos (ER)](general-electronic-reporting.md).
- Importe [configuraciones](general-electronic-reporting.md#Configuration) de ER [proporcionadas](general-electronic-reporting.md#Provider) por Microsoft y se utilizan para generar [facturas de servicios](../../../finance/accounts-receivable/create-free-text-invoice-new.md), basadas en [plantilla](er-fillable-excel.md#excel-file-component) en formato de Microsoft Excel.
- Cree una versión [personalizada (derivada)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) de una configuración de formato ER estándar proporcionada por Microsoft.
- Modifique la configuración del formato ER personalizado para que genere un informe de factura de texto libre que tenga una imagen del logotipo de la empresa en el pie de página.

Los procedimientos de este artículo se pueden completar en la empresa **USMF**. No se requiere codificación. Antes de comenzar, debe descargar y guardar el archivo siguiente.

| Descripción        | Nombre de archivo |
|--------------------|-----------|
| Imagen del logotipo de la empresa | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Contenido

- [Configurar la entidad jurídica](#ConfigureLegalEntity)
- [Configurar el marco ER](#ConfigureFramework)

    - [Configurar los parámetros de ER](#ConfigureParameters)
    - [Activar un proveedor de configuración de ER](#ActivateProvider)

        - [Revise la lista de proveedores de configuración de ER](#ReviewProvidersList)
        - [Añada una nueva configuración para el proveedor de ER](#AddProvider)
        - [Activar el nuevo proveedor de configuración de ER](#ActivateAddedProvider)

- [Importar configuraciones del formato estándar de ER](#ImportERSolution1)

    - [Importar configuraciones estándar de ER](#ImportERFormat)
    - [Revisar las configuraciones importadas de ER](#ReviewImportedERSolution)

- [Imprimir una factura de servicios mediante el formato estándar de ER](#PrintInvoice1)

    - [Configurar la gestión de impresión](#ConfigurePrintManagement1)
    - [Imprimir una factura de servicios](#ProcessInvoice1)

- [Personalizar el formato ER estándar](#CustomizeProvidedFormat)

    - [Crear un formato personalizado](#DeriveProvidedFormat)
    - [Editar el formato personalizado](#ConfigureDerivedFormat)
    - [Marcar el formato personalizado como ejecutable](#MarkFormatRunnable)

- [Imprimir una factura de servicios mediante el formato personalizado de ER](#PrintInvoice2)

    - [Configurar la gestión de impresión](#ConfigurePrintManagement2)
    - [Imprimir una factura de servicios](#ProcessInvoice2)

- [Recursos adicionales](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>Configurar la entidad jurídica

1. Vaya a **Administración de la organización** \> **Organizaciones** \> **Entidades jurídicas**.
2. En la página **Entidades legales**, en la ficha desplegable **Informar la imagen del logotipo de la empresa**, seleccione **Cambiar**.
3. En el cuadro de diálogo **Seleccione el archivo de imagen para cargar**, seleccione **Navegar** y seleccione el archivo **Company logo.png** que descargó anteriormente.
4. Seleccione **Guardar** y, a continuación, cierre la página **Entidades jurídicas**.

![Imagen del logotipo de la empresa seleccionada en la página de entidades legales.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurar el marco ER

Como usuario en el rol de Consultor Funcional de Informes Electrónicos, debe configurar el conjunto mínimo de parámetros de ER antes de comenzar a usar el marco de ER para diseñar una versión personalizada de un formato de ER estándar.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurar los parámetros de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.
3. En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.
4. En la pestaña **Adjuntos**, establezca los parámetros siguientes:

    - En el campo **Configuraciones**, seleccione el tipo **Archivo** para el **USMF** de la empresa.
    - En los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros**, seleccione el tipo **Archivo**.

Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Activar un proveedor de configuración de ER

Cada configuración de ER que se agrega está marcada como propiedad de un proveedor de configuración de ER. El proveedor de configuración de ER que se activa en el espacio de trabajo **Informes electrónicos** se utiliza para este propósito. Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.

> [!NOTE]
> Solo el propietario de la configuración puede editar una configuración de ER. Antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Revise la lista de proveedores de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Tabla de proveedor de configuración**, cada registro de proveedor tiene un nombre y URL únicos. Revise el contenido de esta página. Si un registro para **Litware, Inc.** (`https://www.litware.com`) ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Añada una nueva configuración para el proveedor de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Proveedores de configuración**, seleccione **Nuevo**.
4. En el campo **Nombre**, introduzca **Litware, Inc.**
5. En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.
6. Seleccione **Guardar**.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Activar el nuevo proveedor de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Litware, Inc.** y luego seleccione **Establecer activo**.

Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importar configuraciones del formato estándar de ER

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>Importar configuraciones estándar de ER

Para agregar las configuraciones ER estándar a su instancia actual de Dynamics 365 Finance, debe importarlos desde el [repositorio](general-electronic-reporting.md#Repository) de ER que se configuró para esa instancia.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de **Microsoft**.
3. En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**. Si se le solicita autorización para conectarse al [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md), siga las instrucciones de autorización.
4. En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **Factura de servicios (Excel)**.
5. En la ficha desplegable **Versiones**, seleccione la última versión (por ejemplo, **240.112**) de la configuración de ER seleccionada.
6. Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a la instancia actual de Finance.

![Importación de las configuraciones de ER estándar en la página Repositorio de configuración.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> Si tiene problemas para acceder al [Repositorio global](er-download-configurations-global-repo.md), puede [descargar configuraciones](download-electronic-reporting-configuration-lcs.md) de Microsoft Dynamics Lifecycle Services (LCS) en su lugar.

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Revisar las configuraciones importadas de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura**.
4. Además del formato de ER **Factura de servicios (Excel)** seleccionado, se importaron otras configuraciones de ER necesarias. Asegúrese de que las siguientes configuraciones de ER estén disponibles en el árbol de configuración:

    - **Modelo de factura** - Esta configuración contiene el modelo de datos del componente ER que representa la estructura de datos del dominio comercial de factura.
    - **Asignación del modelo de factura** - Esta configuración contiene el asignado de modelos del componente ER que describe cómo se completa el modelo de datos con los datos de la aplicación en tiempo de ejecución.
    - **Factura de servicios (Excel)** - Esta configuración contiene el formato y componentes de ER de mapeo de formato. El componente de formato especifica el diseño del informe, basado en una plantilla en formato Excel. El componente de asignación de formato contiene el origen de datos del modelo y especifica cómo se usa este origen de datos para rellenar el diseño del informe en tiempo de ejecución.

![Configuraciones de ER importadas en la página Configuraciones.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Imprimir una factura de servicios mediante el formato estándar de ER

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Configure la gestión de impresión

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, seleccione la factura **FTI-00000002** y luego en el Panel de acciones, en la pestaña **Factura**, en el grupo **Gestión de impresión**, seleccione **Gestión de impresión**.
3. En la página **Configuración de gestión de impresión**, en el árbol de la izquierda, expanda **Módulo - cuentas por cobrar \> Documentos \> Factura de servicios** y luego seleccione el elemento **Original \<Default\>**.
4. En el campo **Formato de informe**, seleccione **Factura de servicios (Excel)**.
5. Seleccione la tecla **Esc** para dejar la página **Configuración de gestión de impresión** y volver a la página **Factura de servicios**.

![Configuración de administración de impresión para una factura de servicios en el formato estándar ER en la página de configuración de administración de impresión.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Imprimir una factura de servicios

1. En la página **Factura de servicios**, asegúrese de que se selecciona la factura **FTI-00000002** y luego en el Panel de acciones, en la pestaña **Factura**, en el grupo **Documento**, seleccione **Imprimir** \> **Seleccionado**.
2. Descargue la factura generada en formato Excel y ábrala para obtener una vista previa.
3. Observe que, de acuerdo con la estructura de la plantilla de Excel para el formato ER proporcionado, el pie de página de la factura generada contiene información sobre el número de página actual y el número total de páginas del informe.

![Factura de servicios generada.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personalizar el formato ER estándar

Para el ejemplo de esta sección, puede utilizar las configuraciones de ER que proporciona Microsoft para generar una factura de texto libre en formato Excel. Sin embargo, debe agregar una personalización para colocar una imagen del logotipo de la empresa en el pie de página de las facturas generadas.

En este caso, como representante de Litware, Inc., debe crear (derivar) una nueva configuración de formato basada en la configuración proporcionada por Microsoft **Factura de servicios (Excel)**.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Crear un formato personalizado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura** y luego seleccione **Factura de servicios (Excel)**. Litware, Inc. utilizará la versión importada (por ejemplo, **240.112**) de esta configuración de formato ER como base para la versión personalizada.
3. Seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable. Use este cuadro de diálogo para crear una nueva configuración para un formato de pago personalizado.
4. En el grupo de campos **Nuevo**, seleccione la opción **Derivar del nombre: Factura de servicios (Excel), Microsoft**.
5. En el campo **Nombre**, introduzca **Factura de servicios (Excel) personalizada**.
6. Seleccionar **Crear configuración**.

![Crear una configuración para un formato de pago personalizado en el cuadro de diálogo desplegable Crear configuración.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

Se crea la versión 240.112.1 de la configuración del formato ER de la **Factura de servicios (Excel) personalizada**. Esta versión tiene un [estado](general-electronic-reporting.md#component-versioning) de **Borrador** y puede editarse. El contenido actual de su formato ER personalizado coincide con el contenido del formato proporcionado por Microsoft.

![Nueva versión de la configuración de formato de ER creada en la página Configuraciones.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Editar el formato personalizado

Configure su formato personalizado para que la imagen del logotipo de la empresa se coloque en el pie de página de cada página del informe.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y luego seleccione **Factura de servicios (Excel) personalizada**.
3. En la ficha desplegable **Versiones**, seleccione la versión **240.112.1** de la configuración seleccionada.
4. Seleccione **Diseñador**.
5. En la página del **Diseñador de formato**, seleccione **Mostrar detalles** para ver más información sobre los elementos de formato.
6. Expanda y revise los siguientes elementos:

    - El elemento **Factura de servicios** del tipo **Excel**. Este elemento se utiliza para generar una factura en formato de libro de Excel.
    - El elemento **Factura de servicios \\ Factura** del tipo **Hoja**. Este elemento se utiliza para generar una hoja de trabajo del libro de Excel generado.
    - El elemento **Factura de servicios \\ Factura \\ Pie de página** del tipo **Pie de página**. Este elemento se utiliza para completar el pie de página de una factura.

7. Seleccione el elemento **Factura de servicios \\ Factura \\ Pie de página**.

    ![Elemento de pie de página en el diseñador de operaciones de ER.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > Cada pie de página de una factura generada contiene información sobre el número de página actual y el número total de páginas del informe. Como puede ver, el elemento **Factura de servicios \\ Factura \\ Pie de página** no contiene elementos secundarios. Por lo tanto, la plantilla de Excel que se está utilizando está configurada para mostrar detalles de paginación en el centro del pie de página de cada informe.

8. Seleccione **Agregar** y luego seleccione el tipo **Excel \\ Imagen** del elemento de formato que está agregando:

    1. En el campo **Alineación**, seleccione **Derecha**.
    2. En el campo **Escala la altura**, seleccione **Relativo**.
    3. En el campo **Escala en porcentaje**, introduzca **70**.
    4. Seleccione **Aceptar**.

        > [!NOTE]
        > El elemento **Excel \\ Imagen** se utiliza para agregar una imagen del logotipo de la empresa y alinearla en el lado derecho del pie de página.

    ![Propiedades del elemento Imagen en el cuadro de diálogo Propiedades del componente.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. En el árbol de estructura de formato de la izquierda, seleccione el elemento **Imagen** que acaba de agregar, y luego, en la pestaña **Cartografía**, expanda el origen de datos de **modelo**.
10. Expanda **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo** y luego seleccione el campo de fuente de datos **model.InvoiceBase.CompanyInfo.Logo**. El campo de fuente de datos del tipo [Contenedor](er-formula-supported-data-types-composite.md#container) expone la imagen del logotipo de la empresa como contenido multimedia.
11. Seleccione **Enlazar**. El elemento de formato **Imagen** ahora está vinculado con el campo **model.InvoiceBase.CompanyInfo.Logo** de fuente de datos. Por lo tanto, en tiempo de ejecución, se colocará una imagen del logotipo de la empresa en el pie de página de las facturas generadas.

    ![El elemento de formato Imagen está vinculado con el campo model.InvoiceBase.CompanyInfo.Logo enel diseñador de operaciones de ER.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Seleccione **Guardar** y después, cierre la página **Diseñador**.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Marcar el formato personalizado como ejecutable

Debido a que se ha creado la primera versión del formato personalizado y tiene un estado de **Borrador**, puede ejecutarlo con fines de prueba. Para ejecutar el informe, procese un pago de proveedor utilizando el método de pago que se refiere a su formato ER personalizado. De forma predeterminada, cuando llama a un formato de ER desde la aplicación, las únicas versiones que tienen un estado de **Completado** o **Compartido** son las que se [consideran](general-electronic-reporting.md#component-versioning). Este comportamiento ayuda a evitar el uso de formatos ER que tienen diseños inacabados. Sin embargo, para sus ejecuciones de prueba, puede obligar a la aplicación a usar la versión de su formato ER que tenga un estado de **Borrador**. De esta manera, puede ajustar la versión del formato actual si se requieren modificaciones. Para obtener más información, consulte [Aplicabilidad](electronic-reporting-destinations.md#applicability).

Para utilizar la versión borrador de un formato ER, debe marcar de forma explícita el formato ER.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.
4. Seleccione **Editar** para hacer que la página actual sea editable y luego, en el árbol de configuraciones del panel izquierdo, seleccione **Factura de servicios (Excel) personalizada**.
5. Establezca la opción **Ejecutar borrador** en **Sí**.

![Marcando el formato personalizado como ejecutable en la página Configuraciones.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Imprimir una factura de servicios mediante el formato personalizado de ER

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Configure la gestión de impresión

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, seleccione la factura **FTI-00000002** y luego en el Panel de acciones, en la pestaña **Factura**, en el grupo **Gestión de impresión**, seleccione **Gestión de impresión**.
3. En la página **Configuración de gestión de impresión**, en el árbol de la izquierda, expanda **Módulo - cuentas por cobrar** \> **Documentos** \> **Factura de servicios** y luego seleccione el elemento **Original** **\<Default\>**.
4. En el campo **Formato de informe**, seleccione **Factura de servicios (Excel) personalizada**.
5. Seleccione **Esc** para dejar la página **Configuración de gestión de impresión** y volver a la página **Factura de servicios**.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Imprimir una factura de servicios

1. En la página **Factura de servicios**, asegúrese de que se selecciona la factura **FTI-00000002** y luego en el Panel de acciones, en la pestaña **Factura**, en el grupo **Documento**, seleccione **Imprimir** \> **Seleccionado**.
2. Descargue la factura generada en formato Excel y ábrala para obtener una vista previa.
3. Tenga en cuenta que, de acuerdo con la estructura del formato ER personalizado, el pie de página de la factura generada contiene una imagen del logotipo de la empresa además de información sobre la paginación del informe.

![Factura de servicios generada con una imagen del logotipo de la empresa en el pie de página.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>Recursos adicionales

- [Diseñar una configuración para generar documentos en formato de Excel](er-fillable-excel.md)
- [Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md)
