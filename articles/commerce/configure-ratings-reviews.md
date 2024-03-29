---
title: Configurar calificaciones y opiniones
description: Este artículo describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 27b1beddd474a2ca4db73f8e344b2d85934c43b1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276875"
---
# <a name="configure-ratings-and-reviews"></a>Configurar calificaciones y opiniones

[!include [banner](includes/banner.md)]

Este artículo describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.

Las clasificaciones y opiniones en sitios web de comercio electrónico ayudan a los clientes a obtener información acerca de los productos antes de tomar una decisión de compra, al mostrarles qué piensan otros clientes acerca de esos productos. Para los sitios web de comercio electrónicos, las clasificaciones y opiniones son también un mecanismo para obtener los comentarios de los clientes acerca de los productos. 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a>Configurar un sitio para mostrar clasificaciones y opiniones

Los valores de configuración para clasificaciones y opiniones, como el id. de inquilino, la longitud del texto de opinión y la longitud del título de la opinión, se configuran en el nivel de sitio. 

Para configurar un sitio para que muestre clasificaciones y opiniones, siga estos pasos. 

1. Vaya a **Inicio \> Sitios**.
1. Seleccione el nombre de su sitio. 
1. Ir **Configuraciones del sitio \> Extensiones**. 
1. En el campo **Longitud máxima del texto de la opinión**, especifique el número máximo de caracteres que puede tener el texto de la opinión (por ejemplo, **1000**). 
1. En el campo **Longitud máxima del título de la opinión**, especifique el número máximo de caracteres que pueden tener los títulos de opinión (por ejemplo, **55**). 
1. Seleccione **Guardar y publicar**. 

La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.

![Configuración de un sitio para mostrar clasificaciones y opiniones.](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a>Vincular una clasificación de producto a la sección de revisiones de un PDP

Una clasificación de producto se muestra debajo del título del producto en la parte superior del PDP. La clasificación del producto se puede configurar para que esté vinculada a la sección **Revisiones** del mismo PDP. 

Para vincular una clasificación de producto a la sección **Revisiones** del PDP, siga estos pasos.

1. Abra la plantilla PDP. 
1. Vaya a **Configuración del módulo de contenedor de cuadro de compra**.
1. En **Cuadro de compra**, seleccione **Clasificaciones de producto** y la casilla **Módulo de vincular el clic para opiniones completas**.

La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.

![Vinculación de una clasificación de producto a la sección de revisiones de un PDP.](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a>Configurar el vínculo para la página de directiva y privacidad

Para configurar el vínculo para la página de directiva y privacidad, siga estos pasos.

1. Vaya a **Inicio \> Sitios**.
1. Seleccione el nombre de su sitio. 
1. Ir **Configuraciones del sitio \> Extensiones**.
1. En la pestaña **Rutas**, en **Directiva y privacidad RNR**, seleccione **Agregar un vínculo**. Si ya se ha introducido un vínculo, y desea reemplazarlo, selecciónelo. 
1. En el cuadro de diálogo **Agregar un vínculo**, seleccione el vínculo para la página de directiva y privacidad y, a continuación, seleccione **Aceptar**. 
1. Seleccione **Guardar y publicar**. 

La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.

![Configuración del vínculo para la página de directiva y privacidad.](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a>Configure los módulos de valoraciones y reseñas en las páginas de detalles del producto

Para obtener información sobre la configuración de módulos de valoraciones y reseñas en las páginas de detalles del producto, consulte [Módulos de valoraciones y comentarios](ratings-reviews-modules.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar clasificaciones y revisiones](manage-reviews.md)

[Sincronizar clasificaciones de productos en Dynamics 365 Retail](sync-product-ratings.md)

[Habilitar la publicación manual de calificaciones y reseñas por parte de un moderador](manual-publish-rating-reviews.md)

[Importación y exportación de calificaciones y opiniones](import-export-reviews.md)

[Configurar autenticación de servicio a servicio](service-to-service-auth.md)

[P+F de clasificaciones y revisiones](ratings-reviews-faq.md)

[Módulos de clasificaciones y opiniones](ratings-reviews-modules.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
