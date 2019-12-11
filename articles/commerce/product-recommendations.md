---
title: Visión general de recomendaciones de producto
description: En este tema se proporciona información general sobre recomendaciones de productos. Las recomendaciones de producto permiten a los clientes encontrar fácil y rápidamente los productos que desean, e incluso los productos que no pensaban comprar en un principio.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770056"
---
# <a name="product-recommendations-overview"></a>Visión general de recomendaciones de producto

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce se puede utilizar para mostrar recomendaciones de productos en el dispositivo de punto de venta (PDV) y sitio web de comercio electrónico. Las recomendaciones de productos son artículos en los que un cliente puede estar interesado. Las recomendaciones se basan en las tendencias de compras de otros clientes en tiendas físicas o en línea.

Las recomendaciones de productos permiten a los clientes buscar con facilidad y rapidez lo que desean a la vez que tienen una experiencia que les sirve bien. Las ventas cruzadas y verticales se pueden usar incluso para ayudar a clientes a encontrar productos adicionales que no se pensaron en un principio para comprar. Cuando se usan recomendaciones para ayudar con la detección de productos, pueden crear más oportunidades de conversión, ayudan a aumentar los ingresos de ventas e incluso ayudan a mejorar la retención y la satisfacción del cliente.

En Commerce, las recomendaciones de productos son impulsadas con tecnologías de aprendizaje automático de Microsoft Recommendations a gran escala.


## <a name="scenarios"></a>Situaciones

Las recomendaciones de productos están disponibles para los siguientes escenarios:

- **En cualquier página de tienda para explorar o página de aterrizaje en comercio electrónico:** si los clientes o socios de tienda visitan una página de la tienda, el motor de recomendaciones puede sugerir productos en las listas **Nuevos**, **Más vendidos** y **Tendencias**.
- **En la página Detalles de producto:** si los clientes o socios de tienda visitan una página **Detalles de producto**, el motor de recomendaciones sugiere artículos adicionales de los que también hay probabilidad que se compren. Estos artículos aparecen en la lista **A la gente también le gustó**.
- **En la página Transacción o la página de finalización de compra:** el motor de recomendaciones sugiere artículos, en función de la lista completa de artículos de la cesta. Estos artículos aparecen en la lista **Los usuarios que compraron esto también compraron**.

## <a name="recommendation-service"></a>Servicio de recomendaciones

Las recomendaciones de productos utilizan las tecnologías de aprendizaje automático de recomendaciones de la siguiente manera:

- Los datos en el formato requerido por el servicio de recomendaciones se extraen de la base de datos operativa de Commerce y se envían al almacén de entidades.
- El servicio de recomendaciones utiliza los datos para entrenar modelos de recomendaciones para las listas **A la gente también le gustó**, **Los usuarios que compraron esto también compraron**, **Nuevos**, **Más vendidos** y **Tendencias**.

## <a name="additional-resources"></a>Recursos adicionales

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Crear listas mantenidas de recomendaciones de producto](create-editorial-recommendation-lists.md)

[Administrar resultados de recomendaciones de producto basadas en AI-ML](modify-product-recommendation-results.md)

[Agregar listas de recomendaciones a páginas](add-reco-list-to-page.md)
