---
title: Dimensiones de producto
description: "Existen cuatro dimensiones de producto - Color, configuración, tamaño y Estilo. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8854ab94a71cc363bcd073d2df47bc01a243b6cd
ms.lasthandoff: 03/31/2017


---

# <a name="product-dimensions"></a>Dimensiones de producto

Existen cuatro dimensiones de producto - Color, configuración, tamaño y Estilo. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto.

Las dimensiones de un producto son las características que permiten identificar una variante del producto. Puede utilizar combinaciones de dimensiones de producto para definir variantes de producto. Se debe definir al menos una dimensión del producto para un producto maestro si desea crear una variante del producto.
Variantes de producto
----------------

Las variantes del producto también se conocen como artículos. Un artículo es un producto tangible, que no es igual que el servicio. También es posible definir un producto maestro con el tipo de servicio. Mediante el tipo Servicio, puede especificar las variantes del producto que incluyen servicios. Por ejemplo, puede especificar un producto maestro para el asesoramiento del trabajo y variantes del producto para el trabajo realizado por los asesores sénior y júnior.

## <a name="product-dimensions"></a>Dimensiones de producto
Las dimensiones de producto siguientes están disponibles: Configuración, Color, tamaño, y Estilo. Una variante del producto se puede generar en función de los valores de dimensión de producto.

Los valores de las dimensiones del producto como tamaño, Color y Estilo se pueden crear en ** ** tamaño, ** ** Color y Estilo ** ** páginas, que son accesibles desde las ubicaciones siguientes: ** Gestión de información de productos ** &gt; ** configuración ** &gt; ** dimensión y grupos de variantes ** &gt; ** tamaños/colores o estilos **. Los valores de dimensión del producto para la dimensión de configuración se crean normalmente mediante el configurador de productos o el configurador basado en dimensiones. Las dimensiones del producto también se pueden crear y mantener en la página **Dimensiones de producto**, a la que se puede tener acceso desde las ubicaciones siguientes:
-   ** Haga clic en Gestión de información de productos ** &gt; ** productos ** &gt; ** productos maestros **. En ** panel de acciones, haga clic ** ** dimensiones de producto **.
-   ** Haga clic en Gestión de información de productos ** &gt; ** productos ** &gt; ** todos los productos y productos maestros **. Seleccione un producto maestro. En ** panel de acciones, haga clic ** ** dimensiones de producto **.
-   ** Haga clic en Gestión de información de productos ** &gt; ** productos emitidos **. Seleccione un producto maestro. En ** panel de acciones, haga clic ** ** ** producto. En el grupo **Producto maestro**, haga clic en **Dimensiones de producto**.

El número de variantes que se pueden crear para un artículo está limitado por el número de posibles combinaciones de las dimensiones del producto.
| **Sugerencia **                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Al utilizar un producto en, por ejemplo, una línea de pedido, seleccione las dimensiones del producto para identificar la variante del producto con la que desee trabajar. |

## <a name="example"></a>Ejemplo
Una empresa vende pantalones vaqueros. El artículo, vaqueros, utiliza las dimensiones de producto Color y Tamaño. Éstos se venden en tres colores distintos y seis tamaños distintos. Colores: azul, negro, marrón Tamaños: XS, S, M, L, XL, XXL No todos los tamaños están disponibles en los tres colores. Si todas las combinaciones estuviesen disponibles, el resultado sería de 18 tipos de vaqueros distintos. En este ejemplo solo se producen las nueve combinaciones siguientes de variantes del producto.

| Color | Tamaño |
|-------|------|
| Azul  | XS   |
| Azul  | S    |
| Azul  | M    |
| Negro | M    |
| Negro | L    |
| Negro | XL   |
| Marrón | L    |
| Marrón | XL   |
| Marrón | XXL  |




