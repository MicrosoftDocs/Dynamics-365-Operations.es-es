---
title: Requisitos del sistema para implementaciones en la nube
description: "Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, para implementaciones en la nube."
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="e0ac6-103">Requisitos del sistema para implementaciones en la nube</span><span class="sxs-lookup"><span data-stu-id="e0ac6-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e0ac6-104">Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, para implementaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="e0ac6-105">Antes de instalar Finance and Operations, si es necesario, compruebe que el sistema con el que trabaja cumple o supera los requisitos mínimos de red, hardware y software.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="e0ac6-106">Exploradores web compatibles</span><span class="sxs-lookup"><span data-stu-id="e0ac6-106">Supported web browsers</span></span>
<span data-ttu-id="e0ac6-107">La aplicación web se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="e0ac6-108">Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10</span><span class="sxs-lookup"><span data-stu-id="e0ac6-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="e0ac6-109">Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0ac6-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="e0ac6-110">Google Chrome (la versión disponible publicada más recientemente) en Windows 10, Windows 8.1, Windows 8, Windows 7 o la tableta Google Nexus 10</span><span class="sxs-lookup"><span data-stu-id="e0ac6-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="e0ac6-111">Apple Safari (la versión disponible publicada más recientemente) en Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) o 10.12 (Sierra) o Apple iPad</span><span class="sxs-lookup"><span data-stu-id="e0ac6-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="e0ac6-112">Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="e0ac6-113">Debe instalar una extensión preliminar de Chrome para permitir al Grabador de tareas hacer capturas de pantalla e incluir las imágenes documentos generados de Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="e0ac6-114">El editor de flujo de trabajo se inicia como aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="e0ac6-115">Solo Microsoft Edge y Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="e0ac6-116">La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="e0ac6-117">El Diseñador de informes para informes financieros se inicia como aplicación ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="e0ac6-118">Requiere un sistema operativo compatible de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="e0ac6-119">Si está usando Chrome, debe instalar una extensión ClickOnce para descargar el cliente del diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="e0ac6-120">Si usa Chrome en modo incógnito, asegúrese de que la extensión ClickOnce está también activada para el modo incógnito.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="e0ac6-121">Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="e0ac6-122">Exploradores web admitidos para Retail Cloud POS</span><span class="sxs-lookup"><span data-stu-id="e0ac6-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="e0ac6-123">Retail Cloud POS se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="e0ac6-124">Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10</span><span class="sxs-lookup"><span data-stu-id="e0ac6-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="e0ac6-125">Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0ac6-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="e0ac6-126">Chrome (la versión disponible publicada recientemente) en Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0ac6-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="e0ac6-127">Requisitos de red</span><span class="sxs-lookup"><span data-stu-id="e0ac6-127">Network requirements</span></span>
-   <span data-ttu-id="e0ac6-128">Finance and Operations está diseñado para redes que tengan una latencia de 250-300 milisegundos (ms) o menos.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="e0ac6-129">Esta latencia es de un cliente de explorador al centro de datos de Microsoft Azure que aloja Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="e0ac6-130">Se recomienda que pruebe la latencia de red en <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="e0ac6-131">Los requisitos del ancho de banda para Dynamics 365 for Finance and Operations dependen de su caso.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="e0ac6-132">La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="e0ac6-133">Sin embargo, recomendamos más ancho de banda para las situaciones con requisitos de carga elevados, como los espacios de trabajo o las situaciones que implican una personalización amplia.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="e0ac6-134">En general, Finance and Operations está optimizado para Internet.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="e0ac6-135">El número de acciones de ida y vuelta de un cliente de explorador al centro de datos de Azure es muy pequeño y se comprime la carga completa.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="e0ac6-136">No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="e0ac6-137">El uso simultáneo de una ubicación determinada es muy difícil de calcular.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="e0ac6-138">Los clientes que estén preocupados por los requisitos del ancho de banda, deberían usar una versión preliminar de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="e0ac6-139">Requisitos de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e0ac6-139">.NET Framework requirements</span></span>
<span data-ttu-id="e0ac6-140">Finance and Operations requiere la versión 4.6.2 de .NET Framework de Microsoft para todas las aplicaciones de un solo clic como el agente de ruta del documento.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="e0ac6-141">Para obtener instrucciones de instalación, consulte [Instalación de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="e0ac6-142">Aplicaciones de Microsoft Office compatibles</span><span class="sxs-lookup"><span data-stu-id="e0ac6-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="e0ac6-143">Las siguientes aplicaciones de Microsoft Office se admiten en implementaciones locales y en la nube de Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="e0ac6-144">Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="e0ac6-145">Para obtener más información acerca de los requisitos de la versión, consulte [Solucionador de problemas de integración de Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-145">For more information about version requirements, see [Office integration troubleshooting](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span></span>
-   <span data-ttu-id="e0ac6-146">Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="e0ac6-147">Requisitos de Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="e0ac6-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="e0ac6-148">Si PDV minorista moderno utiliza una base de datos desconectada, el equipo debe cumplir con todos los requisitos del sistema para Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="e0ac6-149">Una base de datos sin conexión de PDV minorista moderno funcionará en Microsoft SQL Server 2012 con Service Pack 3 o más posterior, Microsoft SQL Server 2014 con Service Pack 2 o más posterior, y Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="e0ac6-150">Se recomienda usar siempre la última versión disponible, e instalar todos los últimos Service Pack.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="e0ac6-151">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="e0ac6-151">Supported operating systems</span></span>

-   <span data-ttu-id="e0ac6-152">Retail Modern POS es una aplicación de 32 bits, pero se ejecutará en arquitecturas de x86 y de x64.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="e0ac6-153">Retail Modern POS solo se admite en las ediciones Pro, Enterprise y Enterprise Long Term Servicing Branch (LTSB) de Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="e0ac6-154">Requisitos mínimos del sistema</span><span class="sxs-lookup"><span data-stu-id="e0ac6-154">Minimum system requirements</span></span>

-   <span data-ttu-id="e0ac6-155">La resolución compatible mínima es 1280 × 1024.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="e0ac6-156">El equipo donde se ejecuta Retail Modern POS debe cumplir estos requisitos:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="e0ac6-157">Es necesario, como mínimo, un procesador de doble núcleo que se ejecute como mínimo a 2 gigahercios (GHz).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="e0ac6-158">Es necesario, como mínimo, 3 gigabytes (GB) de RAM.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="e0ac6-159">Debe tener acceso a Internet.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="e0ac6-160">Requisitos de Retail hardware station</span><span class="sxs-lookup"><span data-stu-id="e0ac6-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="e0ac6-161">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="e0ac6-161">Supported operating systems</span></span>

-   <span data-ttu-id="e0ac6-162">Retail hardware station es una aplicación de 32 bits, pero se ejecutará en arquitecturas de x86 y de x64.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="e0ac6-163">Retail hardware station se admite en los sistemas operativos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="e0ac6-164">Las ediciones Professional, Enterprise y Ultimate de Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0ac6-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="e0ac6-165">Windows 7 solo se admite si Internet Explorer 11 está instalado manualmente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="e0ac6-166">Las ediciones Professional, Enterprise y Embedded de Windows 8.1 Update 1</span><span class="sxs-lookup"><span data-stu-id="e0ac6-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="e0ac6-167">Ediciones Pro, Enterprise y Enterprise LTSB de Windows 10</span><span class="sxs-lookup"><span data-stu-id="e0ac6-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="e0ac6-168">Requisitos mínimos del sistema</span><span class="sxs-lookup"><span data-stu-id="e0ac6-168">Minimum system requirements</span></span>

<span data-ttu-id="e0ac6-169">El equipo debe cumplir todos los requisitos del sistema para instalar y usar los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="e0ac6-170">Servicios de Internet Information Server (IIS)</span><span class="sxs-lookup"><span data-stu-id="e0ac6-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="e0ac6-171">Hardware de terceros</span><span class="sxs-lookup"><span data-stu-id="e0ac6-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="e0ac6-172">Requisitos de Retail Store Scale Unit</span><span class="sxs-lookup"><span data-stu-id="e0ac6-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="e0ac6-173">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="e0ac6-173">Supported operating systems</span></span>

-   <span data-ttu-id="e0ac6-174">Retail Store Scale Unit es una aplicación de 32 bits, pero se ejecutará en arquitecturas de x86 y de x64.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="e0ac6-175">Retail Store Scale Unit se admite en los sistemas operativos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="e0ac6-176">Las ediciones Professional, Enterprise y Ultimate de Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0ac6-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="e0ac6-177">Las ediciones Professional, Enterprise y Embedded de Windows 8.1 Update 1</span><span class="sxs-lookup"><span data-stu-id="e0ac6-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="e0ac6-178">Ediciones Pro, Enterprise y Enterprise LTSB de Windows 10</span><span class="sxs-lookup"><span data-stu-id="e0ac6-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="e0ac6-179">Requisitos mínimos del sistema</span><span class="sxs-lookup"><span data-stu-id="e0ac6-179">Minimum system requirements</span></span>

-   <span data-ttu-id="e0ac6-180">4 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="e0ac6-180">4 GB of RAM</span></span>
-   <span data-ttu-id="e0ac6-181">Velocidad de CPU pico de 1,6 GHz por núcleo (dos núcleos como mínimo).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="e0ac6-182">Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="e0ac6-183">Requisitos del sistema recomendados</span><span class="sxs-lookup"><span data-stu-id="e0ac6-183">Recommended system requirements</span></span>

-   <span data-ttu-id="e0ac6-184">6 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="e0ac6-184">6 GB of RAM</span></span>
-   <span data-ttu-id="e0ac6-185">Velocidad de CPU pico de 2,4 GHz i7 por núcleo (se recomiendan cuatro núcleos).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="e0ac6-186">Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="e0ac6-187">Requisitos de Connector</span><span class="sxs-lookup"><span data-stu-id="e0ac6-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="e0ac6-188">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="e0ac6-188">Supported operating systems</span></span>

-   <span data-ttu-id="e0ac6-189">El Connector para Microsoft Dynamics AX tiene dos instaladores independientes, uno para el Servidor de Connector de Servidor y otro para el Servicio en tiempo real para Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="e0ac6-190">Ambos componentes son aplicaciones de 32 bits, pero funcionan en arquitecturas x86 y x64.</span><span class="sxs-lookup"><span data-stu-id="e0ac6-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="e0ac6-191">Ambos componentes son compatibles con los sistemas operativos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e0ac6-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="e0ac6-192">Las ediciones Professional, Enterprise y Ultimate de Windows 7</span><span class="sxs-lookup"><span data-stu-id="e0ac6-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="e0ac6-193">Las ediciones Professional, Enterprise y Embedded de Windows 8.1 Update 1</span><span class="sxs-lookup"><span data-stu-id="e0ac6-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="e0ac6-194">Ediciones Pro, Enterprise y Enterprise LTSB de Windows 10</span><span class="sxs-lookup"><span data-stu-id="e0ac6-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="e0ac6-195">Microsoft Windows Server 2012 R2 y Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="e0ac6-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="e0ac6-196">Requisitos mínimos del sistema</span><span class="sxs-lookup"><span data-stu-id="e0ac6-196">Minimum system requirements</span></span>
-   <span data-ttu-id="e0ac6-197">2 GB de RAM, aunque se recomiendan 4 GB de RAM</span><span class="sxs-lookup"><span data-stu-id="e0ac6-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="e0ac6-198">Velocidad de CPU pico de 1,6 GHz por núcleo (dos núcleos como mínimo).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="e0ac6-199">Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="e0ac6-200">Requisitos de desarrollo en VM locales</span><span class="sxs-lookup"><span data-stu-id="e0ac6-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="e0ac6-201">Para obtener información acerca de los requisitos de desarrollo en las máquinas virtuales locales (VM), consulte [la ejecución de VM en las instalaciones](../../dev-itpro/dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="e0ac6-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../../dev-itpro/dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="e0ac6-202">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0ac6-202">See also</span></span>

[<span data-ttu-id="e0ac6-203">Obtenga una copia de evaluacion de Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e0ac6-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](../../dev-itpro/dev-tools/get-evaluation-copy.md)

