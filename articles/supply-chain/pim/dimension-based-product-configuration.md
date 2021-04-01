---
title: Visión general de la configuración de producto basada en dimensiones
description: La configuración de producto basada en dimensiones representa una solución sencilla para crear muchas variantes de producto a partir de un producto maestro único y su lista de materiales.
author: cvocph
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 823d1b356d914eb0477c41d77a690d02fc4ee630
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5243258"
---
# <a name="dimension-based-product-configuration-overview"></a><span data-ttu-id="3cdd5-103">Visión general de la configuración de producto basada en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3cdd5-103">Dimension-based product configuration overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cdd5-104">La configuración de producto basada en dimensiones representa una solución sencilla para crear muchas variantes de producto a partir de un producto maestro único y su lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-104">Dimension-based product configuration represents a simple solution for creating many product variants from a single product master and its bill of materials.</span></span>

<span data-ttu-id="3cdd5-105">La configuración de producto basada en dimensiones es una de las tres tecnologías de configuración de producto integradas.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-105">Dimension-based product configuration is one of the three built-in product configuration technologies.</span></span> <span data-ttu-id="3cdd5-106">Las otras dos tecnologías son variantes predefinidas y configuración basada en restricciones.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-106">The two other technologies are predefined variants and constraint-based configuration.</span></span> <span data-ttu-id="3cdd5-107">Las tres tecnologías usan un producto maestro como punto de partida y permiten al usuario crear muchas variantes del producto para un producto maestro.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-107">All three technologies use a product master as the starting point and allow the user to create many product variants for one product master.</span></span>

## <a name="key-concepts"></a><span data-ttu-id="3cdd5-108">Conceptos clave</span><span class="sxs-lookup"><span data-stu-id="3cdd5-108">Key concepts</span></span>
<span data-ttu-id="3cdd5-109">La configuración de producto basada en dimensiones se basa en los siguientes conceptos clave:</span><span class="sxs-lookup"><span data-stu-id="3cdd5-109">Dimension-based product configuration is based on the following key concepts:</span></span>

-   <span data-ttu-id="3cdd5-110">Productos maestros</span><span class="sxs-lookup"><span data-stu-id="3cdd5-110">Product masters</span></span>
-   <span data-ttu-id="3cdd5-111">Dimensión del producto de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-111">Configuration product dimension</span></span>
-   <span data-ttu-id="3cdd5-112">Grupos de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-112">Configuration groups</span></span>
-   <span data-ttu-id="3cdd5-113">Lista de materiales (L. MAT)</span><span class="sxs-lookup"><span data-stu-id="3cdd5-113">Bill of materials (BOM)</span></span>
-   <span data-ttu-id="3cdd5-114">Ruta de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-114">Configuration route</span></span>
-   <span data-ttu-id="3cdd5-115">Reglas de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-115">Configuration rules</span></span>

### <a name="product-masters"></a><span data-ttu-id="3cdd5-116">Productos maestros</span><span class="sxs-lookup"><span data-stu-id="3cdd5-116">Product masters</span></span>

<span data-ttu-id="3cdd5-117">Un producto maestro es el punto de partida para cualquier proceso de configuración de producto.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-117">A product master is the starting point for any product configuration process.</span></span> <span data-ttu-id="3cdd5-118">Para la configuración de producto basada en dimensiones, necesita un producto maestro con esta tecnología de configuración concreto y un grupo de dimensiones de producto que incluye la dimensión del producto de configuración.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-118">For the dimension-based product configuration, you need a product master with this particular configuration technology and a product dimension group that includes the configuration product dimension.</span></span>

### <a name="configuration-product-dimension"></a><span data-ttu-id="3cdd5-119">Dimensión del producto de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-119">Configuration product dimension</span></span>

<span data-ttu-id="3cdd5-120">La dimensión del producto de configuración se usa para identificar las variantes del producto para un producto maestro con la tecnología de configuración basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-120">The configuration product dimension is used to identify the product variants for a product master with the dimension-based configuration technology.</span></span> <span data-ttu-id="3cdd5-121">El usuario especifica el valor de dimensión de configuración y debe ayudar a identificar las variantes de producto individuales.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-121">The configuration dimension value is entered by the user and should help to identify the individual product variants.</span></span>

