---
title: Integración casi en tiempo real entre Finance and Operations y Common Data Service
description: Este tema proporciona una visión general de la integración entre Microsoft Dynamics 365 for Finance and Operations y Common Data Service.
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797237"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a><span data-ttu-id="bccf5-103">Integración casi en tiempo real entre Finance and Operations y Common Data Service</span><span class="sxs-lookup"><span data-stu-id="bccf5-103">Near-real-time data integration between Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="bccf5-104">En el mundo digital actual, los ecosistemas de negocio usan el conjunto Microsoft Dynamics 365 como una unidad.</span><span class="sxs-lookup"><span data-stu-id="bccf5-104">In the current digital world, business ecosystems use the Microsoft Dynamics 365 suite as a whole.</span></span> <span data-ttu-id="bccf5-105">Dado que los datos de personas, clientes, operaciones y de dispositivos de Internet de las cosas (IoT) fluyen en un origen, existe una oportunidad para los bucles de retroalimentación digitales.</span><span class="sxs-lookup"><span data-stu-id="bccf5-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="bccf5-106">Para efectuar esta experiencia, la integración entre lsa aplicaciones Dynamics 365 for Finance and Operations y Dynamics 365 para Customer Engagement es esencial.</span><span class="sxs-lookup"><span data-stu-id="bccf5-106">To achieve this experience, integration between Dynamics 365 for Finance and Operations and Dynamics 365 for Customer Engagement applications is essential.</span></span> <span data-ttu-id="bccf5-107">Las aplicaciones de Customer Engagement se construyen sobre Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bccf5-107">Customer Engagement applications are built on top of Common Data Service.</span></span> <span data-ttu-id="bccf5-108">La integración entre los datos de Finance and Operations y Common Data Service permite a las aplicaciones de Customer Engagement comunicarse de forma coherente y fluida con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bccf5-108">Integration between Finance and Operations data with Common Data Service lets Customer Engagement applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="bccf5-109">Finance and Operations y Common Data Service proporcionan sincronización de los datos casi en tiempo real entre las aplicaciones de Finance and Operations y Customer Engagement mediante un marco de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="bccf5-109">Finance and Operations and Common Data Service provide near-real-time data synchronization between Finance and Operations and Customer Engagement applications via a dual-write framework.</span></span> <span data-ttu-id="bccf5-110">La cobertura es amplia y abarca 28 áreas expuestas de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bccf5-110">The coverage is broad and spans 28 surface areas of Finance and Operations.</span></span> <span data-ttu-id="bccf5-111">El objetivo es proporcionar una sola experiencia de Dynamics 365 al usuario a través de flujos de datos fluidos que conectan los procesos empresariales entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bccf5-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagrama de visión general de la arquitectura](media/dual-write-overview.jpg)

<span data-ttu-id="bccf5-113">Las propuestas de valores siguientes están disponibles para los clientes:</span><span class="sxs-lookup"><span data-stu-id="bccf5-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="bccf5-114">Jerarquía organizativa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="bccf5-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="bccf5-115">Concepto de empresa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="bccf5-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="bccf5-116">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="bccf5-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="bccf5-117">Maestro de proveedores integrado</span><span class="sxs-lookup"><span data-stu-id="bccf5-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="bccf5-118">Maestro de productos unificado</span><span class="sxs-lookup"><span data-stu-id="bccf5-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="bccf5-119">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="bccf5-119">System requirements</span></span>

<span data-ttu-id="bccf5-120">Los flujos de datos sincrónicos, bidireccionales, casi en tiempo real requieren las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bccf5-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="bccf5-121">Microsoft Dynamics 365 for Finance and Operations versión 10.0.4 (julio de 2019) con la actualización de plataforma 28 o posterior.</span><span class="sxs-lookup"><span data-stu-id="bccf5-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="bccf5-122">Microsoft Dynamics 365 for Customer Engagement, versión de plataforam 9.1 (4.2) o posterior</span><span class="sxs-lookup"><span data-stu-id="bccf5-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="bccf5-123">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="bccf5-123">Setup instructions</span></span>

<span data-ttu-id="bccf5-124">Siga estos pasos para configurar la integración entre Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="bccf5-124">Follow these steps to set up integration between Finance and Operations and Common Data Service.</span></span>
    
1. <span data-ttu-id="bccf5-125">Para la configuración del sistema de escritura dual, consulte [guía paso a paso](https://aka.ms/dualwrite-docs) en Anuncio de la vista previa de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="bccf5-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="bccf5-126">Descargue e instale la solución en el grupo de Yammer [Integración de Finance and Operations, Common Data Service y Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="bccf5-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="bccf5-127">El paquete contiene cinco soluciones:</span><span class="sxs-lookup"><span data-stu-id="bccf5-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="bccf5-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="bccf5-128">Dynamics365Company</span></span>
    + <span data-ttu-id="bccf5-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="bccf5-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="bccf5-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="bccf5-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="bccf5-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="bccf5-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="bccf5-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="bccf5-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="bccf5-133">Siga el orden de ejecución para [sincronizar los datos de referencia iniciales](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="bccf5-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="bccf5-134">Si encuentra problemas de sincronización de escritura dual, consulte [Guía de solución de problemas para la integración de datos](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="bccf5-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bccf5-135">No puede ejecutar la escritura dual y [Cliente potencial a cliente](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="bccf5-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="bccf5-136">Si ejecuta la solución Cliente potencial a cliente, debe desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="bccf5-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="bccf5-137">También debe deshabilitar las plantillas de escritura dual de cliente y proveedor que forman parte de la solución Cliente potencial a cliente.</span><span class="sxs-lookup"><span data-stu-id="bccf5-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
