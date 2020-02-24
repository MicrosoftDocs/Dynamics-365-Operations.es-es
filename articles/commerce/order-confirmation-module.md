---
title: Módulo Detalles del pedido
description: En este tema se tratan los módulos de detalles de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026026"
---
# <a name="order-details-module"></a>Módulo Detalles del pedido


[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de detalles de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El módulo Detalles del pedido se usa para mostrar los detalles de confirmación de pedido después de que se haya realizado un pedido. Muestra el id. de confirmación del pedido, la información de contacto del pedido y otros detalles del pedido, como los artículos que se compraron, la información de pago y el método de envío.

## <a name="order-confirmation-module-properties"></a>Propiedades del módulo de confirmación de pedido

| Nombre de la propiedad  | Valores | Descripción |
|----------------|--------|-------------|
| Título        | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | El módulo de confirmación de pedido puede tener un encabezado. De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado. Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad. |
| Número de contacto | Text | Se puede proporcionar un número de contacto para preguntas relacionadas con pedidos. |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a>Módulos que se pueden usar en una página de detalles del pedido

Al crear una página de detalles del pedido, puede agregar otros módulos relevantes además del módulo de detalles del pedido. A continuación, encontrará algunos ejemplos:

- **Módulo Recomendaciones**: el módulo de recomendaciones se puede agregar a la página de detalles del pedido para sugerir otros productos al cliente.
- **Módulos de marketing**: se puede agregar cualquier módulo de marketing a la página de detalles del pedido para mostrar el contenido de marketing.

## <a name="create-an-order-details-page-module"></a>Crear un módulo de página de detalles del pedido

1. Cree una plantilla de página con el nombre **Plantilla de detalles del pedido**.
1. En la franja **Principal** de la página predeterminada, agregue un módulo de detalles de pedido.
1. En el módulo de detalles del pedido, agregue un módulo de recomendaciones.
1. Guarde la plantilla y obtenga una vista previa de ella. No se representará el módulo de detalles del pedido porque requiere el contexto del número de confirmación de pedido.
1. Termine de editar la plantilla y publíquela.
1. Use la plantilla de detalles del pedido que acaba de crear para crear una página con el nombre **página de detalles de pedido**.
1. Agregue la página predeterminada al esquema de página.
1. En la franja **Encabezado**, agregue un fragmento de encabezado.
1. En la franja **Pie de página**, agregue un fragmento de pie de página.
1. En la franja **Principal**, agregue un módulo de detalles de pedido.
1. En el panel de propiedades para el módulo de detalles de pedido, agregue el encabezado **Detalles de pedido**.
1. Debajo del módulo de detalles de pedido, agregue un módulo de recomendaciones y configúrelo para que use la configuración **Nuevos** y **Más vendidos**.
1. Guarde la página y obtenga una vista previa de ella.
1. Termine de editar la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
