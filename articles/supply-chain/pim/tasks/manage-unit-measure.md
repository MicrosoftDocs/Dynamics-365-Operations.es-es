---
title: Gestionar la unidad de medida
description: Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71b478ca294719c20af9de16c27139aeca36bf07
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992304"
---
# <a name="manage-unit-of-measure"></a><span data-ttu-id="ba2ff-103">Gestionar la unidad de medida</span><span class="sxs-lookup"><span data-stu-id="ba2ff-103">Manage unit of measure</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba2ff-104">Este procedimiento muestra cómo definir una unidad de medida, proporcionar traducciones para la unidad y su descripción, y definir reglas de conversión para las unidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-104">This procedure shows how to define a unit of measure, provide translations for the unit and it's description, and define conversion rules for related units.</span></span> <span data-ttu-id="ba2ff-105">Puede revisar este procedimiento con datos de demostración, o bien, utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-105">You can walk through this procedure using demo data, or using your own data.</span></span>

1. <span data-ttu-id="ba2ff-106">Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Mantenimiento de Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-106">Go to **Navigation pane > Modules > Product information management > Released product maintenance**.</span></span>
2. <span data-ttu-id="ba2ff-107">Haga clic en **Unidades**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-107">Click **Units**.</span></span>

## <a name="create-a-unit-of-measure"></a><span data-ttu-id="ba2ff-108">Creación de una unidad de medida</span><span class="sxs-lookup"><span data-stu-id="ba2ff-108">Create a unit of measure</span></span>
1. <span data-ttu-id="ba2ff-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-109">Click **New**.</span></span>
2. <span data-ttu-id="ba2ff-110">En el campo **Unidad**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-110">In the **Unit** field, type a value.</span></span> <span data-ttu-id="ba2ff-111">Especifique el identificador o el símbolo que usar al hacer referencia a la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-111">Enter the ID or symbol to use when referring to the unit of measure.</span></span>  
3. <span data-ttu-id="ba2ff-112">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-112">In the **Description** field, type a value.</span></span> <span data-ttu-id="ba2ff-113">Especifique un nombre descriptivo para la unidad de medida en el idioma del sistema.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-113">Enter a descriptive name for the unit of measure in the system language.</span></span>  
4. <span data-ttu-id="ba2ff-114">En el campo **Clase de unidad**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-114">In the **Unit class** field, select an option.</span></span> <span data-ttu-id="ba2ff-115">La clase de unidad define a qué agrupación lógica de medida, como área, masa o cantidad, pertenece la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-115">The unit class defines what logical grouping, such as area, mass, or quantity, the unit of measure is part of.</span></span>  
5. <span data-ttu-id="ba2ff-116">En el campo **Precisión decimal**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-116">In the **Decimal precision** field, enter a number.</span></span> <span data-ttu-id="ba2ff-117">Especifique el número de decimales a los que se redondea la unidad de medida convertida cuando se completa un cálculo para la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-117">Specify the number of decimals that the converted unit of measure must be rounded to when a calculation is completed for the unit of measure.</span></span>  
6. <span data-ttu-id="ba2ff-118">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-118">Click **Save**.</span></span>

## <a name="define-unit-translations"></a><span data-ttu-id="ba2ff-119">Definición de conversiones de unidades</span><span class="sxs-lookup"><span data-stu-id="ba2ff-119">Define unit translations</span></span>
1. <span data-ttu-id="ba2ff-120">En el **Panel Acciones**, haga clic en **Textos de la unidad**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-120">On the **Action Pane**, click **Unit texts**.</span></span>
2. <span data-ttu-id="ba2ff-121">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-121">Click **New**.</span></span> <span data-ttu-id="ba2ff-122">Use el texto de unidad para crear una traducción del identificador o de un símbolo que represente a la unidad de medida para su uso en documentos externos en los idiomas específicos del cliente o del proveedor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-122">Use unit text to create a translation of the ID or a symbol representing the unit of measure for use on external documents in customer- or vendor-specific languages.</span></span>  
3. <span data-ttu-id="ba2ff-123">En el campo **Idioma**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-123">In the **Language** field, enter or select a value.</span></span>
4. <span data-ttu-id="ba2ff-124">En el campo **Texto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-124">In the **Text** field, type a value.</span></span>
5. <span data-ttu-id="ba2ff-125">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-125">Click **Save**.</span></span>
6. <span data-ttu-id="ba2ff-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-126">Close the page.</span></span>
7. <span data-ttu-id="ba2ff-127">En el **Panel Acciones**, haga clic en **Descripciones de unidades convertidas**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-127">On the **Action Pane**, click **Translated unit descriptions**.</span></span>
8. <span data-ttu-id="ba2ff-128">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-128">Click **New**.</span></span> <span data-ttu-id="ba2ff-129">Defina descripciones en idiomas específicos para la unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-129">Define language-specific descriptions for the unit of measure.</span></span>  
9. <span data-ttu-id="ba2ff-130">En el campo **Idioma**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-130">In the **Language** field, enter or select a value.</span></span>
10. <span data-ttu-id="ba2ff-131">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-131">In the **Description** field, type a value.</span></span>
11. <span data-ttu-id="ba2ff-132">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-132">Click **Save**.</span></span>
12. <span data-ttu-id="ba2ff-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-133">Close the page.</span></span>

## <a name="define-unit-conversion-rules"></a><span data-ttu-id="ba2ff-134">Definición de reglas de conversión de unidades</span><span class="sxs-lookup"><span data-stu-id="ba2ff-134">Define unit conversion rules</span></span>
1. <span data-ttu-id="ba2ff-135">En el **Panel Acciones**, haga clic en **Conversiones de unidades**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-135">On the **Action Pane**, click **Unit conversions**.</span></span> <span data-ttu-id="ba2ff-136">Defina reglas para convertir la unidad de medida a y de otras unidades de medida en la clase de unidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-136">Define rules for converting the unit of measure to and from other units of measure in the selected unit class.</span></span>  
2. <span data-ttu-id="ba2ff-137">Haga clic en **Nueva** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-137">Click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="ba2ff-138">En el campo **Factor**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-138">In the **Factor** field, enter a number.</span></span> <span data-ttu-id="ba2ff-139">Factor de conversión entre la unidad de origen y la de destino.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-139">Conversion factor between the From unit and the To unit.</span></span> <span data-ttu-id="ba2ff-140">Por ejemplo, el factor de conversión de centímetros a metros es 100 porque hay 100 centímetros en un metro.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-140">For example, the conversion factor from centimeter to meter is 100 because there are 100 centimeters in one meter.</span></span>  
4. <span data-ttu-id="ba2ff-141">En el campo **Hasta unidad**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-141">In the **To unit** field, enter or select a value.</span></span>
5. <span data-ttu-id="ba2ff-142">En el campo **Redondeo**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-142">In the **Rounding** field, select an option.</span></span> <span data-ttu-id="ba2ff-143">Defina cómo se debe redondear el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-143">Define how the converted value should be rounded.</span></span>  
6. <span data-ttu-id="ba2ff-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-144">Click **OK**.</span></span>
7. <span data-ttu-id="ba2ff-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ba2ff-145">Close the page.</span></span>

