---
title: Visión general de la impresión de documentos
description: Puede imprimir documentos mediante una impresora local o un dispositivo conectado a la red. Este artículo proporciona una visión general de cómo se imprimen los documentos.
author: TJVass
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c8475e26d9a2234d4c429ef1b5e482ac06fde08
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182908"
---
# <a name="document-printing-overview"></a><span data-ttu-id="1f459-104">Visión general de la impresión de documentos</span><span class="sxs-lookup"><span data-stu-id="1f459-104">Document printing overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f459-105">Puede imprimir documentos mediante una impresora local o un dispositivo conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="1f459-105">You can print documents by using either a local printer or a network-connected device.</span></span> <span data-ttu-id="1f459-106">Este artículo proporciona una visión general de cómo se imprimen los documentos.</span><span class="sxs-lookup"><span data-stu-id="1f459-106">This article provides an overview of how documents are printed.</span></span>

## <a name="printing-overview"></a><span data-ttu-id="1f459-107">Visión general de la impresión</span><span class="sxs-lookup"><span data-stu-id="1f459-107">Printing overview</span></span>

<span data-ttu-id="1f459-108">La aplicación proporciona los servicios integrados y las aplicaciones cliente que facilitan la generación, el almacenamiento y la distribución de documentos que respaldan la actividad empresarial.</span><span class="sxs-lookup"><span data-stu-id="1f459-108">The application provides integrated services and client applications that make it easy to generate, store, and distribute documents that support business activity.</span></span> <span data-ttu-id="1f459-109">Puede imprimir documentos mediante una impresora local o un dispositivo conectado a la red.</span><span class="sxs-lookup"><span data-stu-id="1f459-109">You can print documents by using either a local printer or a network-connected device.</span></span> <span data-ttu-id="1f459-110">Además, puede exportar páginas e informes directamente desde el cliente, como archivos PDF o documentos de Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="1f459-110">In addition, you can export pages and reports directly from the client, as PDF files or Microsoft Office documents.</span></span> <span data-ttu-id="1f459-111">Finalmente, la carga de trabajo distribuida le permite imprimir documentos empresariales directamente desde un dispositivo móvil mediante el uso de recursos de red.</span><span class="sxs-lookup"><span data-stu-id="1f459-111">Finally, the distributed workload lets you print business documents directly from a mobile device by using network resources.</span></span> <span data-ttu-id="1f459-112">Aunque los requisitos de impresión pueden variar, normalmente todas las industrias deben crear copias impresas de documentos empresariales mediante la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f459-112">Although printing requirements might vary, all industries typically must create hard copies of business documents by using the application.</span></span> <span data-ttu-id="1f459-113">La impresión de documentos en dispositivos de red desde aplicaciones hospedadas presenta un conjunto exclusivo de retos.</span><span class="sxs-lookup"><span data-stu-id="1f459-113">Printing documents on network devices from hosted applications presents a unique set of challenges.</span></span> <span data-ttu-id="1f459-114">A continuación se incluyen algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="1f459-114">Here are some examples:</span></span>

- <span data-ttu-id="1f459-115">Puede que los controladores de impresión no estén disponibles en el dispositivo del usuario.</span><span class="sxs-lookup"><span data-stu-id="1f459-115">Print drivers might not be available on the user's device.</span></span>
- <span data-ttu-id="1f459-116">Puede que el dispositivo del usuario no esté conectado a la red corporativa.</span><span class="sxs-lookup"><span data-stu-id="1f459-116">The user's device might not be connected to the corporate network.</span></span>

<span data-ttu-id="1f459-117">Al utilizar el host dedicado y tras unos sencillos pasos, los administradores del sistema pueden configurar las implementaciones de modo que los usuarios puedan imprimir directamente desde aplicaciones empresariales en los dispositivos de red.</span><span class="sxs-lookup"><span data-stu-id="1f459-117">By using a dedicated host and following a few easy steps, system administrators can configure deployments so that users can print directly from business applications on network devices.</span></span>

### <a name="application-printing-scenarios"></a><span data-ttu-id="1f459-118">Situaciones de impresión de la aplicación</span><span class="sxs-lookup"><span data-stu-id="1f459-118">Application printing scenarios</span></span> 

<span data-ttu-id="1f459-119">La siguiente tabla describe los tres escenarios principales de impresión.</span><span class="sxs-lookup"><span data-stu-id="1f459-119">The following table describes the three primary printing scenarios.</span></span>

