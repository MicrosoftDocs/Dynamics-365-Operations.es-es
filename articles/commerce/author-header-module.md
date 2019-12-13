---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697284"
---
# <a name="header-module"></a>Módulo de encabezado

[!include [banner](includes/preview-banner.md)] [!include [banner](includes/banner.md)]

En este tema se tratan los módulos de encabezado y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de encabezado es un contenedor especial que se usa para alojar todos los módulos que se mostrarán en un encabezado de página. Por ejemplo, puede incluir el logotipo de su sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas del sitio y la barra de la búsqueda.

Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil). Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).

## <a name="properties-of-a-header"></a>Propiedades de un encabezado

Como los contenedores genéricos, un módulo de encabezado admite las propiedades de **encabezado** y **ancho**.

Un módulo de cabecera tiene varias franjas. Por ejemplo, hay franjas para un mensaje informativo, un menú de navegación, un logotipo, una barra de búsqueda, un icono de carro, un icono de lista de deseos e información de cuenta. Cada franja admite un conjunto concreto de módulos.

## <a name="modules-that-are-available-in-a-header-module"></a>Módulos disponibles en un módulo de encabezado

Los módulos siguientes se pueden usar en un módulo de encabezado:

- **Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos. La jerarquía de navegación de canales se puede configurar en Dynamics 365 Retail. Los artículos configurados aparecerán como navegación de encabezado. Además, se pueden configurar los vínculos de navegación estáticos y se pueden proporcionar los vínculos relativos a otras páginas del sitio de comercio electrónico. El propio encabezado se puede alinear a la izquierda, a la derecha o al centro.
- **Icono de carro**: El icono de carro es un icono especial que representa el carro. Se muestra en el encabezado e indica el número de artículos del carro. Un vínculo a la página del carro debe acompañar al icono del carro, para poder redirigir a los clientes a la página del carro cuando interactúan con el icono.
- **Icono de lista de deseos**: El icono de la lista de deseos se muestra en el encabezado e indica el número de artículos que se han agregado a la lista de deseos del cliente. Un vínculo a la página de lista de deseos debe acompañar a este icono, para poder redirigir a los clientes a la página de la lista de deseos cuando interactúan con el icono.
- **Módulo de inicio de sesión**: El módulo de inicio de sesión se muestra en el encabezado. Permite a los clientes iniciar sesión en su cuenta o registrarse para una cuenta. Si el cliente ya ha iniciado sesión, el módulo se puede configurar para mostrar vínculos a la página de la cuenta, a la página de historial de pedidos o a otra página.
- **Módulo de logotipo**: Este módulo muestra el logotipo que representa al minorista y a la marca. Es una imagen con un vínculo. El vínculo se configura normalmente para que tenga una redirección a la página principal. Por tanto, los clientes pueden regresar rápidamente a la página principal desde cualquier página del sitio.
- **Alerta**: Aparece una alerta en el encabezado y se utiliza para mostrar un mensaje en línea que se aplica a todas las páginas del sitio. Por ejemplo, una alerta puede mostrar un mensaje como “La venta anual finaliza en 2 días”.
- **Barra de búsqueda**: La barra de la búsqueda permite a los usuarios especificar términos de búsqueda de modo que puedan buscar los productos. El módulo se debe configurar con la dirección URL de la página de resultados de la búsqueda. El parámetro de la cadena de consulta se puede configurar (el valor predeterminado es **“q”**). La barra de búsqueda tiene una franja de sugerencia automática donde se debe agregar el módulo de sugerencia automática.
- **Sugerencia automática**: El módulo de sugerencia automática muestra resultados automáticamente. Estos resultados pueden ser palabras clave, productos o categorías donde se encuentra el término de búsqueda.

## <a name="create-a-header-module"></a>Crear un módulo de encabezado

Para crear un módulo de encabezado, siga estos pasos.

1. Cree un fragmento de página que incluya un módulo de encabezado.
1. Agregue módulos a las franjas del módulo de encabezado.
1. Actualice la configuración para cada módulo.
1. Guarde el fragmento de página. 
1. Proteja la página y publíquela.

Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.

1. En la página predeterminada, agregue el fragmento de página que contiene el módulo de encabezado en el encabezado de la franja principal.
1. Guarde la plantilla. 
1. Proteja la plantilla y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
