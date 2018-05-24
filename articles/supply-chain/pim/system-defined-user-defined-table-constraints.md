---
title: Restricciones de tablas definidas por el usuario o definidas por el sistema
description: "Este artículo explica los dos tipos de restricciones de tablas para componentes en un modelo de configuración de productos: definidos por el usuario y definidos por el sistema. Las restricciones de tablas representan matrices de las combinaciones de atributos permitidas, donde cada fila define un conjunto de valores de atributos posibles."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCTableConstraintAttachAttributeTree, PCTableConstraintColumnSystem, PCTableConstraintContentUserDef, PCTableConstraintDefinition, PCTableConstraintWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19781
ms.assetid: 0a4ea930-b344-43a8-871e-d5cd077892c4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: cd5fc329877bbb1f8f4ec26191e66914da29d034
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="system-defined-and-user-defined-table-constraints"></a><span data-ttu-id="5612a-104">Restricciones de tablas definidas por el usuario o definidas por el sistema</span><span class="sxs-lookup"><span data-stu-id="5612a-104">System-defined and user-defined table constraints</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5612a-105">Este artículo explica los dos tipos de restricciones de tablas para componentes en un modelo de configuración de productos: definidos por el usuario y definidos por el sistema.</span><span class="sxs-lookup"><span data-stu-id="5612a-105">This article explains the two types of table constraints for components in a product configuration model -  user-defined and system-defined.</span></span> <span data-ttu-id="5612a-106">Las restricciones de tablas representan matrices de las combinaciones de atributos permitidas, donde cada fila define un conjunto de valores de atributos posibles.</span><span class="sxs-lookup"><span data-stu-id="5612a-106">Table constraints represent matrices of the allowed attribute combinations, where each row defines one set of possible attribute values.</span></span>

<span data-ttu-id="5612a-107">Las restricciones de tablas representan las matrices de combinaciones de atributos que se permiten para componentes en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="5612a-107">Table constraints represent matrices of the combinations of attributes that are allowed for components in a product configuration model.</span></span> <span data-ttu-id="5612a-108">Cada fila en la tabla define un conjunto de valores de atributo posibles.</span><span class="sxs-lookup"><span data-stu-id="5612a-108">Each row in the table defines one set of possible attribute values.</span></span> <span data-ttu-id="5612a-109">Puede declarar dos tipos de restricciones en un modelo de configuración de productos:</span><span class="sxs-lookup"><span data-stu-id="5612a-109">You can declare two types of constraints in a product configuration model:</span></span>

-   <span data-ttu-id="5612a-110">**Restricción de expresión**: cree una expresión que defina relaciones entre atributos para garantizar que solo se puedan seleccionar valores compatibles durante la configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="5612a-110">**Expression constraint** – Create an expression that defines relations between attributes to guarantee that only compatible values can be selected during product configuration.</span></span>
-   <span data-ttu-id="5612a-111">**Restricción de tablas**: cree una tabla que defina todas las combinaciones posible para un conjunto concreto de atributos.</span><span class="sxs-lookup"><span data-stu-id="5612a-111">**Table constraint** – Create a table that defines all the combinations that are allowed for a specified set of attributes.</span></span> <span data-ttu-id="5612a-112">Hay dos tipos de restricciones de tablas disponibles: restricciones de tablas definidas por el usuario y restricciones de tablas definidas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="5612a-112">Two types of table constraints are available: user-defined table constraints and system-defined table constraints.</span></span>

<span data-ttu-id="5612a-113">Este artículo describe las restricciones de tablas que define el usuario y las definidas por el sistema para componentes en un modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="5612a-113">This article describes user-defined and system-defined table constraints for components in a product configuration model.</span></span>

