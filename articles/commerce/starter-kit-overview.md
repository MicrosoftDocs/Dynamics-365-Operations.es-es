---
title: Visión general de kit de inicio
description: Este tema presenta una visión general del kit de inicio de Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1960e1354744fe1034783177ba331f5877d0bee7
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025911"
---
# <a name="starter-kit-overview"></a>Visión general de kit de inicio


[!include [banner](includes/banner.md)]

Este tema presenta una visión general del kit de inicio de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El kit de inicio de Dynamics 365 Commerce es una colección de módulos que se puede usar para crear un sitio web de comercio electrónico. Los módulos tienen tanto aspectos de la interfaz de usuario (IU) como aspectos de comportamiento funcional.

Se pueden aplicar temas a los módulos del kit de inicio para cambiar su aspecto. Los temas usan hojas de estilo CSS (CSS). Se proporciona un tema para un sitio de comercio electrónico ficticio con el nombre “Fabrikam” como parte de kit de inicio y se puede utilizar como referencia.

## <a name="starter-kit-modules"></a>Módulos de kit de inicio

Los siguientes tipos de módulos se proporcionan en el kit de inicio:

- **Módulo de contenedor**: un módulo de contenedor es un módulo sencillo que actúa como host para otros módulos. Controla el diseño de los módulos que se encuentran dentro.
- **Módulos de marketing**: los módulos de marketing incluyen módulos de carrusel, bloque de contenido, bloque de texto y reproductor de vídeo. Todos estos módulos se pueden usar para mostrar el contenido. Se pueden colocar en cualquier página y se controlan por datos desde el sistema de gestión de contenidos (CMS).
- **Módulos de encabezado y pie de página**: los módulos de encabezado y pie de página aparecen en el encabezado y el pie de página de todas las páginas del sitio. Esos módulos se pueden configurar según sea necesario a través de las propiedades.
- **Módulos de búsqueda**: los productos se pueden descubrir mediante el módulo de búsqueda en el encabezado. Los resultados de la búsqueda aparecen en la página de resultados de la búsqueda. Los productos también se pueden descubrir en las páginas de categoría, que son páginas dedicadas para cada categoría que se admite en la jerarquía de navegación de canal. Además, los módulos de refinador se pueden usar para filtrar aún más los resultados en los resultados de la búsqueda y páginas de categoría.
- **Módulos de página de detalles de productos**: las páginas de detalles de producto utilizan varios módulos para mostrar la información del producto. El módulo del cuadro de compra permite a los clientes ver productos y agregarlos al carro. Otros módulos, como el módulo de especificaciones técnicas, muestran los detalles de productos. El módulo de clasificaciones y revisiones se puede usar para ver y proporcionar revisiones.
- **Módulo de comprar en línea y recoger en una tienda**: el módulo de comprar en línea y recoger en una tienda se integra con Bing Maps. Se puede utilizar para encontrar tiendas cercanas donde los clientes pueden recoger productos que han comprado.
- **Módulos de compra**: los módulos de compra incluyen el módulo de carro, que se puede usar para agregar artículos al carro. El módulo de finalización de la compra captura la dirección de envío, las opciones de entrega, la tarjeta regalo, el programa de fidelización y la información de la tarjeta de crédito, para poder procesar un pedido. Una vez realizado un pedido, el módulo de confirmación de pedido se puede utilizar para mostrar los detalles de confirmación.
- **Módulos de página de gestión de cuentas**: el módulo de inicio de sesión permite a los clientes iniciar sesión en una cuenta existente y el módulo de suscripción les permite crear una cuenta nueva. Una vez creada una cuenta, el módulo de historial del pedido se puede usar para ver pedidos recientes y el módulo de detalles del pedido se puede usar para ver los detalles del pedido.
- **Módulo de recomendaciones**: las recomendaciones se muestran a través del módulo de colocación de producto. Este módulo admite listas algorítmicas y listas editoriales que se pueden mostrar en cualquier página.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
