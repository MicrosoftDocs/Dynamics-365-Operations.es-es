---
title: Agregar una restricción de expresión a un modelo de configuración de producto
description: Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 411e20bd8631b70df981c5785f502693d5ba3705
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987138"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="03db9-103">Agregar una restricción de expresión a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="03db9-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="03db9-104">Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="03db9-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="03db9-105">Muestra cómo puede ordenar que la protección de la esquina se aplique a un altavoz si el usuario ha seleccionado una parrilla delantera metálica.</span><span class="sxs-lookup"><span data-stu-id="03db9-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="03db9-106">El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="03db9-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>


## <a name="create-an-expression-constraint"></a><span data-ttu-id="03db9-107">Crear una restricción de expresión</span><span class="sxs-lookup"><span data-stu-id="03db9-107">Create an expression constraint</span></span>
1. <span data-ttu-id="03db9-108">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="03db9-108">Click Product variant model definition.</span></span>
2. <span data-ttu-id="03db9-109">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="03db9-109">Click Product configuration models.</span></span>
3. <span data-ttu-id="03db9-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="03db9-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="03db9-111">Este ejemplo usa el modelo de altavoz superior.</span><span class="sxs-lookup"><span data-stu-id="03db9-111">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="03db9-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="03db9-112">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="03db9-113">Expanda la sección Restricciones.</span><span class="sxs-lookup"><span data-stu-id="03db9-113">Expand the Constraints section.</span></span>
6. <span data-ttu-id="03db9-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="03db9-114">Click Add.</span></span>
7. <span data-ttu-id="03db9-115">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="03db9-115">Click Create.</span></span>
8. <span data-ttu-id="03db9-116">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="03db9-116">In the Name field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="03db9-117">Introducir expresión</span><span class="sxs-lookup"><span data-stu-id="03db9-117">Enter expression</span></span>
1. <span data-ttu-id="03db9-118">Haga clic en Editar expresión.</span><span class="sxs-lookup"><span data-stu-id="03db9-118">Click Edit expression.</span></span>
    * <span data-ttu-id="03db9-119">Si desbloquea la interfaz del usuario en la grabación de tareas en esta fase, puede usar IntelliSense y la lista de símbolos para crear la expresión de la restricción.</span><span class="sxs-lookup"><span data-stu-id="03db9-119">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="03db9-120">En el campo ConstraintBody, especifique "Implies[FrontGrill=="Metal", CornerProtection]".</span><span class="sxs-lookup"><span data-stu-id="03db9-120">In the ConstraintBody field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="03db9-121">Esta lógica de la expresión indica: Si la parrilla delantera es metálica, se debe seleccionar la opción de protección de la esquina.</span><span class="sxs-lookup"><span data-stu-id="03db9-121">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="03db9-122">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="03db9-122">Click Validate.</span></span>
    * <span data-ttu-id="03db9-123">La función validar se ejecuta a través de la expresión de restricción y comprueba los errores de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="03db9-123">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="03db9-124">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="03db9-124">Click Close.</span></span>
5. <span data-ttu-id="03db9-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="03db9-125">Click OK.</span></span>

