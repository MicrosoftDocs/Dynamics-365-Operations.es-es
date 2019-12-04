---
title: Integración de datos casi en tiempo real con Common Data Service
description: Este tema proporciona una visión general de la integración entre Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 11a5792c9c039eb76337309ef2fdb2b994ce191a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772396"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="ac5c3-103">Integración de datos casi en tiempo real con Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac5c3-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ac5c3-104">En el mundo digital actual, los ecosistemas de negocio usan las aplicaciones de Microsoft Dynamics 365 como una unidad.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="ac5c3-105">Dado que los datos de personas, clientes, operaciones y de dispositivos de Internet de las cosas (IoT) fluyen en un origen, existe una oportunidad para los bucles de retroalimentación digitales.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="ac5c3-106">Para efectuar esta experiencia, la integración entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 es esencial.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="ac5c3-107">Algunas aplicaciones se construyen sobre Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="ac5c3-108">La integración entre los datos de aplicaciones de Finance and Operations y Common Data Service permite a otras aplicaciones comunicarse de forma coherente y fluida con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="ac5c3-109">Las aplicaciones de Finance and Operations y Common Data Service proporcionan sincronización de los datos casi en tiempo real entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 mediante un marco de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="ac5c3-110">La cobertura es amplia y abarca 28 áreas expuestas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="ac5c3-111">El objetivo es proporcionar una sola experiencia de Dynamics 365 al usuario a través de flujos de datos fluidos que conectan los procesos empresariales entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagrama de visión general de la arquitectura](media/dual-write-overview.jpg)

<span data-ttu-id="ac5c3-113">Las propuestas de valores siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="ac5c3-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="ac5c3-114">Jerarquía organizativa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac5c3-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="ac5c3-115">Concepto de empresa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac5c3-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="ac5c3-116">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="ac5c3-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="ac5c3-117">Libro mayor integrado</span><span class="sxs-lookup"><span data-stu-id="ac5c3-117">Integrated ledger</span></span>](dual-write-ledger.md)
+ [<span data-ttu-id="ac5c3-118">Experiencia unificada del producto</span><span class="sxs-lookup"><span data-stu-id="ac5c3-118">Unified product experience</span></span>](dual-write-product.md)
+ [<span data-ttu-id="ac5c3-119">Maestro de proveedores integrado</span><span class="sxs-lookup"><span data-stu-id="ac5c3-119">Integrated vendor master</span></span>](dual-write-vendor.md)
+ [<span data-ttu-id="ac5c3-120">Sitios y almacenes integrados</span><span class="sxs-lookup"><span data-stu-id="ac5c3-120">Integrated sites and warehouses</span></span>](dual-write-sites-and-warehouses.md)
+ [<span data-ttu-id="ac5c3-121">Datos fiscales maestros integrados</span><span class="sxs-lookup"><span data-stu-id="ac5c3-121">Integrated tax master</span></span>](dual-write-tax.md)

## <a name="system-requirements"></a><span data-ttu-id="ac5c3-122">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="ac5c3-122">System requirements</span></span>

<span data-ttu-id="ac5c3-123">Los flujos de datos sincrónicos, bidireccionales, casi en tiempo real requieren las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac5c3-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="ac5c3-124">Microsoft Dynamics 365 for Finance and Operations versión 10.0.4 (julio de 2019) con la actualización de plataforma 28 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="ac5c3-125">Microsoft Dynamics 365 for Customer Engagement, versión de plataforam 9.1 (4.2) o posterior</span><span class="sxs-lookup"><span data-stu-id="ac5c3-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="ac5c3-126">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="ac5c3-126">Setup instructions</span></span>

<span data-ttu-id="ac5c3-127">Siga estos pasos para configurar la integración entre aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="ac5c3-128">Para la configuración del sistema de escritura dual, consulte [guía paso a paso](https://aka.ms/dualwrite-docs) en Anuncio de la vista previa de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="ac5c3-129">Descargue e instale la solución en el grupo de Yammer [Integración de Finance and Operations, Common Data Service y Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="ac5c3-129">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="ac5c3-130">El paquete contiene cinco soluciones:</span><span class="sxs-lookup"><span data-stu-id="ac5c3-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="ac5c3-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="ac5c3-131">Dynamics365Company</span></span>
    + <span data-ttu-id="ac5c3-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="ac5c3-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="ac5c3-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="ac5c3-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="ac5c3-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="ac5c3-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="ac5c3-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="ac5c3-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="ac5c3-136">Siga el orden de ejecución para [sincronizar los datos de referencia iniciales](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="ac5c3-136">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="ac5c3-137">Si encuentra problemas de sincronización de escritura dual, consulte [Guía de solución de problemas para la integración de datos](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ac5c3-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac5c3-138">No puede ejecutar la escritura dual y [Cliente potencial a cliente](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-138">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="ac5c3-139">Si ejecuta la solución Cliente potencial a cliente, debe desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="ac5c3-140">También debe deshabilitar las plantillas de escritura dual de cliente y proveedor que forman parte de la solución Cliente potencial a cliente.</span><span class="sxs-lookup"><span data-stu-id="ac5c3-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