## <a name="user-defined-table-constraints"></a><span data-ttu-id="5612a-114">Restricciones de tablas definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="5612a-114">User-defined table constraints</span></span>
<span data-ttu-id="5612a-115">Una restricción de tablas definida por el usuario es un tipo de matriz que se usa para describir las combinaciones de los valores de atributos definidos mediante los tipos de atributo.</span><span class="sxs-lookup"><span data-stu-id="5612a-115">A user-defined table constraint is a type of matrix that is used to describe the combinations of attribute values that are defined by attribute types.</span></span> <span data-ttu-id="5612a-116">Por ejemplo, si fabrica altavoces, puede incluir columnas para el acabado de la caja y la rejilla frontal en la restricción de tablas definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5612a-116">For example, if you produce speakers, you can include columns for the cabinet finish and the front grill in the user-defined table constraint.</span></span> <span data-ttu-id="5612a-117">El tipo de atributo para el acabado de la caja tiene cuatro valores, y el tipo de atributo para la rejilla delantera tiene tres valores.</span><span class="sxs-lookup"><span data-stu-id="5612a-117">The attribute type for the cabinet finish has four values, and the attribute type for the front grill has three values.</span></span> <span data-ttu-id="5612a-118">Por lo tanto, si no se usan restricciones, existen las combinaciones posibles 4 × 3 = 12.</span><span class="sxs-lookup"><span data-stu-id="5612a-118">Therefore, if constraints aren't used, there are 4 × 3 = 12 possible combinations.</span></span> <span data-ttu-id="5612a-119">Sin embargo, en este ejemplo, únicamente hay seis combinaciones posibles, tal y como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="5612a-119">However, in this example, only six combinations are allowed, as shown in the following table.</span></span> <span data-ttu-id="5612a-120">Esta información se muestra en la ficha **Combinaciones permitidas** de la página **Editar restricción de tabla**.</span><span class="sxs-lookup"><span data-stu-id="5612a-120">This information is displayed on the **Allowed combinations** tab on the **Edit table constraint** page.</span></span>

| <span data-ttu-id="5612a-121">Acabado de la caja</span><span class="sxs-lookup"><span data-stu-id="5612a-121">Cabinet finish</span></span> | <span data-ttu-id="5612a-122">Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="5612a-122">Front grill</span></span> |
|----------------|-------------|
| <span data-ttu-id="5612a-123">Negro</span><span class="sxs-lookup"><span data-stu-id="5612a-123">Black</span></span>          | <span data-ttu-id="5612a-124">Negro</span><span class="sxs-lookup"><span data-stu-id="5612a-124">Black</span></span>       |
| <span data-ttu-id="5612a-125">Negro</span><span class="sxs-lookup"><span data-stu-id="5612a-125">Black</span></span>          | <span data-ttu-id="5612a-126">Metálico</span><span class="sxs-lookup"><span data-stu-id="5612a-126">Metal</span></span>       |
| <span data-ttu-id="5612a-127">Roble</span><span class="sxs-lookup"><span data-stu-id="5612a-127">Oak</span></span>            | <span data-ttu-id="5612a-128">Negro</span><span class="sxs-lookup"><span data-stu-id="5612a-128">Black</span></span>       |
| <span data-ttu-id="5612a-129">Palisandro</span><span class="sxs-lookup"><span data-stu-id="5612a-129">Rosewood</span></span>       | <span data-ttu-id="5612a-130">Blanco</span><span class="sxs-lookup"><span data-stu-id="5612a-130">White</span></span>       |
| <span data-ttu-id="5612a-131">Blanco</span><span class="sxs-lookup"><span data-stu-id="5612a-131">White</span></span>          | <span data-ttu-id="5612a-132">Negro</span><span class="sxs-lookup"><span data-stu-id="5612a-132">Black</span></span>       |
| <span data-ttu-id="5612a-133">Blanco</span><span class="sxs-lookup"><span data-stu-id="5612a-133">White</span></span>          | <span data-ttu-id="5612a-134">Blanco</span><span class="sxs-lookup"><span data-stu-id="5612a-134">White</span></span>       |

