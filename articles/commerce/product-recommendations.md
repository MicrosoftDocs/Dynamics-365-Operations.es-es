---
title: Visión general de recomendaciones de producto
description: En este tema se proporciona información general sobre recomendaciones de productos. Las recomendaciones de producto permiten a los clientes encontrar fácil y rápidamente los productos que desean, e incluso los productos que no pensaban comprar en un principio.
author: Moonma
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fc7d47897d1a332ba1af7305525f9e75bca12afd
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "6337512"
---
# <a name="product-recommendations-overview"></a>Visión general de recomendaciones de producto

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce se puede utilizar para mostrar recomendaciones de productos en el dispositivo de punto de venta (PDV) y el sitio web de comercio electrónico. Las recomendaciones de productos son artículos en los que un cliente puede estar interesado. Las recomendaciones se basan en las tendencias de compras de otros clientes en tiendas físicas o en línea.

Las recomendaciones de productos permiten a los clientes buscar con facilidad y rapidez lo que desean a la vez que tienen una experiencia que les sirve bien. Las ventas cruzadas y verticales se pueden usar incluso para ayudar a clientes a encontrar productos adicionales que no se pensaron en un principio para comprar. Cuando se usan recomendaciones para mejorar la detección de productos, pueden crear más oportunidades de conversión, ayudan a aumentar los ingresos de ventas e incluso ayudan a amplificar la retención y la satisfacción del cliente.

En el comercio electrónico, las recomendaciones de productos son impulsadas con tecnologías de aprendizaje automático de Microsoft Recommendations a gran escala.

Este servicio es un complemento de Dynamics 365 Commerce. Para obtener más información, descargue la última [Guía de licencias de Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).


## <a name="recommendation-service"></a>Servicio de recomendaciones

El servicio de recomendaciones de productos utiliza tecnologías de inteligencia artificial y aprendizaje automático (AI-ML) de la siguiente manera:

- Los datos en el formato requerido por el servicio de recomendaciones se extraen de la base de datos operativa de Commerce y se envían a Azure Data Lake Storage o al almacén de entidades.
- El servicio de recomendaciones utiliza los datos almacenados para entrenar modelos de recomendaciones para las listas **A la gente también le gustó**, **Los usuarios que compraron esto también compraron**, **Nuevos**, **Más vendidos** y **Tendencias**.

## <a name="scenarios"></a>Situaciones

Las recomendaciones de productos están disponibles para los siguientes escenarios:

- **En cualquier página de tienda para explorar o página de aterrizaje en comercio electrónico:** si los clientes o socios de tienda visitan una página de la tienda, el motor de recomendaciones puede sugerir productos en las listas **Nuevos**, **Más vendidos** y **Tendencias**.
- **En la página Detalles de producto:** si los clientes o socios de tienda visitan una página **Detalles de producto**, el motor de recomendaciones sugiere artículos adicionales de los que también hay probabilidad que se compren. Estos artículos aparecen en la lista **A la gente también le gustó**.
- **En la página Transacción o la página de finalización de compra:** el motor de recomendaciones sugiere artículos, en función de la lista completa de artículos de la cesta. Estos artículos aparecen en la lista **Los usuarios que compraron esto también compraron**.
- **Recomendaciones personalizadas**: los comerciantes pueden proporcionar a los clientes que han iniciado una lista de **Picking para usted** personalizada, además de la nueva funcionalidad que permite personalizar los escenarios de lista existentes en función de ese cliente. Para obtener más información, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Tipos de recomendaciones de producto

En la tabla siguiente se describen varios tipos de recomendaciones automáticas de productos disponibles que los minoristas pueden implementar en su solución de Dynamics 365 Commerce a través del [módulo de colección de productos](product-collection-module-overview.md). Los comercios minoristas también pueden mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción.

| Módulo de colección de productos  | Tipo | Descripción |
|----------------------------|------|-------------|
| Nuevas                        | Algorítmico | Este módulo muestra una lista de los productos que se han surtido recientemente a canales y catálogos. |
| Más vendidos               | Algorítmico | Este módulo muestra una lista de productos que están clasificados por el número máximo de ventas. |
| Tendencias                   | Algorítmico | Este módulo muestra una lista de los productos con el máximo rendimiento para un período determinado, clasificados por la mayor cantidad de ventas.  |
| Los usuarios que compraron este artículo también compraron | AI-ML | Este módulo recomienda una lista de productos que se suelen comprar a la vez que el contenido del carro actual del consumidor. |
| A la gente también le gustó           | AI-ML | Este módulo recomienda productos para un producto de inicialización determinado según los patrones de compra del consumidor. |
| Picking para usted              | AI-ML | Este módulo recomienda una lista personalizada de productos basada en los patrones de compra del usuario que inició sesión. Para un usuario invitado, esta lista se contraerá. |

## <a name="additional-resources"></a>Recursos adicionales

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
