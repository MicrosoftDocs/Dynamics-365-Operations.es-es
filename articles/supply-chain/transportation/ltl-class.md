---
title: Inferior a clases de camión (LTL)
description: Este tema explica qué son las clases de carga inferior a un camión (LTL) y describe cómo configurarlas en Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 295006cac0a67cd577809a1b62566de043ea55fb
ms.sourcegitcommit: 636c1bf096a8666a551b67e898da1f48feb9a187
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941819"
---
# <a name="less-than-truckload-ltl-classes"></a><span data-ttu-id="c79f0-103">Inferior a clases de camión (LTL)</span><span class="sxs-lookup"><span data-stu-id="c79f0-103">Less than truckload (LTL) classes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c79f0-104">Una clase de carga inferior a un camión (LTL) es una clase de envío de carga que se utiliza para clasificar los artículos que se pueden enviar.</span><span class="sxs-lookup"><span data-stu-id="c79f0-104">A less than truckload (LTL) class is a freight shipping class that is used to classify items that can be shipped.</span></span> <span data-ttu-id="c79f0-105">Generalmente, cada tipo de producto o mercancía tiene un código de Clasificación Nacional de Transporte de Carga Motorizada (NMFC) que corresponde a un número de clase de carga específico para envíos LTL.</span><span class="sxs-lookup"><span data-stu-id="c79f0-105">Generally, every type of product or commodity has a National Motor Freight Classification (NMFC) code that corresponds to a specific freight class number for LTL shipments.</span></span> <span data-ttu-id="c79f0-106">Las clases de carga LTL representan categorías de artículos, mientras que los códigos NMFC están relacionados con productos específicos en cada una de las 18 clases de carga.</span><span class="sxs-lookup"><span data-stu-id="c79f0-106">LTL freight classes represent categories of items, whereas NMFC codes are related to specific commodities in each of the 18 freight classes.</span></span>

<span data-ttu-id="c79f0-107">Esta característica le permite usar su sistema para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c79f0-107">This feature lets you use your system to perform the following tasks:</span></span>

- <span data-ttu-id="c79f0-108">Defina las clases de flete LTL que se utilizan en su empresa.</span><span class="sxs-lookup"><span data-stu-id="c79f0-108">Define the LTL freight classes that are used at your company.</span></span>
- <span data-ttu-id="c79f0-109">Asigne cada clase LTL a un código NMFC en la página **Códigos NMFC**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-109">Assign each LTL class to an NMFC code on the **NMFC Codes** page.</span></span> <span data-ttu-id="c79f0-110">Para más información, vea [Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)](nmfc-codes.md).</span><span class="sxs-lookup"><span data-stu-id="c79f0-110">For more information, see [National Motor Freight Classification (NMFC) codes](nmfc-codes.md).</span></span>
- <span data-ttu-id="c79f0-111">Asigne un código NMFC (y por lo tanto su código LTL asociado) a cada producto en la página **Productos**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-111">Assign an NMFC code (and therefore its associated LTL code) to each product on the **Products** page.</span></span>
- <span data-ttu-id="c79f0-112">Evalúe con precisión la clase LTL de cada producto al que se le asigna un código NMFC.</span><span class="sxs-lookup"><span data-stu-id="c79f0-112">Accurately assess the LTL class of each product that an NMFC code is assigned to.</span></span>
- <span data-ttu-id="c79f0-113">Determine los requisitos de embalaje para cada clase de LTL comprobando los estándares internacionales de LTL.</span><span class="sxs-lookup"><span data-stu-id="c79f0-113">Determine packing requirements for each LTL class by checking the international LTL standards.</span></span> <span data-ttu-id="c79f0-114">De esta manera, se asegura de que sus productos estén bien protegidos y se envíen de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c79f0-114">In this way, you ensure that your products will be well protected and safely shipped.</span></span>
- <span data-ttu-id="c79f0-115">Obtenga estimaciones de envío precisas, basadas en la clase de carga LTL para cada producto.</span><span class="sxs-lookup"><span data-stu-id="c79f0-115">Get accurate shipping estimates, based on the LTL freight class for each product.</span></span>

<span data-ttu-id="c79f0-116">En este tema se describe cómo crear clases LTL en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c79f0-116">This topic describes how to create LTL classes in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="create-an-ltl-class"></a><span data-ttu-id="c79f0-117">Crear una clase LTL</span><span class="sxs-lookup"><span data-stu-id="c79f0-117">Create an LTL class</span></span>

<span data-ttu-id="c79f0-118">Para crear una clase LTL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c79f0-118">To create an LTL class, follow these steps.</span></span>

1. <span data-ttu-id="c79f0-119">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c79f0-119">Follow one of these steps:</span></span>

    - <span data-ttu-id="c79f0-120">Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Clases LTL**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-120">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
    - <span data-ttu-id="c79f0-121">Vaya a **Administración de transporte \> Configuración \> Estándares de transporte \> Clases LTL**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-121">Go to **Transportation management \> Setup \> Transportation standards \> LTL classes**.</span></span>

