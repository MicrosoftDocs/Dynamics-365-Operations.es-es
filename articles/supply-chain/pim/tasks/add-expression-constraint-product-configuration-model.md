---
title: Agregar una restricción de expresión a un modelo de configuración de producto
description: Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd5475e48cbcd8dcee6b228297f58e364ac503d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920890"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a><span data-ttu-id="d4ed7-103">Agregar una restricción de expresión a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="d4ed7-103">Add an expression constraint to a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4ed7-104">Este procedimiento muestra cómo puede agregar una nueva expresión de restricción a un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-104">This procedure shows how you can add a new constraint expression to a product configuration model.</span></span> <span data-ttu-id="d4ed7-105">Muestra cómo puede ordenar que la protección de la esquina se aplique a un altavoz si el usuario ha seleccionado una parrilla delantera metálica.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-105">It shows how you can mandate that corner protection must be applied to a speaker if the user has selected a front grill in metal.</span></span> <span data-ttu-id="d4ed7-106">El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-106">The procedure uses the High end speaker component in the demo company USMF.</span></span>

## <a name="create-an-expression-constraint"></a><span data-ttu-id="d4ed7-107">Crear una restricción de expresión</span><span class="sxs-lookup"><span data-stu-id="d4ed7-107">Create an expression constraint</span></span>

1. <span data-ttu-id="d4ed7-108">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-108">Go to **Product information management \> Products \> Product configuration models**.</span></span>
3. <span data-ttu-id="d4ed7-109">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d4ed7-110">Este ejemplo usa el modelo de altavoz superior.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-110">This example uses the high end speaker model.</span></span>  
4. <span data-ttu-id="d4ed7-111">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-111">In the list, select the link in the selected row.</span></span>
5. <span data-ttu-id="d4ed7-112">Expandir la sección **Restricciones**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-112">Expand the **Constraints** section.</span></span>
6. <span data-ttu-id="d4ed7-113">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-113">Select **Add**.</span></span>
7. <span data-ttu-id="d4ed7-114">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-114">Select **Create**.</span></span>
8. <span data-ttu-id="d4ed7-115">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-115">In the **Name** field, type a value.</span></span>

## <a name="enter-expression"></a><span data-ttu-id="d4ed7-116">Introducir expresión</span><span class="sxs-lookup"><span data-stu-id="d4ed7-116">Enter expression</span></span>

1. <span data-ttu-id="d4ed7-117">Seleccione **Editar expresión**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-117">Select **Edit expression**.</span></span>
    * <span data-ttu-id="d4ed7-118">Si desbloquea la interfaz del usuario en la grabación de tareas en esta fase, puede usar IntelliSense y la lista de símbolos para crear la expresión de la restricción.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-118">If you unlock the user interface in the task recording at this stage, you can use IntelliSense and the list of symbols to build the constraint expression .</span></span>  
2. <span data-ttu-id="d4ed7-119">En el campo **ConstraintBody**, especifique 'Implies[FrontGrill=="Metal", CornerProtection] '.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-119">In the **ConstraintBody** field, enter 'Implies[FrontGrill=="Metal", CornerProtection] '.</span></span>
    * <span data-ttu-id="d4ed7-120">Esta lógica de la expresión indica: Si la parrilla delantera es metálica, se debe seleccionar la opción de protección de la esquina.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-120">This expression logic states: If the Front grill is  metal, then the corner protection option must be selected.</span></span>  
3. <span data-ttu-id="d4ed7-121">Seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-121">Select **Validate**.</span></span>
    * <span data-ttu-id="d4ed7-122">La función validar se ejecuta a través de la expresión de restricción y comprueba los errores de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-122">The validate function runs through the constraint expression and checks for syntax errors.</span></span>  
4. <span data-ttu-id="d4ed7-123">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-123">Select **Close**.</span></span>
5. <span data-ttu-id="d4ed7-124">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4ed7-124">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]