<span data-ttu-id="5612a-135">Las restricciones de tablas definidas por el usuario se definen mediante entradas de tabla estática que funciona del mismo modo que una restricción de expresión.</span><span class="sxs-lookup"><span data-stu-id="5612a-135">User-defined table constraints are defined by static table input that works the same way as an expression constraint.</span></span> <span data-ttu-id="5612a-136">Al usar una restricción de tablas definida por el usuario, la ventaja es que las tablas suelen ser más fáciles de crear, comprender y mantener que las restricciones de expresión largas.</span><span class="sxs-lookup"><span data-stu-id="5612a-136">When you use a user-defined table constraint, the advantage is that tables are often easier to create, understand, and maintain than long expression constraints.</span></span>

## <a name="system-defined-table-constraints"></a><span data-ttu-id="5612a-137">Restricciones de tablas definidas por el sistema</span><span class="sxs-lookup"><span data-stu-id="5612a-137">System-defined table constraints</span></span>
<span data-ttu-id="5612a-138">Una restricción de tabla definida por el sistema crea una asignación dinámica entre un tipo de atributo y un campo en una tabla.</span><span class="sxs-lookup"><span data-stu-id="5612a-138">A system-defined table constraint creates a dynamic mapping between an attribute type and a field in a table.</span></span> <span data-ttu-id="5612a-139">Cuando una restricción de tabla definida por el sistema se incluye en un modelo de configuración de productos, la asignación garantiza que se mostrarán los datos de la tabla en lugar de los valores del tipo.</span><span class="sxs-lookup"><span data-stu-id="5612a-139">When a system-defined table constraint is included in a product configuration model, the mapping guarantees that the data in the table is shown instead of the values of the attribute type.</span></span> <span data-ttu-id="5612a-140">El resultado es una restricción dinámica, porque el contenido de la tabla se puede modificar (por ejemplo, mediante otros módulos).</span><span class="sxs-lookup"><span data-stu-id="5612a-140">The result is a dynamic constraint, because the table contents can be modified (for example, by other modules).</span></span>  

<span data-ttu-id="5612a-141">Cuando se crea una restricción de tabla definida por el sistema, se selecciona una tabla, se define opcionalmente la consulta que se debe usar y luego se asocian tipos de atributo a los campos de la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5612a-141">When you create a system-defined table constraint, you select a table, optionally define the query to use, and then associate attribute types to the fields in the selected table.</span></span> <span data-ttu-id="5612a-142">Los tipos de campos deben coincidir con los tipos de atributo.</span><span class="sxs-lookup"><span data-stu-id="5612a-142">The types of fields must match the types of attribute types.</span></span>  

<span data-ttu-id="5612a-143">Para que una restricción de tablas pueda surtir efecto en un modelo de configuración de productos, la restricción de tabla se debe incluir en una restricción en uno de los componentes del modelo.</span><span class="sxs-lookup"><span data-stu-id="5612a-143">Before a table constraint can take effect on a product configuration model, the table constraint must be included in a constraint on one of the model's components.</span></span> <span data-ttu-id="5612a-144">El procedimiento es crear una nueva restricción, seleccionar el tipo de restricción de tabla y seleccionar la definición de la restricción de tabla que usar.</span><span class="sxs-lookup"><span data-stu-id="5612a-144">The procedure is to create a new constraint, select the table constraint type, and then select the table constraint definition to use.</span></span> <span data-ttu-id="5612a-145">Por último, todos los campos de la restricción de tabla se deben asignar a atributos en el modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="5612a-145">Finally, all fields in the table constraint must be mapped to attributes in the product configuration model.</span></span>

<a name="additional-resources"></a><span data-ttu-id="5612a-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5612a-146">Additional resources</span></span>
--------

[<span data-ttu-id="5612a-147">Conceptos clave en los modelos de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="5612a-147">Key concepts in product configuration models</span></span>](product-configuration-models.md)




