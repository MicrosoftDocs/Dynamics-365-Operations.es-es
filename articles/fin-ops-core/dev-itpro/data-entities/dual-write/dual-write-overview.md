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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020002"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="3778b-103">Integración de datos casi en tiempo real con Common Data Service</span><span class="sxs-lookup"><span data-stu-id="3778b-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="3778b-104">En el mundo digital actual, los ecosistemas de negocio usan las aplicaciones de Microsoft Dynamics 365 como una unidad.</span><span class="sxs-lookup"><span data-stu-id="3778b-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="3778b-105">Dado que los datos de personas, clientes, operaciones y de dispositivos de Internet de las cosas (IoT) fluyen en un origen, existe una oportunidad para los bucles de retroalimentación digitales.</span><span class="sxs-lookup"><span data-stu-id="3778b-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="3778b-106">Para efectuar esta experiencia, la integración entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 es esencial.</span><span class="sxs-lookup"><span data-stu-id="3778b-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="3778b-107">Algunas aplicaciones se construyen sobre Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3778b-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="3778b-108">La integración entre los datos de las aplicaciones de Finance and Operations con Common Data Service permite que otras aplicaciones se comuniquen de manera coherente y fluida con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3778b-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="3778b-109">Las aplicaciones de Finance and Operations y Common Data Service proporcionan sincronización de los datos casi en tiempo real entre las aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 mediante un marco de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="3778b-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="3778b-110">La cobertura es amplia y abarca 28 áreas expuestas de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3778b-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="3778b-111">El objetivo es proporcionar una sola experiencia de Dynamics 365 al usuario a través de flujos de datos fluidos que conectan los procesos empresariales entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3778b-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagrama de visión general de la arquitectura](media/dual-write-overview.jpg)

<span data-ttu-id="3778b-113">Las propuestas de valores siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="3778b-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="3778b-114">Jerarquía organizativa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="3778b-114">Organization hierarchy in Common Data Service</span></span>](organization-mapping.md)
+ [<span data-ttu-id="3778b-115">Concepto de empresa en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="3778b-115">Company concept in Common Data Service</span></span>](company-data.md)
+ [<span data-ttu-id="3778b-116">Maestro de clientes integrado</span><span class="sxs-lookup"><span data-stu-id="3778b-116">Integrated customer master</span></span>](customer-mapping.md)
+ [<span data-ttu-id="3778b-117">Libro mayor integrado</span><span class="sxs-lookup"><span data-stu-id="3778b-117">Integrated ledger</span></span>](ledger-mapping.md)
+ [<span data-ttu-id="3778b-118">Experiencia unificada del producto</span><span class="sxs-lookup"><span data-stu-id="3778b-118">Unified product experience</span></span>](product-mapping.md)
+ [<span data-ttu-id="3778b-119">Maestro de proveedores integrado</span><span class="sxs-lookup"><span data-stu-id="3778b-119">Integrated vendor master</span></span>](vendor-mapping.md)
+ [<span data-ttu-id="3778b-120">Sitios y almacenes integrados</span><span class="sxs-lookup"><span data-stu-id="3778b-120">Integrated sites and warehouses</span></span>](sites-warehouses-mapping.md)
+ [<span data-ttu-id="3778b-121">Datos fiscales maestros integrados</span><span class="sxs-lookup"><span data-stu-id="3778b-121">Integrated tax master</span></span>](tax-mapping.md)

## <a name="system-requirements"></a><span data-ttu-id="3778b-122">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="3778b-122">System requirements</span></span>

<span data-ttu-id="3778b-123">Los flujos de datos sincrónicos, bidireccionales, casi en tiempo real requieren las versiones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3778b-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="3778b-124">Microsoft Dynamics 365 for Finance and Operations versión 10.0.4 (julio de 2019) con la actualización de plataforma 28 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3778b-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="3778b-125">Microsoft Dynamics 365 for Customer Engagement, versión de plataforam 9.1 (4.2) o posterior</span><span class="sxs-lookup"><span data-stu-id="3778b-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="3778b-126">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="3778b-126">Setup instructions</span></span>

<span data-ttu-id="3778b-127">Siga estos pasos para configurar la integración entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3778b-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="3778b-128">Para la configuración del sistema de escritura dual, consulte [guía paso a paso](https://aka.ms/dualwrite-docs) en Anuncio de la vista previa de escritura dual.</span><span class="sxs-lookup"><span data-stu-id="3778b-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="3778b-129">Descargue e instale la solución desde el grupo de Yammer [Fin Ops e integración de CDS / CE a través de doble escritura](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096).</span><span class="sxs-lookup"><span data-stu-id="3778b-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="3778b-130">El paquete contiene cinco soluciones:</span><span class="sxs-lookup"><span data-stu-id="3778b-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="3778b-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="3778b-131">Dynamics365Company</span></span>
    + <span data-ttu-id="3778b-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="3778b-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="3778b-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="3778b-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="3778b-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="3778b-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="3778b-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="3778b-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="3778b-136">Siga el orden de ejecución para [sincronizar los datos de referencia iniciales](initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="3778b-136">Follow the execution order for [synchronizing initial reference data](initial-sync.md).</span></span>
4. <span data-ttu-id="3778b-137">Si encuentra problemas de sincronización de escritura dual, consulte [Guía de solución de problemas para la integración de datos](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="3778b-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3778b-138">No puede ejecutar la escritura dual y [Cliente potencial a cliente](../../../../supply-chain/sales-marketing/prospect-to-cash.md) de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="3778b-138">You can’t run dual-write and [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) side-by-side.</span></span> <span data-ttu-id="3778b-139">Si ejecuta la solución Cliente potencial a cliente, debe desinstalarla.</span><span class="sxs-lookup"><span data-stu-id="3778b-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="3778b-140">También debe deshabilitar las plantillas de escritura dual de cliente y proveedor que forman parte de la solución Cliente potencial a cliente.</span><span class="sxs-lookup"><span data-stu-id="3778b-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>