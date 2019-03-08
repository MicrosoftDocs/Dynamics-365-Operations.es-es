---
title: Configuración de almacenes para pedidos de transferencia
description: Este tema describe cómo puede configurar los almacenes para pedidos de transferencia.
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8111601cb2948c66097b0f5b2f261b7462b279f9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "337472"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="ce781-103">Configuración de almacenes para pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="ce781-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ce781-104">Puede utilizar niveles de almacén para crear una jerarquía que admita pedidos de transferencia entre almacenes.</span><span class="sxs-lookup"><span data-stu-id="ce781-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="ce781-105">En función de esta configuración, la programación maestra calcula los requisitos de artículos a nivel de almacén individual y genera pedidos de transferencia planificados desde un almacén de origen asignado para cumplirlos.</span><span class="sxs-lookup"><span data-stu-id="ce781-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="ce781-106">Haga clic en **Gestión del inventario> Configuración > Desglose del inventario > Almacenes**</span><span class="sxs-lookup"><span data-stu-id="ce781-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="ce781-107">Seleccione el almacén que desee reabastecer.</span><span class="sxs-lookup"><span data-stu-id="ce781-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="ce781-108">En la ficha desplegable **Planificación maestra**, seleccione la casilla **Reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="ce781-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="ce781-109">En el campo **Almacén principal**, seleccione el almacén que desee asignar como almacén de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="ce781-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="ce781-110">La programación maestra calcula un requisito de transferencia para el almacén seleccionado y genera un pedido de transferencia planificado desde el **Almacén principal** asignado.</span><span class="sxs-lookup"><span data-stu-id="ce781-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="ce781-111">Si deja el campo <STRONG>Reabastecimiento</STRONG> en blanco, se asigna al almacén seleccionado un nivel de almacén en relación con el <STRONG>Almacén principal</STRONG>, pero no se define el <STRONG>Almacén principal</STRONG> como almacén de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="ce781-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="ce781-112">Cierre la página para aplicar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="ce781-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="ce781-113">Si desea asignar un almacén para reabastecimiento, en primer lugar debe configurar el almacén como una dimensión de almacenamiento en el formulario <STRONG>Grupos de dimensiones de almacenamiento</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ce781-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="ce781-114">En esta página, seleccione el campo <STRONG>Activo</STRONG> y el campo <STRONG>Plan de cobertura por dimensión</STRONG> para el almacén.</span><span class="sxs-lookup"><span data-stu-id="ce781-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="ce781-115">Configuración del plazo de transporte</span><span class="sxs-lookup"><span data-stu-id="ce781-115">Set up transport lead time</span></span>

<span data-ttu-id="ce781-116">También debe configurar el plazo de transporte entre los almacenes en la página **Días de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ce781-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="ce781-117">Vaya a **Administración de inventario > configuración > distribución > días de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ce781-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="ce781-118">En el campo **Punto de recepción**, seleccione **almacén**.</span><span class="sxs-lookup"><span data-stu-id="ce781-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="ce781-119">Seleccione **Almacén de envío**, **Almacén de recepción** y **Días de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ce781-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="ce781-120">(opcional) También puede establecer el tiempo de transporte, en función del modo de entrega, en la pestaña **Días de transporte por modo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="ce781-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>
