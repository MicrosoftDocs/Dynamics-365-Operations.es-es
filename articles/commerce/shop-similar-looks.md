---
title: Habilitar recomendaciones de "comprar looks similares"
description: Este tema describe cómo habilitar las recomendaciones de productos "comprar looks similares" en Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: da957850072e233a41a042d5857f81ddbf178f7a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415608"
---
# <a name="enable-shop-similar-looks-recommendations"></a>Habilitar recomendaciones de "comprar looks similares"

[!include [banner](includes/banner.md)]

Este tema describe cómo habilitar las recomendaciones de productos "comprar looks similares" en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La característica de recomendaciones "comprar looks similares" de Dynamics 365 Commerce utiliza el poder de la inteligencia artificial y el aprendizaje automático (AI-ML) para ofrecer a los clientes recomendaciones de productos visualmente similares. Al hacer que las recomendaciones de "comprar looks similares" estén disponibles para todos los canales minoristas en Commerce, los minoristas pueden aumentar la satisfacción del cliente al ayudarlos a encontrar fácilmente lo que buscan.

La funcionalidad para recomendaciones de "comprar looks similares" utiliza imágenes de productos de variantes de productos de inicialización para encontrar y recomendar productos visualmente similares en el catálogo de productos de un minorista. 

Las recomendaciones de "Comprar looks similares" están disponibles tanto en puntos de venta (PDV) como en experiencias de comercio electrónico.

### <a name="example-scenarios"></a>Escenarios de ejemplo

- Un cliente ve un suéter de rayas negras y recibe una recomendación para un suéter similar de color rojo. El cliente selecciona el producto recomendado en lugar del producto visto originalmente y luego recibe recomendaciones de productos similares en rojo. 
- Un cliente utiliza las recomendaciones de "comprar looks similares" para descubrir pendientes a juego para un anillo que el cliente está interesado en comprar.

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a>Habilitar recomendaciones de "comprar looks similares" en la sede de Commerce

Las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Gen2.

### <a name="prerequisites"></a>Requisitos previos

Antes de que los minoristas puedan comenzar a mostrar recomendaciones de "comprar looks similares" a los clientes, hay dos pasos previos:

- [Habilitar recomendaciones de productos](enable-product-recommendations.md) en la sede de Commerce.
- Confirmar que el servidor de medios admite llamadas HTTPS.

Para que el motor de recomendaciones acceda a las imágenes del producto, los minoristas deben generar las direcciones URL del producto. Para generar direcciones URL de producto en la sede de Commerce, siga estos pasos.

1. Vaya a **Imágenes de productos**.
1. En el panel de acciones, seleccione **Definir plantilla de medios**.
1. En el panel de propiedades **Definir plantilla de medios**, en **Direcciones URL de medios**, seleccione **Generar direcciones URL**.

> [!NOTE]
> Al habilitar la característica de recomendaciones "comprar looks similares", comienza el proceso de generar listas de recomendaciones de productos. Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en los terminales de PDV.

Para habilitar la características de recomendaciones "comprar looks similares" en la sede de Commerce, siga estos pasos.

1. Vaya a **Administración de características**.
1. En la lista de características disponibles, busque y seleccione **Comprar looks similares**.
1. En el panel derecho, seleccione **Habilitar** para activar el servicio.

La siguiente ilustración muestra la característica **Comprar looks similares** en la página **Administración de características** de la sede de Commerce.

![La característica Comprar looks similares en la página de Administración de características de la sede de Commerce](./media/enableshopsimilarlooks.png)

Una vez completadas las tareas anteriores, los terminales de PDV se mejoran automáticamente con un panel **Comprar productos similares** contextual. Si selecciona **Ver más**, se puede llevar a los usuarios de terminales de PDV a una página "comprar looks similares" dedicada que se puede filtrar más.

> [!NOTE]
> Si desactiva la característica de recomendaciones "comprar looks similares", no se verá afectado ningún otro tipo de recomendaciones de productos. Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones de productos](product-recommendations.md).

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a>Agregar un botón Comprar looks similares a las páginas de detalles del producto a través del generador de sitios de Commerce

Después de habilitar la característica de recomendaciones "comprar looks similares" en la sede de Commerce, una opción del generador de sitios de Commerce permite a los minoristas agregar un botón **Comprar looks similares** al cuadro de compra en cualquier página de detalles del producto (PDP). Un cliente que seleccione este botón irá a una página dedicada a "comprar looks similares" que muestra productos visualmente similares. Allí, el cliente puede utilizar selectores para filtrar todavía más los productos.

Para agregar un botón **Comprar looks similares** a un PDP a través del generador de sitios de Commerce, siga estos pasos.

1. Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de cuadro de compra.
1. En el panel de navegación de la izquierda, seleccione el módulo de cuadro de compra.
1. En el panel de navegación derecho, active la casilla **Habilitar vínculo para comprar looks similares**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla. Una vez publicada la página, el PDP incluirá un botón **Comprar looks similares**.

La siguiente ilustración muestra la casilla **Habilitar vínculo para comprar looks similares** y **Comprar looks similares** en un ejemplo de PDP en el generador de sitios.

![La casilla Habilitar vínculo para comprar looks similares y el botón Comprar looks similares en un PDP en el generador de sitios](./media/SSLecomtooling.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]