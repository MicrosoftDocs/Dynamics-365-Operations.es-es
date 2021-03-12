---
title: Configurar precios basados en atributos para productos configurables
description: En este tema se explica cómo configurar unos precios en función del atributo.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2f9a78902ff1a0333c46c8ad9142338678b6e7d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986788"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="f3a1b-103">Configurar precios basados en atributos para productos configurables</span><span class="sxs-lookup"><span data-stu-id="f3a1b-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3a1b-104">En este tema se explica cómo configurar unos precios en función del atributo.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="f3a1b-105">Como requisito previo, debe tener un modelo de configuración de productos con uno o más componentes y atributos.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="f3a1b-106">Este ejemplo usa el modelo de producto Altavoz de gama alta en los datos de demostración de la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="f3a1b-107">Normalmente, un responsable de productos utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="f3a1b-108">Cree un nuevo modelo de precio</span><span class="sxs-lookup"><span data-stu-id="f3a1b-108">Create a new price model</span></span>
1. <span data-ttu-id="f3a1b-109">Seleccione **Definición de modelo de variante del producto** en la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-109">Select **Product variant model definition** on the home page.</span></span>
2. <span data-ttu-id="f3a1b-110">Seleccione **Modelos de configuración del producto** en la sección **vínculos**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-110">Select **Product configuration models** in the **links** section.</span></span>
3. <span data-ttu-id="f3a1b-111">En la lista, seleccione la línea **Altavoz de gama alta**, pero no seleccione el vínculo del nombre.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-111">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
4. <span data-ttu-id="f3a1b-112">En el panel de acciones, haga clic en **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-112">On the Action Pane, select **Model**.</span></span>
5. <span data-ttu-id="f3a1b-113">Seleccione **Modelos de precio**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-113">Select **Price models**.</span></span>
6. <span data-ttu-id="f3a1b-114">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-114">Select **New**.</span></span>
7. <span data-ttu-id="f3a1b-115">En el campo **Nombre de modelo de precio**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-115">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="f3a1b-116">Use un nombre que permita identificar fácilmente el modelo.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="f3a1b-117">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-117">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="f3a1b-118">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-118">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="f3a1b-119">Agregue elementos de precio</span><span class="sxs-lookup"><span data-stu-id="f3a1b-119">Add price elements</span></span>
1. <span data-ttu-id="f3a1b-120">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-120">Select **Edit**.</span></span> <span data-ttu-id="f3a1b-121">Cada componente de un modelo de producto puede tener un elemento de precio base y cualquier número de reglas de la expresión del precio.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="f3a1b-122">También puede agregar precios en divisas distintas.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="f3a1b-123">En el campo **Expresión de precio base**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-123">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="f3a1b-124">Por ejemplo, escriba 100.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-124">For example, type 100.</span></span> <span data-ttu-id="f3a1b-125">Una expresión del precio base puede ser un valor numérico, o puede estar compuesto por un cálculo aritmético que contenga uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="f3a1b-126">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-126">Select **Add**.</span></span>
4. <span data-ttu-id="f3a1b-127">En el campo **Nombre**, escriba `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-127">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="f3a1b-128">Las ayudas del nombre de la expresión del precio permiten identificar lo que representa el elemento de precio.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="f3a1b-129">En este ejemplo, estamos creando un elemento de precio para la opción de acabado de la caja del altavoz en madera de palo de rosa.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="f3a1b-130">Seleccione **Editar condición**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-130">Select **Edit condition**.</span></span> <span data-ttu-id="f3a1b-131">Una condición de precio permite garantizar que un elemento de la expresión del precio se incluya en el precio de venta únicamente si está presente una combinación específica de atributos.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="f3a1b-132">En el campo **ConstraintBody**, introduzca `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-132">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="f3a1b-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-133">Select **OK**.</span></span>
8. <span data-ttu-id="f3a1b-134">En el campo **Expresión**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-134">In the **Expression** field, type a value.</span></span> <span data-ttu-id="f3a1b-135">Por ejemplo, escriba `50`.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-135">For example, type `50`.</span></span> 
9. <span data-ttu-id="f3a1b-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f3a1b-136">Close the page.</span></span>

