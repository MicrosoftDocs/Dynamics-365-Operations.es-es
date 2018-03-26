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


# <a name="enhanced-product-and-category-management"></a>Administración mejorada de productos y categorías

[!include[banner](./includes/banner.md)]

Este tema describe una forma mejorada de gestionar categorías de productos al por menor en Dynamics 365 for Retail. Estas mejoras permiten a los encargados de comercialización visualizar una estructura común de propiedades del producto entre la jerarquía del producto al por menor y los detalles del producto liberado.

Para obtener más información sobre la administración de categorías de productos al por menor, vaya a la **Jerarquía del producto al por menor** del espacio de trabajo **Administración de categorías y productos** y observe la estructura mejorada de la página **Categoría de productos al por menor**.

![Espacio de trabajo de administración de categorías y productos](media/LaunchRetailProductHierarchy.png)

En versiones anteriores, las propiedades del producto se dividían en **Propiedades básicas de producto** y **Propiedades de producto al por menor**, en función del ámbito de su aplicabilidad. Las **Propiedades de producto al por menor** eran *globales* por el ámbito de aplicabilidad, lo que significa que para una determinada **Propiedad de producto al por menor**, se comparte el mismo valor en todas las entidades jurídicas. Las **propiedades básicas del producto** son *específicas de cada entidad jurídica*. En otras palabras, para una determinada **propiedad básica del producto**, el valor puede ser diferente entre entidades jurídicas, en función de los requisitos empresariales individuales.

En la estructura mejorada de categorías de productos al por menor, las propiedades del producto se separan de forma lógica en función de su aplicabilidad dentro de un grupo, para así reflejar la estructura del formulario de detalles del producto liberado.

![Agrupación de campos en función de su ámbito de aplicabilidad](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Puede elegir si quiere gestionar las propiedades específicas de todas las entidades jurídicas o gestionarlas según una entidad jurídica específica. Para realizar esto, seleccione **Ver o editar todas las entidades jurídicas** o **Ver o editar una entidad jurídica específica**.

![Alternar vista entre un entidad individual y todas las entidades jurídicas](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Alternar vista entre un entidad individual y todas las entidades jurídicas](media/ToggleToEditForAllLegalEntities.PNG)  

En comparación con las versiones anteriores, en la nueva estructura de categorías de productos al por menor un responsable de comercialización también podrá definir valores predeterminados para un conjunto adicional de propiedades de producto en un nivel de categoría individual. En el momento de la creación del producto, estos valores predeterminados de propiedades de producto son heredados por un producto en función de su asociación a una categoría individual de la jerarquía del producto al por menor. Estas propiedades de producto heredadas también se pueden modificar para cada producto, y así poder cumplir con los requisitos empresariales individuales.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Seleccionar las propiedades adecuadas para actualizar productos desde el formulario de categoría de productos al por menor 
 
Puede usar esta nueva estructura mejorada para las propiedades del producto para seleccionar las propiedades de producto actualizadas que deben incluirse en los productos asociados. 

![Nueva vista mejorada de Actualizar productos](media/NewUpdateProductsEnhancedView.PNG) 

Los encargados comercialización pueden modificar estas propiedades de producto heredadas para cada producto, y así poder cumplir con los requisitos empresariales individuales.


