---
title: Crear directivas de compra
description: Este procedimiento le muestra cómo crear directivas de compra para alinearlas con sus procesos empresariales para compras.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicyParameters, SysPolicy, RequisitionPurposeRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3bd4d6f8625c91f2190e994f04cbec4548272f04
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557834"
---
# <a name="create-purchasing-policies"></a><span data-ttu-id="6f942-103">Crear directivas de compra</span><span class="sxs-lookup"><span data-stu-id="6f942-103">Create purchasing policies</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6f942-104">Este procedimiento le muestra cómo crear directivas de compra para alinearlas con sus procesos empresariales para compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-104">This procedure shows you how to create purchasing policies to align with your business processes for purchasing.</span></span> <span data-ttu-id="6f942-105">Para crear directivas de compra, es necesario configurar los parámetros de directiva de compra.</span><span class="sxs-lookup"><span data-stu-id="6f942-105">Before you can create purchasing policies, you must set up the purchasing policy parameters.</span></span> <span data-ttu-id="6f942-106">Es posible crear, modificar y retirar una directiva de compras, pero no puede eliminar una directiva de compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-106">It’s possible to create, modify, and retire a purchasing policy, but you can’t delete a purchasing policy.</span></span> <span data-ttu-id="6f942-107">Este procedimiento lo realizará normalmente un director de compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-107">This procedure would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="6f942-108">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="6f942-108">You can use this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-policy-parameters"></a><span data-ttu-id="6f942-109">Configuración de los parámetros de directivas</span><span class="sxs-lookup"><span data-stu-id="6f942-109">Set up policy parameters</span></span>
1. <span data-ttu-id="6f942-110">Vaya a Directivas de compra.</span><span class="sxs-lookup"><span data-stu-id="6f942-110">Go to Purchasing policies.</span></span>
2. <span data-ttu-id="6f942-111">Haga clic en parámetros.</span><span class="sxs-lookup"><span data-stu-id="6f942-111">Click Parameters.</span></span>
    * <span data-ttu-id="6f942-112">Las reglas de prioridad de directivas se aplican a diferentes niveles de su organización.</span><span class="sxs-lookup"><span data-stu-id="6f942-112">Policy precedence rules apply to different levels in your organization.</span></span> <span data-ttu-id="6f942-113">Las unidades organizativas que se muestran dependen de su jerarquía organizativa y de a qué niveles de la jerarquía se ha asignado el propósito del Control interno de compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-113">The organizational units that are shown depend on your organizational hierarchy, and on which levels in the hierarchy have been assigned the purpose of Procurement internal control.</span></span> <span data-ttu-id="6f942-114">Por ejemplo, su organización puede tener entidades jurídicas, centros de costes, regiones y departamentos, pero es posible que solo algunos de estos tengan un propósito de jerarquía del Control interno de compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-114">For example, your organization might have legal entities, cost centers, regions, and departments, but it may be that only some of these have a hierarchy purpose of Procurement internal control.</span></span> <span data-ttu-id="6f942-115">De forma predeterminada, la organización de tipo Empresa está disponible.</span><span class="sxs-lookup"><span data-stu-id="6f942-115">As a default, the organization of type Company is available.</span></span>  
3. <span data-ttu-id="6f942-116">Haga clic en la pestaña Parámetros de tipo de regla de directiva.</span><span class="sxs-lookup"><span data-stu-id="6f942-116">Click the Policy rule type parameters tab.</span></span>
4. <span data-ttu-id="6f942-117">En el árbol, seleccione "Directiva de compra\Regla de control de la solicitud de compra".</span><span class="sxs-lookup"><span data-stu-id="6f942-117">In the tree, select 'Purchasing policy\Purchase requisition control rule'.</span></span>
    * <span data-ttu-id="6f942-118">El orden de prioridad para la resolución de directivas se define en el nivel de directiva.</span><span class="sxs-lookup"><span data-stu-id="6f942-118">You define the order of precedence for policy resolution at the policy level.</span></span> <span data-ttu-id="6f942-119">Sin embargo, para algunos tipos de directivas, puede anular el orden de prioridad para tipos de reglas de directivas individuales.</span><span class="sxs-lookup"><span data-stu-id="6f942-119">However, for some policy types, you can override the order of precedence for individual policy rule types.</span></span> <span data-ttu-id="6f942-120">Por ejemplo, puede definir la orden de prioridad para que las directivas de compra sean: centro de coste, departamento, empresa.</span><span class="sxs-lookup"><span data-stu-id="6f942-120">For example, you might define the order of precedence for purchasing policies to be: cost center, department, company.</span></span> <span data-ttu-id="6f942-121">Para la regla de directivas de catálogo, puede que desee que el orden de prioridad sea: departamento, centro de coste, empresa.</span><span class="sxs-lookup"><span data-stu-id="6f942-121">For the catalog policy rule, you might want the order of precedence to be: department, cost center, company.</span></span> <span data-ttu-id="6f942-122">Puede cambiar el orden de prioridad para la regla de directivas del catálogo.</span><span class="sxs-lookup"><span data-stu-id="6f942-122">You can change the order of precedence for the Catalog policy rule.</span></span> <span data-ttu-id="6f942-123">Cuando un trabajador cree una solicitud, el catálogo que se muestra está determinado por las directivas asociadas con el departamento del trabajador, su centro de coste y su empresa, por este orden.</span><span class="sxs-lookup"><span data-stu-id="6f942-123">When a worker creates a requisition, the catalog that is displayed is determined by the policies that are associated with the worker’s department, then their cost center, and then their company.</span></span>  
    * <span data-ttu-id="6f942-124">Si se muestra más de un nivel de organización, puede utilizar las flechas arriba/abajo para establecer la orden de prioridad para la Regla de control de la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="6f942-124">If there’s more than one organizational level listed, you can use the Up/Down arrows to set the order of precedence for the Purchase requisition control rule.</span></span>  
