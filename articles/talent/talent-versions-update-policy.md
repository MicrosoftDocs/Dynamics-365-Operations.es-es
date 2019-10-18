---
title: Requisitos del sistema de Talent y directiva de actualización
description: Este tema muestra los requisitos de Dynamics 365 Talent. También se describe la directiva de actualización.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
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
ms.openlocfilehash: b8bf44fc76be968b0b04fd894c39b4c19fd374ce
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024169"
---
# <a name="talent-system-requirements-and-update-policy"></a><span data-ttu-id="ffb46-104">Requisitos del sistema de Talent y directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="ffb46-104">Talent system requirements and update policy</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ffb46-105">Este tema describe los requisitos para Microsoft Dynamics 365 Talent, incluido Attract, Onboard y Core HR.</span><span class="sxs-lookup"><span data-stu-id="ffb46-105">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract, Onboard, and Core HR.</span></span> <span data-ttu-id="ffb46-106">También describe los países y regiones donde Talent está disponible, además de información sobre idiomas y ubicación para los datos de Talent.</span><span class="sxs-lookup"><span data-stu-id="ffb46-106">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="ffb46-107">Además, este tema proporciona la actualización de la directiva de Talent.</span><span class="sxs-lookup"><span data-stu-id="ffb46-107">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="ffb46-108">Exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="ffb46-108">Supported web browsers</span></span>

<span data-ttu-id="ffb46-109">Microsoft Dynamics 365 Talent se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:</span><span class="sxs-lookup"><span data-stu-id="ffb46-109">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="ffb46-110">Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10</span><span class="sxs-lookup"><span data-stu-id="ffb46-110">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="ffb46-111">Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="ffb46-111">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="ffb46-112">Google Chrome (la última versión disponible públicamente)</span><span class="sxs-lookup"><span data-stu-id="ffb46-112">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="ffb46-113">Apple Safari (la última versión disponible públicamente)</span><span class="sxs-lookup"><span data-stu-id="ffb46-113">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="ffb46-114">Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software.</span><span class="sxs-lookup"><span data-stu-id="ffb46-114">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="ffb46-115">Para tomar las imágenes generadas en el Grabador de tareas y incluirlas en los documentos de Microsoft Word, debe tener una extensión de Chrome instalada.</span><span class="sxs-lookup"><span data-stu-id="ffb46-115">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="ffb46-116">El editor de flujo de trabajo se inicia como aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="ffb46-116">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="ffb46-117">Sólo Microsoft Edge e Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnces.</span><span class="sxs-lookup"><span data-stu-id="ffb46-117">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="ffb46-118">La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="ffb46-118">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="ffb46-119">Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores modernos como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="ffb46-119">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="ffb46-120">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="ffb46-120">Network requirements</span></span>
> * <span data-ttu-id="ffb46-121">Dynamics 365 Talent está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos.</span><span class="sxs-lookup"><span data-stu-id="ffb46-121">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="ffb46-122">Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Talent.</span><span class="sxs-lookup"><span data-stu-id="ffb46-122">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="ffb46-123">Se recomienda que pruebe la latencia de red en [www.azurespeed.com](https://www.azurespeed.com "Prueba de latencia de Azure").</span><span class="sxs-lookup"><span data-stu-id="ffb46-123">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="ffb46-124">Los requisitos de ancho de banda de Talent dependen de su situación.</span><span class="sxs-lookup"><span data-stu-id="ffb46-124">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="ffb46-125">La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps).</span><span class="sxs-lookup"><span data-stu-id="ffb46-125">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="ffb46-126">No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="ffb46-126">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="ffb46-127">El uso simultáneo de una ubicación determinada es muy difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="ffb46-127">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="ffb46-128">Para los clientes que estén preocupados por los requisitos del ancho de banda, use una versión de prueba de Talent.</span><span class="sxs-lookup"><span data-stu-id="ffb46-128">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="ffb46-129">Aplicaciones de Microsoft Office admitidas</span><span class="sxs-lookup"><span data-stu-id="ffb46-129">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="ffb46-130">Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac.</span><span class="sxs-lookup"><span data-stu-id="ffb46-130">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="ffb46-131">Para obtener más información acerca de los requisitos de la versión, consulte la [Solución de problemas de la integración de Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solución de problemas de la integración de Office").</span><span class="sxs-lookup"><span data-stu-id="ffb46-131">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="ffb46-132">Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="ffb46-132">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="ffb46-133">Disponibilidad, idiomas, y localización regional</span><span class="sxs-lookup"><span data-stu-id="ffb46-133">Regional availability, languages, and localization</span></span>

<span data-ttu-id="ffb46-134">Puede descargar un archivo PDF de países, las regiones e idiomas compatibles con Talent en [Disponibilidad internacional de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="ffb46-134">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="ffb46-135">Aunque la interfaz de usuario se encuentre en otros idiomas, todos los datos de usuario se almacenan en el idioma en el que se introdujeron.</span><span class="sxs-lookup"><span data-stu-id="ffb46-135">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="ffb46-136">Puede crear mensajes de correo electrónico y plantillas en otros idiomas, pero los datos como información de programación solo está disponible en inglés en este momento.</span><span class="sxs-lookup"><span data-stu-id="ffb46-136">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="ffb46-137">Si es desarrollador de software y está interesado en crear país o personalizaciones específicas de una región, o en crear una solución de un país o región no compatible actualmente con Microsoft, consulte [Globalización](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="ffb46-137">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

## <a name="update-policy"></a><span data-ttu-id="ffb46-138">Directiva de actualización</span><span class="sxs-lookup"><span data-stu-id="ffb46-138">Update policy</span></span>

<span data-ttu-id="ffb46-139">Talent se mantiene como oferta de nube.</span><span class="sxs-lookup"><span data-stu-id="ffb46-139">Talent is serviced as a cloud offering.</span></span> <span data-ttu-id="ffb46-140">Las actualizaciones de Talent son continuas y Microsoft las aplica automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ffb46-140">Talent updates are continuous and applied automatically by Microsoft.</span></span>

<span data-ttu-id="ffb46-141">Las actualizaciones se lanzan en una cadencia regular, las actualizaciones y se crearán a todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="ffb46-141">Updates are released on a regular cadence and will be made to all environments.</span></span> <span data-ttu-id="ffb46-142">Talent es admitido por la directiva [Soporte técnico del ciclo de vida de Microsoft](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Soporte técnico del ciclo de vida de Microsoft"), que proporciona directrices coherentes y fiables para la disponibilidad de asistencia técnica.</span><span class="sxs-lookup"><span data-stu-id="ffb46-142">Talent is supported according to the [Microsoft Support Lifecycle policy](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Microsoft Support Lifecycle"), which provides consistent and predictable guidelines for product support availability.</span></span>
