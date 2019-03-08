---
title: Configurar precios basados en atributos para productos configurables
description: Este procedimiento muestra cómo configurar unos precios en función del atributo.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8568b5f4933ae58bc2d55a169c798668e03bed2a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "333792"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a><span data-ttu-id="1c63b-103">Configurar precios basados en atributos para productos configurables</span><span class="sxs-lookup"><span data-stu-id="1c63b-103">Set up attribute-based pricing for configurable products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c63b-104">Este procedimiento muestra cómo configurar unos precios en función del atributo.</span><span class="sxs-lookup"><span data-stu-id="1c63b-104">This procedure shows how to set up attribute-based pricing.</span></span> <span data-ttu-id="1c63b-105">Como requisito previo, debe tener un modelo de configuración de productos con uno o más componentes y atributos.</span><span class="sxs-lookup"><span data-stu-id="1c63b-105">As a prerequisite, you must have a product configuration model that has one or more components and attributes.</span></span> <span data-ttu-id="1c63b-106">Este ejemplo usa el modelo de producto Altavoz de gama alta en los datos de demostración de la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="1c63b-106">This example uses the High End Speaker product model in the USMF demo data company.</span></span> <span data-ttu-id="1c63b-107">Normalmente, un responsable de productos utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c63b-107">Typically, a product manager uses this procedure.</span></span>


## <a name="create-a-new-price-model"></a><span data-ttu-id="1c63b-108">Cree un nuevo modelo de precio</span><span class="sxs-lookup"><span data-stu-id="1c63b-108">Create a new price model</span></span>
1. <span data-ttu-id="1c63b-109">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="1c63b-109">Click Product variant model definition.</span></span>
2. <span data-ttu-id="1c63b-110">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="1c63b-110">Click Product configuration models.</span></span>
3. <span data-ttu-id="1c63b-111">En la lista, seleccione la línea Altavoz de gama alta, pero no haga clic en el vínculo del nombre.</span><span class="sxs-lookup"><span data-stu-id="1c63b-111">In the list, select the High End Speaker line, but don’t click the link for the name.</span></span>
4. <span data-ttu-id="1c63b-112">En el panel de acciones, haga clic en Modelo.</span><span class="sxs-lookup"><span data-stu-id="1c63b-112">On the Action Pane, click Model.</span></span>
5. <span data-ttu-id="1c63b-113">Haga clic en Modelos de precio.</span><span class="sxs-lookup"><span data-stu-id="1c63b-113">Click Price models.</span></span>
6. <span data-ttu-id="1c63b-114">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1c63b-114">Click New.</span></span>
7. <span data-ttu-id="1c63b-115">En el campo Nombre de modelo de precio, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1c63b-115">In the Price model name field, type a value.</span></span>
    * <span data-ttu-id="1c63b-116">Use un nombre que permita identificar fácilmente el modelo.</span><span class="sxs-lookup"><span data-stu-id="1c63b-116">Use a name that makes the model easy to identify.</span></span>  
8. <span data-ttu-id="1c63b-117">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1c63b-117">In the Description field, type a value.</span></span>
9. <span data-ttu-id="1c63b-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1c63b-118">Click Save.</span></span>

## <a name="add-price-elements"></a><span data-ttu-id="1c63b-119">Agregue elementos de precio</span><span class="sxs-lookup"><span data-stu-id="1c63b-119">Add price elements</span></span>
1. <span data-ttu-id="1c63b-120">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="1c63b-120">Click Edit.</span></span>
    * <span data-ttu-id="1c63b-121">Cada componente de un modelo de producto puede tener un elemento de precio base y cualquier número de reglas de la expresión del precio.</span><span class="sxs-lookup"><span data-stu-id="1c63b-121">Each component in a product model can have a base price element and any number of price expression rules.</span></span> <span data-ttu-id="1c63b-122">También puede agregar precios en divisas distintas.</span><span class="sxs-lookup"><span data-stu-id="1c63b-122">You can also add prices in different currencies.</span></span>  
2. <span data-ttu-id="1c63b-123">En el campo Expresión de precio base, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1c63b-123">In the Base price expression field, type a value.</span></span>
    * <span data-ttu-id="1c63b-124">Por ejemplo, escriba 100.</span><span class="sxs-lookup"><span data-stu-id="1c63b-124">For example, type 100.</span></span>   <span data-ttu-id="1c63b-125">Una expresión del precio base puede ser un valor numérico, o puede estar compuesto por un cálculo aritmético que contenga uno o varios atributos.</span><span class="sxs-lookup"><span data-stu-id="1c63b-125">A base price expression can be a numerical value, or it can consist of an arithmetic calculation that involves one or more attributes.</span></span>  
3. <span data-ttu-id="1c63b-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="1c63b-126">Click Add.</span></span>
4. <span data-ttu-id="1c63b-127">En el campo Nombre, escriba "Palo de rosa".</span><span class="sxs-lookup"><span data-stu-id="1c63b-127">In the Name field, type ‘Rosewood’.</span></span>
    * <span data-ttu-id="1c63b-128">Las ayudas del nombre de la expresión del precio permiten identificar lo que representa el elemento de precio.</span><span class="sxs-lookup"><span data-stu-id="1c63b-128">The price expression name helps identify what the price element represents.</span></span> <span data-ttu-id="1c63b-129">En este ejemplo, estamos creando un elemento de precio para la opción de acabado de la caja del altavoz en madera de palo de rosa.</span><span class="sxs-lookup"><span data-stu-id="1c63b-129">In this example, we are creating a price element for the Rosewood speaker cabinet finish option.</span></span>  
5. <span data-ttu-id="1c63b-130">Haga clic en Editar condición.</span><span class="sxs-lookup"><span data-stu-id="1c63b-130">Click Edit condition.</span></span>
    * <span data-ttu-id="1c63b-131">Una condición de precio permite garantizar que un elemento de la expresión del precio se incluya en el precio de venta únicamente si está presente una combinación específica de atributos.</span><span class="sxs-lookup"><span data-stu-id="1c63b-131">A price condition helps guarantee that a price expression element is included in the sales price only if a specific combination of attributes is present.</span></span>  
6. <span data-ttu-id="1c63b-132">En el campo ConstraintBody, especifique "CabinetFinish=="Rosewood"".</span><span class="sxs-lookup"><span data-stu-id="1c63b-132">In the ConstraintBody field, enter 'CabinetFinish=="Rosewood"'.</span></span>
7. <span data-ttu-id="1c63b-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1c63b-133">Click OK.</span></span>
8. <span data-ttu-id="1c63b-134">En el campo Expresión, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1c63b-134">In the Expression field, type a value.</span></span>
    * <span data-ttu-id="1c63b-135">Por ejemplo, escriba 50.</span><span class="sxs-lookup"><span data-stu-id="1c63b-135">For example, type 50.</span></span>  
9. <span data-ttu-id="1c63b-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1c63b-136">Close the page.</span></span>
10. <span data-ttu-id="1c63b-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1c63b-137">Close the page.</span></span>

