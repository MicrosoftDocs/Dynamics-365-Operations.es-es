---
title: Cargos para operaciones de disconformidad
description: Este tema describe cómo crear cargos por calidad que se pueden usar con operaciones para una disconformidad.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 382890232bff47a885840af1eb7e91d27bb46cae
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022309"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="4ae9a-103">Cargos para operaciones de disconformidad</span><span class="sxs-lookup"><span data-stu-id="4ae9a-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ae9a-104">Este tema describe cómo crear cargos por calidad que se pueden usar con operaciones para una disconformidad.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="4ae9a-105">Use la página **Gastos de calidad** para definir los tipos de cargos que pueden agregarse a operaciones para una disconformidad.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="4ae9a-106">Los cargos le permiten realizar un seguimiento de los detalles sobre las tarifas o los cargos que debe a un cliente por productos en disconfomidad, o que un proveedor le debe por productos en disconformidad que recibió.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="4ae9a-107">También puede utilizar cargos para realizar un seguimiento de los costes que son necesarios para que los proveedores o servicios externos realicen una operación.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="4ae9a-108">Ejemplos de cargos de calidad</span><span class="sxs-lookup"><span data-stu-id="4ae9a-108">Examples of quality charges</span></span>

<span data-ttu-id="4ae9a-109">Usted trabaja para una empresa de fabricación.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-109">You work for a manufacturing company.</span></span> <span data-ttu-id="4ae9a-110">Su empresa tiene contratos con varios proveedores.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="4ae9a-111">Esos contratos describen los estándares para el envío a tiempo, los daños y la calidad del producto para los artículos.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="4ae9a-112">Asimismo, varios de sus clientes tienen acuerdos con su empresa sobre devoluciones, daños y calidad del producto.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="4ae9a-113">Se define una estructura de precios para cada circunstancia y se especifica en el contrato.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="4ae9a-114">Puede configurar cargos de calidad para describir los distintos tipos de cargos, como *Daños*, *Envío tardío*, y *Calidad*.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="4ae9a-115">Luego, cuando crea una disconformidad, agregue una o más operaciones.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="4ae9a-116">Para cada operación, seleccione **Cargos** para definir los detalles sobre los precios.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="4ae9a-117">Crear un cargo de calidad</span><span class="sxs-lookup"><span data-stu-id="4ae9a-117">Create a quality charge</span></span>

1. <span data-ttu-id="4ae9a-118">Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Cargos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="4ae9a-119">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="4ae9a-120">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="4ae9a-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="4ae9a-121">**Código de cargos**: introduzca un id. o nombre único para el cargo de calidad.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="4ae9a-122">**Descripción**: escriba una descripción detallada del cargo de calidad.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="4ae9a-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4ae9a-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="4ae9a-124">Agregar un cargo de calidad a una operación para una disconformidad</span><span class="sxs-lookup"><span data-stu-id="4ae9a-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="4ae9a-125">Para obtener detalles sobre cómo agregar operaciones a una disconformidad y aplicarles cargos, consulte [Operaciones para disconformidades](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="4ae9a-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ae9a-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4ae9a-126">Additional resources</span></span>

- [<span data-ttu-id="4ae9a-127">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="4ae9a-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="4ae9a-128">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="4ae9a-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="4ae9a-129">Trabajadores responsables de aprobar no conformidades</span><span class="sxs-lookup"><span data-stu-id="4ae9a-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="4ae9a-130">Zonas de cuarentena para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4ae9a-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="4ae9a-131">Tipos de diagnóstico de disconformidades</span><span class="sxs-lookup"><span data-stu-id="4ae9a-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="4ae9a-132">Cargos de calidad para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4ae9a-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="4ae9a-133">Operaciones para disconformidades</span><span class="sxs-lookup"><span data-stu-id="4ae9a-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="4ae9a-134">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="4ae9a-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
