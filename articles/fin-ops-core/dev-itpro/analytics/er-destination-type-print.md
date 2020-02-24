---
title: Tipo de destino de ER de impresora
description: Este tema explica cómo configurar un destino de impresora para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes en formato PDF o de Microsoft Office (Excel o Word).
author: NickSelin
manager: AnnBe
ms.date: 01/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 58e067baa130458e3a8e788d978604f208140a03
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019987"
---
# <a name="PrinterDestinationType"></a>Destino de impresora

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

Esta característica está en versión preliminar y está sujeta a los términos de uso que se describen en [Términos de uso complementarios para las versiones preliminares de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274).

El destino de **impresora** solo es compatible con implementaciones en la nube.

### <a name="use-the-printer-destination"></a>Usar destino de impresora

1. Establezca la opción **Habilitado** en **Sí** para enviar un documento generado a una impresora.
2. En el campo **Nombre de impresora**, seleccione la impresora de red requerida.
3. Establezca la opción **¿Guardar en archivo de impresión?** en **Sí** para almacenar la salida generada en el archivo de impresión, de modo que esté disponible para su posterior impresión. Para acceder a la salida archivada más tarde, vaya a **Administración de la organización** \> **Consultas e informes** \> **Archivo de informes**.

[![Uso del destino de impresora](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)

> [!NOTE]
> La opción **Convertir a PDF** no tiene que estar activada cuando se configura el destino de **impresora**. La conversión a PDF para fines de impresión ocurrirá incluso si la opción está desactivada.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
