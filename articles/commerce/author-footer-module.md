---
title: Módulo de pie de página
description: En este tema se tratan los módulos de pie de página y cómo crearlos en Dynamics 365 Commerce.
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
ms.openlocfilehash: 7c253cd9620180b09f2f5cae232e46d236deabdd
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697322"
---
# <a name="footer-module"></a>Módulo de pie de página  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de pie de página y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El módulo de pie de página es un contenedor especial que se usa para hospedar los módulos que aparecen en el pie de página. Por ejemplo, puede incluir vínculos a las diversas páginas de todo el sitio, como las páginas **Ponerse en contacto con nosotros** y **Directivas de la tienda**.

## <a name="footer-module-properties"></a>Propiedades del módulo de pie de página 

Como la mayoría de los contenedores, un módulo de pie de página admite propiedades para el encabezado y el ancho. También admite la adición de varios módulos de categoría de pie de página. Cada módulo de categoría de pie de página que se agrega se representa como columna en el módulo de pie de página.

## <a name="modules-available-in-a-footer-module"></a>Módulos disponibles en un módulo de pie de página

**Elementos de pie de página**: un módulo de elementos de pie de página puede contener un encabezado, una imagen y un vínculo. El encabezado se puede usar solo o combinado con una imagen y un vínculo. Cada vínculo del pie de página se puede configurar para que tenga solo texto (por ejemplo, los vínculos “Ponerse en contacto con nosotros” y “Privacidad”), o de modo que tenga tanto texto e imagen (por ejemplo, vínculos de redes sociales).

**Volver arriba**: Un módulo Volver arriba ofrece un vínculo de navegación rápida hasta la parte superior de la página. Es necesario un destino. El valor predeterminado de destino es #, que lleva al usuario a la parte superior de la página.

## <a name="author-a-footer-module"></a>Crear un módulo de pie de página

1. En el panel de navegación, seleccione **Fragmentos** y después seleccione **Nuevo fragmento de página**.
1. En el cuadro de diálogo **Nuevo fragmento de página**, seleccione el módulo de pie de página, especifique un nombre para el fragmento de la página y, a continuación, seleccione **Aceptar**.
1. En el árbol de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) para el módulo de pie de página y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo de categoría de pie de página y, a continuación, **Aceptar**.
1. En el árbol de esquema de la izquierda, seleccione el botón de puntos suspensivos para el módulo de categoría de pie de página y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo de elemento de pie de página y, a continuación, **Aceptar**.
1. En el esquema de árbol, seleccione el módulo de elemento de pie de página. A continuación, en el panel de propiedades de la derecha, configure el encabezado, el vínculo y el texto del vínculo, y la imagen según sea necesario.
1. Para agregar más elementos de pie de página, repita los pasos del 5 al 7.
1. Para agregar un vínculo "Volver arriba" a su pie de página, seleccione el botón de puntos suspensivos para el módulo de categoría de pie de página y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo Volver arriba y, a continuación, **Aceptar**.
1. En el esquema de árbol, seleccione el módulo Volver arriba. A continuación, en el panel de propiedades de la derecha, configure el módulo Volver arriba según sea necesario.
1. Guarde el fragmento de página, protéjalo y publíquelo.

En cada plantilla de página que se ha creado para el sitio, siga estos pasos.

1. En la franja **Principal** de la página predeterminada, en el módulo de pie de página, agregue el fragmento de pie de página que ha creado.
1. Guarde la plantilla, protéjala y publíquela.

Al agregar el fragmento de página a plantillas de página, ayuda a garantizar que el pie de página se representa en cada página.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
