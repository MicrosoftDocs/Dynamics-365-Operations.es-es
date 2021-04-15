---
title: Guardar, obtener una vista previa y publicar una página
description: En este tema se describe cómo guardar, obtener una vista previa y publicar una página en Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f1eff0edeb630628057bd0a90e2dadc4857600f1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791832"
---
# <a name="save-preview-and-publish-a-page"></a>Guardar, obtener una vista previa y publicar una página

[!include [banner](includes/banner.md)]

En este tema se describe cómo guardar, obtener una vista previa y publicar una página en Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Guardar una página

Para guardar una página, debe haberla desprotegida para usted y abrirla en el editor de páginas. Para desproteger una página, en la barra de comandos, seleccione **Editar**. Después de finalizar la edición de una página, debe guardarla inmediatamente para garantizar que se almacenan los cambios.

Al guardar una página, los cambios solo son visibles para usted. La operación de guardar está pensada principalmente para almacenar cambios mientras la página no está lista aún para protegerse. Cuando haya terminado de modificar la página, se recomienda que la proteja, de modo que los cambios pasen a ser visibles para otros. En ese momento, la página también se puede desproteger por otros usuarios que deben modificarla.

## <a name="preview-a-page"></a>Obtener una vista previa de una página

La herramienta de creación ofrece dos tipos de características de vista previa: generador de página visual, que es un panel de vista previa de “Lo que se ve es lo que se verá” (WYSIWYG) en el editor de páginas, y una ventana de vista previa independiente.

Mientras usa el editor de páginas, una vista previa de “Lo que se ve es lo que se verá" (WYSIWYG) aparece en el panel central. Esta vista previa se actualiza automáticamente siempre que guarde la página. También puede actualizarla manualmente seleccionando **Actualizar** en la barra de comandos. La vista previa representa la página justo como la verán los usuarios, pero los ayudantes de la configuración se representan encima.

Cuando haya terminado de modificar la página, es posible que desee obtener una vista previa de ella para ver lo que verán los clientes. Para obtener una vista previa de una página, seleccione **Vista previa** en la barra de comandos. La vista previa aparecerá en una ventana de explorador independiente. La página de la ventana de vista previa se representa justo como la verá el usuario del sitio. Puede cambiar el tamaño de la ventana para asegurarse de que los módulos dinámicos se representan correctamente en todos los puertos de vista.

> [!NOTE]
> Se requiere autenticación y permisos adecuados para obtener una vista previa de contenido no publicado. Por tanto, si comparte la dirección URL de la vista previa con alguien, esa persona debe tener los permisos adecuados para obtener acceso al contenido.

## <a name="publish-a-page"></a>Publicar una página

Cuando la página está lista, el paso siguiente es publicarla, de modo que los usuarios externos puedan ver el contenido. Antes de poder publicar una página, debe protegerla seleccionando **Finalizar edición** en la barra de comandos.

Puede publicar y despublicar páginas desde el inspector de página o el editor de páginas. El inspector de página muestra una lista de páginas y permite operaciones masivas. El editor de páginas se puede usar para publicar o cancelar la publicación solo de la única página que se abre en él.

Para publicar una o varias páginas del inspector de página, seleccione las páginas, asegúrese de que se han protegido y, a continuación, seleccione **Publicar** en la barra de comandos. Las páginas se publican y recibe una notificación acerca de la operación en la herramienta de creación.

Para publicar una sola página del editor de página, el procedimiento es similar. Mientras que la página se encuentra abierta en el editor de páginas, asegúrese de que se ha protegido y, a continuación seleccione **Publicar** en la barra de comandos. La página se publica y recibe una notificación acerca de la operación.

Al publicar una página, solo se publica su contenido. Otros usuarios y usted pueden ir a la página y verla únicamente una vez una dirección URL se ha asociado a ella. La dirección URL debe publicarse por separado.

> [!IMPORTANT]
> Para poder publicar una página, las imágenes o los fragmentos a los que hace referencia la página deben estar ya publicados.

## <a name="save-preview-and-publish-a-home-page"></a>Guardar, obtener una vista previa y publicar una página principal

Para guardar, obtener una vista previa y publicar una página principal, siga estos pasos.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación de la izquierda, seleccione **Páginas**.
1. Busque y seleccione la página principal para abrirla en el editor de páginas.
1. Seleccione **Editar**.
1. Modifique la página según sea necesario.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. En el campo **Comentarios**, especifique una nota acerca de los cambios que ha realizado y, a continuación, seleccione **Aceptar**.
1. Seleccione **Vista previa** para obtener una vista previa de la página. Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.
1. Seleccione **Publicar**.

## <a name="publish-a-url"></a>Publicar una dirección URL

Para publicar una dirección URL, siga estos pasos.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación de la izquierda, seleccione **Direcciones URL**.
1. Busque y seleccione la dirección que desea publicar.
1. En la barra de comandos, seleccione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Modificar una página de sitio existente](modify-existing-page.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Enriquecer una página de aterrizaje de categoría](enrich-category-page.md)

[Verificar accesibilidad de contenido de página](verify-accessibility.md)

[Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]