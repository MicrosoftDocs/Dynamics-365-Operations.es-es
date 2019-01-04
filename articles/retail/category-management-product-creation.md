---
title: "Gestionar las categorías de productos y productos de Retail"
description: "Este tema describe cómo los encargados de comercialización pueden usar categorías de productos de Retail para administrar relaciones entre la jerarquía de productos de Retail y los detalles del producto liberado."
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
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 0bcc5989edd9913fce414c0c24068f111d8c1aeb
ms.contentlocale: es-es
ms.lasthandoff: 01/04/2019

---

# <a name="manage-retail-product-categories-and-products"></a><span data-ttu-id="83b95-103">Gestionar las categorías de productos y productos de Retail</span><span class="sxs-lookup"><span data-stu-id="83b95-103">Manage Retail product categories and products</span></span>

[!include [banner](./includes/banner.md)]

<span data-ttu-id="83b95-104">Este tema describe una forma mejorada de gestionar categorías de productos de Retail en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="83b95-104">This topic describes an enhanced way to manage Retail product categories and products in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="83b95-105">Las mejoras permiten a los encargados de comercialización visualizar una estructura de propiedades del producto que se reparte entre la jerarquía del producto de Retail y los detalles del producto liberado.</span><span class="sxs-lookup"><span data-stu-id="83b95-105">The enhancements let merchandising managers view a structure of product properties that is shared between the Retail product hierarchy and released product details.</span></span>

<span data-ttu-id="83b95-106">Para obtener más información acerca de cómo gestionar categorías de producto de Retail, en el área de trabajo **Gestión de categorías y productos**, seleccione el mosaico **Jerarquía del producto de Retail**.</span><span class="sxs-lookup"><span data-stu-id="83b95-106">To learn more about how to manage Retail product categories, in the **Category and product management** workspace, select the **Retail product hierarchy** tile.</span></span>

<span data-ttu-id="83b95-107">Observe la estructura ampliada de la página **Jerarquía del producto de Retail** que aparece.</span><span class="sxs-lookup"><span data-stu-id="83b95-107">Notice the enhanced structure of the **Retail product hierarchy** page that appears.</span></span> <span data-ttu-id="83b95-108">En versiones anteriores de Retail, las propiedades del producto se dividían en *propiedades básicas de producto* y *propiedades de producto de Retail*, en función del ámbito de su aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="83b95-108">In previous versions of Retail, product properties were divided into *basic product properties* and *Retail product properties*, based on the scope of their applicability.</span></span> <span data-ttu-id="83b95-109">Las propiedades de producto de Retail son *global* en su ámbito de la aplicabilidad.</span><span class="sxs-lookup"><span data-stu-id="83b95-109">Retail product properties are *global* in their scope of applicability.</span></span> <span data-ttu-id="83b95-110">Es decir, para una propiedad dada del producto de Retail, el mismo valor se comparte en todas las entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="83b95-110">In other words, for a given Retail product property, the same value is shared across all legal entities.</span></span> <span data-ttu-id="83b95-111">Por el contrario, las propiedades básicas del producto son *específicas de cada entidad jurídica*.</span><span class="sxs-lookup"><span data-stu-id="83b95-111">By contrast, basic product properties are *legal entity–specific*.</span></span> <span data-ttu-id="83b95-112">En otras palabras, para una determinada propiedad básica del producto, el valor puede ser diferente entre entidades jurídicas, en función de los requisitos empresariales individuales de cada entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="83b95-112">In other words, for a given basic product property, the value can differ across legal entities, depending on the individual business requirements of each legal entity.</span></span>

<span data-ttu-id="83b95-113">En la estructura mejorada de categorías de productos de Retail, las propiedades del producto se separan de forma lógica en función de su aplicabilidad en un grupo, para así reflejar la estructura del formulario de detalles del producto liberado.</span><span class="sxs-lookup"><span data-stu-id="83b95-113">In the enhanced Retail product category structure, product properties are logically separated based on their applicability in a group, to reflect the structure of the released product details form structure.</span></span>

