---
title: Información general del entorno de evaluación de Dynamics 365 Commerce
description: Este tema ofrece una visión general del entorno de evaluación de Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 25c0574e8d4502bcb846fba0ddf913d81eded87b
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599775"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a><span data-ttu-id="ccb4a-103">Información general del entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-103">Dynamics 365 Commerce evaluation environment overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ccb4a-104">Este tema ofrece una visión general del entorno de evaluación de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

> [!NOTE]
> <span data-ttu-id="ccb4a-105">Los entornos de evaluación de Commerce no suelen estar disponibles y se conceden a socios y clientes por solicitud.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-105">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="ccb4a-106">Para obtener más información, póngase en contacto con su partner de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-106">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="ccb4a-107">Información general</span><span class="sxs-lookup"><span data-stu-id="ccb4a-107">Overview</span></span>

<span data-ttu-id="ccb4a-108">El entorno de evaluación de Commerce es un entorno integral opcional de Dynamics 365 Commerce que permite a partners y posibles clientes probar el producto de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-108">The Commerce evaluation environment is an optional end-to-end environment of Dynamics 365 Commerce that lets partners and potential customers try out the Commerce product.</span></span>

<span data-ttu-id="ccb4a-109">Los entornos de evaluación están parcialmente preconfigurados para reducir los pasos necesarios posteriores al aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-109">Evaluation environments are partially preconfigured to reduce the required post-provisioning steps.</span></span>

<span data-ttu-id="ccb4a-110">Además de algunas limitaciones secundarias que no afectan a las características o a la funcionalidad, el entorno de evaluación de Commerce proporciona la experiencia completa de Commerce, y los clientes y partners de implementación pueden usarlo para evaluar el producto, proporcionar comentarios y realizar análisis de idoneidad/lagunas.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-110">Aside from some minor limitations that don't affect features or functionality, the Commerce evaluation environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-evaluation-environment"></a><span data-ttu-id="ccb4a-111">Limitaciones del entorno de evaluación de Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-111">Limitations of the Commerce evaluation environment</span></span>

<span data-ttu-id="ccb4a-112">Aunque el entorno de evaluación de Commerce proporciona el conjunto completo de características y funcionalidades de Commerce, hay algunas limitaciones secundarias:</span><span class="sxs-lookup"><span data-stu-id="ccb4a-112">Although the Commerce evaluation environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="ccb4a-113">Aunque el entorno de evaluación de Commerce en sí no tiene limitaciones geográficas, los componentes del entorno, como el Retail Cloud Scale Unit (RCSU) y las aplicaciones de comercio electrónico, solo se deben aprovisionar en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-113">Although the Commerce evaluation environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, should be provisioned only in the United States.</span></span>
- <span data-ttu-id="ccb4a-114">El entorno de evaluación de Commerce tiene un límite de tiempo de uso de 30 días a partir de la fecha de aprovisionamiento de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-114">Use of the Commerce evaluation environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="ccb4a-115">El entorno de evaluación de Commerce solo se puede implementar e inicializar correctamente en un entorno que utiliza la topología de demostración, donde todos los componentes de un entorno se implementan en una sola máquina virtual hospedada en la nube (VM).</span><span class="sxs-lookup"><span data-stu-id="ccb4a-115">The Commerce evaluation environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed on a single cloud-hosted virtual machine (VM).</span></span> <span data-ttu-id="ccb4a-116">La limitación principal de esta topología es el número de usuarios simultáneos que puede admitir el entorno.</span><span class="sxs-lookup"><span data-stu-id="ccb4a-116">The main limitation of this topology is the number of concurrent users that the environment can support.</span></span>

## <a name="get-started"></a><span data-ttu-id="ccb4a-117">Introducción</span><span class="sxs-lookup"><span data-stu-id="ccb4a-117">Get started</span></span>

<span data-ttu-id="ccb4a-118">Para aprovisionar el entorno de evaluación de Commerce, consulte [Aprovisionar un entorno de evaluación de Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="ccb4a-118">To provision the Commerce evaluation environment, see [Provision a Commerce evaluation environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ccb4a-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ccb4a-119">Additional resources</span></span>

[<span data-ttu-id="ccb4a-120">Aprovisionar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-120">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="ccb4a-121">Configurar un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-121">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="ccb4a-122">Configurar BOPIS en un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-122">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="ccb4a-123">Configurar características opcionales para un entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-123">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="ccb4a-124">Preguntas más frecuentes sobre el entorno de evaluación de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="ccb4a-124">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)
