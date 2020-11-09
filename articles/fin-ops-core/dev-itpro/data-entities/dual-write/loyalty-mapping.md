---
title: Tarjetas de fidelización de clientes y puntos de recompensa
description: Este tema describe la integración de datos sobre tarjetas de fidelización de clientes y puntos de recompensa entre aplicaciones Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998023"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="c641d-103">Tarjetas de fidelización de clientes y puntos de recompensa</span><span class="sxs-lookup"><span data-stu-id="c641d-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="c641d-104">Las empresas clasifican a los clientes y brindan servicios sofisticados, basados en los patrones de compras y gastos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="c641d-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="c641d-105">En el conjunto de aplicaciones Microsoft Dynamics 365, Dynamics 365 Commerce tiene la infraestructura y las funciones para facilitar y gestionar tarjetas de fidelización de clientes, puntos de recompensa, precios basados en lealtad y experiencias de compra basadas en recompensas.</span><span class="sxs-lookup"><span data-stu-id="c641d-105">In the Microsoft Dynamics 365 suite of applications, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="c641d-106">Cuando los datos sobre tarjetas de fidelización de clientes y puntos de recompensa en Commerce se sincronizan con Common Data Service, las aplicaciones basadas en modelos en Dynamics 365 pueden usar esos datos.</span><span class="sxs-lookup"><span data-stu-id="c641d-106">When data about customer loyalty cards and reward points in Commerce is synced to Common Data service, model-driven apps in Dynamics 365 can use that data.</span></span> <span data-ttu-id="c641d-107">Por ejemplo, los usuarios de Dynamics 365 Customer Service pueden usar los datos para proporcionar los mismos servicios sofisticados a través del servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="c641d-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="c641d-108">Plantillas</span><span class="sxs-lookup"><span data-stu-id="c641d-108">Templates</span></span>

| <span data-ttu-id="c641d-109">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c641d-109">Finance and Operations apps</span></span> | <span data-ttu-id="c641d-110">Aplicaciones basadas en modelos en Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c641d-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="c641d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c641d-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="c641d-112">Tarjeta de fidelización</span><span class="sxs-lookup"><span data-stu-id="c641d-112">Loyalty card</span></span>                | <span data-ttu-id="c641d-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="c641d-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="c641d-114">Esta plantilla sincroniza información sobre las tarjetas de fidelización del cliente.</span><span class="sxs-lookup"><span data-stu-id="c641d-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="c641d-115">Puntos de recompensa de fidelización</span><span class="sxs-lookup"><span data-stu-id="c641d-115">Loyalty reward points</span></span>       | <span data-ttu-id="c641d-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="c641d-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="c641d-117">Esta plantilla sincroniza información sobre los puntos de recompensa del cliente.</span><span class="sxs-lookup"><span data-stu-id="c641d-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
