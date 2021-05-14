---
title: Operaciones para disconformidades
description: Este tema describe cómo crear y utilizar operaciones para no conformidades.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6454a56323ea66369696dd6e3310a41b4eb9ee58
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956825"
---
# <a name="operations-for-nonconformances"></a><span data-ttu-id="e7450-103">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-103">Operations for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7450-104">Este tema describe cómo crear y utilizar operaciones para no conformidades.</span><span class="sxs-lookup"><span data-stu-id="e7450-104">This topic describes how to create and use operations for nonconformances.</span></span>

<span data-ttu-id="e7450-105">Use la página **Operaciones** para definir clasificaciones del trabajo que se puede efectuar para un caso de disconformidad aprobado.</span><span class="sxs-lookup"><span data-stu-id="e7450-105">You can use the **Operations** page to define classifications of the work that can be performed for an approved nonconformance.</span></span> <span data-ttu-id="e7450-106">Al asignar una operación relacionada a una disconformidad, también puede proporcionar detalles, como el material asociado, las horas de trabajo y los gastos requeridos para llevar a cabo la operación.</span><span class="sxs-lookup"><span data-stu-id="e7450-106">When you assign a related operation to a nonconformance, you can provide details such as the associated material, labor hours, and charges that are required to do the operation.</span></span> <span data-ttu-id="e7450-107">El sistema usa esta información para calcular el coste estimado para la operación.</span><span class="sxs-lookup"><span data-stu-id="e7450-107">The system uses this information to calculate an estimated cost for the operation.</span></span> <span data-ttu-id="e7450-108">La información detallada y los costes estimados sirven como referencia.</span><span class="sxs-lookup"><span data-stu-id="e7450-108">The detailed information and estimated costs are for reference.</span></span> <span data-ttu-id="e7450-109">Las operaciones relacionadas para la calidad son diferentes de las operaciones que se pueden definir para una ruta de producción.</span><span class="sxs-lookup"><span data-stu-id="e7450-109">The related operations for quality differ from the operations that can be defined for a production route.</span></span>

> [!NOTE]
> <span data-ttu-id="e7450-110">Aunque puede realizar un seguimiento de los costos, el tiempo y los elementos que se utilizan en una operación relacionada con una disconformidad, los datos que introduce son solo informativos.</span><span class="sxs-lookup"><span data-stu-id="e7450-110">Although you can track costs, time, and the items that are used in an operation that is related to a nonconformance, the data that you enter is only informational.</span></span> <span data-ttu-id="e7450-111">No se integra automáticamente con el libro mayor, el subdirectorio de inventario ni el módulo **Tiempo y asistencia**.</span><span class="sxs-lookup"><span data-stu-id="e7450-111">It isn't automatically integrated with the general ledger, inventory subledger, or the **Time and attendance** module.</span></span>

## <a name="examples-of-operations"></a><span data-ttu-id="e7450-112">Ejemplos de operaciones</span><span class="sxs-lookup"><span data-stu-id="e7450-112">Examples of operations</span></span>

<span data-ttu-id="e7450-113">Usted trabaja para una empresa de fabricación.</span><span class="sxs-lookup"><span data-stu-id="e7450-113">You work for a manufacturing company.</span></span> <span data-ttu-id="e7450-114">Se creó y aprobó una disconformidad para los artículos que no pasaron una prueba de calidad.</span><span class="sxs-lookup"><span data-stu-id="e7450-114">A nonconformance was created and approved for items that failed a quality test.</span></span> <span data-ttu-id="e7450-115">Se creó una corrección para indicar que el problema estaba relacionado con un rodamiento averiado de una máquina.</span><span class="sxs-lookup"><span data-stu-id="e7450-115">A correction was created to indicate that the problem was related to a bad bearing on a machine.</span></span> <span data-ttu-id="e7450-116">Se requieren varios pasos para reemplazar el rodamiento y se hace un seguimiento de la responsabilidad de cada operación.</span><span class="sxs-lookup"><span data-stu-id="e7450-116">Several steps are required to replace the bearing, and the responsibility for each operation is tracked.</span></span> <span data-ttu-id="e7450-117">Por ejemplo, es posible que se requieran los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e7450-117">For example, the following steps might be required:</span></span>