### <a name="configuration-groups"></a><span data-ttu-id="3cdd5-122">Grupos de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-122">Configuration groups</span></span>

<span data-ttu-id="3cdd5-123">Los grupos de configuración se definen en un repositorio central y se pueden usar para todos los modelos de configuración de productos basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-123">Configuration groups are defined in a central repository and can be used for all dimension-based product configuration models.</span></span> <span data-ttu-id="3cdd5-124">Los grupos de configuración se asocian a las líneas de L. MAT individuales y mantienen unidas un grupo de líneas que son mutuamente exclusivas.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-124">Configuration groups are associated to the individual BOM lines and hold together a group of lines that are mutually exclusive.</span></span> <span data-ttu-id="3cdd5-125">Esto significa que solo se puede seleccionar una línea de un grupo para una única variante del producto.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-125">This means that only one line in a group can be selected for a single product variant.</span></span>

### <a name="bill-of-materials-bom"></a><span data-ttu-id="3cdd5-126">Lista de materiales (L. MAT)</span><span class="sxs-lookup"><span data-stu-id="3cdd5-126">Bill of materials (BOM)</span></span>

<span data-ttu-id="3cdd5-127">La L. MAT representa los bloques de creación para una configuración de producto basada en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-127">The BOM represent the building blocks for a dimension-based product configuration.</span></span> <span data-ttu-id="3cdd5-128">Debe incluir todos los productos diferentes que se pueden usar en cualquier variante del producto.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-128">It must include all the different products that can be used in any product variant.</span></span> <span data-ttu-id="3cdd5-129">Cada línea de la L. MAT. puede hacer referencia a un grupo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-129">Each line in the BOM can reference a configuration group.</span></span> <span data-ttu-id="3cdd5-130">Si una línea no hace referencia a un grupo de configuración, se incluirá en todas las variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-130">If a line doesn’t reference a configuration group, it will be included in all product variants.</span></span>

### <a name="configuration-route"></a><span data-ttu-id="3cdd5-131">Ruta de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-131">Configuration route</span></span>

<span data-ttu-id="3cdd5-132">La ruta de configuración determina la secuencia de los grupos de configuración, como se mostrarán al usuario durante el proceso de configuración de producto.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-132">The configuration route determines the sequence of the configuration groups, as they will be displayed to the user during the product configuration process.</span></span>

### <a name="configuration-rules"></a><span data-ttu-id="3cdd5-133">Reglas de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-133">Configuration rules</span></span>

<span data-ttu-id="3cdd5-134">Las reglas de configuración representan un mecanismo para garantizar que un producto incluido en un grupo de configuración de una L. MAT fuerza una inclusión o una exclusión de un producto en un grupo de configuración diferente en la misma L. MAT.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-134">The configuration rules represent a mechanism for ensuring that a product included in one configuration group in a BOM enforces either an inclusion or an exclusion of a product in a different configuration group in the same BOM.</span></span>

