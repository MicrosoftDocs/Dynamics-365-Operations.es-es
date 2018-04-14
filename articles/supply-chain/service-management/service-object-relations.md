---
title: Relaciones de objetos de servicio
description: Es posible crear relaciones de objeto de servicio entre un objeto de servicio y un acuerdo o pedido de servicio.
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e7ee1935c006636f8d7bfce53287229e736e2f80
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="service-object-relations"></a><span data-ttu-id="e7d98-103">Relaciones de objetos de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-103">Service object relations</span></span> 

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e7d98-104">Es posible crear relaciones de objeto de servicio entre un objeto de servicio y un acuerdo o pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-104">You can create service object relations between a service object and a service agreement or service order.</span></span> <span data-ttu-id="e7d98-105">Al crear una relación, se vincula un objeto de servicio al acuerdo o pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-105">When you create a relation, you attach the service object to the service agreement or service order.</span></span>

<span data-ttu-id="e7d98-106">Una vez creada la relación, puede vincular el objeto de servicio a cualquier línea del acuerdo o pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-106">After the relation is created, you can attach the service object to any lines on the service agreement or service order.</span></span>

## <a name="template-boms"></a><span data-ttu-id="e7d98-107">Plantilla de L. MAT</span><span class="sxs-lookup"><span data-stu-id="e7d98-107">Template BOMs</span></span>

<span data-ttu-id="e7d98-108">También se puede especificar una plantilla de L. MAT para la relación de objetos.</span><span class="sxs-lookup"><span data-stu-id="e7d98-108">You can also specify a template BOM for the object relation.</span></span> <span data-ttu-id="e7d98-109">Ésta es una lista de materiales para el objeto en el que se realiza el servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-109">The template BOM is a bill of materials for the object on which you perform service.</span></span> <span data-ttu-id="e7d98-110">Si sustituye una pieza de componente del objeto de servicio durante una visita de servicio, puede registrar este cambio en la lista de materiales de servicio mediante el formulario Objetos de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-110">If you replace a component part of the service object during a service visit, you can register this change in the service BOM by using the Service objects form.</span></span>

## <a name="example"></a><span data-ttu-id="e7d98-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7d98-111">Example</span></span>

<span data-ttu-id="e7d98-112">Puede crear un acuerdo de servicio para la reparación o el mantenimiento de dos ascensores en las instalaciones de un cliente.</span><span class="sxs-lookup"><span data-stu-id="e7d98-112">You create a service agreement for servicing two elevators at a customer site.</span></span>
<span data-ttu-id="e7d98-113">El acuerdo de servicio tiene el identificador ID SAL-001.</span><span class="sxs-lookup"><span data-stu-id="e7d98-113">The service agreement has the identifier ID SAL-001.</span></span>

<span data-ttu-id="e7d98-114">Los ascensores se han configurado en el formulario Objetos de servicio como los objetos EL-S/1000 y EL-L/1000.</span><span class="sxs-lookup"><span data-stu-id="e7d98-114">The elevators are set up in the Service objects form as objects, EL-S/1000 and EL-L/1000.</span></span>

<span data-ttu-id="e7d98-115">Puede vincular los objetos de servicio (EL-S/1000 y EL-L/1000) al acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-115">You attach the service objects, EL-S/1000 and EL-L/1000, to the service agreement.</span></span>

<span data-ttu-id="e7d98-116">Dado que desea registrar los cambios en la lista de materiales para el objeto de servicio a medida que sustituye las piezas de componente del objeto, deberá vincular una lista de materiales de servicio a la relación de objeto de servicio, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7d98-116">You want to register changes in the BOM for the service object as you replace component parts of the object, so you attach a service BOM to the service object relation, as described in the following table.</span></span>

| <span data-ttu-id="e7d98-117">Objeto de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-117">Service object</span></span> | <span data-ttu-id="e7d98-118">Relación - Acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-118">Relation – Service agreement</span></span> | <span data-ttu-id="e7d98-119">L. MAT de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-119">Service BOM</span></span>   |
|----------------|------------------------------|---------------|
| <span data-ttu-id="e7d98-120">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-120">EL-S/1000</span></span>      | <span data-ttu-id="e7d98-121">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="e7d98-121">ID SAL-001</span></span>                   | <span data-ttu-id="e7d98-122">L. MAT-EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-122">BOM-EL-S/1000</span></span> |
| <span data-ttu-id="e7d98-123">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-123">EL-L/1000</span></span>      | <span data-ttu-id="e7d98-124">ID SAL-001</span><span class="sxs-lookup"><span data-stu-id="e7d98-124">ID SAL-001</span></span>                   | <span data-ttu-id="e7d98-125">L. MAT-EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-125">BOM-EL-L/1000</span></span> |

<span data-ttu-id="e7d98-126">Dado que existen relaciones de objeto de servicio para el acuerdo, ahora puede crear líneas de acuerdo de servicio con estos objetos, tal como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7d98-126">Because there are service object relations for the agreement, you can now create service agreement lines with these objects, as shown in the following table.</span></span>

