---
title: Características quitadas u obsoletas de Dynamics 365 Supply Chain Management
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Supply Chain Management.
author: kamaybac
manager: AnnBe
ms.date: 04/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7502cd16129431d41d152508fb3b49ff85a5a9f8
ms.sourcegitcommit: f1db998ecfccca660eb15cc2739b12c8463fa54d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "3331257"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a><span data-ttu-id="e194f-103">Características quitadas u obsoletas de Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e194f-103">Removed or deprecated features in Dynamics 365 Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e194f-104">Este tema se actualizará a medida que se documenten nuevas características quitadas o en desuso para Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e194f-104">This topic will be updated as new removed or deprecated features are documented for Dynamics 365 Supply Chain Management.</span></span>

- <span data-ttu-id="e194f-105">Una función *quitada* dejará de estar disponible en el producto.</span><span class="sxs-lookup"><span data-stu-id="e194f-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="e194f-106">Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="e194f-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="e194f-107">Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="e194f-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span>

> [!NOTE]
> <span data-ttu-id="e194f-108">La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="e194f-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="e194f-109">Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e194f-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a><span data-ttu-id="e194f-110">Funciones quitadas o en desuso en la versión 10.0.11 de Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="e194f-110">Features removed or deprecated in the Supply Chain Management 10.0.11 release</span></span>

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a><span data-ttu-id="e194f-111">Usar el motor de planificación maestro de Supply Chain Management para escenarios de distribución</span><span class="sxs-lookup"><span data-stu-id="e194f-111">Use of built-in Supply Chain Management master planning engine for distribution scenarios</span></span>

|   |  |
|------------|--------------------|
| <span data-ttu-id="e194f-112">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="e194f-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e194f-113">Para mejorar el rendimiento y minimizar la carga de la base de datos SQL durante las ejecuciones de planificación maestra, la optimización de planificación reemplaza el motor integrado de planificación maestra de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e194f-113">To enhance performance and minimize the SQL database load during master planning runs, the built-in Supply Chain Management master planning engine is being replaced by Planning Optimization.</span></span> <span data-ttu-id="e194f-114">La optimización de planificación permite realizar ejecuciones de planificación rápida que se pueden realizar incluso durante el horario de oficina.</span><span class="sxs-lookup"><span data-stu-id="e194f-114">Planning Optimization allows for fast planning runs that can be performed even during office hours.</span></span> <span data-ttu-id="e194f-115">Esto permite a los planificadores reaccionar de inmediato a los cambios en la demanda o los parámetros de planificación.</span><span class="sxs-lookup"><span data-stu-id="e194f-115">This enables planners to react immediately to changes in demand or planning parameters.</span></span> |
| <span data-ttu-id="e194f-116">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="e194f-116">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e194f-117">Sí, la optimización de la planificación reemplazará al motor de planificación maestro de Supply Chain Management integrado.</span><span class="sxs-lookup"><span data-stu-id="e194f-117">Yes, Planning Optimization will replace the existing built-in Supply Chain Management master planning engine.</span></span> |
| <span data-ttu-id="e194f-118">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="e194f-118">**Product areas affected**</span></span>         | <span data-ttu-id="e194f-119">Supply Chain Management: planificación maestra</span><span class="sxs-lookup"><span data-stu-id="e194f-119">Supply Chain Management - Master planning</span></span> |
| <span data-ttu-id="e194f-120">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="e194f-120">**Deployment option**</span></span>              | <span data-ttu-id="e194f-121">Solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="e194f-121">Cloud only.</span></span> <span data-ttu-id="e194f-122">Optimización de planificación no se admite en implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="e194f-122">Planning Optimization is not supported with on-premises deployments.</span></span> |
| <span data-ttu-id="e194f-123">**Estado**</span><span class="sxs-lookup"><span data-stu-id="e194f-123">**Status**</span></span>                         | <span data-ttu-id="e194f-124">En desuso.</span><span class="sxs-lookup"><span data-stu-id="e194f-124">Deprecated.</span></span> <span data-ttu-id="e194f-125">En abril de 2021, los escenarios de distribución ya no serán compatibles con lel motor de planificación maestra de Dynamics 365 Supply Chain Management integrado.</span><span class="sxs-lookup"><span data-stu-id="e194f-125">On April 2021, distribution scenarios will no longer be supported with the built-in Dynamics 365 Supply Chain Management master planning engine.</span></span> <span data-ttu-id="e194f-126">Para escenarios de distribución, los clientes deben usar Optimización de planificación para los cálculos de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="e194f-126">For distribution scenarios, customers must use Planning Optimization for master planning calculations.</span></span> <span data-ttu-id="e194f-127">Para obtener más información, consulte la [documentación de Optimización de planificación](https://go.microsoft.com/fwlink/?linkid=2105830).</span><span class="sxs-lookup"><span data-stu-id="e194f-127">For more information, see [Planning Optimization documentation](https://go.microsoft.com/fwlink/?linkid=2105830).</span></span> <span data-ttu-id="e194f-128">Los clientes con implementaciones locales de Dynamics 365 Supply Chain Management pueden continuar usando el motor de planificación maestra de Supply Chain Management para escenarios de distribución después de abril de 2021.</span><span class="sxs-lookup"><span data-stu-id="e194f-128">Customers with on-premises deployments of Dynamics 365 Supply Chain Management may continue to use the Supply Chain Management master planning engine for distribution scenarios after April 2021.</span></span> <span data-ttu-id="e194f-129">Sin embargo, no se proporcionarán más mejoras de funciones.</span><span class="sxs-lookup"><span data-stu-id="e194f-129">However, no more feature enhancements will be provided.</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="e194f-130">Anuncios anteriores sobre funciones quitadas u obsoletas</span><span class="sxs-lookup"><span data-stu-id="e194f-130">Previous announcements about removed or deprecated features</span></span>

<span data-ttu-id="e194f-131">Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="e194f-131">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).</span></span>
