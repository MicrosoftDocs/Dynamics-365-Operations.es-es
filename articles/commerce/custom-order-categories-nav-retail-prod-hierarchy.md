---
title: Cambiar el orden de clasificación de entidades de comercialización
description: Este artículo explica los conceptos relacionados con el control el orden de visualización para diversas entidades relacionadas con la comercialización en Dynamics 365 Commerce.
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265846"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Cambiar el orden de clasificación de entidades de comercialización


[!Include [banner](includes/banner.md)]

Los minoristas consideran el descubrimiento de productos una herramienta principal para la interacción de clientes en todos los canales. Hay varias características que pueden ayudar a los clientes a descubrir productos fácilmente. Por ejemplo, los clientes pueden examinar categorías, buscar y filtrar.

Este artículo explica los conceptos relacionados con el control el orden de visualización para diversas entidades relacionadas con la comercialización. También explica cómo cambiar el orden de clasificación.

## <a name="overview"></a>Información general

En Commerce, la clasificación de varias entidades relacionadas con la comercialización se alinea con los escenarios de clientes existentes y ya no requiere extensiones de los socios de implementación.

En las versiones de Commerce anteriores a la versión 10.0.5, el criterio de clasificación para las categorías de la jerarquía de navegación era alfabético. La funcionalidad personalizada del orden de clasificación actual permite a los encargados de comercialización configurar el orden de clasificación para diversas entidades relacionadas con la comercialización en todos los clientes de usuario final. Estos clientes incluyen sedes empresariales y centros de llamadas.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Configurar el orden de visualización para las categorías de la jerarquía de productos

Antes de poder completar este procedimiento, los datos de prueba se deben instalar en el entorno.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Jerarquía de productos de Commerce**.
2. Haga clic en **Editar jerarquía de categoría**.
3. Haga clic en **Editar**.
4. En el árbol, expanda **ALL \> Action Sports**.
5. En el árbol, expanda **ALL \> Team Sports**.
6. En el campo **Orden de visualización**, escriba un número. (El número puede ser negativo).
7. Repita los pasos del 4 al 6 para todas las categorías adicionales para las que desee cambiar el orden.

El orden de visualización para la jerarquía de navegación de canal se reflejará en la sede para la jerarquía de productos comerciales y productos liberados por categoría.

![Jerarquía de productos ordenada de forma personalizada con valores negativos.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Productos liberados por categoría ordenados de forma personalizada en función de la jerarquía de productos.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configurar el orden de visualización para las categorías de la jerarquía de navegación de canales

Antes de poder completar este procedimiento, los datos de prueba se deben instalar en el entorno.

1. Vaya a **Retail y Commerce \> Productos y categorías \> Categorías de navegación de canales**.
2. En la lista, seleccione la jerarquía **Navegación de moda** .
3. Haga clic en **Editar jerarquía de categoría**.
4. Haga clic en **Editar**.
5. En el árbol seleccione, **Fashion \> Womenswear \> Women's Shoes**.
6. En el campo **Orden de visualización**, escriba un número.
7. En el árbol seleccione, **Fashion \> Womenswear \> Tops**.

Del mismo modo, puede definir el orden de clasificación para las subcategorías.

8. En el árbol seleccione, **Fashion \> Menswear \> Casual Shirts**.
9. En el campo **Orden de visualización**, escriba un número.
10. En el árbol seleccione, **Fashion \> Menswear \> Coats & Jackets**.
11. En el campo **Orden de visualización**, escriba un número.
12. Repita los pasos para todas las categorías adicionales para las que desee cambiar el orden.

El orden de visualización para la jerarquía de navegación de canales se refleja en la sede, el catálogo y los canales.

![Jerarquía de navegación de canales ordenada de forma personalizada.](./media/ChannelNavCustomSorted.png)

![Jerarquía de navegación de catálogos ordenada de forma personalizada en función de la jerarquía de navegación de canales.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV con categorías ordenadas de forma personalizada.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Por defecto, la función **Habilitar orden de visualización para entidades de comercialización** está desactivada. Use [Gestión de características](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activarla. Desués de activar la función, ejecute el trabajo CDX **1110 (Configuración global)** desde el programa de distribución.
> Si su pedido de categorías en POS no está actualizado, reactive el dispositivo. La información de categoría se recupera cuando se activa el dispositivo, por lo que es posible que el dispositivo deba recuperar la información de categoría con órdenes de visualización actualizadas. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
