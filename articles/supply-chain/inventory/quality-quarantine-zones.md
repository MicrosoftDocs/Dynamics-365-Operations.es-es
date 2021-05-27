---
title: Zonas de cuarentena para disconformidades
description: Este tema describe cómo crear y utilizar zonas de cuarentena para disconformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80f4b9dfc7882af4570bf1908784b8d114396402
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021813"
---
# <a name="quarantine-zones-for-nonconformances"></a><span data-ttu-id="4e32f-103">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-103">Quarantine zones for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4e32f-104">Este tema describe cómo crear y utilizar zonas de cuarentena para disconformidades.</span><span class="sxs-lookup"><span data-stu-id="4e32f-104">This topic describes how to create and use quarantine zones for nonconformances.</span></span>

<span data-ttu-id="4e32f-105">Use la página **Zonas de cuarentena** para definir zonas que pueden asignarse a disconformidades.</span><span class="sxs-lookup"><span data-stu-id="4e32f-105">You use the **Quarantine zones** page to define zones that can be assigned to nonconformances.</span></span> <span data-ttu-id="4e32f-106">Cuando crea una disconformidad, puede establecer los campos **Zona de cuarentena** y **Tipo de cuarentena** en la pestaña **General** de la página **Disconformidades**.</span><span class="sxs-lookup"><span data-stu-id="4e32f-106">When you create a nonconformance, you can set the **Quarantine zone** and **Quarantine type** fields on the **General** tab of the **Non conformances** page.</span></span> <span data-ttu-id="4e32f-107">El campo **Zona de cuarentena** normalmente indica el área o ubicación donde se encuentra el artículo.</span><span class="sxs-lookup"><span data-stu-id="4e32f-107">The **Quarantine zone** field typically indicates the area or location where the item is located.</span></span> <span data-ttu-id="4e32f-108">El campo **Tipo de cuarentena** define el elemento como *Uso restringido* o *Inutilizable*.</span><span class="sxs-lookup"><span data-stu-id="4e32f-108">The **Quarantine type** field defines the item as either *Restricted usage* or *Unusable*.</span></span>

<span data-ttu-id="4e32f-109">Cuando imprime un informe de disconformidad o correcciones para una no conformidad, puede ver la zona de cuarentena donde se encuentra el artículo.</span><span class="sxs-lookup"><span data-stu-id="4e32f-109">When you print a nonconformance or corrections report for a nonconformance, you can view the quarantine zone where the item is located.</span></span>

<span data-ttu-id="4e32f-110">También puede imprimir una etiqueta de disconformidad para una disconformidad.</span><span class="sxs-lookup"><span data-stu-id="4e32f-110">You can also print a nonconformance tag for a nonconformance.</span></span> <span data-ttu-id="4e32f-111">Este informe muestra la zona de cuarentena asignada e información de uso para ofrecer orientación sobre como debe manejarse el material defectuoso.</span><span class="sxs-lookup"><span data-stu-id="4e32f-111">This report shows the assigned quarantine zone and information about usage to provide guidance about how defective material should be handled.</span></span> <span data-ttu-id="4e32f-112">Las zonas de cuarentena pueden corresponder a ubicaciones de inventario o a recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4e32f-112">The quarantine zones might correspond to inventory locations or operations resources.</span></span>

## <a name="examples-of-quarantine-zones"></a><span data-ttu-id="4e32f-113">Ejemplos de zonas de cuarentena</span><span class="sxs-lookup"><span data-stu-id="4e32f-113">Examples of quarantine zones</span></span>

### <a name="example-1"></a><span data-ttu-id="4e32f-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4e32f-114">Example 1</span></span>

<span data-ttu-id="4e32f-115">Trabaja en una empresa de fabricación de productos electrónicos que produce y distribuye televisores, altavoces y reproductores multimedia.</span><span class="sxs-lookup"><span data-stu-id="4e32f-115">You work at an electronics manufacturing company that produces and distributes televisions, speakers, and media players.</span></span> <span data-ttu-id="4e32f-116">En este caso, puede configurar una zona de cuarentena para representar cada tipo de producto.</span><span class="sxs-lookup"><span data-stu-id="4e32f-116">In this case, you can configure a quarantine zone to represent each type of product.</span></span>

### <a name="example-2"></a><span data-ttu-id="4e32f-117">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="4e32f-117">Example 2</span></span>

<span data-ttu-id="4e32f-118">Se utilizan tres contenedores y dos estantes para almacenar artículos que no son conformes.</span><span class="sxs-lookup"><span data-stu-id="4e32f-118">Three bins and two racks are used to store items that are nonconforming.</span></span> <span data-ttu-id="4e32f-119">En este caso, puede configurar cinco zonas de cuarentena, una para cada contenedor y cada bastidor.</span><span class="sxs-lookup"><span data-stu-id="4e32f-119">In this case, you can configure five quarantine zones, one for each bin and each rack.</span></span>

## <a name="create-a-quarantine-zone"></a><span data-ttu-id="4e32f-120">Crear una zona de cuarentena</span><span class="sxs-lookup"><span data-stu-id="4e32f-120">Create a quarantine zone</span></span>

1. <span data-ttu-id="4e32f-121">Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Zonas de cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="4e32f-121">Go to **Inventory management \> Setup \> Quality management \> Quarantine zones**.</span></span>
1. <span data-ttu-id="4e32f-122">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4e32f-122">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="4e32f-123">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="4e32f-123">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="4e32f-124">**Zona de cuarentena**: introduzca un id. o nombre único para la zona de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4e32f-124">**Quarantine zone** – Enter a unique ID or name for the quarantine zone.</span></span>
    - <span data-ttu-id="4e32f-125">**Descripción**: escriba una descripción detallada de la zona de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4e32f-125">**Description** – Enter a detailed description of the quarantine zone.</span></span>

1. <span data-ttu-id="4e32f-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e32f-126">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e32f-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4e32f-127">Additional resources</span></span>

- [<span data-ttu-id="4e32f-128">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="4e32f-128">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="4e32f-129">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-129">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="4e32f-130">Trabajadores responsables de aprobar no conformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-130">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="4e32f-131">Tipos de probemas para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-131">Problem types for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="4e32f-132">Tipos de diagnóstico de disconformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-132">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="4e32f-133">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-133">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="4e32f-134">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4e32f-134">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="4e32f-135">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="4e32f-135">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
