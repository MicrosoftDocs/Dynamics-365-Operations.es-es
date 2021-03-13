---
title: Tipo de destino de ER de impresora
description: Este tema explica cómo puede configurar un destino de impresora para cada componente FOLDER o FILE de un informe electrónico (ER).
author: NickSelin
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: c6e298f62ec69f349eb713d66313e535c7e01881
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094088"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="4ad34-103">Destino de la impresora</span><span class="sxs-lookup"><span data-stu-id="4ad34-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ad34-104">Puede enviar un documento generado directamente a una impresora de red para su impresión directa.</span><span class="sxs-lookup"><span data-stu-id="4ad34-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4ad34-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4ad34-105">Prerequisites</span></span>

<span data-ttu-id="4ad34-106">Antes de comenzar, debe instalar y configurar el Agente de enrutamiento de documentos y luego registrar las impresoras de red.</span><span class="sxs-lookup"><span data-stu-id="4ad34-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="4ad34-107">Para más información, consulte [Instalar el agente de ruta de documentos para habilitar la impresión de red](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent)</span><span class="sxs-lookup"><span data-stu-id="4ad34-107">For more information, see [Install the Document Routing Agent to enable network printing](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/install-document-routing-agent).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="4ad34-108">Hacer que el destino de impresora esté disponible</span><span class="sxs-lookup"><span data-stu-id="4ad34-108">Make the Printer destination available</span></span>

<span data-ttu-id="4ad34-109">Para hacer que el destino de **impresora** esté disponible en la instancia actual de Microsoft Dynamics 365 Finance, vaya al espacio de trabajo **Administración de características** y active las siguientes características, en este orden:</span><span class="sxs-lookup"><span data-stu-id="4ad34-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="4ad34-110">Convertir documentos de salida de informes electrónicos desde formatos de Microsoft Office a PDF</span><span class="sxs-lookup"><span data-stu-id="4ad34-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="4ad34-111">Agente de ruta de documentos como destino de informes electrónicos para documentos de salida</span><span class="sxs-lookup"><span data-stu-id="4ad34-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="4ad34-112">[![Activar la característica de destino de impresora de ER en Administración de características](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="4ad34-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="4ad34-113">Aplicabilidad</span><span class="sxs-lookup"><span data-stu-id="4ad34-113">Applicability</span></span>

<span data-ttu-id="4ad34-114">El destino de **impresora** solo se puede configurar para componentes de archivo que se utilizan para generar resultados en formato PDF imprimible (elementos de formato de archivo PDF o fusión de PDF) o de Microsoft Office Excel/Word (archivo Excel).</span><span class="sxs-lookup"><span data-stu-id="4ad34-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="4ad34-115">Cuando la salida se genera en formato PDF, se envía a una impresora.</span><span class="sxs-lookup"><span data-stu-id="4ad34-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="4ad34-116">Cuando la salida se genera en formato de Microsoft Office, se convierte automáticamente a formato PDF y luego se envía a una impresora.</span><span class="sxs-lookup"><span data-stu-id="4ad34-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="4ad34-117">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4ad34-117">Limitations</span></span>

<span data-ttu-id="4ad34-118">Esta característica está en versión preliminar y está sujeta a los términos de uso que se describen en [Términos de uso complementarios para las versiones preliminares de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274).</span><span class="sxs-lookup"><span data-stu-id="4ad34-118">This feature is a preview feature and is subject to the terms of use that are described in [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://go.microsoft.com/fwlink/?linkid=2105274).</span></span>

<span data-ttu-id="4ad34-119">El destino de **impresora** solo es compatible con implementaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="4ad34-119">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="4ad34-120">Usar destino de impresora</span><span class="sxs-lookup"><span data-stu-id="4ad34-120">Use the Printer destination</span></span>

1. <span data-ttu-id="4ad34-121">Establezca la opción **Habilitado** en **Sí** para enviar un documento generado a una impresora.</span><span class="sxs-lookup"><span data-stu-id="4ad34-121">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="4ad34-122">En el campo **Nombre de impresora**, seleccione la impresora de red requerida.</span><span class="sxs-lookup"><span data-stu-id="4ad34-122">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="4ad34-123">Establezca la opción **¿Guardar en archivo de impresión?** en **Sí** para almacenar la salida generada en el archivo de impresión, de modo que esté disponible para su posterior impresión.</span><span class="sxs-lookup"><span data-stu-id="4ad34-123">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="4ad34-124">Para acceder a la salida archivada más tarde, vaya a **Administración de la organización** \> **Consultas e informes** \> **Archivo de informes**.</span><span class="sxs-lookup"><span data-stu-id="4ad34-124">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="4ad34-125">[![Uso del destino de impresora](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="4ad34-125">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="4ad34-126">La opción **Convertir a PDF** no tiene que estar activada cuando se configura el destino de **impresora**.</span><span class="sxs-lookup"><span data-stu-id="4ad34-126">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="4ad34-127">La conversión a PDF para fines de impresión ocurrirá incluso si la opción está desactivada.</span><span class="sxs-lookup"><span data-stu-id="4ad34-127">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="4ad34-128">Para usar una [orientación de la página](electronic-reporting-destinations.md#SelectPdfPageOrientation) específica cuando imprime un documento saliente en formato Excel, debe activar la opción **Convertir a PDF**.</span><span class="sxs-lookup"><span data-stu-id="4ad34-128">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="4ad34-129">Cuando establece la opción **Convertir a PDF** a **Sí**, el campo **Orientación de la página** queda disponible.</span><span class="sxs-lookup"><span data-stu-id="4ad34-129">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="4ad34-130">En el campo **Orientación de la página**, puede seleccionar una orientación de página.</span><span class="sxs-lookup"><span data-stu-id="4ad34-130">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ad34-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4ad34-131">Additional resources</span></span>

- [<span data-ttu-id="4ad34-132">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="4ad34-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="4ad34-133">Destinos de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="4ad34-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
