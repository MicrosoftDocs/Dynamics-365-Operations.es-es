---
title: Requisitos del sistema de Talent
description: Este tema muestra los requisitos de Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 10/21/2019
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
ms.openlocfilehash: 509827d5736887f56e7754a0760af7dea76277f7
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006064"
---
# <a name="talent-system-requirements"></a><span data-ttu-id="d2cf2-103">Requisitos del sistema de Talent</span><span class="sxs-lookup"><span data-stu-id="d2cf2-103">Talent system requirements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d2cf2-104">Este tema describe los requisitos para Microsoft Dynamics 365 Talent, incluido Attract y Onboard.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-104">This topic describes requirements for Microsoft Dynamics 365 Talent, including Attract and Onboard.</span></span> <span data-ttu-id="d2cf2-105">También describe los países y regiones donde Talent está disponible, además de información sobre idiomas y ubicación para los datos de Talent.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-105">It also outlines the countries and regions where Talent is available, plus information about languages and localization for Talent data.</span></span> <span data-ttu-id="d2cf2-106">Además, este tema proporciona la actualización de la directiva de Talent.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-106">In additions, this topic provides the update policy for Talent.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="d2cf2-107">Exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="d2cf2-107">Supported web browsers</span></span>

<span data-ttu-id="d2cf2-108">Microsoft Dynamics 365 Talent se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:</span><span class="sxs-lookup"><span data-stu-id="d2cf2-108">Microsoft Dynamics 365 Talent can run in any of the following web browsers that run on the specified operating systems:</span></span> 

*   <span data-ttu-id="d2cf2-109">Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10</span><span class="sxs-lookup"><span data-stu-id="d2cf2-109">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
*   <span data-ttu-id="d2cf2-110">Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="d2cf2-110">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
*   <span data-ttu-id="d2cf2-111">Google Chrome (la última versión disponible públicamente)</span><span class="sxs-lookup"><span data-stu-id="d2cf2-111">Google Chrome (latest publicly available version)</span></span>
*   <span data-ttu-id="d2cf2-112">Apple Safari (la última versión disponible públicamente)</span><span class="sxs-lookup"><span data-stu-id="d2cf2-112">Apple Safari (latest publicly available version)</span></span>

<span data-ttu-id="d2cf2-113">Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-113">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> * <span data-ttu-id="d2cf2-114">Para tomar las imágenes generadas en el Grabador de tareas y incluirlas en los documentos de Microsoft Word, debe tener una extensión de Chrome instalada.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-114">To capture images that are generated from Task Recorder and include them in Microsoft Word documents, you must have a Chrome extension installed.</span></span> 
> * <span data-ttu-id="d2cf2-115">El editor de flujo de trabajo se inicia como aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-115">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="d2cf2-116">Sólo Microsoft Edge e Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnces.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-116">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="d2cf2-117">La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-117">The Workflow Editor ClickOnce application requires a 64-bit compatible operating system.</span></span>
> * <span data-ttu-id="d2cf2-118">Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores modernos como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-118">To preview PDF files, we recommend that you use modern browsers like Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>
>   <span data-ttu-id="d2cf2-119">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="d2cf2-119">Network requirements</span></span>
> * <span data-ttu-id="d2cf2-120">Dynamics 365 Talent está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-120">Dynamics 365 Talent is designed for networks with latency of 250-300 milliseconds (ms) or less.</span></span> <span data-ttu-id="d2cf2-121">Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Talent.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-121">This is the latency from a browser client to the Microsoft Azure data center that hosts Talent.</span></span> <span data-ttu-id="d2cf2-122">Se recomienda que pruebe la latencia de red en [www.azurespeed.com](https://www.azurespeed.com "Test de latencia de Azure").</span><span class="sxs-lookup"><span data-stu-id="d2cf2-122">We recommend that you test network latency at [www.azurespeed.com](https://www.azurespeed.com "Azure Latency Test").</span></span>
> * <span data-ttu-id="d2cf2-123">Los requisitos de ancho de banda de Talent dependen de su situación.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-123">Bandwidth requirements for Talent depend on your scenario.</span></span> <span data-ttu-id="d2cf2-124">La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps).</span><span class="sxs-lookup"><span data-stu-id="d2cf2-124">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span>
> 
> [!WARNING]
> <span data-ttu-id="d2cf2-125">No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-125">Don't compute bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="d2cf2-126">El uso simultáneo de una ubicación determinada es muy difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-126">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="d2cf2-127">Para los clientes que estén preocupados por los requisitos del ancho de banda, use una versión de prueba de Talent.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-127">For customers who are concerned about bandwidth requirements, use a trial version of Talent.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="d2cf2-128">Aplicaciones de Microsoft Office admitidas</span><span class="sxs-lookup"><span data-stu-id="d2cf2-128">Supported Microsoft Office applications</span></span>

* <span data-ttu-id="d2cf2-129">Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-129">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="d2cf2-130">Para obtener más información acerca de los requisitos de la versión, consulte [Solución de problemas de la integración de Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solución de problemas de la integración con Office").</span><span class="sxs-lookup"><span data-stu-id="d2cf2-130">For more details about version requirements, see [Office integration troubleshooting](../dev-itpro/office-integration/office-integration-troubleshooting.md "Office integration troubleshooting").</span></span>
* <span data-ttu-id="d2cf2-131">Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-131">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="regional-availability-languages-and-localization"></a><span data-ttu-id="d2cf2-132">Disponibilidad, idiomas, y localización regional</span><span class="sxs-lookup"><span data-stu-id="d2cf2-132">Regional availability, languages, and localization</span></span>

<span data-ttu-id="d2cf2-133">Puede descargar un archivo PDF de países, las regiones e idiomas compatibles con Talent en [Disponibilidad internacional de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span><span class="sxs-lookup"><span data-stu-id="d2cf2-133">You can download a PDF file of the countries, regions, and languages Talent supports at [International availability of Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).</span></span> 

> [!NOTE]
> <span data-ttu-id="d2cf2-134">Aunque la interfaz de usuario se encuentre en otros idiomas, todos los datos de usuario se almacenan en el idioma en el que se introdujeron.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-134">While the user interface is localized into other languages, all user data is stored in the language in which it was entered.</span></span> <span data-ttu-id="d2cf2-135">Puede crear mensajes de correo electrónico y plantillas en otros idiomas, pero los datos como información de programación solo está disponible en inglés en este momento.</span><span class="sxs-lookup"><span data-stu-id="d2cf2-135">You can create emails and templates in other languages, but data such as scheduling information is only available in English at this time.</span></span>

<span data-ttu-id="d2cf2-136">Si es desarrollador de software y está interesado en crear país o personalizaciones específicas de una región, o en crear una solución de un país o región no compatible actualmente con Microsoft, consulte [Globalización](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span><span class="sxs-lookup"><span data-stu-id="d2cf2-136">If you're a developer interested in creating country- or region-specific customizations, or in creating a solution for a country or region not currently supported by Microsoft, see [Globalization](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).</span></span>

