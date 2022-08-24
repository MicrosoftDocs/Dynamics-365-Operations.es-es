---
title: Módulo de compartir en redes sociales
description: En este artículo se tratan los módulos de compartir en redes sociales y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 88bc5469e3072b625836cc942efbd2206f6dd6ba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284694"
---
# <a name="social-share-module"></a>Módulo de compartir en redes sociales

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de compartir en redes sociales y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos para compartir en redes sociales permiten a los usuarios compartir las direcciones URL de las páginas del sitio de comercio electrónico en las redes sociales, como Facebook, Twitter, Pinterest y LinkedIn. Las direcciones URL de las páginas del sitio también se pueden compartir por correo electrónico. Los módulos para compartir en redes sociales se utilizan comúnmente en las páginas de detalles del producto (PDP) para ayudar a los usuarios a compartir información sobre el producto.

Cada módulo para compartir en redes sociales es un contenedor para los módulos de elementos para compartir en redes sociales. Cada módulo de elementos para compartir en redes sociales se puede configurar para que apunte a un sitio de redes sociales específico. La integración con Facebook, Twitter, Pinterest, LinkedIn y el correo electrónico son compatibles desde el primer momento. Cuando un usuario del sitio selecciona un símbolo de red social, se lanza un iframe HTML para el sitio de red social respectivo. Dentro del iframe, el usuario puede iniciar sesión y publicar el contenido de la página que estaba viendo.

Cada plataforma de redes sociales puede rastrear cookies, por lo que este módulo requiere que los usuarios del sitio acepten el mensaje de notificación de consentimiento de cookies. Cuando no se acepta el consentimiento de las cookies, el módulo se ocultará en la página. Para obtener más información, consulte [Cumplimiento de las cookies](cookie-compliance.md).

La siguiente ilustración destaca un ejemplo de un módulo para compartir en redes sociales utilizado en la página de detalles de un producto.

![Ejemplo de un módulo para compartir en redes sociales.](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Propiedades del módulo Compartir en redes sociales

| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Leyenda                  | Texto | Esta propiedad especifica un título para el módulo. |
| Orientación | **Vertical** u **Horizontal**  | Esta propiedad define la orientación del diseño de los elementos de redes sociales. |

## <a name="social-share-item-module-properties"></a>Propiedades del módulo del elemento Compartir en redes sociales
| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Redes sociales              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Correo** | Un menú desplegable con una lista de plataformas de redes sociales. |
| Icono |Imagen    | Esta será la imagen que se mostrará para las respectivas redes sociales. Como práctica recomendada, consulte el SDK de la plataforma de redes sociales para conocer la imagen recomendada para cada plataforma. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Agregar un módulo de compartir en redes sociales a un módulo de cuadro de compra

Para agregar un módulo de compartir en redes sociales a un módulo de cuadro de compra, siga estos pasos.

1. En el sitio de Fabrikam, seleccione **Páginas** y luego seleccione la página **DefaultPDP** para abrir la página de detalles del producto. 
1. En el espacio **Cuadro de compra (obligatorio)**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Redes sociales** y, a continuación, **Aceptar**.
1. En el espacio **Redes sociales**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **SocialShare** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Compartir en redes sociales**, **Orientación**, seleccione **Horizontal**. Agregue un título según sea necesario.
1. En el espacio **SocialShare**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **SocialShareItem** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Elemento para compartir en redes sociales**, en **Redes sociales**, seleccione **Facebook**.
1. En el panel de propiedades del módulo **Elemento para compartir en redes sociales**, en **Icono**, seleccione **+ Agregar una imagen**.
1. En el cuadro de diálogo **Selector de medios**, seleccione la imagen del logotipo de Facebook y, después, seleccione **Aceptar**. Si no está presente una imagen del logotipo de Facebook, seleccione **Cargar nuevo elemento multimedia** para cargar uno.
1. Agregar y configurar módulos adicionales de **Elemento para compartir en redes sociales** según sea necesario.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. La página mostrará el módulo de compartir en redes sociales.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Cumplimiento de cookies](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
