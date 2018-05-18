---
title: Dimensiones de producto
description: "Hay cuatro dimensiones de producto: Color, Configuración, Tamaño y Estilo. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 9cb4bded4b8d841c6d164e6b8ded2cb3fb4d0978
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---

# <a name="product-dimensions"></a>Dimensiones de producto

[!include [banner](../includes/banner.md)]

[!include [Retail name](../includes/retail-name.md)]

Hay cuatro dimensiones de producto: Color, Configuración, Tamaño y Estilo. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto.

Las dimensiones de un producto son las características que permiten identificar una variante del producto. Puede utilizar combinaciones de dimensiones de producto para definir variantes de producto. Se debe definir al menos una dimensión del producto para un producto maestro si desea crear una variante del producto.
Variantes de producto
----------------

Las variantes del producto también se conocen como artículos. Un artículo es un producto tangible, que no es igual que el servicio. También es posible definir un producto maestro con el tipo Servicio. Mediante el tipo Servicio, puede especificar las variantes del producto que incluyen servicios. Por ejemplo, puede especificar un producto maestro para el asesoramiento del trabajo y variantes del producto para el trabajo realizado por los asesores sénior y júnior.

## <a name="product-dimensions"></a>Dimensiones de producto
Están disponibles las siguientes dimensiones de producto: Configuración, Color, Tamaño y Estilo. Se puede generar una variante del producto a partir de los valores de dimensión del producto.

Los valores de las dimensiones del producto como tamaño, color y estilo se pueden crear en las páginas **Tamaño**, **Color** y **Estilo**, a las que se puede obtener acceso desde las ubicaciones siguientes: **Gestión de información de productos** &gt; **Configurar** &gt; **Grupos de variantes y dimensiones** &gt; **Tamaños/Colores/Estilos**. Los valores de dimensión del producto para la dimensión de configuración se crean normalmente mediante el configurador de productos o el configurador basado en dimensiones. Las dimensiones del producto también se pueden crear y mantener en la página **Dimensiones de producto**, a la que se puede tener acceso desde las ubicaciones siguientes:
-   Haga clic en **Gestión de información de productos** &gt; **Productos** &gt; **Productos maestros**. En el **Panel de acciones**, haga clic en **Dimensiones de producto**.
-   Haga clic en **Gestión de información de productos** &gt; **Productos** &gt; **Todos los productos y productos maestros**. Seleccione un producto maestro. En el **Panel de acciones**, haga clic en **Dimensiones de producto**.
-   Haga clic en **Gestión de información de productos** &gt; **Productos emitidos**. Seleccione un producto maestro. En el **Panel de acciones**, haga clic en **Producto**. En el grupo **Producto maestro**, haga clic en **Dimensiones de producto**.

El número de variantes que se pueden crear para un artículo está limitado por el número de posibles combinaciones de las dimensiones del producto.

| **Sugerencia**                                                                                                                                              |
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






