---
title: Administrar las categorías de productos y los productos
description: En este tema se describe cómo los encargados de comercialización pueden usar categorías de productos para administrar relaciones entre la jerarquía de productos de Commerce y los detalles del producto liberado.
author: ashishmsft
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 678561856fbb5514ff954363a767091edac6dee2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794382"
---
# <a name="manage-product-categories-and-products"></a>Administrar las categorías de productos y los productos

[!include [banner](./includes/banner.md)]

Este tema describe una forma mejorada de gestionar categorías de productos y productos en Dynamics 365 Commerce. Las mejoras permiten a los encargados de comercialización visualizar una estructura de propiedades del producto que se reparte entre la jerarquía del producto y los detalles del producto liberado.

Para obtener más información acerca de cómo gestionar categorías de productos, en el espacio de trabajo **Administración de categorías y productos**, seleccione el icono **Jerarquía de productos de Commerce**.

Observe la estructura ampliada de la página **Jerarquía de productos de Commerce** que aparece. En versiones anteriores de la aplicación, las propiedades del producto se dividían en *propiedades básicas de producto* y *propiedades de producto de Retail*, en función del ámbito de su aplicabilidad. Las propiedades de producto de Retail son *global* en su ámbito de la aplicabilidad. Es decir, para una propiedad dada del producto, el mismo valor se comparte en todas las entidades jurídicas. Por el contrario, las propiedades básicas del producto son *específicas de cada entidad jurídica*. En otras palabras, para una determinada propiedad básica del producto, el valor puede ser diferente entre entidades jurídicas, en función de los requisitos empresariales individuales de cada entidad jurídica.

En la estructura mejorada de categorías de productos, las propiedades del producto se separan de forma lógica en función de su aplicabilidad en un grupo, para así reflejar la estructura del formulario de detalles del producto liberado.

![Campos agrupados en función del ámbito de aplicabilidad de las propiedades](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Puede alternar entre gestionar las propiedades de entidades jurídicas específicas de todas las entidades jurídicas o gestionarlas según una entidad jurídica específica.

Para gestionar propiedades en todas las entidades jurídicas, seleccione **Ver todas las entidades jurídicas** (o **Editar todas las entidades jurídicas**).

![Ver o editar todas las entidades jurídicas](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Para gestionar las propiedades de una entidad jurídica específica, seleccione **Ver una entidad jurídica específica** (o **Editar una entidad jurídica específica**).

![Ver o editar una entidad jurídica específica](media/ToggleToEditForAllLegalEntities.PNG)

Además, ahora en la estructura mejorada de categorías de productos un responsable de comercialización podrá definir valores predeterminados para un conjunto adicional de propiedades de producto en el nivel de categoría individual. Después, cuando se cran los productos, heredan los valores predeterminados de sus propiedades de producto, en función de la asociación de esas propiedades con una categoría individual de la jerarquía del producto. Estas propiedades de producto heredadas también se pueden modificar para cada producto y así poder cumplir con los requisitos empresariales individuales.

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a>Seleccionar las propiedades para actualizar productos en la página de la jerarquía de productos de Commerce

Puede usar la nueva estructura mejorada para las propiedades del producto para seleccionar las propiedades de producto actualizadas que deben incluirse en los productos asociados. En la página **Jerarquía de productos de Commerce**, en el panel de acciones, seleccione **Categoría** y, a continuación, seleccione **Actualizar productos** para abrir el cuadro de diálogo **Actualizar productos**.

![Cuadro de diálogo Actualizar productos](media/NewUpdateProductsEnhancedView.PNG)


[!INCLUDE[footer-include](../includes/footer-banner.md)]