1. <span data-ttu-id="e7450-118">Se detiene la línea de producción y se realiza la rutina de limpieza.</span><span class="sxs-lookup"><span data-stu-id="e7450-118">The production line is stopped, and the clean-out routine is performed.</span></span>
1. <span data-ttu-id="e7450-119">El personal de mantenimiento reemplaza el rodamiento.</span><span class="sxs-lookup"><span data-stu-id="e7450-119">Maintenance personnel replace the bearing.</span></span>
1. <span data-ttu-id="e7450-120">El personal de control de calidad inspecciona la máquina antes de volver a encenderla.</span><span class="sxs-lookup"><span data-stu-id="e7450-120">Quality assurance personnel inspect the machine before it's turned back on.</span></span>

<span data-ttu-id="e7450-121">Para este ejemplo, se pueden crear las siguientes operaciones para representar el trabajo que se debe realizar:</span><span class="sxs-lookup"><span data-stu-id="e7450-121">For this example, the following operations can be created to represent the work that must be done:</span></span>

- <span data-ttu-id="e7450-122">Detener la línea de producción.</span><span class="sxs-lookup"><span data-stu-id="e7450-122">Stop the production line.</span></span>
- <span data-ttu-id="e7450-123">Limpiar la línea de producción.</span><span class="sxs-lookup"><span data-stu-id="e7450-123">Clean out the production line.</span></span>
- <span data-ttu-id="e7450-124">Realizar mantenimiento de la máquina.</span><span class="sxs-lookup"><span data-stu-id="e7450-124">Perform machine maintenance.</span></span>
- <span data-ttu-id="e7450-125">Inspeccionar la máquina.</span><span class="sxs-lookup"><span data-stu-id="e7450-125">Inspect the machine.</span></span>

## <a name="create-an-operation"></a><span data-ttu-id="e7450-126">Crear una operación</span><span class="sxs-lookup"><span data-stu-id="e7450-126">Create an operation</span></span>

1. <span data-ttu-id="e7450-127">Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Operaciones**.</span><span class="sxs-lookup"><span data-stu-id="e7450-127">Go to **Inventory management \> Setup \> Quality management \> Operations**.</span></span>
1. <span data-ttu-id="e7450-128">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e7450-128">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="e7450-129">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="e7450-129">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="e7450-130">**Operación**: introduzca un id. o nombre único para la operación.</span><span class="sxs-lookup"><span data-stu-id="e7450-130">**Operation** – Enter a unique ID or name for the operation.</span></span>
    - <span data-ttu-id="e7450-131">**Descripción**: escriba una descripción detallada de la operación.</span><span class="sxs-lookup"><span data-stu-id="e7450-131">**Description** – Enter a detailed description of the operation.</span></span>
    - <span data-ttu-id="e7450-132">**Tipo**: si la operación se puede utilizar solo con disconformidades relacionadas con un tipo específico de pedido, seleccione el tipo de pedido (*Pedido de compra* o *Pedido de ventas*).</span><span class="sxs-lookup"><span data-stu-id="e7450-132">**Type** – If the operation can be used only with nonconformances that are related to a specific type of order, select the order type (*Purchase order* or *Sales order*).</span></span>

1. <span data-ttu-id="e7450-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e7450-133">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7450-134">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e7450-134">Additional resources</span></span>

- [<span data-ttu-id="e7450-135">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="e7450-135">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="e7450-136">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-136">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="e7450-137">Crear y procesar disconformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-137">Create and process nonconformances</span></span>](tasks/create-process-non-conformance.md)
- [<span data-ttu-id="e7450-138">Trabajadores responsables de aprobar no conformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="e7450-139">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="e7450-140">Tipos de diagnóstico de disconformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="e7450-141">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="e7450-142">Tipos de probemas para disconformidades</span><span class="sxs-lookup"><span data-stu-id="e7450-142">Problem types for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="e7450-143">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="e7450-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
