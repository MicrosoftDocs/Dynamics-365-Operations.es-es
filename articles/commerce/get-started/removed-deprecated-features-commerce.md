---
title: Características quitadas u obsoletas de Dynamics 365 Commerce
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335285"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a><span data-ttu-id="e2483-103">Características quitadas u obsoletas de Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="e2483-103">Removed or deprecated features in Dynamics 365 Commerce</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2483-104">En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e2483-104">This topic describes features that have been removed, or that are planned for removal from Dynamics 365 Commerce.</span></span>

- <span data-ttu-id="e2483-105">Una función *quitada* dejará de estar disponible en el producto.</span><span class="sxs-lookup"><span data-stu-id="e2483-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="e2483-106">Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.</span><span class="sxs-lookup"><span data-stu-id="e2483-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="e2483-107">Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.</span><span class="sxs-lookup"><span data-stu-id="e2483-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="e2483-108">La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="e2483-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="e2483-109">Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e2483-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a><span data-ttu-id="e2483-110">Funciones quitadas o en desuso en la versión Commerce 10.0.10</span><span class="sxs-lookup"><span data-stu-id="e2483-110">Features removed or deprecated in the Commerce 10.0.10 release</span></span>
### <a name="pos-operation-803---picking-and-receiving"></a><span data-ttu-id="e2483-111">Operación POS 803: recogida y recepción</span><span class="sxs-lookup"><span data-stu-id="e2483-111">POS operation 803 - Picking and receiving</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="e2483-112">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="e2483-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e2483-113">Las operaciones de recogida y recepción están en desuso debido al nuevo diseño de la operación.</span><span class="sxs-lookup"><span data-stu-id="e2483-113">Picking and receiving operations is being deprecated due to new operation redesign.</span></span> |
| <span data-ttu-id="e2483-114">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="e2483-114">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e2483-115">Sí.</span><span class="sxs-lookup"><span data-stu-id="e2483-115">Yes.</span></span> <span data-ttu-id="e2483-116">Se reemplazan por dos nuevas operaciones POS: operación entrante (804) y operación saliente (805).</span><span class="sxs-lookup"><span data-stu-id="e2483-116">It is replaced by two new POS operations: inbound operation (804) and outbound operation (805).</span></span>|
| <span data-ttu-id="e2483-117">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="e2483-117">**Product areas affected**</span></span>         | <span data-ttu-id="e2483-118">Aplicación de punto de venta (POS)</span><span class="sxs-lookup"><span data-stu-id="e2483-118">Point of sale (POS) application</span></span> |
| <span data-ttu-id="e2483-119">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="e2483-119">**Deployment option**</span></span>              | <span data-ttu-id="e2483-120">Todos</span><span class="sxs-lookup"><span data-stu-id="e2483-120">All</span></span> |
| <span data-ttu-id="e2483-121">**Estado**</span><span class="sxs-lookup"><span data-stu-id="e2483-121">**Status**</span></span>                         | <span data-ttu-id="e2483-122">En desuso: a partir de la versión 10.0.10, la operación de selección y recepción ya no recibirá actualizaciones de nuevas funciones.</span><span class="sxs-lookup"><span data-stu-id="e2483-122">Deprecated: As of release 10.0.10, the picking and receiving operation will no longer receive any new feature updates.</span></span> <span data-ttu-id="e2483-123">Solo se realizarán correcciones de errores críticos para esta operación en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="e2483-123">Only critical bug fixes will be done for this operation in future releases.</span></span> <span data-ttu-id="e2483-124">Se anima a todos los clientes a cambiar a las nuevas [Operaciones de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) y [Operaciones de salida](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), que seguirán formando parte de nuestra hoja de ruta de productos a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="e2483-124">All customers are encouraged to move to the new [Inbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) and [Outbound operations](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), which will continue to be part of our long-term product roadmap.</span></span> |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a><span data-ttu-id="e2483-125">Funciones quitadas o en desuso en la versión Commerce 10.0.7</span><span class="sxs-lookup"><span data-stu-id="e2483-125">Features removed or deprecated in the Commerce 10.0.7 release</span></span>
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a><span data-ttu-id="e2483-126">API de GetProductAvailabilities y GetAvailableInventoryNearby</span><span class="sxs-lookup"><span data-stu-id="e2483-126">Commerce GetProductAvailabilities and GetAvailableInventoryNearby API's</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="e2483-127">**Motivo de la depreciación/eliminación**</span><span class="sxs-lookup"><span data-stu-id="e2483-127">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="e2483-128">Se han creado API nuevas y optimizadas para reemplazar las API de GetProductAvailabilities y GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="e2483-128">New optimized APIs have been created to replace the GetProductAvailabilities and GetAvailableInventoryNearby APIs.</span></span> |
| <span data-ttu-id="e2483-129">**¿Reemplazado por otra característica?**</span><span class="sxs-lookup"><span data-stu-id="e2483-129">**Replaced by another feature?**</span></span>   | <span data-ttu-id="e2483-130">Sí: se reemplaza por las API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability.</span><span class="sxs-lookup"><span data-stu-id="e2483-130">Yes: It is replaced by GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs.</span></span> |
| <span data-ttu-id="e2483-131">**Áreas de producto afectadas**</span><span class="sxs-lookup"><span data-stu-id="e2483-131">**Product areas affected**</span></span>         | <span data-ttu-id="e2483-132">SDK de aplicación de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="e2483-132">e-Commerce application SDK</span></span> |
| <span data-ttu-id="e2483-133">**Opción de implementación**</span><span class="sxs-lookup"><span data-stu-id="e2483-133">**Deployment option**</span></span>              | <span data-ttu-id="e2483-134">Todos</span><span class="sxs-lookup"><span data-stu-id="e2483-134">All</span></span> |
| <span data-ttu-id="e2483-135">**Estado**</span><span class="sxs-lookup"><span data-stu-id="e2483-135">**Status**</span></span>                         | <span data-ttu-id="e2483-136">En desuso: a partir de la versión 10.0.7, ya no se realizarán inversiones de ingeniería para GetProductAvailabilities y GetAvailableInventoryNearby.</span><span class="sxs-lookup"><span data-stu-id="e2483-136">Deprecated: As of release 10.0.7, there will no longer be engineering investments made for GetProductAvailabilities and GetAvailableInventoryNearby.</span></span> <span data-ttu-id="e2483-137">Las organizaciones que usan estas API en sus implementaciones de comercio electrónico deben convertirse a las nuevas API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability y habilitar la [Función optimizada de cálculo de disponibilidad del producto](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="e2483-137">Organizations that use these APIs in their e-Commerce deployments should convert to the new GetEstimatedAvailabilty and GetEstimatedProductWarehouseAvailability APIs and enable the [Optimized product availability calculation feature](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).</span></span>  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="e2483-138">Anuncios anteriores sobre funciones quitadas u obsoletas</span><span class="sxs-lookup"><span data-stu-id="e2483-138">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="e2483-139">Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="e2483-139">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).</span></span>