2. <span data-ttu-id="c79f0-122">En el panel de acciones, seleccione **Nueva** para crear una clase LTL.</span><span class="sxs-lookup"><span data-stu-id="c79f0-122">On the Action Pane, select **New** to create an LTL class.</span></span> <span data-ttu-id="c79f0-123">Entonces establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c79f0-123">Then set the following fields:</span></span>

    - <span data-ttu-id="c79f0-124">**Clase LTL**: introduzca el identificador (ID) de clase LTL interno de su empresa para el tipo de producto.</span><span class="sxs-lookup"><span data-stu-id="c79f0-124">**LTL class** – Enter your company's internal LTL class identifier (ID) for the commodity type.</span></span> <span data-ttu-id="c79f0-125">La mayoría de las empresas utilizan el estándar internacional.</span><span class="sxs-lookup"><span data-stu-id="c79f0-125">Most companies use the international standard.</span></span> <span data-ttu-id="c79f0-126">En ese caso, el valor de este campo coincidirá con el valor del campo **Clase**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-126">In that case, the value of this field will match the value of the **Class** field.</span></span> <span data-ttu-id="c79f0-127">Sin embargo, si su empresa utiliza su propio estándar, introduzca un código que se ajuste a ese estándar.</span><span class="sxs-lookup"><span data-stu-id="c79f0-127">However, if your company uses its own standard, enter a code that conforms to that standard.</span></span>
    - <span data-ttu-id="c79f0-128">**Nombre**: introduzca un nombre descriptivo que le ayudará a usted y a otros usuarios a seleccionar la clase LTL correcta para cada código NMFC.</span><span class="sxs-lookup"><span data-stu-id="c79f0-128">**Name** – Enter a descriptive name that will help you and other users select the correct LTL class for each NMFC code.</span></span>
    - <span data-ttu-id="c79f0-129">**Clase**: introduzca el id. de clase LTL estándar internacional para el tipo de producto.</span><span class="sxs-lookup"><span data-stu-id="c79f0-129">**Class** – Enter the international standard LTL class ID for the commodity type.</span></span> <span data-ttu-id="c79f0-130">El código que introduzca aquí debe cumplir con el estándar oficial.</span><span class="sxs-lookup"><span data-stu-id="c79f0-130">The code that you enter here must conform to the official standard.</span></span>

## <a name="example-set-up-ltl-classes"></a><span data-ttu-id="c79f0-131">Ejemplo: configurar clases LTL</span><span class="sxs-lookup"><span data-stu-id="c79f0-131">Example: Set up LTL classes</span></span>

<span data-ttu-id="c79f0-132">El siguiente ejemplo muestra cómo configurar dos clases LTL diferentes que puede utilizar con diferentes tipos de productos.</span><span class="sxs-lookup"><span data-stu-id="c79f0-132">The following example shows how to set up two different LTL classes that you can use with different types of products.</span></span>

1. <span data-ttu-id="c79f0-133">Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Clases LTL**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-133">Go to **Warehouse management \> Setup \> Inventory \> LTL classes**.</span></span>
1. <span data-ttu-id="c79f0-134">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-134">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c79f0-135">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c79f0-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c79f0-136">**Clase LTL:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="c79f0-136">**LTL class:** *92.5*</span></span>
    - <span data-ttu-id="c79f0-137">**Nombre:** *Ordenadores, monitores, refrigeradores*</span><span class="sxs-lookup"><span data-stu-id="c79f0-137">**Name:** *Computers, monitors, refrigerators*</span></span>
    - <span data-ttu-id="c79f0-138">**Clase:** *92.5*</span><span class="sxs-lookup"><span data-stu-id="c79f0-138">**Class:** *92.5*</span></span>

1. <span data-ttu-id="c79f0-139">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-139">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="c79f0-140">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-140">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c79f0-141">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c79f0-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c79f0-142">**Clase LTL:** *125*</span><span class="sxs-lookup"><span data-stu-id="c79f0-142">**LTL class:** *125*</span></span>
    - <span data-ttu-id="c79f0-143">**Nombre:** *Pequeños electrodomésticos*</span><span class="sxs-lookup"><span data-stu-id="c79f0-143">**Name:** *Small household appliances*</span></span>
    - <span data-ttu-id="c79f0-144">**Clase:** *125*</span><span class="sxs-lookup"><span data-stu-id="c79f0-144">**Class:** *125*</span></span>

1. <span data-ttu-id="c79f0-145">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c79f0-145">On the Action Pane, select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c79f0-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c79f0-146">Additional resources</span></span>

- [<span data-ttu-id="c79f0-147">Códigos de clasificación nacional de transporte de mercancías por motor (NMFC)</span><span class="sxs-lookup"><span data-stu-id="c79f0-147">National Motor Freight Classification (NMFC) codes</span></span>](nmfc-codes.md)
- [<span data-ttu-id="c79f0-148">Crear un conocimiento de embarque</span><span class="sxs-lookup"><span data-stu-id="c79f0-148">Create a bill of lading</span></span>](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
