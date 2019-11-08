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
ms.openlocfilehash: d70bce4e47c05a7974c1b974fdca17682e5370aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550866"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="d9054-103">Integración de datos casi en tiempo real con Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d9054-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="d9054-104">En el mundo digital actual, los ecosistemas de negocio usan las aplicaciones de Microsoft Dynamics 365 como una unidad.</span><span class="sxs-lookup"><span data-stu-id="d9054-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="d9054-105">Dado que los datos de personas, clientes, operaciones y de dispositivos de Internet de las cosas (IoT) fluyen en un origen, existe una oportunidad para los bucles de retroalimentación digitales.</span><span class="sxs-lookup"><span data-stu-id="d9054-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="d9054-106">Para efectuar esta experiencia, la integración entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 es esencial.</span><span class="sxs-lookup"><span data-stu-id="d9054-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="d9054-107">Algunas aplicaciones se construyen sobre Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d9054-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="d9054-108">La integración entre los datos de aplicaciones de Finance and Operations y Common Data Service permite a otras aplicaciones comunicarse de forma coherente y fluida con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d9054-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="d9054-109">Las aplicaciones de Finance and Operations y Common Data Service proporcionan sincronización de los datos casi en tiempo real entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 mediante un marco de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="d9054-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="d9054-110">La cobertura es amplia y abarca 28 áreas expuestas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d9054-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="d9054-111">El objetivo es proporcionar una sola experiencia de Dynamics 365 al usuario a través de flujos de datos fluidos que conectan los procesos empresariales entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d9054-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagrama de visión general de la arquitectura](media/dual-write-overview.jpg)

<span data-ttu-id="d9054-113">Las propuestas de valores siguientes están disponibles para los clientes:</span><span class="sxs-lookup"><span data-stu-id="d9054-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="d9054-114">Jerarquía organizativa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d9054-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="d9054-115">Concepto de empresa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d9054-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="d9054-116">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="d9054-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="d9054-117">Maestro de proveedores integrado</span><span class="sxs-lookup"><span data-stu-id="d9054-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="d9054-118">Maestro de productos unificado</span><span class="sxs-lookup"><span data-stu-id="d9054-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="d9054-119">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="d9054-119">System requirements</span></span>

<span data-ttu-id="d9054-120">Los flujos de datos sincrónicos, bidireccionales, casi en tiempo real requieren las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9054-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="d9054-121">Microsoft Dynamics 365 for Finance and Operations versión 10.0.4 (julio de 2019) con la actualización de plataforma 28 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d9054-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="d9054-122">Microsoft Dynamics 365 for Customer Engagement, versión de plataforam 9.1 (4.2) o posterior</span><span class="sxs-lookup"><span data-stu-id="d9054-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="d9054-123">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="d9054-123">Setup instructions</span></span>

<span data-ttu-id="d9054-124">Siga estos pasos para configurar la integración entre aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d9054-124">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="d9054-125">Para la configuración del sistema de escritura dual, consulte [guía paso a paso](https://aka.ms/dualwrite-docs) en Anuncio de la vista previa de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="d9054-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="d9054-126">Descargue e instale la solución en el grupo de Yammer [Integración de Finance and Operations, Common Data Service y Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="d9054-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="d9054-127">El paquete contiene cinco soluciones:</span><span class="sxs-lookup"><span data-stu-id="d9054-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="d9054-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="d9054-128">Dynamics365Company</span></span>
    + <span data-ttu-id="d9054-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="d9054-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="d9054-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="d9054-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="d9054-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="d9054-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="d9054-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="d9054-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="d9054-133">Siga el orden de ejecución para [sincronizar los datos de referencia iniciales](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="d9054-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="d9054-134">Si encuentra problemas de sincronización de escritura dual, consulte [Guía de solución de problemas para la integración de datos](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="d9054-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9054-135">No puede ejecutar la escritura dual y [Cliente potencial a cliente](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="d9054-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="d9054-136">Si ejecuta la solución Cliente potencial a cliente, debe desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="d9054-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="d9054-137">También debe deshabilitar las plantillas de escritura dual de cliente y proveedor que forman parte de la solución Cliente potencial a cliente.</span><span class="sxs-lookup"><span data-stu-id="d9054-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
