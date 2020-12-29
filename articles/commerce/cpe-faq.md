---
title: Preguntas frecuentes sobre entorno de evaluación de Dynamics 365 Commerce
description: Este tema proporciona respuestas a preguntas frecuentes acerca del entorno de evaluación de Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 637714e28b9f8f4aa66e251e709d8f78bff2739d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415433"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="1f769-103">Preguntas frecuentes sobre entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1f769-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1f769-104">Este tema proporciona respuestas a preguntas frecuentes acerca del entorno de evaluación de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1f769-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="1f769-105">**¿Podemos usar el entorno de evaluación de Commerce como escaparate de comercio electrónico para los clientes que actualmente implementan Retail?**</span><span class="sxs-lookup"><span data-stu-id="1f769-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="1f769-106">N. º</span><span class="sxs-lookup"><span data-stu-id="1f769-106">No.</span></span> <span data-ttu-id="1f769-107">El entorno de evaluación de Commerce sirve solo para la evaluación.</span><span class="sxs-lookup"><span data-stu-id="1f769-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="1f769-108">Si necesita un entorno para un cliente que implementa Retail, póngase en contacto con Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f769-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="1f769-109">**¿Se puede usar el entorno de evaluación de Commerce para aprovisionar las características de comercio electrónico además de una aplicación / entorno existente que implementa Retail?**</span><span class="sxs-lookup"><span data-stu-id="1f769-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="1f769-110">No (mayormente).</span><span class="sxs-lookup"><span data-stu-id="1f769-110">No (mostly).</span></span> <span data-ttu-id="1f769-111">Los componentes de evaluación de Commerce están disponibles solo para entornos que coinciden con las configuraciones que se especifican en los requisitos previos y la guía de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="1f769-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="1f769-112">Además, los datos de demostración base requeridos no estarán disponibles en entornos implementados con una versión inicial anterior a 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="1f769-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="1f769-113">**¿Qué costos están involucrados en la implementación del entorno de evaluación de Commerce en Microsoft Azure vía Microsoft Dynamics Lifecycle Services (LCS)?**</span><span class="sxs-lookup"><span data-stu-id="1f769-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="1f769-114">Se alojará en su suscripción de Azure un entorno de demostración de sedes centrales de Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce (máquina virtual \[VM\]).</span><span class="sxs-lookup"><span data-stu-id="1f769-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="1f769-115">Puede usar la [Calculadora de precios de Azure ](https://azure.microsoft.com/pricing/calculator/) para estimar este coste.</span><span class="sxs-lookup"><span data-stu-id="1f769-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="1f769-116">Otros componentes como Commerce Scale Unit, el generador de sitios de Commerce y su sitio de comercio electrónico estarán disponibles como software como servicio (SaaS) y estarán alojados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1f769-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="1f769-117">**¿Qué geografías de Azure son compatibles actualmente para el entorno de evaluación de Commerce?**</span><span class="sxs-lookup"><span data-stu-id="1f769-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="1f769-118">El entorno de evaluación de Commerce solo se puede implementar en la geografía de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="1f769-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="1f769-119">**¿Existe un disco duro virtual descargable (VHD) que tenga la opción completa de máquina virtual (VM) OneBox?**</span><span class="sxs-lookup"><span data-stu-id="1f769-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="1f769-120">Dynamics 365 Commerce y Commerce Scale Unit son completamente software como servicio (SaaS) y deben estar alojados en la nube.</span><span class="sxs-lookup"><span data-stu-id="1f769-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="1f769-121">**¿Cuánto tiempo se puede usar el entorno de evaluación de Commerce?**</span><span class="sxs-lookup"><span data-stu-id="1f769-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="1f769-122">El entorno de evaluación de Commerce tiene un límite de tiempo de 30 días a partir de la fecha en que se aprovisionan componentes de SaaS como Commerce Scale Unit, el generador de sitios de Commerce y su sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="1f769-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="1f769-123">**¿Puedo extender el límite de tiempo para mi entorno de evaluación de Commerce?**</span><span class="sxs-lookup"><span data-stu-id="1f769-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="1f769-124">La extensión del límite de tiempo es una excepción a la norma y se considera caso por caso.</span><span class="sxs-lookup"><span data-stu-id="1f769-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="1f769-125">Póngase en contacto con su partner de Microsoft si requiere asistencia.</span><span class="sxs-lookup"><span data-stu-id="1f769-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1f769-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1f769-126">Additional resources</span></span>

[<span data-ttu-id="1f769-127">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1f769-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="1f769-128">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1f769-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="1f769-129">Configurar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1f769-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="1f769-130">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1f769-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="1f769-131">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="1f769-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)
