---
title: Módulo de confirmación de pedido
description: En este tema se tratan los módulos de confirmación de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf33ebf9c0c5136f40fcd7e1012988d186c4169b
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415698"
---
# <a name="order-confirmation-module"></a>Módulo de confirmación de pedido

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de confirmación de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

El módulo para la confirmación del pedido se usa para mostrar los detalles de confirmación de pedido después de que se haya realizado un pedido. Muestra el id. de confirmación del pedido, la información de contacto del pedido y otros detalles del pedido, como los artículos que se compraron, la información de pago, las opciones de recogida y el método de envío.

## <a name="order-confirmation-module-properties"></a>Propiedades del módulo de confirmación de pedido

| Nombre de la propiedad  | Valores | Descripción |
|----------------|--------|-------------|
| Título        | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | El módulo de confirmación de pedido puede tener un encabezado. De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado. Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad. |
| Número de contacto | Text | Se puede proporcionar un número de contacto para preguntas relacionadas con pedidos. |
| Mostrar información sobre el horario de recogida | Verdadero o falso | Esta propiedad está disponible en Dynamics 365 Commerce 10.0.15 y versiones posteriores. Cuando se establece en True, muestra la información del intervalo de tiempo de recogida si se proporciona para un artículo de recogida|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Módulos que se pueden usar en una página de confirmación del pedido

Al crear una página de confirmación del pedido, puede agregar otros módulos relevantes además del módulo de confirmación del pedido. A continuación, encontrará algunos ejemplos:

- **Módulo Recomendaciones**: el módulo de recomendaciones se puede agregar a la página de confirmación del pedido para sugerir otros productos al cliente.
- **Módulos de marketing**: se puede agregar cualquier módulo de marketing a la página de confirmación del pedido para mostrar el contenido de marketing.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Agregar un módulo de confirmación del pedido a una página

Para agregar un módulo de confirmación del pedido a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en de **Nombre de la plantilla**, especifique el nombre **Plantilla de confirmación del pedio** y luego seleccione **Aceptar**.
1. En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Confirmación del pedido** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la plantilla. No se representará el módulo de confirmación de pedido porque requiere el contexto del número de confirmación de pedido.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de confirmación del pedido**. En **Nombre de página**, introduzca **Página de confirmación del pedido** y después seleccione **Aceptar**.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Confirmación del pedido** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de confirmación del pedido, seleccione **Encabezado** al lado del símbolo de lápiz.
1. En el campo **Texto de encabezado** del cuadro de diálogo **Encabezado**, especifique el texto de encabezado **Confirmación del pedido** y luego seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)