## <a name="product-modeling-process"></a><span data-ttu-id="3cdd5-135">Proceso de modelos del producto</span><span class="sxs-lookup"><span data-stu-id="3cdd5-135">Product modeling process</span></span>
<span data-ttu-id="3cdd5-136">La secuencia natural para crear un modelo de producto para un producto basado en dimensiones comienza con la definición de los grupos de configuración pertinentes.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-136">The natural sequence for building a product model for a dimension-based product starts with defining the relevant configuration groups.</span></span> <span data-ttu-id="3cdd5-137">Es importante garantizar que todos los productos que se usarán en la L. MAT se han liberado a la empresa para la que se crea el modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-137">It is important to ensure that all products which will be used in the BOM have been released to the company that the product model is built for.</span></span> <span data-ttu-id="3cdd5-138">Con estos bloques de creación implementados, el usuario puede crear la L. MAT y asignar grupos de configuración a todas las líneas de L. MAT pertinentes.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-138">With these building blocks in place, the user can create the BOM and assign configuration groups to all relevant BOM lines.</span></span> <span data-ttu-id="3cdd5-139">Cuando se completa la L. MAT, se puede definir una ruta de configuración para solicitar los grupos de configuración en la secuencia adecuada.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-139">When the BOM is complete, a configuration route can be defined for ordering the configuration groups in the proper sequence.</span></span> <span data-ttu-id="3cdd5-140">[![Proceso de modelado de productos basado en dimensiones](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Si hay determinados productos de diferentes grupos de configuración que deben o no deben usarse juntos, puede crear reglas de configuración que se aplicarán a estas relaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-140">[![Dimension-based product modeling process](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) If there are certain products from different configuration groups that either must or must not be used together, you can create configuration rules that will enforce these product relationships.</span></span> <span data-ttu-id="3cdd5-141">Después de que la L. MAT. se haya vinculado a un producto maestro basado en dimensiones a través de una versión de L. MAT y se hayan tanto aprobado como activado, puede crear configuraciones de productos y especificar un nombre para cada configuración.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-141">After the BOM has been tied together with a dimension-based product master through a BOM version and both have been approved and activated, you can create product configurations and enter a name for each configuration.</span></span> <span data-ttu-id="3cdd5-142">Las configuraciones se pueden definir antes de que se genere cualquier transacción o se pueden realizar cuando se produzca la necesidad de una configuración determinada.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-142">The configurations can be defined before any transactions are generated or it can be done when the need for a certain configuration occurs.</span></span>

### <a name="suggested-use"></a><span data-ttu-id="3cdd5-143">Uso sugerido</span><span class="sxs-lookup"><span data-stu-id="3cdd5-143">Suggested use</span></span>

<span data-ttu-id="3cdd5-144">La tecnología de configuración basada en dimensiones se puede usar para productos con variabilidad limitada y la combinación del tamaño de las dimensiones de producto estándar, color, estilo y configuración es inadecuada para identificar una variante del producto específica.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-144">The dimension-based configuration technology is best used for products with limited variability and the combination of the standard product dimensions size, color, style, and configuration is unsuitable for identifying a specific product variant.</span></span> <span data-ttu-id="3cdd5-145">Un ejemplo podría ser la bicicleta con el alto del marco de la bicicleta, el tamaño de la rueda, los tipos de freno y las distintas marchas.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-145">An example could be bicycle with frame height, wheel size, brake types, and different gears.</span></span>

### <a name="next-step"></a><span data-ttu-id="3cdd5-146">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="3cdd5-146">Next step</span></span> 

<span data-ttu-id="3cdd5-147">Las siguientes ocho guías de taras se muestran en el orden en que debe completarlas.</span><span class="sxs-lookup"><span data-stu-id="3cdd5-147">The following eight task guides are listed in the order in which you should complete them.</span></span> 

1.  [<span data-ttu-id="3cdd5-148">Crear un producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3cdd5-148">Create a dimension-based product master</span></span>](tasks/create-dimension-based-product-master.md)
2.  [<span data-ttu-id="3cdd5-149">Liberar un producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3cdd5-149">Release a dimension-based product master</span></span>](tasks/release-dimension-based-product-master.md)
3.  [<span data-ttu-id="3cdd5-150">Completar la configuración básica de un producto maestro liberado</span><span class="sxs-lookup"><span data-stu-id="3cdd5-150">Complete basic setup of a released product master</span></span>](tasks/complete-basic-setup-released-product-master.md)
4.  [<span data-ttu-id="3cdd5-151">Definir grupos de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-151">Define configuration groups</span></span>](tasks/define-configuration-groups.md)
5.  [<span data-ttu-id="3cdd5-152">Crear una lista de materiales para un producto maestro basado en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3cdd5-152">Create a bill of materials for a dimension-based product master</span></span>](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [<span data-ttu-id="3cdd5-153">Definir rutas de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-153">Define configuration routes</span></span>](tasks/define-configuration-route.md)
7.  [<span data-ttu-id="3cdd5-154">Crear reglas de configuración</span><span class="sxs-lookup"><span data-stu-id="3cdd5-154">Create configuration rules</span></span>](tasks/create-configuration-rules.md)
8.  [<span data-ttu-id="3cdd5-155">Crear configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="3cdd5-155">Create dimension-based configurations</span></span>](tasks/create-dimension-based-configurations.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]