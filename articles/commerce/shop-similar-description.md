---
title: Habilitar recomendaciones de "comprar descripción similar"
description: Este tema describe cómo habilitar las recomendaciones de productos "comprar descripción similar" en Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b3b7abf47a3bdacaa4b91ae32b68a809a84b0b1d
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "5098648"
---
# <a name="enable-shop-similar-description-recommendations"></a>Habilitar recomendaciones de "comprar descripción similar"

[!include [banner](includes/banner.md)]

Este tema describe cómo habilitar las recomendaciones de productos "comprar descripción similar" en Microsoft Dynamics 365 Commerce.

La característica de recomendaciones "comprar descripción similar" de Dynamics 365 Commerce aprovecha la eficacia de la inteligencia artificial y el aprendizaje automático (AI-ML) para ofrecer a los clientes recomendaciones de productos visualmente similares. Al hacer que las recomendaciones de "comprar descripción similar" estén disponibles para todos los canales minoristas en Commerce, los minoristas pueden aumentar la satisfacción del cliente al ayudarle a encontrar fácilmente lo que busca.

La funcionalidad de recomendaciones de "comprar descripción similar" utiliza el nombre y la descripción del producto de productos de inicialización para encontrar y recomendar productos visualmente similares en el catálogo de productos de un minorista.

Las recomendaciones de "Comprar descripción similar" están disponibles tanto en puntos de venta (PDV) como en experiencias de comercio electrónico.

## <a name="example-scenarios"></a>Escenarios de ejemplo

Los siguientes escenarios de ejemplo muestran los tipos de recomendaciones que puede proporcionar la funcionalidad "Comprar descripción similar":

- Un cliente ve un par de anteojos de estilo retro y recibe un conjunto de recomendaciones para otros anteojos con un diseño similar, en el contexto de la industria del minorista.
- Un cliente utiliza recomendaciones de "comprar descripción similar" para descubrir sabores de café que son similares a un sabor que compró previamente al minorista.

## <a name="set-up-shop-similar-description-recommendations"></a>Configurar las recomendaciones de "comprar descripción similar"

Las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento a Azure Data Lake Storage Gen2.

### <a name="prerequisites"></a>Requisitos previos

Antes de que se puedan mostrar a los clientes las recomendaciones de "comprar descripción similar", debe completar los siguientes requisitos previos:

- [Habilitar recomendaciones de productos](enable-product-recommendations.md) en la sede de Commerce.
- Confirmar que el servidor de medios admite llamadas HTTPS.

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a>Activar la característica de recomendaciones de "comprar descripción similar"

Para activar la característica de recomendaciones "comprar descripción similar" en la sede central de Commerce, siga estos pasos.

1. En el espacio de trabajo **Administración de características**, en la lista de características disponibles, busque y seleccione **Comprar descripción similar**.
1. En el panel derecho, seleccione **Habilitar**.

> [!NOTE]
> Cuando activa la característica, el sistema comienza a generar listas de recomendaciones de productos. Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en los terminales de PDV.
>
> Si desactiva la características, los otros tipos de recomendaciones de productos no se verán afectados. Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones de productos](product-recommendations.md).

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a>Agregar un botón de comprar descripción similar a las páginas de detalles de producto

Después de activar la característica de recomendaciones "comprar descripción similar" en la sede central de Commerce, puede agregar un botón **Comprar descripción similar** al cuadro de compra de cualquier página de detalles de producto (PDP). Un cliente que seleccione este botón irá a una página **Comprar descripción similar** dedicada que muestra productos visualmente similares. El cliente podrá utilizar selectores para filtrar todavía más los productos.

Para agregar un botón **Comprar descripción similar** a una PDP a través del generador de sitios de Commerce, siga estos pasos.

1. Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de cuadro de compra.
1. En el panel de navegación de la izquierda, seleccione el módulo de cuadro de compra.
1. En el panel de navegación derecho, active la casilla **Habilitar vínculo para comprar descripción similar**.
1. Seleccione **Guardar**.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla. Una vez publicada la página, la PDP incluirá un botón **Comprar descripción similar**.

La siguiente ilustración muestra la casilla **Habilitar vínculo para comprar descripción similar** y el botón **Comprar descripción similar** en un ejemplo de PDP del generador de sitios.

![La casilla Habilitar vínculo para comprar descripción similar y el botón Comprar descripción similar en una PDP del generador de sitios](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)
