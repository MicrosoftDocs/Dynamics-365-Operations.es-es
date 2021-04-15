---
title: Tipo de destino de ER de impresora
description: Este tema explica cómo puede configurar un destino de impresora para cada componente FOLDER o FILE de un informe electrónico (ER).
author: NickSelin
ms.date: 02/24/2021
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
ms.openlocfilehash: 83081f8c17a903cd447a34596df2e61ebda0cafc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753441"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a>Destino de la impresora

[!include [banner](../includes/banner.md)]

Puede enviar un documento generado directamente a una impresora de red para su impresión directa.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, debe instalar y configurar el Agente de enrutamiento de documentos y luego registrar las impresoras de red. Para más información, consulte [Instalar el agente de ruta de documentos para habilitar la impresión de red](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent)

## <a name="make-the-printer-destination-available"></a>Hacer que el destino de impresora esté disponible

Para hacer que el destino de **impresora** esté disponible en la instancia actual de Microsoft Dynamics 365 Finance, vaya al espacio de trabajo **Administración de características** y active las siguientes características, en este orden:

1. Convertir documentos de salida de informes electrónicos desde formatos de Microsoft Office a PDF
2. Agente de ruta de documentos como destino de informes electrónicos para documentos de salida

[![Activar la característica de destino de impresora de ER en Administración de características](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)

### <a name="applicability"></a>Aplicabilidad

El destino de **impresora** solo se puede configurar para componentes de archivo que se utilizan para generar resultados en formato PDF imprimible (elementos de formato de archivo PDF o fusión de PDF) o de Microsoft Office Excel/Word (archivo Excel). Cuando la salida se genera en formato PDF, se envía a una impresora. Cuando la salida se genera en formato de Microsoft Office, se convierte automáticamente a formato PDF y luego se envía a una impresora.

### <a name="limitations"></a>Limitaciones

El destino de **impresora** solo es compatible con implementaciones en la nube.

### <a name="use-the-printer-destination"></a>Usar destino de impresora

1. Establezca la opción **Habilitado** en **Sí** para enviar un documento generado a una impresora.
2. En el campo **Nombre de impresora**, seleccione la impresora de red requerida.
3. Establezca la opción **¿Guardar en archivo de impresión?** en **Sí** para almacenar la salida generada en el archivo de impresión, de modo que esté disponible para su posterior impresión. Para acceder a la salida archivada más tarde, vaya a **Administración de la organización** \> **Consultas e informes** \> **Archivo de informes**.

[![Uso del destino de impresora](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> La opción **Convertir a PDF** no tiene que estar activada cuando se configura el destino de **impresora**. La conversión a PDF para fines de impresión ocurrirá incluso si la opción está desactivada.

Para usar una [orientación de la página](electronic-reporting-destinations.md#SelectPdfPageOrientation) específica cuando imprime un documento saliente en formato Excel, debe activar la opción **Convertir a PDF**. Cuando establece la opción **Convertir a PDF** a **Sí**, el campo **Orientación de la página** queda disponible. En el campo **Orientación de la página**, puede seleccionar una orientación de página.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
