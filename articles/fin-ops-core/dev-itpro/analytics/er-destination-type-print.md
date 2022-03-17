---
title: Tipo de destino de ER de impresora
description: Este tema explica cómo puede configurar un destino de impresora para cada componente FOLDER o FILE de un informe electrónico (ER).
author: NickSelin
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2513fc4f86519c71602089cd46e9757813b1a708
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388297"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destino de la impresora

[!include [banner](../includes/banner.md)]

Puede enviar un documento generado directamente a una impresora de red para su impresión directa.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, debe instalar y configurar el Agente de enrutamiento de documentos y luego registrar las impresoras de red. Para más información, consulte [Instalar el agente de ruta de documentos para habilitar la impresión de red](./install-document-routing-agent.md)

## <a name="make-the-printer-destination-available"></a>Hacer que el destino de impresora esté disponible

Para hacer que el destino de **impresora** esté disponible en la instancia actual de Microsoft Dynamics 365 Finance, vaya al espacio de trabajo **Administración de características** y active las siguientes características, en este orden:

1. Convertir documentos de salida de informes electrónicos desde formatos de Microsoft Office a PDF
2. Agente de ruta de documentos como destino de informes electrónicos para documentos de salida

[![Activar la característica de destino de impresora de ER en Administración de características.](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Aplicabilidad

#### <a name="pdf-printing"></a>Impresión PDF

En las versiones de Finance anteriores a la versión 10.0.18, el destino de **Impresora** solo se puede configurar para componentes de archivo que se utilizan para generar resultados en formato PDF imprimible (**elementos de formato de archivo PDF** o **fusión de PDF**) o de formato Microsoft Office Excel y Word (elemento de formato de **archivo Excel**). Cuando la salida se genera en formato PDF, se envía a una impresora. Cuando la salida se genera en formato de Office usando el elemento de formato **Archivo Excel**, se convierte automáticamente a formato PDF y luego se envía a una impresora.

Sin embargo, a partir de la versión 10.0.18, puede configurar el destino **Impresora** para el elemento de formato **Archivo común**. Este elemento de formato se usa principalmente para generar resultados en formato TXT o XML. Puede configurar un formato ER que contenga el elemento de formato **Archivo común** como el elemento de formato raíz y el elemento de formato **Contenidos binarios** como el único elemento anidado debajo de él. En este caso, el elemento de formato **Archivo común** producirá una salida en el formato especificado por el enlace que configure para el elemento de formato **Contenidos binarios**. Por ejemplo, puede configurar este enlace para [llenar](tasks/er-document-management-files-5.md#modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format) este elemento con el contenido de un adjunto de un [Gestor de documentos](../../fin-ops/organization-administration/configure-document-management.md) en formato PDF u Office (Excel o Word). Puede imprimir la salida usando el destino **Impresora** configurado. 

> [!NOTE]
> Cuando selecciona el elemento de formato **Common\\File** elemento de formato para configurar el destino **Impresora**, no hay forma de garantizar, en el momento del diseño, que el elemento seleccionado producirá una salida en formato PDF o una salida que se pueda convertir a formato PDF. Por lo tanto, recibe el siguiente mensaje de advertencia: "Por favor, asegúrese de que la salida generada por el componente de formato seleccionado se pueda convertir a PDF. De lo contrario, desmarque la opción 'Convertir a PDF'". Debe tomar medidas para ayudar a evitar problemas de tiempo de ejecución cuando se proporciona una salida que no es PDF o que no es PDF convertible para imprimir en tiempo de ejecución. Si espera recibir la salida en el formato de Office (Excel o Word), la opción **Convertir a PDF** debe seleccionarse.
>
> En la versión 10.0.26 y posteriores, para usar la opción **Convertir a PDF**, debe seleccionar **PDF** para el parámetro **Tipo de enrutamiento de documentos** del destino de **Impresora** configurado.

#### <a name="zpl-printing"></a>Impresión ZPL

En la versión 10.0.26 y posteriores, puede configurar el destino **Impresora** para el elemento de formato **Common\\File** seleccionando **ZPL** para el parámetro **Tipo de enrutamiento de documentos**. En este caso, la opción **Convertir a PDF** se ignora en tiempo de ejecución y la salida TXT o XML se envía directamente a una impresora seleccionada mediante el contrato del lenguaje de programación Zebra (ZPL) del [Agente de enrutamiento de documentos (DRA)](install-document-routing-agent.md). Utilice esta función para un formato ER que represente un diseño de etiqueta ZPL II para imprimir varias etiquetas.

[![Configuración del parámetro Tipo de enrutamiento de documentos en el cuadro de diálogo Configuración de destino.](./media/ER_Destinations-SetDocumentRoutingType.png)](./media/ER_Destinations-SetDocumentRoutingType.png)

Para obtener más información acerca de esta función, consulte [Diseñe una nueva solución ER para imprimir etiquetas ZPL](er-design-zpl-labels.md).

### <a name="limitations"></a>Limitaciones

El destino de **impresora** solo es compatible con implementaciones en la nube.

### <a name="use-the-printer-destination"></a>Usar destino de impresora

1. Establezca la opción **Habilitado** en **Sí** para enviar un documento generado a una impresora.
2. En el campo **Nombre de impresora**, seleccione la impresora de red requerida.
3. Establezca la opción **¿Guardar en archivo de impresión?** en **Sí** para almacenar la salida generada en el archivo de impresión, de modo que esté disponible para su posterior impresión. Para acceder a la salida archivada más tarde, vaya a **Administración de la organización** \> **Consultas e informes** \> **Archivo de informes**.

[![Uso del destino de impresora.](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> La opción **Convertir a PDF** no tiene que estar activada cuando se configura el destino de **impresora**. La conversión a PDF para fines de impresión ocurrirá incluso si la opción está desactivada.

Para usar una [orientación de la página](electronic-reporting-destinations.md#SelectPdfPageOrientation) específica cuando imprime un documento saliente en formato Excel, debe activar la opción **Convertir a PDF**. Cuando establece la opción **Convertir a PDF** a **Sí**, el campo **Orientación de la página** queda disponible. En el campo **Orientación de la página**, puede seleccionar una orientación de página.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
