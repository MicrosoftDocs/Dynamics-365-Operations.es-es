---
title: Gestionar las categorías de productos y productos de Retail
description: Este tema describe cómo los encargados de comercialización pueden usar categorías de productos de Retail para administrar relaciones entre la jerarquía de productos de Retail y los detalles del producto liberado.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 27870fe6172479b891b885d9e84ca10b250e3399
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019520"
---
# <a name="manage-retail-product-categories-and-products"></a>Gestionar las categorías de productos y productos comerciales

[!include [banner](./includes/banner.md)]

Este tema describe una forma mejorada de gestionar categorías de productos y productos en Dynamics 365 Retail. Las mejoras permiten a los encargados de comercialización visualizar una estructura de propiedades del producto que se reparte entre la jerarquía del producto y los detalles del producto liberado.

Para obtener más información acerca de cómo gestionar categorías de producto, en el área de trabajo **Gestión de categorías y productos**, seleccione el mosaico **Jerarquía del producto de Retail**.

Observe la estructura ampliada de la página **Jerarquía del producto de Retail** que aparece. En versiones anteriores de Retail, las propiedades del producto se dividían en *propiedades básicas de producto* y *propiedades de producto de Retail*, en función del ámbito de su aplicabilidad. Las propiedades de producto de Retail son *global* en su ámbito de la aplicabilidad. Es decir, para una propiedad dada del producto, el mismo valor se comparte en todas las entidades jurídicas. Por el contrario, las propiedades básicas del producto son *específicas de cada entidad jurídica*. En otras palabras, para una determinada propiedad básica del producto, el valor puede ser diferente entre entidades jurídicas, en función de los requisitos empresariales individuales de cada entidad jurídica.

En la estructura mejorada de categorías de productos, las propiedades del producto se separan de forma lógica en función de su aplicabilidad en un grupo, para así reflejar la estructura del formulario de detalles del producto liberado.

![Campos agrupados en función del ámbito de aplicabilidad de las propiedades](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

Puede alternar entre gestionar las propiedades de entidades jurídicas específicas de todas las entidades jurídicas o gestionarlas según una entidad jurídica específica.

Para gestionar propiedades en todas las entidades jurídicas, seleccione **Ver todas las entidades jurídicas** (o **Editar todas las entidades jurídicas**).

![Ver o editar todas las entidades jurídicas](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Para gestionar las propiedades de una entidad jurídica específica, seleccione **Ver una entidad jurídica específica** (o **Editar una entidad jurídica específica**).

![Ver o editar una entidad jurídica específica](media/ToggleToEditForAllLegalEntities.PNG)

Adicionalmente, en las versiones mejorada de categorías de productos de Retail, un responsable de comercialización ahora podrá definir valores predeterminados para un conjunto adicional de propiedades de producto en el nivel de categoría individual. Después, cuando se cran los productos, heredan los valores predeterminados de sus propiedades de producto, en función de la asociación de esas propiedades con una categoría individual de la jerarquía del producto. Estas propiedades de producto heredadas también se pueden modificar para cada producto y así poder cumplir con los requisitos empresariales individuales.

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a>Seleccionar las propiedades para actualizar productos en la página de herarquía de productos de Retail

Puede usar la nueva estructura mejorada para las propiedades del producto para seleccionar las propiedades de producto actualizadas que deben incluirse en los productos asociados. En la página **Jerarquía del producto de Retail**, en el panel de acciones, seleccione **Categoría** y, después, seleccione **Actualizar productos** para abrir el cuadro de diálogo **Actualización de productos**.

![Cuadro de diálogo Actualizar productos](media/NewUpdateProductsEnhancedView.PNG)
