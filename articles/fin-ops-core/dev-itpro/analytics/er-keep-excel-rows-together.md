---
title: Diseñe un formato ER para mantener las filas juntas en la misma página de Excel
description: Este artículo explica cómo diseñar un formato de informes electrónicos (ER) que mantiene las filas juntas en la misma página de Microsoft Excel.
author: kfend
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.custom: 220314
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 7ecc4358a0d4d9ae9e729393bd3ac4cefbf15ad2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287970"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>Diseñe un formato ER para mantener las filas juntas en la misma página de Excel

[!include [banner](../includes/banner.md)]


Este artículo explica cómo un usuario con el rol de administrador del sistema o Consultor funcional de Informes electrónicos puede configurar un [formato](er-overview-components.md#format-component) de [Informes electrónicos (ER)](general-electronic-reporting.md) para generar documentos salientes en Microsoft Excel y gestionar la paginación de documentos para que las filas que se creen se conserven en la misma página.

En este ejemplo, modificará el formato ER proporcionado por Microsoft que se utiliza para imprimir facturas de texto sin formato en Excel. Sus modificaciones le permitirán administrar la paginación de un informe de factura de texto libre generado para que todas las filas de una sola línea de factura se mantengan en la misma página cuando sea posible.

Los procedimientos de este artículo se pueden completar en la empresa **USMF**. No se requiere codificación.

En este ejemplo, creará las [configuraciones](general-electronic-reporting.md#Configuration) de ER necesarias para la empresa de ejemplo, **Litware, Inc**. Asegúrese de que está disponible el proveedor de la configuración para la empresa de ejemplo **Litware, Inc.** (`http://www.litware.com`) está en la lista del marco de ER y que está como **Activo**. Si este proveedor de configuración no aparece en la lista o si no está marcado como **Activo**, siga los pasos de [Crear un proveedor de configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Introducir una factura de servicios nueva

1. Siga los pasos en [Crear una factura de texto libre](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1) para agregar una factura de texto libre.

    1. Agregue una línea única a la factura.
    2. Agregue cinco notas para la línea de factura.

    ![Revisar las notas de la línea de factura en la página Adjuntos.](./media/er-keep-excel-rows-together-notes.png)

2. Siga los pasos en [Copiar líneas](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) para crear cinco líneas de factura adicionales que son copias de la línea de factura que agregó en el paso anterior.

    ![Revisar las líneas de factura de texto sin formato en la página Factura de texto sin formato.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>Configurar el marco ER

Siga los pasos de [Configurar el marco de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar el conjunto mínimo de parámetros de ER. Debe completar esta configuración antes de comenzar a utilizar el marco ER para diseñar una versión personalizada de un formato ER estándar.

## <a name="import-the-standard-er-format-configuration"></a>Importar configuraciones del formato estándar de ER

Siga los pasos de [Importar la configuración de formato estándar de ER](er-quick-start2-customize-report.md#ImportERSolution1) para agregar las configuraciones estńdar de ER a su instancia actual de Dynamics 365 Finance. Por ejemplo, importa la versión **252.116** de la configuración de la **Factura de servicios (Excel)**. Versión básica de la base **252** de la configuración del **Modelo de factura** que se importa automáticamente desde el repositorio junto con la configuración de la **Asignación del modelo de factura** necesaria.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>Configurar la gestión de impresión para usar el formato ER estándar

Siga los pasos en [Configurar la gestión de impresión](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1) para configurar la gestión de impresión para el módulo **Clientes** para que se utilice el formato ER estándar para imprimir facturas de texto libre.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>Configurar un destino de formato para el formato ER estándar

Siga los pasos en [Configurar un destino de formato para la vista previa en pantalla](er-quick-start1-new-solution.md#ConfigureDestination) para configurar el destino ER [Pantalla](er-destination-type-screen.md) del formato ER estándar para que los informes generados se conviertan a formato PDF y se previsualicen en una nueva pestaña del navegador.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Imprimir una factura de servicios mediante el formato estándar de ER

1. Siga los pasos en [Imprimir una factura de texto libre](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1) para utilizar el formato ER estándar para generar un informe de factura de texto libre en formato Excel para la factura añadida.
2. Descargue el libro de trabajo de Excel generado y revíselo en la aplicación de escritorio de Excel.

    Observe que la sexta línea de la factura comienza en la primera página del informe y continúa en la segunda página. La última nota aparece en la segunda página y no es obvio que pertenezca a la sexta línea de la factura. Por lo tanto, el salto de página en medio del contenido de la línea de factura hace que este documento sea más difícil de leer.

    ![Revisar la paginación de la factura de texto libre generada en la aplicación de escritorio de Excel.](./media/er-keep-excel-rows-together-invoice1.gif)

Los procedimientos restantes de este artículo muestran cómo puede ajustar el formato de ER estándar para mejorar el aspecto y la legibilidad del informe de factura manteniendo todo el contenido de una sola línea de factura en la misma página.

## <a name="create-a-custom-format"></a>Crear un formato personalizado

Siga los pasos en [Crear un formato personalizado](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat) para derivar un formato del formato ER importado y crear una configuración de ER **Factura de texto libre (Excel) personalizada** que está disponible para editar y modificar.

## <a name="edit-the-custom-format"></a>Editar el formato personalizado

1. Siga los pasos en [Crear un formato personalizado](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) para abrir el formato ER derivado para editarlo en el diseñador de formato ER.
2. En la página **Diseñador de formatos**, en el árbol de componente de formato, expanda **Factura de texto libre \> Hoja \> InvoiceLines** y seleccione el componente **InvoiceLines_Values**.
3. En la pestaña **Formato** , establezca la opción **Mantener las filas juntas** a **Sí**.

    ![Configuración de la opción Mantener filas juntas para el formato ER editable en la página del diseñador de formato.](./media/er-keep-excel-rows-together-format.png)

4. Seleccione **Guardar** y cierre la página.

## <a name="mark-the-custom-format-as-runnable"></a>Marcar el formato personalizado como ejecutable

Siga los pasos en [Marque el formato personalizado como ejecutable](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable) para hacer ejecutable la versión modificada del formato ER personalizado.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Configurar la gestión de impresión para usar el formato ER personalizado

Siga los pasos en [Configurar la gestión de impresión](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2) para configurar la gestión de impresión para el módulo **Clientes** para que se utilice el formato ER personalizado para imprimir facturas de texto libre.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Configurar un destino de formato para el formato ER personalizado

Siga los pasos en [Configurar un destino de formato para la vista previa en pantalla](er-quick-start1-new-solution.md#ConfigureDestination) para configurar el destino ER **Pantalla** del formato ER personalizado para que los informes generados se conviertan a formato PDF y se previsualicen en una nueva pestaña del navegador.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Imprimir una factura de servicios mediante el formato personalizado de ER

1. Siga los pasos en [Imprimir una factura de texto libre](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2) para utilizar el formato ER personalizado para generar un informe de factura de texto libre en formato Excel para la factura añadida.
2. Descargue el libro de trabajo de Excel generado y revíselo en la aplicación de escritorio de Excel.

    Observe que la sexta línea de la factura comienza en la segunda página y todas las filas de Excel que representan esta línea de la factura aparecen juntas en esa página.

    ![Revisar la paginación actualizada de la factura de texto libre generada en la aplicación de escritorio de Excel.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>Recursos adicionales

[Diseñar una configuración para generar documentos en formato de Excel](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
