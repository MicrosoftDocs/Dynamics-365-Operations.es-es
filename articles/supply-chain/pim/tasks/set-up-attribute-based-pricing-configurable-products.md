---
title: Configurar precios basados en atributos para productos configurables
description: En este tema se explica cómo configurar unos precios en función del atributo.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921250"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="80646-103">Configurar precios basados en atributos para productos configurables</span><span class="sxs-lookup"><span data-stu-id="80646-103">Set up attribute-based pricing for configurable products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="80646-104">En este tema se explica cómo configurar unos precios en función del atributo.</span><span class="sxs-lookup"><span data-stu-id="80646-104">This topic explains how to set up attribute-based pricing.</span></span> <span data-ttu-id="80646-105">Como requisito previo, debe tener un modelo de configuración de productos con uno o más componentes y atributos.</span><span class="sxs-lookup"><span data-stu-id="80646-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="80646-106">Este ejemplo usa el modelo de producto Altavoz de gama alta en los datos de demostración de la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="80646-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="80646-107">Normalmente, un responsable de productos utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="80646-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="80646-108">Cree un nuevo modelo de precio</span><span class="sxs-lookup"><span data-stu-id="80646-108">Create a new price model</span></span>

1. <span data-ttu-id="80646-109">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="80646-109">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="80646-110">En la lista, seleccione la línea **Altavoz de gama alta**, pero no seleccione el vínculo del nombre.</span><span class="sxs-lookup"><span data-stu-id="80646-110">In the list, select the **High End Speaker** line, but don't select the link for the name.</span></span>
1. <span data-ttu-id="80646-111">En el panel de acciones, haga clic en **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="80646-111">On the Action Pane, select **Model**.</span></span>
1. <span data-ttu-id="80646-112">Seleccione **Modelos de precio**.</span><span class="sxs-lookup"><span data-stu-id="80646-112">Select **Price models**.</span></span>
1. <span data-ttu-id="80646-113">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="80646-113">Select **New**.</span></span>
1. <span data-ttu-id="80646-114">En el campo **Nombre de modelo de precio**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="80646-114">In the **Price model name** field, type a value.</span></span> <span data-ttu-id="80646-115">Use un nombre que permita identificar fácilmente el modelo.</span><span class="sxs-lookup"><span data-stu-id="80646-115">Use a name that makes the model easy to identify.</span></span>  
1. <span data-ttu-id="80646-116">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="80646-116">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="80646-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="80646-117">Select **Save**.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="80646-118">Agregue elementos de precio</span><span class="sxs-lookup"><span data-stu-id="80646-118">Add price elements</span></span>

1. <span data-ttu-id="80646-119">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="80646-119">Select **Edit**.</span></span> <span data-ttu-id="80646-120">Cada componente de un modelo de producto puede tener un elemento de precio base y cualquier número de reglas de la expresión del precio.</span><span class="sxs-lookup"><span data-stu-id="80646-120">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="80646-121">También puede agregar precios en divisas distintas.</span><span class="sxs-lookup"><span data-stu-id="80646-121">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="80646-122">En el campo **Expresión de precio base**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="80646-122">In the **Base price expression** field, type a value.</span></span> <span data-ttu-id="80646-123">Por ejemplo, escriba 100.</span><span class="sxs-lookup"><span data-stu-id="80646-123">For example, type 100.</span></span> <span data-ttu-id="80646-124">Una expresión del precio base puede ser un valor numérico, o puede estar compuesto por un cálculo aritmético que contenga uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="80646-124">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="80646-125">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="80646-125">Select **Add**.</span></span>
4. <span data-ttu-id="80646-126">En el campo **Nombre**, escriba `Rosewood`.</span><span class="sxs-lookup"><span data-stu-id="80646-126">In the **Name** field, type `Rosewood`.</span></span> <span data-ttu-id="80646-127">Las ayudas del nombre de la expresión del precio permiten identificar lo que representa el elemento de precio.</span><span class="sxs-lookup"><span data-stu-id="80646-127">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="80646-128">En este ejemplo, estamos creando un elemento de precio para la opción de acabado de la caja del altavoz en madera de palo de rosa.</span><span class="sxs-lookup"><span data-stu-id="80646-128">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="80646-129">Seleccione **Editar condición**.</span><span class="sxs-lookup"><span data-stu-id="80646-129">Select **Edit condition**.</span></span> <span data-ttu-id="80646-130">Una condición de precio permite garantizar que un elemento de la expresión del precio se incluya en el precio de venta únicamente si está presente una combinación específica de atributos.</span><span class="sxs-lookup"><span data-stu-id="80646-130">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="80646-131">En el campo **ConstraintBody**, introduzca `CabinetFinish=="Rosewood"`.</span><span class="sxs-lookup"><span data-stu-id="80646-131">In the **ConstraintBody** field, enter `CabinetFinish=="Rosewood"`.</span></span>
7. <span data-ttu-id="80646-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80646-132">Select **OK**.</span></span>
8. <span data-ttu-id="80646-133">En el campo **Expresión**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="80646-133">In the **Expression** field, type a value.</span></span> <span data-ttu-id="80646-134">Por ejemplo, escriba `50`.</span><span class="sxs-lookup"><span data-stu-id="80646-134">For example, type `50`.</span></span> 
9. <span data-ttu-id="80646-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="80646-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]