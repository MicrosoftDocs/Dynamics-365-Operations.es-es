---
title: Configurar clasificaciones y revisiones
description: Este tema describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770490"
---
# <a name="configure-ratings-and-reviews"></a>Configurar clasificaciones y revisiones

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Las clasificaciones y opiniones en sitios web de comercio electrónico ayudan a los clientes a obtener información acerca de los productos antes de tomar una decisión de compra, al mostrarles qué piensan otros clientes acerca de esos productos. Para los sitios web de comercio electrónicos, las clasificaciones y opiniones son también un mecanismo para obtener los comentarios de los clientes acerca de los productos. 

Las clasificaciones se muestran en las páginas de lista de productos, páginas de lista de categorías, páginas de resultados de la búsqueda y otras páginas del sitio. Las histogramas de clasificaciones y revisiones de productos se muestran en las páginas de detalles de producto (PDP). Un botón **Escribir una opinión** permite a los clientes enviar clasificaciones y opiniones para un producto.

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

![Cuadro de diálogo Escribir una opinión](media/rnr-eCommerce-write-review-module.png)

En la tabla siguiente se muestra la propiedad del módulo de escribir una opinión que tiene que configurarse en la herramienta de creación.

| Nombre de la propiedad | Valor        | Descripción de la propiedad                 |
|---------------|--------------|--------------------------------------|
| Nombre          | Escribir opinión | El nombre del módulo de escribir opinión. |

### <a name="ratings-histogram-module"></a>Módulo de histograma de clasificaciones

El módulo del histograma de clasificaciones muestra un histograma de clasificaciones. Este módulo normalmente aparece entre el módulo de escribir opinión y el módulo de lista de opiniones de productos en un PDP.

El módulo del histograma de calificaciones no requiere ninguna configuración. Solo tiene que agregar el módulo en la plantilla PDP. 

En las siguientes ilustraciones se muestran el aspecto de una plantilla PDP en Dynamics 365 Commerce cuando se configuran los módulos de clasificaciones y opiniones para su visualización en PDP.

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

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurar un sitio para mostrar clasificaciones y opiniones

Los valores de configuración para clasificaciones y opiniones, como el id. de inquilino, la longitud del texto de opinión y la longitud del título de la opinión, se configuran en el nivel de sitio. 

Para configurar un sitio para que muestre clasificaciones y opiniones, siga estos pasos. 

1. Vaya a **Inicio \> Sitios**.
1. Seleccione el nombre de su sitio. 
1. Vaya a **Administración del sitio \> Extensibilidad**. 
1. En el campo **Longitud máxima del texto de la opinión**, especifique el número máximo de caracteres que puede tener el texto de la opinión (por ejemplo, **1000**). 
1. En el campo **Longitud máxima del título de la opinión**, especifique el número máximo de caracteres que pueden tener los títulos de opinión (por ejemplo, **55**). 
1. Seleccione **Guardar y publicar**. 

La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.

![Configuración de un sitio para mostrar clasificaciones y opiniones](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Vincular una clasificación de producto a la sección de revisiones de un PDP

Una clasificación de producto se muestra debajo del título del producto en la parte superior del PDP. La clasificación del producto se puede configurar para que esté vinculada a la sección **Revisiones** del mismo PDP. 

Para vincular una clasificación de producto a la sección **Revisiones** del PDP, siga estos pasos.

1. Abra la plantilla PDP. 
1. Vaya a **Configuración del módulo de contenedor de cuadro de compra**.
1. En **Cuadro de compra**, seleccione **Clasificaciones de producto** y la casilla **Módulo de vincular el clic para opiniones completas**.

La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.

![Vinculación de una clasificación de producto a la sección de revisiones de un PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurar el vínculo para la página de directiva y privacidad

Para configurar el vínculo para la página de directiva y privacidad, siga estos pasos.

1. Vaya a **Inicio \> Sitios**.
1. Seleccione el nombre de su sitio. 
1. Vaya a **Administración del sitio \> Extensibilidad**.
1. En la pestaña **Rutas**, en **Directiva y privacidad RNR**, seleccione **Agregar un vínculo**. Si ya se ha introducido un vínculo, y desea reemplazarlo, selecciónelo. 
1. En el cuadro de diálogo **Agregar un vínculo**, seleccione el vínculo para la página de directiva y privacidad y, a continuación, seleccione **Aceptar**. 
1. Seleccione **Guardar y publicar**. 

La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.

![Configuración del vínculo para la página de directiva y privacidad](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar clasificaciones y revisiones](manage-reviews.md)

[Sincronizar clasificaciones de productos en Dynamics 365 Retail](sync-product-ratings.md)
