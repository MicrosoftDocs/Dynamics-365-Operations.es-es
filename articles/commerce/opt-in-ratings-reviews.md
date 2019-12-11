---
title: Optar por usar clasificaciones y revisiones de usuario
description: Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697989"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Optar por usar clasificaciones y revisiones de usuario

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

La solución de clasificaciones y revisiones es una solución omnicanal que puede hacer que esté disponible en Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS). LCS es un portal de administración que los minoristas usan para administrar sus entornos del aprovisionamiento a la retirada.

Si desea usar la solución de clasificaciones y revisiones en su sitio web de Commerce, primero debe optar por usarla.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Optar por usar clasificaciones y revisiones de usuario

Para optar por usar las clasificaciones y revisiones en su sitio, siga estos pasos.

1. Siga los pasos de [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md).
1. Mientras se encuentre todavía en LCS, vaya a **Configuración de implementación de Retail \> Otra configuración**.
1. Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.
1. En el campo **Grupo de seguridad de AAD para moderador de clasificaciones y revisiones (id. de objeto del grupo de seguridad)**, especifique el id. del grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que incluye los moderadores de clasificaciones y revisiones.

    ![Optar por usar clasificaciones y revisiones de usuario](media/LCS_RnR_Preference.png)

1. Complete el proceso de inicialización de comercio electrónico.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Administrar clasificaciones y revisiones](manage-reviews.md)

[Configurar clasificaciones y revisiones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de productos en Dynamics 365 Retail](sync-product-ratings.md)
