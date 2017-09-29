--- 
title: Definir dimensiones financieras
description: "Esta guía de tareas muestra la adición de una dimensión financiera respaldada por la entidad y una dimensión financiera personalizada."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0b72acf763f0f6dbc64c3e00986bc9eb0e366bb5
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="define-financial-dimensions"></a><span data-ttu-id="2cd38-103">Definir dimensiones financieras</span><span class="sxs-lookup"><span data-stu-id="2cd38-103">Define financial dimensions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2cd38-104">Esta guía de tareas muestra la adición de una dimensión financiera respaldada por la entidad y una dimensión financiera personalizada.</span><span class="sxs-lookup"><span data-stu-id="2cd38-104">This task guide demonstrates adding an entity backed financial dimension and a custom financial dimension.</span></span>  <span data-ttu-id="2cd38-105">La guía usa la empresa de demostración de USMF.</span><span class="sxs-lookup"><span data-stu-id="2cd38-105">The guide uses the USMF demo company.</span></span>


## <a name="create-an-entity-backed-financial-dimension"></a><span data-ttu-id="2cd38-106">Crear una dimensión financiera respaldada por entidad</span><span class="sxs-lookup"><span data-stu-id="2cd38-106">Create an entity backed financial dimension</span></span>
1. <span data-ttu-id="2cd38-107">Vaya a Contabilidad general > Plan contable > Dimensiones > Dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="2cd38-107">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="2cd38-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2cd38-108">Click New.</span></span>
3. <span data-ttu-id="2cd38-109">En el campo Usar valores de, seleccione una entidad definida por el sistema en la que desea basar la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="2cd38-109">In the User values from field, select a system-defined entity to base the financial dimension on.</span></span> 
4. <span data-ttu-id="2cd38-110">En el campo Nombre de dimensión, escriba un valor para describir la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="2cd38-110">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="2cd38-111">El nombre puede ser diferente de la entidad definida por el sistema pero no puede contener espacios ni caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="2cd38-111">The name can be different than the system-defined entity but cannot contain spaces or special characters.</span></span>  
5. <span data-ttu-id="2cd38-112">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="2cd38-112">Click Activate.</span></span>
    * <span data-ttu-id="2cd38-113">La activación de la dimensión financiera actualiza la tabla con el nombre de la dimensión financiera y quita las dimensiones eliminadas.</span><span class="sxs-lookup"><span data-stu-id="2cd38-113">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="2cd38-114">Puede especificar valores de dimensión para activar una dimensión financiera, pero no se puede usar una dimensión financiera hasta que esté activada.</span><span class="sxs-lookup"><span data-stu-id="2cd38-114">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="2cd38-115">Haga clic en Cerrar en el mensaje de activación.</span><span class="sxs-lookup"><span data-stu-id="2cd38-115">Click Close on the activation message.</span></span>
7. <span data-ttu-id="2cd38-116">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="2cd38-116">Click Activate.</span></span>
    * <span data-ttu-id="2cd38-117">La activación de la dimensión se puede programar para ejecutarse por lote en una fecha y una hora específicas.</span><span class="sxs-lookup"><span data-stu-id="2cd38-117">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
8. <span data-ttu-id="2cd38-118">Haga clic en Valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd38-118">Click Dimension values.</span></span>
    * <span data-ttu-id="2cd38-119">Algunos valores de dimensión son específicos de la empresa.</span><span class="sxs-lookup"><span data-stu-id="2cd38-119">Some dimension values are company specific.</span></span> <span data-ttu-id="2cd38-120">Puede comprobar si son específicos de la empresa si el nombre de la empresa se muestra en la lista de valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd38-120">You can verify if they are company specific by if the company name is showing in the dimension values list.</span></span>  

