---
title: Tarjetas de fidelización de clientes y puntos de recompensa
description: Este tema describe la integración de datos sobre tarjetas de fidelización de clientes y puntos de recompensa entre aplicaciones en escritura dual.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d2c3845c1a7371d9e992495246e8dd0eb8631020
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747996"
---
# <a name="customer-loyalty-cards-and-reward-points"></a><span data-ttu-id="c7aaf-103">Tarjetas de fidelización de clientes y puntos de recompensa</span><span class="sxs-lookup"><span data-stu-id="c7aaf-103">Customer loyalty cards and reward points</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c7aaf-104">Las empresas clasifican a los clientes y brindan servicios sofisticados, basados en los patrones de compras y gastos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-104">Businesses classify customers and provide sophisticated services, based on customer shopping and spending patterns.</span></span> <span data-ttu-id="c7aaf-105">Por ejemplo, Dynamics 365 Commerce, tiene la infraestructura y las funciones para facilitar y gestionar tarjetas de fidelización de clientes, puntos de recompensa, precios basados en lealtad y experiencias de compra basadas en recompensas.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-105">For example, Dynamics 365 Commerce has the infrastructure and functions to facilitate and handle customer loyalty cards, reward points, loyalty-based pricing, and rewards-based shopping experiences.</span></span> <span data-ttu-id="c7aaf-106">Cuando los datos sobre tarjetas de fidelización de clientes y puntos de recompensa en Commerce se sincronizan con Dataverse, las aplicaciones Customer Engagement pueden usar esos datos.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-106">When data about customer loyalty cards and reward points in Commerce is synced to Dataverse, customer engagement apps can use that data.</span></span> <span data-ttu-id="c7aaf-107">Por ejemplo, los usuarios de Dynamics 365 Customer Service pueden usar los datos para proporcionar los mismos servicios sofisticados a través del servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-107">For example, Dynamics 365 Customer Service users can use the data to provide the same sophisticated services through the help desk.</span></span>

## <a name="templates"></a><span data-ttu-id="c7aaf-108">Plantillas</span><span class="sxs-lookup"><span data-stu-id="c7aaf-108">Templates</span></span>

| <span data-ttu-id="c7aaf-109">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c7aaf-109">Finance and Operations apps</span></span> | <span data-ttu-id="c7aaf-110">Aplicaciones basadas en modelos en Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c7aaf-110">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="c7aaf-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7aaf-111">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="c7aaf-112">Tarjeta de fidelización</span><span class="sxs-lookup"><span data-stu-id="c7aaf-112">Loyalty card</span></span>                | <span data-ttu-id="c7aaf-113">msdyn\_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="c7aaf-113">msdyn\_loyaltycards</span></span>               | <span data-ttu-id="c7aaf-114">Esta plantilla sincroniza información sobre las tarjetas de fidelización del cliente.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-114">This template syncs information about customer loyalty cards.</span></span> |
| <span data-ttu-id="c7aaf-115">Puntos de recompensa de fidelización</span><span class="sxs-lookup"><span data-stu-id="c7aaf-115">Loyalty reward points</span></span>       | <span data-ttu-id="c7aaf-116">msdyn\_loyaltyrewardpoints</span><span class="sxs-lookup"><span data-stu-id="c7aaf-116">msdyn\_loyaltyrewardpoints</span></span>        | <span data-ttu-id="c7aaf-117">Esta plantilla sincroniza información sobre los puntos de recompensa del cliente.</span><span class="sxs-lookup"><span data-stu-id="c7aaf-117">This template syncs information about customer reward points.</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]