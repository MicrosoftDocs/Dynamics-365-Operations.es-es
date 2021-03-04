---
title: Módulos de clasificaciones y opiniones
description: Este tema cubre los módulos de calificaciones y revisiones utilizados en las páginas de detalles del producto en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: 85fb1272103eed7d6e44635b7c20438471d96b34
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415636"
---
# <a name="ratings-and-reviews-modules"></a>Módulos de clasificaciones y opiniones

[!include [banner](includes/banner.md)]

Este tema cubre los módulos de calificaciones y revisiones utilizados en las páginas de detalles (PDP) del producto en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Las clasificaciones y opiniones en sitios web de comercio electrónico ayudan a los clientes a obtener información acerca de los productos antes de tomar una decisión de compra, y también son un mecanismo para obtener opiniones de los clientes acerca de esos productos. 

Las clasificaciones se muestran en las páginas de lista de productos, páginas de lista de categorías, páginas de resultados de la búsqueda y otras páginas del sitio. 

Las histogramas de clasificaciones y revisiones de productos se muestran en las PDP. Un botón **Escribir una opinión** permite a los clientes enviar clasificaciones y opiniones para un producto. Estas características de PDP están controladas por los módulos de calificaciones y revisión.

## <a name="ratings-and-reviews-modules-on-pdps"></a>Módulos de clasificaciones y opiniones en PDP 

Tres módulos muestran el resumen de clasificaciones y opiniones en PDP:
- Módulo Escribir opinión
- Módulo de lista de opiniones de productos
- Módulo de histograma de clasificaciones
 
La ilustración siguiente muestra el aspecto de los módulos de clasificaciones y opiniones en un PDP.

![Módulos de clasificaciones y opiniones en un PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> Para obtener información acerca de cómo optimizar diseños y plantillas PDP de modo que pueda compartir las configuraciones para los módulos de clasificaciones y opiniones entre varios PDP en su sitio de comercio electrónico, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).

La siguiente ilustración muestra cómo el cuadro de diálogo **Agregar módulo** presenta módulos de calificaciones y opiniones en Dynamics 365 Commerce.
![Cuadro de diálogo Agregar módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a>Módulo Escribir opinión

El módulo Escribir opinión incluye un botón **Escribir una opinión** que permite a los usuarios iniciar sesión, asigne una clasificación y escribir una opinión de un producto. Este módulo también permite a los usuarios editar una clasificación u opinión que han enviado anteriormente. Este módulo aparece normalmente encima de los módulos de lista de opiniones de productos e histograma de clasificaciones en un PDP.
La ilustración siguiente muestra el cuadro de diálogo **Escribir una opinión** que aparece cuando un cliente selecciona **Escribir una opinión**. El cliente puede usar este cuadro de diálogo para enviar una clasificación y una revisión.
![Escribir un cuadro de diálogo de opinión](media/rnr-eCommerce-write-review-module.png) En la tabla siguiente se muestra la propiedad del módulo de escribir una opinión que tiene que configurarse en la herramienta de creación.
| Nombre de la propiedad | Valor        | Descripción de la propiedad                 |
|---------------|--------------|--------------------------------------|
| Nombre          | Escribir opinión | El nombre del módulo de escribir opinión. |

### <a name="ratings-histogram-module"></a>Módulo de histograma de clasificaciones

El módulo del histograma de clasificaciones muestra un histograma de clasificaciones. Este módulo normalmente aparece entre el módulo de escribir opinión y el módulo de lista de opiniones de productos en un PDP.
El módulo del histograma de calificaciones no requiere ninguna configuración. Solo tiene que agregar el módulo en la plantilla PDP. En las siguientes ilustraciones se muestran el aspecto de una plantilla PDP en Dynamics 365 Commerce cuando se configuran los módulos de clasificaciones y opiniones para su visualización en PDP.
![Plantilla PDP cuando se configuran las clasificaciones y las opiniones para su visualización en PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a>Módulo de lista de opiniones de productos

El módulo de lista de opiniones de productos muestra una lista de opiniones de productos junto con las opciones de ordenación, filtrado y paginación. Este módulo aparece normalmente después del módulo del histograma de clasificaciones en un PDP.
En la tabla siguiente se muestra las propiedades del módulo de lista de opiniones de productos que se tienen que configurar en la herramienta de creación.

| Nombre de la propiedad              | Valor | Descripción de la propiedad |
|----------------------------|-------| ---------------------|
| Opiniones que se muestran en cada página | 10    | El número de opiniones que se deben mostrar al mismo tiempo en un PDP. Se incluyen los botones **Siguiente** y **Anterior**, de modo que los usuarios puedan moverse por las páginas de opiniones. |

#### <a name="ratings-histogram--summary-view"></a>Histograma de clasificaciones: vista de resumen

El módulo de lista de opiniones de productos incluye una franja donde puede agregar un módulo de histograma de clasificaciones. La ilustración siguiente muestra cómo puede agregar un módulo de histograma de clasificaciones en el módulo de la lista de opiniones de productos en Dynamics 365 Commerce.

![Adición de un módulo de histograma de clasificaciones en un módulo de lista de opiniones de productos](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de contenedor](add-container-module.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]