## <a name="create-a-custom-financial-dimension"></a><span data-ttu-id="2cd38-121">Crear una dimensión financiera personalizada</span><span class="sxs-lookup"><span data-stu-id="2cd38-121">Create a custom financial dimension</span></span>
1. <span data-ttu-id="2cd38-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2cd38-122">Close the page.</span></span>
2. <span data-ttu-id="2cd38-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2cd38-123">Click New.</span></span>
3. <span data-ttu-id="2cd38-124">En el campo Usar valores, seleccione <Custom dimension>.</span><span class="sxs-lookup"><span data-stu-id="2cd38-124">In the Use values from field, select <Custom dimension>.</span></span>
4. <span data-ttu-id="2cd38-125">En el campo Nombre de dimensión, escriba un valor para describir la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="2cd38-125">In the Dimension name field, type a value to describe the financial dimension.</span></span>
    * <span data-ttu-id="2cd38-126">El nombre no puede contener espacios o caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="2cd38-126">The name cannot contain spaces or special characters.</span></span>  
    * <span data-ttu-id="2cd38-127">También puede especificar una máscara de cuenta para limitar el importe y el tipo de información que puede especificar para valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd38-127">You can also specify an account mask to limit the amount and type of information that you can enter for dimension values.</span></span>   
    * <span data-ttu-id="2cd38-128">Puede especificar los caracteres que permanecen iguales para cada valor de dimensión, como letras o un guión.</span><span class="sxs-lookup"><span data-stu-id="2cd38-128">You can enter characters that remain the same for each dimension value, such as letters or a hyphen.</span></span> <span data-ttu-id="2cd38-129">También puede especificar signos de número (#) y ampersands (&) como marcadores de posición para las letras y los números que se modificarán cada vez que se cree un valor de dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd38-129">You can also enter number signs (#) and ampersands (&) as placeholders for letters and numbers that will change every time that a dimension value is created.</span></span> <span data-ttu-id="2cd38-130">Use un signo de número (#) como indicador de posición para un número y un ampersand (&) como indicador de posición para una letra.</span><span class="sxs-lookup"><span data-stu-id="2cd38-130">Use a number sign (#) as a placeholder for a number and an ampersand (&) as a placeholder for a letter.</span></span>  <span data-ttu-id="2cd38-131">Ejemplo: Para limitar el valor de dimensión a letras CC, un guión y tres números, debe especificar CC-### como la máscara de formato.</span><span class="sxs-lookup"><span data-stu-id="2cd38-131">Example: To limit the dimension value to the letters CC and three numbers, you enter CC-### as the format mask.</span></span>  
5. <span data-ttu-id="2cd38-132">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="2cd38-132">Click Activate.</span></span>
    * <span data-ttu-id="2cd38-133">La activación de la dimensión financiera actualiza la tabla con el nombre de la dimensión financiera y quita las dimensiones eliminadas.</span><span class="sxs-lookup"><span data-stu-id="2cd38-133">Activating the financial dimension updates the table with the financial dimension name and removes deleted dimensions.</span></span> <span data-ttu-id="2cd38-134">Puede especificar valores de dimensión para activar una dimensión financiera, pero no se puede usar una dimensión financiera hasta que esté activada.</span><span class="sxs-lookup"><span data-stu-id="2cd38-134">You can enter dimension values before you activate a financial dimension, but a financial dimension cannot be used until it is activated.</span></span>  
6. <span data-ttu-id="2cd38-135">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="2cd38-135">Click Activate.</span></span>
    * <span data-ttu-id="2cd38-136">La activación de la dimensión se puede programar para ejecutarse por lote en una fecha y una hora específicas.</span><span class="sxs-lookup"><span data-stu-id="2cd38-136">Dimension activation can be scheduled to run by batch at a specific date and time.</span></span>  
7. <span data-ttu-id="2cd38-137">Haga clic en Valores de dimensión.</span><span class="sxs-lookup"><span data-stu-id="2cd38-137">Click Dimension values.</span></span>
8. <span data-ttu-id="2cd38-138">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2cd38-138">Click New.</span></span>
9. <span data-ttu-id="2cd38-139">En el campo Valor de dimensión, escriba un nombre para describir el valor de la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="2cd38-139">In the Dimension value field, type a name to describe your financial dimension value.</span></span>
10. <span data-ttu-id="2cd38-140">En el campo Descripción, escriba una descripción del valor de la dimensión financiera.</span><span class="sxs-lookup"><span data-stu-id="2cd38-140">In the Description field, type a description that describes your financial dimension value.</span></span>


