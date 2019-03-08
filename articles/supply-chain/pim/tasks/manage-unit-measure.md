---
title: Gestionar la unidad de medida
description: Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e208b7f1faab77f2b97ff7b440a228656684fca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "358931"
---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="2eff4-103">Gestionar la unidad de medida</span><span class="sxs-lookup"><span data-stu-id="2eff4-103">Manage unit of measure</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2eff4-104">Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2eff4-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="2eff4-105">Puede revisar este procedimiento con datos de demostración, o bien, utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="2eff4-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="2eff4-106">Vaya a Mantenimiento de producto emitido.</span><span class="sxs-lookup"><span data-stu-id="2eff4-106">Go to Released product maintenance.</span></span>
2. <span data-ttu-id="2eff4-107">Haga clic en Unidades.</span><span class="sxs-lookup"><span data-stu-id="2eff4-107">Click Units.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="2eff4-108">Creación de una unidad de medida</span><span class="sxs-lookup"><span data-stu-id="2eff4-108">Create a unit of measure</span></span>
1. <span data-ttu-id="2eff4-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2eff4-109">Click New.</span></span>
2. <span data-ttu-id="2eff4-110">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-110">In the Unit field, type a value.</span></span>
    * <span data-ttu-id="2eff4-111">Especifique el identificador o el símbolo que usar al hacer referencia a la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="2eff4-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="2eff4-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="2eff4-113">Especifique un nombre descriptivo para la unidad de medida en el idioma del sistema.</span><span class="sxs-lookup"><span data-stu-id="2eff4-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="2eff4-114">En el campo Clase de unidad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2eff4-114">In the Unit class field, select an option.</span></span>
    * <span data-ttu-id="2eff4-115">La clase de unidad define a qué agrupación lógica de medida, como área, masa o cantidad, pertenece la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="2eff4-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="2eff4-116">En el campo Precisión decimal, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="2eff4-116">In the Decimal precision field, enter a number.</span></span>
    * <span data-ttu-id="2eff4-117">Especifique el número de decimales a los que se redondea la unidad de medida convertida cuando se completa un cálculo para la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="2eff4-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="2eff4-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="2eff4-118">Click Save.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="2eff4-119">Definición de conversiones de unidades</span><span class="sxs-lookup"><span data-stu-id="2eff4-119">Define unit translations</span></span>
1. <span data-ttu-id="2eff4-120">Haga clic en Textos de unidad.</span><span class="sxs-lookup"><span data-stu-id="2eff4-120">Click Unit texts.</span></span>
2. <span data-ttu-id="2eff4-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2eff4-121">Click New.</span></span>
    * <span data-ttu-id="2eff4-122">Use el texto de unidad para crear una traducción del identificador o de un símbolo que represente a la unidad de medida para su uso en documentos externos en los idiomas específicos del cliente o del proveedor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="2eff4-123">En el campo Idioma, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-123">In the Language field, enter or select a value.</span></span>
4. <span data-ttu-id="2eff4-124">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-124">In the Text field, type a value.</span></span>
5. <span data-ttu-id="2eff4-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="2eff4-125">Click Save.</span></span>
6. <span data-ttu-id="2eff4-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2eff4-126">Close the page.</span></span>
7. <span data-ttu-id="2eff4-127">Haga clic en Descripciones de unidades convertidas.</span><span class="sxs-lookup"><span data-stu-id="2eff4-127">Click Translated unit descriptions.</span></span>
8. <span data-ttu-id="2eff4-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2eff4-128">Click New.</span></span>
    * <span data-ttu-id="2eff4-129">Defina descripciones en idiomas específicos para la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="2eff4-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="2eff4-130">En el campo Idioma, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-130">In the Language field, enter or select a value.</span></span>
10. <span data-ttu-id="2eff4-131">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-131">In the Description field, type a value.</span></span>
11. <span data-ttu-id="2eff4-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="2eff4-132">Click Save.</span></span>
12. <span data-ttu-id="2eff4-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2eff4-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="2eff4-134">Definición de reglas de conversión de unidades</span><span class="sxs-lookup"><span data-stu-id="2eff4-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="2eff4-135">Haga clic en Conversiones de unidades.</span><span class="sxs-lookup"><span data-stu-id="2eff4-135">Click Unit conversions.</span></span>
    * <span data-ttu-id="2eff4-136">Defina reglas para convertir la unidad de medida a y de otras unidades de medida en la clase de unidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2eff4-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="2eff4-137">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="2eff4-137">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="2eff4-138">En el campo Factor, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="2eff4-138">In the Factor field, enter a number.</span></span>
    * <span data-ttu-id="2eff4-139">Factor de conversión entre la unidad de origen y la de destino.</span><span class="sxs-lookup"><span data-stu-id="2eff4-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="2eff4-140">Por ejemplo, el factor de conversión de centímetros a metros es 100 porque hay 100 centímetros en un metro.</span><span class="sxs-lookup"><span data-stu-id="2eff4-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="2eff4-141">En el campo Hasta unidad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="2eff4-141">In the To unit field, enter or select a value.</span></span>
5. <span data-ttu-id="2eff4-142">En el campo Redondeo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2eff4-142">In the Rounding field, select an option.</span></span>
    * <span data-ttu-id="2eff4-143">Defina cómo se debe redondear el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="2eff4-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="2eff4-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2eff4-144">Click OK.</span></span>
7. <span data-ttu-id="2eff4-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2eff4-145">Close the page.</span></span>

