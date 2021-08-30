---
title: Descripción general de la biblioteca de módulos
description: Este tema presenta una visión general de la biblioteca de módulos de Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f1301f61e6bc0d408d4883b238808f66b14abc2d372e97671c71ba7dd5174124
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721985"
---
# <a name="module-library-overview"></a>Descripción general de la biblioteca de módulos

[!include [banner](includes/banner.md)]

Este tema presenta una visión general de la biblioteca de módulos de Microsoft Dynamics 365 Commerce.

La biblioteca de módulos de Dynamics 365 Commerce es una colección de módulos que se pueden usar para crear un sitio web de comercio electrónico. Los módulos tienen tanto aspectos de la interfaz de usuario (IU) como aspectos de comportamiento funcional.

Se pueden aplicar temas a los módulos de la biblioteca de módulos para cambiar su aspecto. Los temas usan hojas de estilo CSS (CSS). Se proporciona un tema para un sitio de comercio electrónico ficticio con el nombre “Fabrikam” como parte de la biblioteca de módulos y se puede utilizar como referencia.

## <a name="module-library-modules"></a>Módulos de la biblioteca de módulos

En la biblioteca de módulos se proporcionan los siguientes tipos de módulos:

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]