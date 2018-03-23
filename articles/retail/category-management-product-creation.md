---
title: "Administración de categorías de productos"
description: "Este tema describe cómo los encargados de comercialización pueden usar categorías de productos al por menor para administrar relaciones entre la jerarquía de productos al por menor y los detalles del producto liberado."
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a><span data-ttu-id="06d9d-103">Administración mejorada de productos y categorías</span><span class="sxs-lookup"><span data-stu-id="06d9d-103">Enhanced product and category management</span></span>

[!include[banner](./includes/banner.md)]

<span data-ttu-id="06d9d-104">Este tema describe una forma mejorada de gestionar categorías de productos al por menor en Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="06d9d-104">This topic describes an enhanced way to manage Retail product categories and products in Dynamics 365 for Retail.</span></span> <span data-ttu-id="06d9d-105">Estas mejoras permiten a los encargados de comercialización visualizar una estructura común de propiedades del producto entre la jerarquía del producto al por menor y los detalles del producto liberado.</span><span class="sxs-lookup"><span data-stu-id="06d9d-105">These enhancements let merchandising managers view a common structure of product properties between Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="06d9d-106">Para obtener más información sobre la administración de categorías de productos al por menor, vaya a la **Jerarquía del producto al por menor** del espacio de trabajo **Administración de categorías y productos** y observe la estructura mejorada de la página **Categoría de productos al por menor**.</span><span class="sxs-lookup"><span data-stu-id="06d9d-106">To learn more about managing Retail product categories, go to **Retail product hierarchy** from the **Category and product management** workspace, and note the enhanced structure of the **Retail product category** page.</span></span>

![Espacio de trabajo de administración de categorías y productos](media/LaunchRetailProductHierarchy.png)

<span data-ttu-id="06d9d-108">En versiones anteriores, las propiedades del producto se dividían en **Propiedades básicas de producto** y **Propiedades de producto al por menor**, en función del ámbito de su aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="06d9d-108">In previous versions, product properties were divided into **Basic product properties** and **Retail product properties**, based on the scope of their applicability.</span></span> <span data-ttu-id="06d9d-109">Las **Propiedades de producto al por menor** eran *globales* por el ámbito de aplicabilidad, lo que significa que para una determinada **Propiedad de producto al por menor**, se comparte el mismo valor en todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="06d9d-109">**Retail product properties** were *global* by scope of applicability, which means that for a given **Retail product property**, the same value is shared across all legal entities.</span></span> <span data-ttu-id="06d9d-110">Las **propiedades básicas del producto** son *específicas de cada entidad jurídica*.</span><span class="sxs-lookup"><span data-stu-id="06d9d-110">**Basic product properties** are *legal entity specific*.</span></span> <span data-ttu-id="06d9d-111">En otras palabras, para una determinada **propiedad básica del producto**, el valor puede ser diferente entre entidades jurídicas, en función de los requisitos empresariales individuales.</span><span class="sxs-lookup"><span data-stu-id="06d9d-111">In other words, for a given **Basic product property** the value can differ across legal entities, based on individual business requirements.</span></span>

<span data-ttu-id="06d9d-112">En la estructura mejorada de categorías de productos al por menor, las propiedades del producto se separan de forma lógica en función de su aplicabilidad dentro de un grupo, para así reflejar la estructura del formulario de detalles del producto liberado.</span><span class="sxs-lookup"><span data-stu-id="06d9d-112">In the enhanced Retail product category structure, product properties are logically separated based on their applicability within a group, to reflect the released product details form structure.</span></span>

![Agrupación de campos en función de su ámbito de aplicabilidad](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="06d9d-114">Puede elegir si quiere gestionar las propiedades específicas de todas las entidades jurídicas o gestionarlas según una entidad jurídica específica.</span><span class="sxs-lookup"><span data-stu-id="06d9d-114">You can switch between managing legal-entity specific properties across all legal entities and managing them for a specific legal entity.</span></span> <span data-ttu-id="06d9d-115">Para realizar esto, seleccione **Ver o editar todas las entidades jurídicas** o **Ver o editar una entidad jurídica específica**.</span><span class="sxs-lookup"><span data-stu-id="06d9d-115">To do this, select either **View/Edit for all legal entities** or **View/Edit for a specific legal entity**.</span></span>

![Alternar vista entre un entidad individual y todas las entidades jurídicas](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Alternar vista entre un entidad individual y todas las entidades jurídicas](media/ToggleToEditForAllLegalEntities.PNG)  

<span data-ttu-id="06d9d-118">En comparación con las versiones anteriores, en la nueva estructura de categorías de productos al por menor un responsable de comercialización también podrá definir valores predeterminados para un conjunto adicional de propiedades de producto en un nivel de categoría individual.</span><span class="sxs-lookup"><span data-stu-id="06d9d-118">Compared to previous versions, in the new Retail product category structure a merchandising manager can also define default values for an additional set of product properties at an individual category level.</span></span> <span data-ttu-id="06d9d-119">En el momento de la creación del producto, estos valores predeterminados de propiedades de producto son heredados por un producto en función de su asociación a una categoría individual de la jerarquía del producto al por menor.</span><span class="sxs-lookup"><span data-stu-id="06d9d-119">At the time of product creation, these default product property values are inherited by a product, based on their association with an individual category from Retail product hierarchy.</span></span> <span data-ttu-id="06d9d-120">Estas propiedades de producto heredadas también se pueden modificar para cada producto, y así poder cumplir con los requisitos empresariales individuales.</span><span class="sxs-lookup"><span data-stu-id="06d9d-120">These inherited product properties can also be modified for each product, to meet individual business requirements.</span></span>

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a><span data-ttu-id="06d9d-121">Seleccionar las propiedades adecuadas para actualizar productos desde el formulario de categoría de productos al por menor</span><span class="sxs-lookup"><span data-stu-id="06d9d-121">Select properties to update products from the Retail product category form</span></span> 
 
<span data-ttu-id="06d9d-122">Puede usar esta nueva estructura mejorada para las propiedades del producto para seleccionar las propiedades de producto actualizadas que deben incluirse en los productos asociados.</span><span class="sxs-lookup"><span data-stu-id="06d9d-122">You can use this new enhanced structure for product properties to select which updated product properties must be pushed to associated products.</span></span> 

![Nueva vista mejorada de Actualizar productos](media/NewUpdateProductsEnhancedView.PNG) 

<span data-ttu-id="06d9d-124">Los encargados comercialización pueden modificar estas propiedades de producto heredadas para cada producto, y así poder cumplir con los requisitos empresariales individuales.</span><span class="sxs-lookup"><span data-stu-id="06d9d-124">Merchandising managers can modify these inherited product properties for each product, to meet individual business requirements.</span></span>