![Campos agrupados en función del ámbito de aplicabilidad de las propiedades](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

<span data-ttu-id="83b95-115">Puede alternar entre gestionar las propiedades de entidades jurídicas específicas de todas las entidades jurídicas o gestionarlas según una entidad jurídica específica.</span><span class="sxs-lookup"><span data-stu-id="83b95-115">You can switch between managing legal entity–specific properties across all legal entities and managing them for a specific legal entity.</span></span>

<span data-ttu-id="83b95-116">Para gestionar propiedades en todas las entidades jurídicas, seleccione **Ver todas las entidades jurídicas** (o **Editar todas las entidades jurídicas**).</span><span class="sxs-lookup"><span data-stu-id="83b95-116">To manage properties across all legal entities, select **View for all legal entities** (or **Edit for all legal entities**).</span></span>

![Ver o editar todas las entidades jurídicas](media/ToggleBackToEditForSpecificLegalEntity.PNG)

<span data-ttu-id="83b95-118">Para gestionar las propiedades de una entidad jurídica específica, seleccione **Ver una entidad jurídica específica** (o **Editar una entidad jurídica específica**).</span><span class="sxs-lookup"><span data-stu-id="83b95-118">To manage properties for a specific legal entity, select **View for a specific legal entity** (or **Edit for a specific legal entity**).</span></span>

![Ver o editar una entidad jurídica específica](media/ToggleToEditForAllLegalEntities.PNG)

<span data-ttu-id="83b95-120">Adicionalmente, en las versiones mejorada de categorías de productos de Retail, un responsable de comercialización ahora podrá definir valores predeterminados para un conjunto adicional de propiedades de producto en el nivel de categoría individual.</span><span class="sxs-lookup"><span data-stu-id="83b95-120">Additionally, in the enhanced Retail product category structure, a merchandising manager can now define default values for an additional set of product properties at the level of the individual category.</span></span> <span data-ttu-id="83b95-121">Después, cuando se cran los productos, heredan los valores predeterminados de sus propiedades de producto, en función de la asociación de esas propiedades con una categoría individual de la jerarquía del producto de Retail.</span><span class="sxs-lookup"><span data-stu-id="83b95-121">Then, when products are created, they inherit default values for their product properties, based on the association of those properties with an individual category in Retail product hierarchy.</span></span> <span data-ttu-id="83b95-122">Estas propiedades de producto heredadas también se pueden modificar para cada producto y así poder cumplir con los requisitos empresariales individuales.</span><span class="sxs-lookup"><span data-stu-id="83b95-122">These inherited product properties can also be modified for each product to meet individual business requirements.</span></span>

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a><span data-ttu-id="83b95-123">Seleccionar las propiedades para actualizar productos en la página de herarquía de productos de Retail</span><span class="sxs-lookup"><span data-stu-id="83b95-123">Selecting properties to update products on the Retail product hierarchy page</span></span>

<span data-ttu-id="83b95-124">Puede usar la nueva estructura mejorada para las propiedades del producto para seleccionar las propiedades de producto actualizadas que deben incluirse en los productos asociados.</span><span class="sxs-lookup"><span data-stu-id="83b95-124">You can use the new enhanced structure for product properties to select updated product properties that must be pushed to the associated products.</span></span> <span data-ttu-id="83b95-125">En la página **Jerarquía del producto de Retail**, en el panel de acciones, seleccione **Categoría** y, después, seleccione **Actualizar productos** para abrir el cuadro de diálogo **Actualización de productos**.</span><span class="sxs-lookup"><span data-stu-id="83b95-125">On the **Retail product hierarchy** page, on the Action Pane, select **Category**, and then select **Update products** to open the **Update products** dialog box.</span></span>

![Cuadro de diálogo Actualizar productos](media/NewUpdateProductsEnhancedView.PNG)

