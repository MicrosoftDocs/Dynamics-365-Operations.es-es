---
title: Enriquecer una página de aterrizaje de categoría
description: Este tema aborda el enriquecimiento de páginas de categoría en Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5bb28c3b5fbb1133d32219b9c47dd1477ae2ac982ee035321dafd77c53dc910b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771016"
---
# <a name="enrich-a-category-landing-page"></a>Enriquecer una página de aterrizaje de categoría

[!include [banner](includes/banner.md)]

Este tema aborda el enriquecimiento de páginas de categoría en Dynamics 365 Commerce.

Commerce proporciona una página de aterrizaje de categoría predeterminada que se utiliza cuando se muestra los datos de categoría. Una página de categoría predeterminada contiene elementos necesarios, como refinadores, ubicación de producto categorizada, opciones de ordenación, resumen de opciones y controles de paginación. 

Sin embargo, en lugar de usar la página de categoría predeterminada, es posible que desee usar una página de aterrizaje de categoría “enriquecida” que tenga más contenido y más elementos específicos. Un enriquecimiento típico puede implicar la adición de contenido de marketing específico de categoría a la página de categoría. Este contenido podría incluir la ubicación de productos entre categorías para fines de venta cruzada, listas editoriales, imágenes, vídeos y otro texto. Puede modificar la página de categoría predeterminada o definir una página de categoría diferente para una categoría específica.

![Página de aterrizaje de categoría enriquecida.](./media/CategoryLandingPages.png)

En el generador de sitios de Commerce, la página **Productos** incluye una lista de categorías del canal que se asignan al sitio. Si el estado **Enriquecido** está seleccionado para una página de categoría, se ha enriquecido esa página de categoría. De lo contrario, la página de categoría predeterminada y el contenido se utilizan para la categoría. Puede obtener una vista preliminar de las páginas de categoría enriquecidas y no enriquecidas para una categoría seleccionando el nombre de la categoría.

Para enriquecer una página de categoría, haga lo siguiente.

1. En la página **Productos**, seleccione el nombre de la categoría para la que desea enriquecer la página de categoría. La página de categoría predeterminada para la categoría seleccionada se abre en el editor de páginas.
2. Seleccione **Enriquecer una página de categoría**.
3. Seleccione una plantilla para la página de categoría enriquecida. Si está realizando solo cambios de menor importancia, puede seleccionar la página de categoría predeterminada. También, puede seleccionar una plantilla específica de página de categoría. Al seleccionar la plantilla, se abre el editor de páginas y la plantilla seleccionada se utiliza para crear una nueva página de categoría para la categoría seleccionada. La página se desprotege para usted y podrá realizar los cambios.

> [!NOTE]
> Los módulos que usan datos de especificación de categoría usan los datos de su categoría seleccionada. La configuración de la plantilla que seleccione determina los cambios que puede realizar.

## <a name="additional-resources"></a>Recursos adicionales

[Modificar una página de sitio existente](modify-existing-page.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)

[Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Verificar accesibilidad de contenido de página](verify-accessibility.md)

[Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
