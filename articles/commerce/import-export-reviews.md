---
title: Importación y exportación de calificaciones y opiniones
description: Este tema describe cómo importar y exportar calificaciones y opiniones de productos en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 3ae85f21f7a78d56621aed60527207badcee9c75
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968526"
---
# <a name="import-and-export-ratings-and-reviews"></a>Importación y exportación de calificaciones y opiniones

[!include [banner](includes/banner.md)]

Este tema describe cómo importar y exportar calificaciones y opiniones de productos en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ofrece [calificaciones y opiniones](ratings-reviews-overview.md) como una solución omnicanal. Cuando cambia a la solución de calificaciones y opiniones de Dynamics 365 Commerce, es posible que desee mover sus calificaciones y opiniones existentes a la plataforma de Commerce. También es posible que desee exportar calificaciones y opiniones de datos de Commerce, según los requisitos de su empresa. Un conector de Power Automate le permite importar y exportar calificaciones y opiniones en Commerce.

> [!NOTE]
> Para obtener información sobre cómo comenzar con los flujos lógicos en Power Automate, consulte [Crer un flujo de nube en Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Requisitos previos

Antes de poder importar y exportar calificaciones y opiniones, debe cumplir con los siguientes requisitos previos:

- La solución de calificaciones y opiniones debe estar habilitada para su sitio de comercio electrónico en la plataforma Commerce. Para más información, consulte [Optar por usar calificaciones y opiniones](opt-in-ratings-reviews.md).
- El conector de Power Apps de calificaciones y opiniones de Dynamics 365 debe configurarse para habilitar las acciones "enviar opiniones" o "exportar opiniones" en Power Automate. Para obtener más información, consulte [Dynamics 365 Commerce: calificaciones y opiniones (versión preliminar)](/connectors/dynamics365ratingsre/).
- La autenticación de servicio a servicio (S2S) debe configurarse para llamar de manera segura a la interfaz de programación de aplicaciones (API) de calificaciones y opiniones desde fuera de Commerce. Para obtener más información, consulte [Configurar autenticación servicio a servicio](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Importar calificaciones y opiniones

Para importar datos de calificaciones y opiniones de su sistema existente a Commerce, debe agregar el conector Power Automate de calificaciones y opiniones de Dynamics 365 a un flujo existente o uno nuevo de Power Automate. Para obtener más información, consulte [Dynamics 365 Commerce: calificaciones y opiniones (versión preliminar)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Para completar este procedimiento, debe [configurar la autenticación de S2S](service-to-service-auth.md).

Para importar calificaciones y opiniones en Commerce mediante el conector de Power Automate de calificaciones y opiniones de Dynamics 365, siga estos pasos.

1. Seleccione la acción **Enviar opinión de usuario**.
1. Establezca una conexión utilizando la información de la aplicación Azure Active Directory (Azure AD) que se creó cuando configuró la autenticación S2S. Para obtener más información, consulte [Configurar autenticación servicio a servicio](service-to-service-auth.md).
1. La acción **Enviar opinión de usuario** funciona con una sola opinión a la vez. Por lo tanto, repita la acción. Use las opiniones de origen como una lista para enviar opiniones masivas.
    
## <a name="export-ratings-and-reviews"></a>Exportar calificaciones y opiniones

Para exportar datos de calificaciones y opiniones desde Commerce, debe agregar el conector Power Automate de calificaciones y opiniones de Dynamics 365 a un flujo existente o uno nuevo de Power Automate. Para obtener más información, consulte [Dynamics 365 Commerce: calificaciones y opiniones (versión preliminar)](/connectors/dynamics365ratingsre/).

Para exportar calificaciones y opiniones desde Commerce mediante el conector de Power Automate de calificaciones y opiniones de Dynamics 365, siga estos pasos.

1. Seleccione la acción **Exportar todas las opiniones**.
1. Complete la acción. 

## <a name="additional-resources"></a>Recursos adicionales

[Información general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Optar por usar clasificaciones y revisiones de usuario](opt-in-ratings-reviews.md)

[Administrar calificaciones y opiniones](manage-reviews.md)

[Configurar calificaciones y opiniones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de producto](sync-product-ratings.md)

[Habilitar la publicación manual de calificaciones y reseñas por parte de un moderador](manual-publish-rating-reviews.md)

[Configurar autenticación de servicio a servicio](service-to-service-auth.md)

[P+F de clasificaciones y revisiones](ratings-reviews-faq.md)
