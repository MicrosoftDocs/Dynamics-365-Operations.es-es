---
title: Productos de tránsito directo del almacén de recepción a las tiendas
description: Este procedimiento le guía por los pasos para crear y procesar un tránsito directo para distribuir productos desde la ubicación de recepción de un pedido de compra a una o varias tiendas.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 650eb648f919169a3e70b72e9f619affdf4514f3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238975"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="11907-103">Productos de tránsito directo del almacén de recepción a las tiendas</span><span class="sxs-lookup"><span data-stu-id="11907-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="11907-104">Este procedimiento le guía por los pasos para crear y procesar un tránsito directo para distribuir productos desde la ubicación de recepción de un pedido de compra a una o varias tiendas.</span><span class="sxs-lookup"><span data-stu-id="11907-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="11907-105">El usuario puede definir varias configuraciones y hacer que el sistema sugiera cómo distribuir los productos, o especificar manualmente a dónde se distribuyen los productos y qué cantidad se distribuye a cada almacén.</span><span class="sxs-lookup"><span data-stu-id="11907-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="11907-106">El procedimiento no incluye la configuración de datos que se puede usar en el tránsito directo, como reglas de reabastecimiento, jerarquías organizativas y pesos de tiendas.</span><span class="sxs-lookup"><span data-stu-id="11907-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="11907-107">El procedimiento usa la empresa de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="11907-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="11907-108">Vaya a Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="11907-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="11907-109">Seleccione un pedido de compra en la lista y haga clic en el vínculo para abrir el pedido.</span><span class="sxs-lookup"><span data-stu-id="11907-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="11907-110">En el panel de acciones, haga clic en Retail y Commerce.</span><span class="sxs-lookup"><span data-stu-id="11907-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="11907-111">Haga clic en Tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="11907-111">Click Cross docking.</span></span>
5. <span data-ttu-id="11907-112">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="11907-112">Click Edit.</span></span>
    * <span data-ttu-id="11907-113">La categoría se puede usar para filtrar los artículos en la sección Líneas.</span><span class="sxs-lookup"><span data-stu-id="11907-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="11907-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="11907-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="11907-115">En el campo Cantidad en tránsito directo, escriba un valor para especificar cuánto se debe distribuir de la cantidad que se compra del producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="11907-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="11907-116">En el campo adicional de la cantidad en tránsito directo, especifique un valor para especificar las cantidades que se distribuirán para los productos disponibles que se están adquiriendo</span><span class="sxs-lookup"><span data-stu-id="11907-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="11907-117">En el campo Distribución, especifique el “Peso en la ubicación”.</span><span class="sxs-lookup"><span data-stu-id="11907-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="11907-118">Puede seleccionar los demás tipos para usar diferentes reglas para la distribución.</span><span class="sxs-lookup"><span data-stu-id="11907-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="11907-119">En el campo Jerarquía de reabastecimiento, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="11907-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="11907-120">Seleccione Sí en el campo Respetar selecciones.</span><span class="sxs-lookup"><span data-stu-id="11907-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="11907-121">Haga clic en Calcular cantidades.</span><span class="sxs-lookup"><span data-stu-id="11907-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="11907-122">Haga clic en Crear pedido.</span><span class="sxs-lookup"><span data-stu-id="11907-122">Click Create order.</span></span>
14. <span data-ttu-id="11907-123">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="11907-123">Click Yes.</span></span>
15. <span data-ttu-id="11907-124">En la lista, busque y seleccione un almacén que recibió productos.</span><span class="sxs-lookup"><span data-stu-id="11907-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="11907-125">Haga clic en Pedido para ver los pedidos que se crearon para el almacén seleccionado</span><span class="sxs-lookup"><span data-stu-id="11907-125">Click Order to view the orders that got created for the selected warehouse</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]