| <span data-ttu-id="e7d98-127">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="e7d98-127">Transaction type</span></span> | <span data-ttu-id="e7d98-128">Categoría</span><span class="sxs-lookup"><span data-stu-id="e7d98-128">Category</span></span>           | <span data-ttu-id="e7d98-129">Objeto de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-129">Service object</span></span> |
|------------------|--------------------|----------------|
| <span data-ttu-id="e7d98-130">Hora</span><span class="sxs-lookup"><span data-stu-id="e7d98-130">Hour</span></span>             | <span data-ttu-id="e7d98-131">Inspección</span><span class="sxs-lookup"><span data-stu-id="e7d98-131">Inspection</span></span>         | <span data-ttu-id="e7d98-132">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-132">EL-S/1000</span></span>      |
| <span data-ttu-id="e7d98-133">Hora</span><span class="sxs-lookup"><span data-stu-id="e7d98-133">Hour</span></span>             | <span data-ttu-id="e7d98-134">Limpieza de la caja de cambios</span><span class="sxs-lookup"><span data-stu-id="e7d98-134">Gear box cleaning</span></span>  | <span data-ttu-id="e7d98-135">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-135">EL-S/1000</span></span>      |
| <span data-ttu-id="e7d98-136">Artículo</span><span class="sxs-lookup"><span data-stu-id="e7d98-136">Item</span></span>             | <span data-ttu-id="e7d98-137">Material de limpieza</span><span class="sxs-lookup"><span data-stu-id="e7d98-137">Cleaning materials</span></span> | <span data-ttu-id="e7d98-138">EL-S/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-138">EL-S/1000</span></span>      |
| <span data-ttu-id="e7d98-139">Hora</span><span class="sxs-lookup"><span data-stu-id="e7d98-139">Hour</span></span>             | <span data-ttu-id="e7d98-140">Inspección</span><span class="sxs-lookup"><span data-stu-id="e7d98-140">Inspection</span></span>         | <span data-ttu-id="e7d98-141">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-141">EL-L/1000</span></span>      |
| <span data-ttu-id="e7d98-142">Hora</span><span class="sxs-lookup"><span data-stu-id="e7d98-142">Hour</span></span>             | <span data-ttu-id="e7d98-143">Limpieza de la caja de cambios</span><span class="sxs-lookup"><span data-stu-id="e7d98-143">Gearbox cleaning</span></span>   | <span data-ttu-id="e7d98-144">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-144">EL-L/1000</span></span>      |
| <span data-ttu-id="e7d98-145">Artículo</span><span class="sxs-lookup"><span data-stu-id="e7d98-145">Item</span></span>             | <span data-ttu-id="e7d98-146">Material de limpieza</span><span class="sxs-lookup"><span data-stu-id="e7d98-146">Cleaning materials</span></span> | <span data-ttu-id="e7d98-147">EL-L/1000</span><span class="sxs-lookup"><span data-stu-id="e7d98-147">EL-L/1000</span></span>      |

<span data-ttu-id="e7d98-148">Durante una visita de servicio, deberá sustituir la caja de cambios del ascensor EL-S/1000.</span><span class="sxs-lookup"><span data-stu-id="e7d98-148">On a service visit, you have to replace the gearbox for elevator EL-S/1000.</span></span> <span data-ttu-id="e7d98-149">Para sustituir una pieza de componente del objeto, puede obtener acceso al Diseñador de L. MAT si usa la relación de objeto de servicio configurada para el acuerdo de servicio actual.</span><span class="sxs-lookup"><span data-stu-id="e7d98-149">To replace a component part of the object, you can access the BOM Designer by using the service object relation that you set up for the current service agreement.</span></span>

<span data-ttu-id="e7d98-150">Acceso al Diseñador de L. MAT mediante una relación de objeto de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-150">Access the BOM Designer by using a service object relation</span></span>

1. <span data-ttu-id="e7d98-151">Contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="e7d98-151">Service agreements</span></span>
2. <span data-ttu-id="e7d98-152">Haga doble clic en un contrato de servicio, o haga clic en Contrato de servicio para crear un nuevo acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-152">Double-click a service agreement, or click Service agreement to create a service agreement.</span></span>
3. <span data-ttu-id="e7d98-153">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="e7d98-153">Click the Setup tab.</span></span>
4. <span data-ttu-id="e7d98-154">Hga clic en Objetos de servicio para adjuntar una L. MAT de plantilla al contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-154">Click Service objects to attach a template BOM to the service agreement.</span></span>
5. <span data-ttu-id="e7d98-155">En el formulario Objetos de servicio, haga clic en Diseñador para abrir el formulario Diseñador para modificar la L. MAT. de plantilla.</span><span class="sxs-lookup"><span data-stu-id="e7d98-155">In the Service objects form, click Designer to open the Designer form to modify the template BOM.</span></span>

## <a name="automatically-created-service-orders"></a><span data-ttu-id="e7d98-156">Pedidos de servicio creados automáticamente</span><span class="sxs-lookup"><span data-stu-id="e7d98-156">Automatically created service orders</span></span>

<span data-ttu-id="e7d98-157">Si crea pedidos de servicio automáticamente para un acuerdo de servicio, las relaciones de objeto de servicio del acuerdo también se crean en los pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7d98-157">If you automatically create service orders for a service agreement, the service object relations in the agreement are also created in the service orders.</span></span>


