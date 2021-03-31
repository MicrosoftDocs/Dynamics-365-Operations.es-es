---
title: Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL
description: Este tema describe cómo configurar una página de comercio electrónico de Microsoft Dynamics 365 Commerce que puede ofrecer contenido dinámico, según los parámetros de URL.
author: StuHarg
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d6b4756fc81dc99786da251d5d9a575a71ccc49
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208024"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tema describe cómo configurar una página de comercio electrónico de Microsoft Dynamics 365 Commerce que puede ofrecer contenido dinámico, según los parámetros de URL.

Una página de comercio electrónico se puede configurar para ofrecer contenido diferente, según un segmento de la ruta de la URL. Por lo tanto, la página se conoce como página dinámica. El segmento se utiliza como parámetro para recuperar el contenido de la página. Por ejemplo, una página que se llama **blog\_viewer** se crea y se asocia con la URL `https://fabrikam.com/blog`. Esta página se puede utilizar para mostrar contenido diferente, según el último segmento de la ruta de la URL. Por ejemplo, el último segmento de la URL `https://fabrikam.com/blog/article-1` es **article-1**.

Las páginas personalizadas independientes que anulan la página dinámica también se pueden asociar con segmentos en la ruta de la URL. Por ejemplo, una página que se llama **blog\_summary** se crea y se asocia con la URL `https://fabrikam.com/blog/about-this-blog`. Cuando se solicita esta URL, se devuelve la página **blog\_summary** que está asociada con el parámetro **/about-this-blog**, en lugar de la página **blog\_viewer**.

> [!NOTE]
> La funcionalidad para alojar, recuperar y mostrar contenido de páginas dinámicas se implementa mediante un módulo personalizado. Para más información, vea [Extensibilidad de canales en línea](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Configurar una página de comercio electrónico dinámica

Para configurar una página de comercio electrónico dinámica, debe crear la página dinámica, crear la URL base y configurar la ruta a la página dinámica.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Crear la página que ofrecerá contenido dinámico

Para crear una página que ofrezca contenido dinámico, siga los pasos de [Agregar una nueva página de sitio](add-new-page.md). La página que cree requerirá la implementación de un módulo que utilice el último segmento de la ruta de la URL para recuperar contenido de un origen de datos externo. Para obtener más información sobre el desarrollo de módulos personalizados, consulte [Extensibilidad de canales en línea](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Crear la URL base para la página dinámica

Para crear la URL base para la página dinámica en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a **URL** y seleccione **Nueva \> Nueva URL**.
1. En el cuadro de diálogo **Crear nueva URL**, seleccione **Página interna**. En **Ruta de URL**, introduzca la ruta que servirá como raíz para la página dinámica (en este ejemplo, **/blog**). A continuación, seleccione **Siguiente**.
1. En el cuadro de diálogo **Seleccionar una página**, seleccione la página que ha creado para servir de página dinámica y, a continuación, seleccione **Aceptar**.
1. Seleccione **Publicar**.

### <a name="configure-the-route-to-the-dynamic-page"></a>Configurar la ruta a la página dinámica

Para configurar la ruta a la página dinámica en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a **Configuración del sitio \> Extensiones**.
1. En **Rutas de URL parametrizadas**, seleccione **Agregar** y luego introduzca la ruta de URL que introdujo al crear la URL (en este ejemplo, **/blog**).
1. Seleccione **Guardar y publicar**.

Una vez configurada la ruta, todas las solicitudes a la ruta URL parametrizada devolverán la página asociada con esa URL. Si alguna solicitud contiene un segmento adicional, se devolverá la página asociada y el contenido de la página se recuperará utilizando el segmento como parámetro. Por ejemplo,`https://fabrikam.com/blog/article-1` devolverá la página **blog\_summary** y el contenido de la página se recuperará utilizando el parámetro **/article-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Reemplazar una URL parametrizada con una página personalizada

Para reemplazar una URL parametrizada con una página personalizada en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a **URL** y seleccione **Nueva \> Nueva URL**.
1. En el cuadro de diálogo **Crear nueva URL**, seleccione **Página interna**. En **Ruta de URL**, introduzca la ruta que incluye el segmento a reemplazar (en este ejemplo, **/blog/about-this-blog**). A continuación, seleccione **Siguiente**.
1. En el cuadro de diálogo **Seleccionar una pagina**, seleccione la página personalizada y luego seleccione **Guardar**.
1. Seleccione **Publicar**.
1. Si la página personalizada aún no se ha publicado, vaya a **Páginas**, seleccione la página personalizada y luego seleccione **Publicar**.

Una vez publicada la página personalizada, se publicará en lugar de la página dinámica que tiene contenido parametrizado.

## <a name="additional-resources"></a>Recursos adicionales

[Modificar una página de sitio existente](modify-existing-page.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)

[Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Enriquecer una página de aterrizaje de categoría](enrich-category-page.md)

[Verificar accesibilidad de contenido de página](verify-accessibility.md)

[Extensibilidad de canal en línea](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]