--- 
title: Gestionar la unidad de medida
description: "Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas."
author: sorenva
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: f9fc2374bb80126e092929182a2c4c8fc8aba9f5
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="4e56b-103">Gestionar la unidad de medida</span><span class="sxs-lookup"><span data-stu-id="4e56b-103">Manage unit of measure</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e56b-104">Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4e56b-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="4e56b-105">Puede revisar este procedimiento con datos de demostración, o bien, utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="4e56b-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="4e56b-106">Vaya a Mantenimiento de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="4e56b-106">Go to Released product maintenance.</span></span>
2. <span data-ttu-id="4e56b-107">Haga clic en Unidades.</span><span class="sxs-lookup"><span data-stu-id="4e56b-107">Click Units.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="4e56b-108">Creación de una unidad de medida</span><span class="sxs-lookup"><span data-stu-id="4e56b-108">Create a unit of measure</span></span>
1. <span data-ttu-id="4e56b-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e56b-109">Click New.</span></span>
2. <span data-ttu-id="4e56b-110">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-110">In the Unit field, type a value.</span></span>
    * <span data-ttu-id="4e56b-111">Especifique el identificador o el símbolo que usar al hacer referencia a la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="4e56b-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="4e56b-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4e56b-113">Especifique un nombre descriptivo para la unidad de medida en el idioma del sistema.</span><span class="sxs-lookup"><span data-stu-id="4e56b-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="4e56b-114">En el campo Clase de unidad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="4e56b-114">In the Unit class field, select an option.</span></span>
    * <span data-ttu-id="4e56b-115">La clase de unidad define a qué agrupación lógica de medida, como área, masa o cantidad, pertenece la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="4e56b-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="4e56b-116">En el campo Precisión decimal, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="4e56b-116">In the Decimal precision field, enter a number.</span></span>
    * <span data-ttu-id="4e56b-117">Especifique el número de decimales a los que se redondea la unidad de medida convertida cuando se completa un cálculo para la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="4e56b-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="4e56b-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e56b-118">Click Save.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="4e56b-119">Definición de conversiones de unidades</span><span class="sxs-lookup"><span data-stu-id="4e56b-119">Define unit translations</span></span>
1. <span data-ttu-id="4e56b-120">Haga clic en Textos de unidad.</span><span class="sxs-lookup"><span data-stu-id="4e56b-120">Click Unit texts.</span></span>
2. <span data-ttu-id="4e56b-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e56b-121">Click New.</span></span>
    * <span data-ttu-id="4e56b-122">Use el texto de unidad para crear una traducción del identificador o de un símbolo que represente a la unidad de medida para su uso en documentos externos en los idiomas específicos del cliente o del proveedor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="4e56b-123">En el campo Idioma, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-123">In the Language field, enter or select a value.</span></span>
4. <span data-ttu-id="4e56b-124">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-124">In the Text field, type a value.</span></span>
5. <span data-ttu-id="4e56b-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e56b-125">Click Save.</span></span>
6. <span data-ttu-id="4e56b-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e56b-126">Close the page.</span></span>
7. <span data-ttu-id="4e56b-127">Haga clic en Descripciones de unidades convertidas.</span><span class="sxs-lookup"><span data-stu-id="4e56b-127">Click Translated unit descriptions.</span></span>
8. <span data-ttu-id="4e56b-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e56b-128">Click New.</span></span>
    * <span data-ttu-id="4e56b-129">Defina descripciones en idiomas específicos para la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="4e56b-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="4e56b-130">En el campo Idioma, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-130">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="4e56b-131">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-131">In the Description field, type a value.</span></span>
11. <span data-ttu-id="4e56b-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e56b-132">Click Save.</span></span>
12. <span data-ttu-id="4e56b-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e56b-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="4e56b-134">Definición de reglas de conversión de unidades</span><span class="sxs-lookup"><span data-stu-id="4e56b-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="4e56b-135">Haga clic en Conversiones de unidades.</span><span class="sxs-lookup"><span data-stu-id="4e56b-135">Click Unit conversions.</span></span>
    * <span data-ttu-id="4e56b-136">Defina reglas para convertir la unidad de medida a y de otras unidades de medida en la clase de unidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e56b-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="4e56b-137">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="4e56b-137">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="4e56b-138">En el campo Factor, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="4e56b-138">In the Factor field, enter a number.</span></span>
    * <span data-ttu-id="4e56b-139">Factor de conversión entre la unidad de origen y la de destino.</span><span class="sxs-lookup"><span data-stu-id="4e56b-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="4e56b-140">Por ejemplo, el factor de conversión de centímetros a metros es 100 porque hay 100 centímetros en un metro.</span><span class="sxs-lookup"><span data-stu-id="4e56b-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="4e56b-141">En el campo Hasta unidad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4e56b-141">In the To unit field, enter or select a value.</span></span>
5. <span data-ttu-id="4e56b-142">En el campo Redondeo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="4e56b-142">In the Rounding field, select an option.</span></span>
    * <span data-ttu-id="4e56b-143">Defina cómo se debe redondear el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="4e56b-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="4e56b-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e56b-144">Click OK.</span></span>
7. <span data-ttu-id="4e56b-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e56b-145">Close the page.</span></span>


