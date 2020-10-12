---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99457b2c98eae0ddd898f852630d690140a5a4c5
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817019"
---
# <a name="header-module"></a>Módulo de encabezado

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

En Dynamics 365 Commerce, un encabezado de página se configura como un fragmento de página que incluye los módulos de encabezado, banner promocional y consentimiento de cookies. 

El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un módulo de icono de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda. Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil). Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).

La siguiente imagen muestra un ejemplo de un módulo de encabezado en una página de sitio.

![Ejemplo de módulo de cabecera](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a>Propiedades de un módulo de encabezado

Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**. 

Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página. Para obtener más información, consulte [Agregar un logotipo](add-logo.md). 

La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.

## <a name="modules-that-are-available-within-a-header-module"></a>Módulos disponibles en un módulo de encabezado

Los módulos siguientes se pueden usar en un módulo de encabezado:

- **Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos. Para obtener más información, consulte [Módulo del menú de navegación](nav-menu-module.md).

- **Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos. La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**. El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera. El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.

- **Ícono de carrito** - El módulo de icono de carrito representa el icono de carrito, que muestra la cantidad de artículos en el carrito en un momento dado. Para más información, ver [Módulo de icono de carrito](cart-icon-module.md).

## <a name="create-a-header-fragment-for-a-page"></a>Crear un fragmento de encabezado para una página

Para crear un fragmento de encabezado, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento y, a continuación, seleccione **Aceptar**.
1. Seleccione el espacio **Contenedor predeterminado** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar pantalla**.
1. En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione los módulos Banner promocional y **Consentimiento de cookies**, **Encabezado** y **Banner promocional** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Banner promocional**, seleccione **Agregar mensaje** y luego seleccione **Mensaje**.
1. En el cuadro de diálogo **Mensaje**, agregue el texto y los vínculos para el contenido promocional y seleccione **Aceptar**.
1. En el panel de propiedades del módulo **Consentimiento de cookies**, agregue y configure texto y un vínculo a la página de privacidad del sitio.
1. En el espacio **Menú de navegación** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Menú de navegación** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo del menú de navegación, en **Fuente para el menú de navegación**, seleccione **Retail Server**.
1. En el panel de propiedades del módulo del menú de navegación, en **Elementos de menú estáticos**, seleccione **Agregar elemento de menú** y luego seleccione **Elemento de menú**. 
1. En el cuadro de diálogo **Elemento de menú**, en **Texto del elemento de menú** escriba "Contacto".
1. En el cuadro de diálogo **Elemento de menú**, en **Destino de vínculo de elemento de menú**, seleccione **Agregar un vínculo**.
1. En el cuadro de diálogo **Agregar un vínculo**, seleccione la dirección URL para la página "Contacto" del sitio y, a continuación, seleccione **Aceptar**.  
1. En el cuadro de diálogo **Elemento de menú**, seleccione **Aceptar**.
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

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de contenedor](add-container-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de banner promocional](add-alert.md)

[Módulo del menú de navegación](nav-menu-module.md) 

[Consentimiento de cookies](cookie-consent-module.md)

[Módulo de pie de página](author-footer-module.md)
