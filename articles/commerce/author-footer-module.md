---
title: Módulo de pie de página
description: En este artículo se tratan los módulos de pie de página y cómo crearlos en Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4e7796d9700eabc923f2bb45187832d5993ae56e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876621"
---
# <a name="footer-module"></a>Módulo de pie de página  

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de pie de página y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.

El módulo de pie de página es un contenedor especial que se usa para hospedar los módulos que aparecen en el pie de página. Por ejemplo, puede incluir vínculos a las diversas páginas de todo el sitio, como las páginas **Ponerse en contacto con nosotros** y **Directivas de la tienda**.

La siguiente imagen muestra un ejemplo de un módulo de pie de página en una página de sitio.

![Ejemplo de módulo de pie de página.](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a>Propiedades del módulo de pie de página 

Como la mayoría de los contenedores, un módulo de pie de página admite propiedades para el encabezado y el ancho. También admite la adición de varios módulos de categoría de pie de página. Cada módulo de categoría de pie de página que se agrega se representa como columna en el módulo de pie de página.

## <a name="modules-available-in-a-footer-module"></a>Módulos disponibles en un módulo de pie de página

**Elemento de pie de página**: un módulo de elemento de pie de página puede contener un encabezado o un vínculo. El encabezado se usa generalmente como un título de sección de pie de página.  Cada vínculo del pie de página se puede configurar para que tenga solo texto (por ejemplo, los vínculos “Ponerse en contacto con nosotros” y “Privacidad”), o de modo que tenga tanto texto e imagen (por ejemplo, vínculos de redes sociales). Si se proporciona un encabezado y un vínculo, la propiedad del encabezado tendrá prioridad sobre el vínculo. 

**Volver arriba**: Un módulo Volver arriba ofrece un vínculo de navegación rápida hasta la parte superior de la página. Es necesario un destino. El valor predeterminado de destino es \#, que lleva al usuario a la parte superior de la página.

## <a name="create-a-footer-module"></a>Crear un módulo de pie de página

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo **Seleccionar fragmento**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento y, a continuación, seleccione **Aceptar**.
1. En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Categoría de pie de página** y, a continuación, **Aceptar**.
1. En el espacio **Categoría de pie de página**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Elemento de pie de página** y, a continuación, **Aceptar**.
1. Seleccione el espacio **Elemento de pie de página** y luego, en el panel de propiedades de la derecha, configure el encabezado, el vínculo y el texto del vínculo, y la imagen según sea necesario.
1. Para agregar más elementos de pie de página, repita para cada uno los pasos del 5 al 7.
1. Para agregar un vínculo "Volver arriba" a su pie de página, seleccione los puntos suspensivos (**...**) en el espacio **Categoría de pie de página** y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Volver arriba** y, a continuación, **Aceptar**.
1. Seleccione el espacio **Volver arriba** y luego, en el panel de propiedades de la derecha, configure el texto y otras propiedades del módulo según sea necesario.
1. Seleccione **Finalizar edición** para comprobar en el fragmento y luego seleccione **Publicar** para publicarlo.

Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.

1. En el espacio **Pie de página** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

Al agregar el fragmento a plantillas de página, ayuda a garantizar que el pie de página se representa en cada página.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