| <span data-ttu-id="1f459-120">Situación</span><span class="sxs-lookup"><span data-stu-id="1f459-120">Scenario</span></span>                        | <span data-ttu-id="1f459-121">Objetivo</span><span class="sxs-lookup"><span data-stu-id="1f459-121">Goal</span></span>                                                      | <span data-ttu-id="1f459-122">Solución</span><span class="sxs-lookup"><span data-stu-id="1f459-122">Solution</span></span> |
|---------------------------------|-----------------------------------------------------------|----------|
| <span data-ttu-id="1f459-123">1. Imprimir lo que ve</span><span class="sxs-lookup"><span data-stu-id="1f459-123">1. Printing what you see</span></span>        | <span data-ttu-id="1f459-124">Imprima lo que se muestra actualmente en el explorador.</span><span class="sxs-lookup"><span data-stu-id="1f459-124">Print what is currently shown in the browser.</span></span>             | <span data-ttu-id="1f459-125">Se genera una versión "fácil de imprimir" de la página web para el explorador.</span><span class="sxs-lookup"><span data-stu-id="1f459-125">A "print-friendly" version of the webpage is generated for the browser.</span></span> |
| <span data-ttu-id="1f459-126">2. Impresión interactiva</span><span class="sxs-lookup"><span data-stu-id="1f459-126">2. Interactive printing</span></span>         | <span data-ttu-id="1f459-127">Imprima un documento de precisión en un dispositivo conectado a nivel local.</span><span class="sxs-lookup"><span data-stu-id="1f459-127">Print a precision document on a locally connected device.</span></span> | <span data-ttu-id="1f459-128">Puede exportar una versión PDF del informe y descargarla en el explorador.</span><span class="sxs-lookup"><span data-stu-id="1f459-128">You can export a PDF version of the report and download it to the browser.</span></span> |
| <span data-ttu-id="1f459-129">3. Impresión en un dispositivo de red</span><span class="sxs-lookup"><span data-stu-id="1f459-129">3. Printing on a network device</span></span> | <span data-ttu-id="1f459-130">Envíe un documento de precisión a una impresora de dominio.</span><span class="sxs-lookup"><span data-stu-id="1f459-130">Send a precision document to a domain printer device.</span></span>     | <span data-ttu-id="1f459-131">Un documento de precisión se envía a una aplicación cliente que se ejecuta en un servidor que se hospeda en el dominio del cliente.</span><span class="sxs-lookup"><span data-stu-id="1f459-131">A precision document is sent to a client application that runs on a server that is hosted in the customer's domain.</span></span> |

<span data-ttu-id="1f459-132">Dado que la solución varía en función del escenario, las aplicaciones proporcionan servicios y herramientas integradas para ayudar a los usuarios a cumplir sus objetivos:</span><span class="sxs-lookup"><span data-stu-id="1f459-132">Because the solution varies, depending on the scenario, applications provide built-in services and tooling to help users accomplish their goals:</span></span>

- <span data-ttu-id="1f459-133">El **Escenario 1** es compatible con la representación del explorador del cliente HTML5.</span><span class="sxs-lookup"><span data-stu-id="1f459-133">**Scenario 1** is supported by the browser's rendering of the HTML5 client.</span></span>
- <span data-ttu-id="1f459-134">El **Escenario 2** usa aplicaciones cliente y servicios de Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f459-134">**Scenario 2** uses client applications and Microsoft Office 365 services.</span></span>
- <span data-ttu-id="1f459-135">El **Escenario 3** requiere soporte desde aplicaciones cliente y desde servicios que se hospedan en Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="1f459-135">**Scenario 3** requires support from client applications and from services that are hosted in Microsoft Azure.</span></span>

<span data-ttu-id="1f459-136">Además de la plataforma que se implementa en la suscripción de Azure, las aplicaciones de Finance and Operations proporcionan a los clientes una aplicación de Azure integrada de primera parte que les ayuda a utilizar con más facilidad dispositivos hospedados en dominios para imprimir documentos.</span><span class="sxs-lookup"><span data-stu-id="1f459-136">In addition to the platform that is deployed to the Azure subscription, Finance and Operations applications provide customers with an integrated, first-party Azure application that helps them more easily use domain-hosted devices to print documents.</span></span>

