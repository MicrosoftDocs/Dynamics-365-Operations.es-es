---
title: Tipos de diagnóstico para disconformidades
description: Este tema describe cómo usar y crear tipos de diagnóstico que se pueden usar con disconformidades.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19fcd57e28efabd6ca32c444ab961b876bde424d
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956813"
---
# <a name="diagnostic-types-for-nonconformances"></a><span data-ttu-id="03c13-103">Tipos de diagnóstico para disconformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-103">Diagnostic types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03c13-104">Este tema describe cómo usar y crear tipos de diagnóstico que se pueden usar con disconformidades.</span><span class="sxs-lookup"><span data-stu-id="03c13-104">This topic describes how to use and create diagnostic types that can be used with nonconformances.</span></span>

<span data-ttu-id="03c13-105">Use la página **Tipos de diagnóstico** para definir una clasificación de acciones de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="03c13-105">You use the **Diagnostic types** page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="03c13-106">Luego, al crear una corrección para una no conformidad, seleccione un diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="03c13-106">Then, when you create a correction for a nonconformance, you select a diagnostic.</span></span> <span data-ttu-id="03c13-107">Una corrección especifica qué tipo de acción de diagnóstico se debe realizar en una disconformidad aprobada, quién debe efectuarla.</span><span class="sxs-lookup"><span data-stu-id="03c13-107">A correction specifies what type of diagnostic action should be taken for an approved nonconformance, and who should take that action.</span></span> <span data-ttu-id="03c13-108">También especifica la fecha de finalización solicitada y la fecha de finalización planificada.</span><span class="sxs-lookup"><span data-stu-id="03c13-108">It also specifies the requested completion date and the planned completion date.</span></span>

## <a name="examples-of-diagnostic-types"></a><span data-ttu-id="03c13-109">Ejemplos de tipos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="03c13-109">Examples of diagnostic types</span></span>

<span data-ttu-id="03c13-110">Trabaja para una empresa de fabricación y varios artículos no han superado las pruebas de calidad.</span><span class="sxs-lookup"><span data-stu-id="03c13-110">You work for a manufacturing company, and several items have failed quality tests.</span></span> <span data-ttu-id="03c13-111">Esos artículos se mueven a un área de cuarentena y se marcan como productos no conformes.</span><span class="sxs-lookup"><span data-stu-id="03c13-111">Those items are moved into a quarantine area and marked as nonconforming products.</span></span> <span data-ttu-id="03c13-112">Se crea un registro de disconformidad en Microsoft Dynamics 365 Supply Chain Management para rastrear los detalles a través de la resolución de problemas.</span><span class="sxs-lookup"><span data-stu-id="03c13-112">A nonconformance record is created in Microsoft Dynamics 365 Supply Chain Management to track the details through issue resolution.</span></span>

<span data-ttu-id="03c13-113">En este caso, los problemas de calidad se deben a que los cojinetes de la máquina que empaqueta los artículos se han estropeado y se están sobrecalentando.</span><span class="sxs-lookup"><span data-stu-id="03c13-113">In this case, the quality issues are occurring because bearings in the machine that packages the items have gone bad and are overheating.</span></span> <span data-ttu-id="03c13-114">La corrección de este problema es reemplazar las piezas de la máquina.</span><span class="sxs-lookup"><span data-stu-id="03c13-114">The correction for this problem is to replace the parts in the machine.</span></span>

<span data-ttu-id="03c13-115">Cuando configura los tipos de diagnóstico, puede crear varios registros, cada uno de los cuales representa un tipo diferente de problema que podría tener la máquina.</span><span class="sxs-lookup"><span data-stu-id="03c13-115">When you configure the diagnostic types, you can create multiple records, each of which represents a different type of problem that the machine might have.</span></span> <span data-ttu-id="03c13-116">Alternativamente, puede crear un tipo de diagnóstico genérico que represente la reparación de la máquina.</span><span class="sxs-lookup"><span data-stu-id="03c13-116">Alternatively, you can create one generic diagnostic type that represents machine repair.</span></span>

## <a name="create-a-diagnostic-type"></a><span data-ttu-id="03c13-117">Crear un tipo de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="03c13-117">Create a diagnostic type</span></span>

1. <span data-ttu-id="03c13-118">Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Tipos de diagnóstico**.</span><span class="sxs-lookup"><span data-stu-id="03c13-118">Go to **Inventory management \> Setup \> Quality management \> Diagnostic types**.</span></span>
1. <span data-ttu-id="03c13-119">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="03c13-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="03c13-120">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="03c13-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="03c13-121">**Diagnóstico**: introduzca un id. o nombre único para el tipo de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="03c13-121">**Diagnostic** – Enter a unique ID or name for the diagnostic type.</span></span>
    - <span data-ttu-id="03c13-122">**Descripción**: escriba una descripción detallada del tipo de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="03c13-122">**Description** – Enter a detailed description of the diagnostic type.</span></span>

1. <span data-ttu-id="03c13-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="03c13-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03c13-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="03c13-124">Additional resources</span></span>

- [<span data-ttu-id="03c13-125">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="03c13-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="03c13-126">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="03c13-127">Trabajadores responsables de aprobar no conformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-127">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="03c13-128">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="03c13-129">Tipos de probemas para disconformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-129">Problem types for nonconformances</span></span>](quality-problem-types.md)
- [<span data-ttu-id="03c13-130">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="03c13-131">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="03c13-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="03c13-132">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="03c13-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
