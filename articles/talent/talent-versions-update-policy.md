---
title: Requisitos del sistema de Talent y directiva de actualización
description: Este tema muestra los requisitos de Dynamics 365 for Talent. También se describe la directiva de actualización.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 2389f00b22ec3b5284eeffb2c015533b7a3d13e0
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "856310"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="02f0f-104">Requisitos del sistema de Talent y directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="02f0f-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02f0f-105">Este tema muestra los requisitos de Microsoft Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="02f0f-105">This topic lists requirements for Microsoft Dynamics 365 for Talent.</span></span> <span data-ttu-id="02f0f-106">También se describe la directiva de actualización.</span><span class="sxs-lookup"><span data-stu-id="02f0f-106">The update policy is outlined, as well.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="02f0f-107">Exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="02f0f-107">Supported web browsers</span></span>

<span data-ttu-id="02f0f-108">La aplicación web de Microsoft Dynamics 365 for Talent se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:</span><span class="sxs-lookup"><span data-stu-id="02f0f-108">The Microsoft Dynamics 365 for Talent web application can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="02f0f-109">Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10</span><span class="sxs-lookup"><span data-stu-id="02f0f-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="02f0f-110">Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="02f0f-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="02f0f-111">Google Chrome (la última versión disponible públicamente)</span><span class="sxs-lookup"><span data-stu-id="02f0f-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="02f0f-112">Apple Safari (la última versión disponible públicamente)</span><span class="sxs-lookup"><span data-stu-id="02f0f-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="02f0f-113">Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software.</span><span class="sxs-lookup"><span data-stu-id="02f0f-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="02f0f-114">Para tomar las imágenes generadas en el Grabador de tareas y incluirlas en los documentos de Microsoft Word, debe tener una extensión de Chrome instalada.</span><span class="sxs-lookup"><span data-stu-id="02f0f-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="02f0f-115">El editor de flujo de trabajo se inicia como aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="02f0f-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="02f0f-116">Sólo Microsoft Edge e Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnces.</span><span class="sxs-lookup"><span data-stu-id="02f0f-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="02f0f-117">La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="02f0f-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="02f0f-118">Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores modernos como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="02f0f-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="02f0f-119">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="02f0f-119">Network requirements</span></span>
> * <span data-ttu-id="02f0f-120">Dynamics 365 for Talent está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos.</span><span class="sxs-lookup"><span data-stu-id="02f0f-120">Dynamics 365 for Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="02f0f-121">Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="02f0f-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Dynamics 365 for Talent.</span></span> <span data-ttu-id="02f0f-122">Se recomienda que pruebe la latencia de red en [www.azurespeed.com](https://www.azurespeed.com "Prueba de latencia de Azure").</span><span class="sxs-lookup"><span data-stu-id="02f0f-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="02f0f-123">Los requisitos de ancho de banda de Dynamics 365 for Talent dependen de su situación.</span><span class="sxs-lookup"><span data-stu-id="02f0f-123">Bandwidth requirements for Dynamics 365 for Talent depend on your scenario.</span></span> <span data-ttu-id="02f0f-124">La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps).</span><span class="sxs-lookup"><span data-stu-id="02f0f-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="02f0f-125">No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="02f0f-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="02f0f-126">El uso simultáneo de una ubicación determinada es muy difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="02f0f-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="02f0f-127">Para los clientes que estén preocupados por los requisitos del ancho de banda, use una versión de prueba de Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="02f0f-127">For customers who are concerned about bandwidth requirements, use a trial version of Dynamics 365 for Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="02f0f-128">Aplicaciones de Microsoft Office admitidas</span><span class="sxs-lookup"><span data-stu-id="02f0f-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="02f0f-129">Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac.</span><span class="sxs-lookup"><span data-stu-id="02f0f-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="02f0f-130">Para obtener más información acerca de los requisitos de la versión, consulte la [Solución de problemas de la integración de Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solución de problemas de la integración de Office").</span><span class="sxs-lookup"><span data-stu-id="02f0f-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="02f0f-131">Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="02f0f-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="update-policy"></a><span data-ttu-id="02f0f-132">Directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="02f0f-132">Update policy</span></span>

<span data-ttu-id="02f0f-133">Microsoft Dynamics 365 for Talent se mantiene como oferta de nube.</span><span class="sxs-lookup"><span data-stu-id="02f0f-133">Microsoft Dynamics 365 for Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="02f0f-134">Las actualizaciones de Dynamics 365 for Talent son continuas y Microsoft las aplica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="02f0f-134">Updates to Dynamics 365 for Talent are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="02f0f-135">Las actualizaciones se lanzan en una cadencia regular, las actualizaciones se crearán a todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="02f0f-135">Updates are released on a regular cadence, updates will be made to all environments.</span></span>  <span data-ttu-id="02f0f-136">Dynamics 365 for Talent es admitido por la directiva [Soporte técnico del ciclo de vida de Microsoft](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Soporte técnico del ciclo de vida de Microsoft"), que proporciona directrices coherentes y fiables para la disponibilidad de asistencia técnica.</span><span class="sxs-lookup"><span data-stu-id="02f0f-136">Dynamics 365 for Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/en-us/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
