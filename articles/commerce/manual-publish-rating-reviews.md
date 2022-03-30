---
title: Habilitar la publicación manual de calificaciones y reseñas por parte de un moderador
description: Este tema describe cómo habilitar la publicación manual de calificaciones y reseñas por parte de un moderador en Microsoft Dynamics 365 Commerce y cómo publicar calificaciones y reseñas manualmente.
author: gvrmohanreddy
manager: annbe
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2b4ba835ff4540b63f6fe49cc847286f8c2a3bcf
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407828"
---
# <a name="enable-manual-publishing-of-ratings-and-reviews-by-a-moderator"></a>Habilitar la publicación manual de calificaciones y reseñas por parte de un moderador

[!include [banner](includes/banner.md)]

Este tema describe cómo habilitar la publicación manual de calificaciones y reseñas por parte de un moderador en Microsoft Dynamics 365 Commerce y cómo publicar calificaciones y reseñas manualmente.

La solución de calificaciones y reseñas de Dynamics 365 Commerce utiliza Azure Cognitive Services para redactar automáticamente las malas palabras en los títulos y el contenido de las reseñas, y para publicar calificaciones y reseñas. Por lo tanto, no se requiere la intervención manual para revisar y publicar calificaciones y reseñas en su sitio de comercio electrónico.

Sin embargo, algunas empresas pueden preferir que los moderadores revisen y aprueben manualmente las reseñas antes de que se publiquen. Para habilitar la publicación manual de calificaciones y reseñas por parte de un moderador, debe habilitar la fucnión **Requerir moderador para calificaciones y reseñas** en el creador de sitios de comercio.

## <a name="enable-the-require-moderator-for-ratings-and-reviews-feature-in-commerce-site-builder"></a>Habilite la función Requerir moderador para calificaciones y reseñas en el creador de sitios de Comercio

Para habilitar la función **Requerir moderador para calificaciones y reseñas** en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a **Inicio \> Revisiones \> Configuración**.
1. Establezca la opción **Requerir moderador para calificaciones y reseñas** en **Activado**.

> [!NOTE]
> Al habilitar la función **Requerir moderador para calificaciones y reseñas**, detiene la publicación automática de calificaciones y reseñas, por lo que ahora se requiere la publicación manual. Sin embargo, Azure Cognitive Services continuará censurando las blasfemias en los títulos y el contenido de las reseñas.

<!--![Require moderator for ratings and reviews setting in Commerce site builder.](media/Ratings-reviews-settings-human-moderation.png)-->

## <a name="publish-ratings-and-reviews"></a>Publicar clasificaciones y opiniones

Al habilitar la función **Requerir moderador para calificaciones y reseñas**, un moderador revisar y publicar manualmente las calificaciones y reserñas para que aparezcan en el sitio de comercio electrónico.

Para revisar y publicar las clasificaciones y revisiones en el creador de sitios de Commerce, siga estos pasos.

1. Vaya a **Revisiones \> Moderación**.
1. En la cuadrícula, si el campo **Estado** de una fila se establece en **Inédito**, la calificación y la reseña de esa fila aún no se han publicado. Para ver solo calificaciones y reseñas no publicadas, seleccione **Estado: necesita revisión** en el filtro de estado sobre la cuadrícula.
1. Seleccione una o más calificaciones y reseñas que tengan un estado de **Inédito** y luego seleccione **Publicar** en la barra de comandos. Las calificaciones y reseñas seleccionadas se agregan a la cola de publicación y aparecerán en el sitio de comercio electrónico después de su publicación.

> [!NOTE]
> - Después de que se publican una calificación y una revisión, el valor de estado cambia de **Inédito** a un valor nulo (campo en blanco).
> - Si selecciona varias calificaciones y reseñas que tienen estados mixtos y luego selecciona **Publicar**, se publicarán calificaciones y reseñas que aún no se hayan publicado. Sin embargo, las calificaciones y reseñas que ya se hayan publicado no se volverán a publicar.

La siguiente ilustración muestra un ejemplo en el que se seleccionan tres calificaciones y reseñas no publicadas en la página **Moderación** en el creador de sitios de Commerce.

![Tres calificaciones y reseñas no publicadas seleccionadas en la página Moderación en el creador de sitios de Commerce.](media/Ratings-reviews-publishing-reviews.png)

<!--![Dynamics 365 Commerce - Ratings and Review configuration 2](media/Ratings-reviews-published-reviews.png)-->
<!--![Status filter](media/Ratings-reviews-published-reviews-status-filter.png)-->

## <a name="additional-resources"></a>Recursos adicionales

[Información general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar clasificaciones y revisiones](manage-reviews.md)

[Configurar clasificaciones y revisiones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de producto](sync-product-ratings.md)

[Importación y exportación de calificaciones y opiniones](import-export-reviews.md)

[Configurar autenticación de servicio a servicio](service-to-service-auth.md)

[P+F de clasificaciones y revisiones](ratings-reviews-faq.md)
