---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686631"
---
# <a name="header-module"></a>Módulo de encabezado

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

En Dynamics 365 Commerce, un encabezado de página consta de varios módulos, como los de encabezado, menú de navegación, búsqueda, banner promocional y consentimiento de cookies. 

El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un símbolo de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda. Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil). Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).

La siguiente imagen muestra un ejemplo de un módulo de encabezado en una página de sitio.

![Ejemplo de módulo de cabecera](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Propiedades de un módulo de encabezado

Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**. 

Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página. Para obtener más información, consulte [Agregar un logotipo](add-logo.md). 

La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.

## <a name="modules-that-are-available-in-a-header-module"></a>Módulos disponibles en un módulo de encabezado

Los módulos siguientes se pueden usar en un módulo de encabezado:

- **Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos. La jerarquía de navegación de canales se puede configurar en Dynamics 365 Commerce. El menú de navegación tiene una propiedad **Origen de navegación** que se utiliza para especificar los elementos del menú de navegación de Retail Server y elementos menú estáticos como un origen. Si los elementos de menú estáticos se especifican como un origen, se pueden proporcionar vínculos relativos a otras páginas en el sitio. Los artículos configurados aparecerán como navegación de encabezado. 

- **Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos. La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**. El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera. El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.

- **Ícono de carrito** - El módulo de icono de carrito representa el icono de carrito, que muestra la cantidad de artículos en el carrito en un momento dado. Para más información, ver [Módulo de icono de carrito](cart-icon-module.md).

## <a name="create-a-header-module-for-a-page"></a>Crear un módulo de encabezado para una página

Para crear un módulo de encabezado, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo **Nuevo fragmento de página**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento de la página y, a continuación, seleccione **Aceptar**.
1. Seleccione el espacio **Contenedor predeterminado** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar contenedor**.
1. En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione los módulos **Banner promocional** y **Consentimiento de cookies** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. Seleccione el espacio **Contenedor** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Encabezado** y, a continuación, **Aceptar**.
1. En el espacio **Menú de navegación** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Menú de navegación** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo del menú de navegación, configure las propiedades según sea necesario.
1. En el espacio **Búsqueda** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Búsqueda** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo del módulo de búsqueda, configure las propiedades según sea necesario.
1. En el espacio **Icono de carro** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Icono de carro** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo del icono de carro, configure las propiedades según sea necesario. Si desea que el icono del carro muestre un resumen del carro (también conocido como minicarro) cuando los usuarios coloquen el cursor sobre él, seleccione **Mostrar minicarro**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.

Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.

1. En el espacio **Encabezado** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carrito](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
