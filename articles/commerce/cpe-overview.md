---
title: Información general del entorno de vista previa de Commerce
description: Este tema ofrece una visión general del entorno de vista previa de Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
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
ms.openlocfilehash: 901583afde4739be5313fa129ff0e52f11326881
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906079"
---
# <a name="commerce-preview-environment-overview"></a><span data-ttu-id="c2762-103">Información general del entorno de vista previa de Commerce</span><span class="sxs-lookup"><span data-stu-id="c2762-103">Commerce preview environment overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="c2762-104">Este tema ofrece una visión general del entorno de vista previa de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c2762-104">This topic gives an overview of the Microsoft Dynamics 365 Commerce preview environment.</span></span>

## <a name="overview"></a><span data-ttu-id="c2762-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="c2762-105">Overview</span></span>

<span data-ttu-id="c2762-106">El entorno de vista previa de Commerce es un entorno de vista previa opcional de extremo a extremo de Dynamics 365 Commerce que permite a los clientes potenciales probar el producto de Commerce antes de su lanzamiento general al público.</span><span class="sxs-lookup"><span data-stu-id="c2762-106">The Commerce preview environment is an optional end-to-end preview environment of Dynamics 365 Commerce that lets potential customers try out the Commerce product before its general release to the public.</span></span>

<span data-ttu-id="c2762-107">Además de algunas limitaciones menores que no afectan las características o la funcionalidad, el entorno de vista previa de Commerce proporciona la experiencia completa de Commerce, y los clientes y socios de implementación pueden usarlo para evaluar el producto, proporcionar comentarios y hacer análisis de ajuste / brecha.</span><span class="sxs-lookup"><span data-stu-id="c2762-107">Aside from some minor limitations that don't affect features or functionality, the Commerce preview environment provides the complete Commerce experience, and can be used by customers and implementation partners to evaluate the product, provide feedback, and do fit/gap analysis.</span></span>

## <a name="limitations-of-the-commerce-preview-environment"></a><span data-ttu-id="c2762-108">Limitaciones del entorno de vista previa de Commerce</span><span class="sxs-lookup"><span data-stu-id="c2762-108">Limitations of the Commerce preview environment</span></span>

<span data-ttu-id="c2762-109">Aunque el entorno de vista previa de Commerce proporciona el conjunto completo de características y funcionalidades de Commerce, existen algunas limitaciones menores:</span><span class="sxs-lookup"><span data-stu-id="c2762-109">Although the Commerce preview environment provides the full set of Commerce features and functionality, there are some minor limitations:</span></span>

- <span data-ttu-id="c2762-110">Aunque el entorno de vista previa de Commerce en sí no tiene limitaciones geográficas, los componentes del entorno, como el Retail Cloud Scale Unit (RCSU) y las aplicaciones de comercio electrónico, solo se pueden aprovisionar en los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c2762-110">Although the Commerce preview environment itself has no geographical limitations, components of the environment, such as the Retail Cloud Scale Unit (RCSU) and e-Commerce applications, can be provisioned only in the United States.</span></span>
- <span data-ttu-id="c2762-111">El entorno de vista previa de Commerce tiene un límite de tiempo de uso de 30 días a partir de la fecha de aprovisionamiento de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c2762-111">Use of the Commerce preview environment is limited to 30 days from the date when e-Commerce is provisioned.</span></span>
- <span data-ttu-id="c2762-112">El entorno de vista previa de Commerce se puede implementar e inicializar con éxito solo en un entorno que utiliza la topología de demostración, donde todos los componentes de un entorno se implementan en una sola máquina virtual (VM).</span><span class="sxs-lookup"><span data-stu-id="c2762-112">The Commerce preview environment can be successfully deployed and initialized only in an environment that uses the demo topology, where all components of an environment are deployed in a single virtual machine (VM).</span></span> <span data-ttu-id="c2762-113">La principal limitación de esta topología de OneBox VM es la cantidad de usuarios simultáneos que el entorno de vista previa puede admitir.</span><span class="sxs-lookup"><span data-stu-id="c2762-113">The main limitation of this OneBox VM topology is the number of concurrent users that the preview environment can support.</span></span>
- <span data-ttu-id="c2762-114">El entorno de vista previa de Commerce solo se puede evaluar hasta la disponibilidad general (GA) del producto de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c2762-114">The Commerce preview environment can be evaluated only until the general availability (GA) of the Commerce product.</span></span> <span data-ttu-id="c2762-115">Nuevos entornos de demostración estarán disponibles después de GA.</span><span class="sxs-lookup"><span data-stu-id="c2762-115">New demo environments will be available after GA.</span></span>

## <a name="get-started"></a><span data-ttu-id="c2762-116">Introducción</span><span class="sxs-lookup"><span data-stu-id="c2762-116">Get started</span></span>

<span data-ttu-id="c2762-117">Para aprovisionar el entorno de vista previa de Commerce, vea [Provisión de un entorno de vista previa de Commerce](provisioning-guide.md).</span><span class="sxs-lookup"><span data-stu-id="c2762-117">To provision the Commerce preview environment, see [Provision a Commerce preview environment](provisioning-guide.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2762-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c2762-118">Additional resources</span></span>

[<span data-ttu-id="c2762-119">Aprovisionar un entorno de vista previa de Commerce</span><span class="sxs-lookup"><span data-stu-id="c2762-119">Provision a Commerce preview environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="c2762-120">Configurar un entorno de vista previa de Commerce</span><span class="sxs-lookup"><span data-stu-id="c2762-120">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="c2762-121">Configurar características opcionales para un entorno de vista previa de Commerce</span><span class="sxs-lookup"><span data-stu-id="c2762-121">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="c2762-122">Preguntas más frecuentes del entorno de vista previa de Commerce</span><span class="sxs-lookup"><span data-stu-id="c2762-122">Commerce preview environment FAQ</span></span>](cpe-faq.md)