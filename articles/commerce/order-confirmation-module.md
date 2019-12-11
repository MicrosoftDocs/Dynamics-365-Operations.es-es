---
title: Módulo de confirmación de pedido
description: En este tema se tratan los módulos de confirmación de pedidos y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698335"
---
# <a name="order-confirmation-module"></a>Módulo de confirmación de pedido

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de confirmación de pedidos y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de la confirmación de pedido se usa para mostrar un mensaje de confirmación en una página de confirmación de pedido después de realizar un pedido. El módulo de confirmación de pedido muestra el número de confirmación de pedido y la dirección de correo electrónico del cliente que se proporcionó durante la finalización de la compra.

Cuando se realiza un pedido durante la finalización de la compra, la dirección de correo electrónico del cliente y el número de confirmación del pedido se pasan a la página de confirmación de pedido como cadena de consulta en la dirección URL de la página. El módulo de confirmación de pedido recibe esta información y genera el estado del pedido en la página de confirmación de pedido. El módulo de confirmación de pedido requiere este contexto de página para proporcionar el estado del pedido.

## <a name="order-confirmation-module-properties"></a>Propiedades del módulo de confirmación de pedido

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Título       | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | El módulo de confirmación de pedido puede tener un encabezado. De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado. Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad. |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a>Módulos que se pueden usar en un módulo de página de confirmación de pedido 

- **Recomendaciones**: el módulo de recomendaciones se puede colocar en la página de confirmación de pedido para sugerir otros productos al cliente.
- **Marketing**: el módulo de marketing puede agregar contenido de marketing a la página de confirmación de pedido.

## <a name="create-an-order-confirmation-page-module"></a>Crear un módulo de página de confirmación de pedido

1. Cree una plantilla de página con el nombre **plantilla de confirmación de pedido**.
1. En la franja **Principal** de la página predeterminada, agregue un módulo de confirmación de pedido.
1. En el módulo de confirmación de pedido, agregue un módulo de recomendaciones.
1. Guarde la plantilla y obtenga una vista previa de ella. No se debe representar el módulo de confirmación de pedido porque requiere el contexto del número de confirmación de pedido.
1. Proteja la plantilla y publíquela.
1. Use la plantilla de confirmación de pedido que acaba de crear para crear una página con el nombre **página de confirmación de pedido**.
1. Agregue la página predeterminada al esquema de página.
1. En la franja **Encabezado**, agregue un fragmento de encabezado.
1. En la franja **Pie de página**, agregue un fragmento de pie de página.
1. En la franja **Principal**, agregue un módulo de confirmación de pedido.
1. En el panel de propiedades del módulo de confirmación de pedido, agregue el encabezado **Confirmación de pedido**.
1. Debajo del módulo de confirmación de pedido, agregue un módulo de recomendaciones y configúrelo para que use la configuración **Nuevos** y **Más vendidos**.
1. Guarde la página y obtenga una vista previa de ella, protéjala y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