5. <span data-ttu-id="6f942-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f942-125">Close the page.</span></span>

## <a name="create-a-new-policy"></a><span data-ttu-id="6f942-126">Crear una nueva directiva</span><span class="sxs-lookup"><span data-stu-id="6f942-126">Create a new policy</span></span>
1. <span data-ttu-id="6f942-127">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6f942-127">Click New.</span></span>
2. <span data-ttu-id="6f942-128">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f942-128">In the Name field, type a value.</span></span>
3. <span data-ttu-id="6f942-129">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f942-129">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6f942-130">Una única directiva de compra solo se puede aplicar a una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="6f942-130">A single purchasing policy can only apply to one organization hierarchy.</span></span> <span data-ttu-id="6f942-131">Por ejemplo, podría tener una jerarquía llamada “Geográfica” y otra llamada “Departamento” y tener una directiva de compras diferente para cada una.</span><span class="sxs-lookup"><span data-stu-id="6f942-131">For example, you could have one hierarchy called “Geographic” and one called “Department”, and have a different purchasing policy for each.</span></span>  
    * <span data-ttu-id="6f942-132">Seleccione una organización a la que se debería aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="6f942-132">Select an organization that the policy should apply to.</span></span>  
4. <span data-ttu-id="6f942-133">Haga clic en la flecha para agregar la organización.</span><span class="sxs-lookup"><span data-stu-id="6f942-133">Click the arrow to add the selected organization.</span></span>
    * <span data-ttu-id="6f942-134">Puede repetir este proceso para agregar más organizaciones.</span><span class="sxs-lookup"><span data-stu-id="6f942-134">You can repeat this process to add more organizations.</span></span>  

## <a name="add-a-policy-rule"></a><span data-ttu-id="6f942-135">Agregar una regla de directivas</span><span class="sxs-lookup"><span data-stu-id="6f942-135">Add a policy rule</span></span>
1. <span data-ttu-id="6f942-136">En la lista Tipo de regla de directivas, seleccione Regla de propósito de pedido.</span><span class="sxs-lookup"><span data-stu-id="6f942-136">In the Policy rule type list, select Requisition purpose rule.</span></span>
    * <span data-ttu-id="6f942-137">Creará una regla que establezca el propósito de pedido predeterminado en el tipo Consumo pero que permita que se seleccione en su lugar el Tipo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="6f942-137">You’ll create a rule that sets the default requisition purpose to type Consumption but allows the Replenishment type to be selected instead.</span></span>  
2. <span data-ttu-id="6f942-138">Haga clic en Crear regla de directivas.</span><span class="sxs-lookup"><span data-stu-id="6f942-138">Click Create policy rule.</span></span>
3. <span data-ttu-id="6f942-139">Seleccione Sí en el campo Permitir anulación manual.</span><span class="sxs-lookup"><span data-stu-id="6f942-139">Select Yes in the Allow manual override field.</span></span>
4. <span data-ttu-id="6f942-140">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="6f942-140">Click Close.</span></span>
    * <span data-ttu-id="6f942-141">Ahora puede configurar otras reglas de directivas para la directiva de compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-141">Now you can set up other policy rules for the purchasing policy.</span></span>   <span data-ttu-id="6f942-142">Observe que un tipo de la regla de directiva no puede tener reglas de superposición que estén activas al mismo tiempo dentro de una sola directiva de compras.</span><span class="sxs-lookup"><span data-stu-id="6f942-142">Note that a Policy rule type cannot have overlapping rules that are active at the same time within a single procurement policy.</span></span>  
5. <span data-ttu-id="6f942-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f942-143">Close the page.</span></span>
6. <span data-ttu-id="6f942-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f942-144">Close the page.</span></span>

