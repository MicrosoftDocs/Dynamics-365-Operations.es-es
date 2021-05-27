---
title: Tipos de problemas para disconformidades
description: Este tema describe cómo crear y utilizar tipos de problemas para disconformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022165"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="880a0-103">Tipos de problemas para disconformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="880a0-104">Este tema describe cómo crear y utilizar tipos de problemas para disconformidades.</span><span class="sxs-lookup"><span data-stu-id="880a0-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="880a0-105">Use la página **Tipos de problemas** para definir una clasificación de los problemas de calidad que podrían ocurrir en los distintos tipos de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="880a0-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="880a0-106">Para cada tipo de problema que cree, debe especificar los tipos de disconformidades con las que se puede utilizar el tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="880a0-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="880a0-107">Puede configurar los siguientes tipos de disconformidad:</span><span class="sxs-lookup"><span data-stu-id="880a0-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="880a0-108">**Interno**: las disconformidades de este tipo están relacionadas con el inventario disponible (por ejemplo, pedidos de calidad o pedidos de cuarentena).</span><span class="sxs-lookup"><span data-stu-id="880a0-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="880a0-109">**Cliente**: las no conformidades de este tipo están relacionadas con pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="880a0-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="880a0-110">**Proveedor**: las no conformidades de este tipo están relacionadas con pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="880a0-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="880a0-111">**Solicitud de servicio**: las no conformidades de este tipo están relacionadas con pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="880a0-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="880a0-112">**Producción**: las disconformidades de este tipo están relacionadas con pedidos de lote o pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="880a0-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="880a0-113">**Producción de coproducto**: las disconformidades de este tipo están relacionadas con pedidos de lote para coproductos.</span><span class="sxs-lookup"><span data-stu-id="880a0-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="880a0-114">Cuando cree un nuevo tipo de problema, seleccione **Tipos de disconformidad** en el panel de acciones para crear una lista de uno o más tipos de disconformidad autorizados para el tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="880a0-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="880a0-115">Por ejemplo, un tipo de problema relacionado con un código defectuoso podría aplicarse a todos los tipos de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="880a0-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="880a0-116">Sin embargo, un tipo de problema relacionado con las quejas de los clientes puede aplicarse solo a los tipos de disconformidad **Cliente** y **Solicitud de servicio**.</span><span class="sxs-lookup"><span data-stu-id="880a0-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="880a0-117">Ejemplos de tipos de problemas</span><span class="sxs-lookup"><span data-stu-id="880a0-117">Examples of problem types</span></span>

<span data-ttu-id="880a0-118">A continuación, se muestran algunos ejemplos de escenarios para tipos de problemas que se pueden utilizar con los diferentes tipos de no conformidad:</span><span class="sxs-lookup"><span data-stu-id="880a0-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="880a0-119">**Cliente:** un cliente presentó una queja, un cliente hizo una devolución o no se cumplieron las especificaciones de calidad.</span><span class="sxs-lookup"><span data-stu-id="880a0-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="880a0-120">**Proveedor:** el producto estaba dañado, no se cumplieron las especificaciones de calidad o se recibió un producto incorrecto.</span><span class="sxs-lookup"><span data-stu-id="880a0-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="880a0-121">**Solicitud de servicio:** no se cumplieron las especificaciones de calidad, un cliente presentó una queja o se requiere mantenimiento de la máquina.</span><span class="sxs-lookup"><span data-stu-id="880a0-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="880a0-122">**Producción:** no se cumplieron las especificaciones de calidad, se requiere mantenimiento de la máquina o el producto estaba dañado.</span><span class="sxs-lookup"><span data-stu-id="880a0-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="880a0-123">**Producción de coproducto:** no se cumplieron las especificaciones de calidad, se requiere mantenimiento de la máquina o el producto estaba dañado.</span><span class="sxs-lookup"><span data-stu-id="880a0-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="880a0-124">Crear un tipo de problema y asignarlo a tipos de disconformidad</span><span class="sxs-lookup"><span data-stu-id="880a0-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="880a0-125">Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Tipos de problemas**.</span><span class="sxs-lookup"><span data-stu-id="880a0-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="880a0-126">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="880a0-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="880a0-127">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="880a0-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="880a0-128">**Tipo de problema**: introduzca un id. o nombre único para el tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="880a0-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="880a0-129">**Descripción**: escriba una descripción detallada del tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="880a0-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="880a0-130">Mientras la nueva fila aún está seleccionada, seleccione **Tipos de no conformidad** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="880a0-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="880a0-131">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="880a0-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="880a0-132">Luego, para la nueva fila, establezca el campo **Tipo de disconformidad** en el tipo de disconformidad que desea permitir para el tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="880a0-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="880a0-133">Repita el paso anterior para cada tipo de disconformidad adicional que desee autorizar para el tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="880a0-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="880a0-134">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="880a0-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="880a0-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="880a0-135">Additional resources</span></span>

- [<span data-ttu-id="880a0-136">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="880a0-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="880a0-137">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="880a0-138">Trabajadores responsables de aprobar no conformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="880a0-139">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="880a0-140">Tipos de diagnóstico de disconformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="880a0-141">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="880a0-142">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="880a0-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="880a0-143">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="880a0-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