## <a name="service-overview"></a><span data-ttu-id="1f459-137">Visión general de servicios</span><span class="sxs-lookup"><span data-stu-id="1f459-137">Service overview</span></span>
<span data-ttu-id="1f459-138">Aunque los documentos producidos por las aplicaciones hospedadas están esperando para ser impresos en un dispositivo conectado a la red, estos se guardan en el almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="1f459-138">While documents that are produced by the hosted applications are waiting to be printed on a network-connected device, they are stored in Azure blob storage.</span></span> <span data-ttu-id="1f459-139">El [Agente de rutas de documentos](install-document-routing-agent.md) utiliza la autenticación de Azure para establecer un canal seguro para los servicios de Azure.</span><span class="sxs-lookup"><span data-stu-id="1f459-139">The [Document Routing Agent](install-document-routing-agent.md) uses Azure authentication to establish a secure channel to the Azure services.</span></span>

<span data-ttu-id="1f459-140">**Secuencia de ejecuciones**</span><span class="sxs-lookup"><span data-stu-id="1f459-140">**Execution sequence**</span></span>

1. <span data-ttu-id="1f459-141">El informe es generado por Microsoft SQL Server Reporting Services (SSRS) y almacenado en el almacenamiento de blobs de Azure.</span><span class="sxs-lookup"><span data-stu-id="1f459-141">The report is generated by Microsoft SQL Server Reporting Services (SSRS) and stored in Azure blob storage.</span></span> <span data-ttu-id="1f459-142">La configuración de la impresora adjunta se almacena junto con el documento.</span><span class="sxs-lookup"><span data-stu-id="1f459-142">Attached printer settings are stored together with the document.</span></span>
2. <span data-ttu-id="1f459-143">El Agente de rutas de documentos consulta la cola de Azure Service Bus para los trabajos activos.</span><span class="sxs-lookup"><span data-stu-id="1f459-143">The Document Routing Agent queries the Azure Service Bus queue for active jobs.</span></span>
3. <span data-ttu-id="1f459-144">El documento es descargado por el Agente de rutas de documentos y se pone en la cola de la impresora de red.</span><span class="sxs-lookup"><span data-stu-id="1f459-144">The document is downloaded by the Document Routing Agent and spooled to the network printer.</span></span>

<span data-ttu-id="1f459-145">La solución basada en cliente permite a los clientes administrar la escala de sus necesidades de impresión.</span><span class="sxs-lookup"><span data-stu-id="1f459-145">The client-based solution lets customers manage the scale of their printing needs.</span></span> <span data-ttu-id="1f459-146">Los clientes que tengan cargas de trabajo de impresión de gran volumen pueden instalar muchos Agentes de rutas de documentos para aumentar el número de operaciones de impresión simultáneas.</span><span class="sxs-lookup"><span data-stu-id="1f459-146">Customers who have heavy-volume printing workloads can install many Document Routing Agents to increase the number of concurrent printing operations.</span></span> <span data-ttu-id="1f459-147">De manera alternativa, algunos clientes requieren muy pocas instalaciones del Agente de rutas de documentos para administrar sus necesidades de impresión anticipadas.</span><span class="sxs-lookup"><span data-stu-id="1f459-147">Alternatively, some customers require very few installations of the Document Routing Agent to handle their anticipated printing needs.</span></span>

### <a name="service-components-for-network-printing"></a><span data-ttu-id="1f459-148">Componentes de servicio para la impresión de red</span><span class="sxs-lookup"><span data-stu-id="1f459-148">Service components for network printing</span></span>

<span data-ttu-id="1f459-149">En el siguiente diagrama se muestran los componentes básicos que ayudan con las operaciones de impresión de red.</span><span class="sxs-lookup"><span data-stu-id="1f459-149">The following diagram shows the basic components that help support network printing operations.</span></span>

<span data-ttu-id="1f459-150">[![componentes de servicio para la impresión de red\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)</span><span class="sxs-lookup"><span data-stu-id="1f459-150">[![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)</span></span>

<span data-ttu-id="1f459-151">Tenga en cuenta que una sola impresora se puede registrar con varios agentes de ruta de documento.</span><span class="sxs-lookup"><span data-stu-id="1f459-151">Note that a single printer can be registered with multiple Document Routing Agents.</span></span> <span data-ttu-id="1f459-152">Para resolver las preferencias de la impresora, el servicio hospedado utiliza la ruta de red que identifica de manera única a cada impresora de red.</span><span class="sxs-lookup"><span data-stu-id="1f459-152">To resolve the printer preferences, the hosted service uses the network path that uniquely identifies every network printer.</span></span> <span data-ttu-id="1f459-153">Como resultado, incluso cuando una impresora es registrada por varios clientes, aparece como única selección en la lista de impresoras disponibles en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f459-153">As a result, even when a printer is registered by multiple clients, it appears as a single selection in the list of printers available in applications.</span></span>