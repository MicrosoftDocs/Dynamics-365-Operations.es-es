---
title: Optar por usar clasificaciones y revisiones de usuario
description: Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6c54a8fa01badb6a383c41dc979e71d82a25ef97
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251244"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a>Optar por usar clasificaciones y revisiones de usuario

[!include [banner](includes/banner.md)]

Este tema explica cómo optar por usar clasificaciones y revisiones en su sitio de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La solución de clasificaciones y revisiones es una solución omnicanal que puede hacer que esté disponible en Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS). LCS es un portal de administración que los minoristas usan para administrar sus entornos del aprovisionamiento a la retirada.

Si desea utilizar la solución de clasificaciones y revisiones en su sitio web de Commerce, debe optar por las clasificaciones y revisiones durante la implementación de su sitio de comercio electrónico en Dynamics 365 Commerce.

## <a name="opt-in-to-use-ratings-and-reviews"></a>Optar por usar clasificaciones y revisiones de usuario

Para optar por usar las clasificaciones y revisiones en su sitio, siga estos pasos.

1. Siga los pasos de [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md).
1. Mientras se encuentre todavía en LCS, vaya a **Configuración de implementación de Retail \> Otra configuración**.
1. Establezca la opción **Habilitar el servicio de clasificaciones y revisiones** en **Sí**.
1. En el campo **Grupo de seguridad de AAD para moderador de clasificaciones y revisiones (id. de objeto del grupo de seguridad)**, especifique el id. del grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que incluye los moderadores de clasificaciones y revisiones.

    ![Optar por usar clasificaciones y revisiones de usuario](media/LCS_RnR_Preference.png)

1. Complete el proceso de inicialización de comercio electrónico.

> [!NOTE] 
> Si eres un cliente de Dynamics 365 Commerce existente que ya ha implementado un sitio de comercio electrónico sin haber optado por participar en clasificaciones y revisiones, y ahora desea usar las clasificaciones y revisiones del paquete de Dynamics 365 Commerce, envíe una solicitud de servicio. Para obtener información acerca de cómo enviar una solicitud de servicio, consulte [Enviar proceso de solicitudes de servicio](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json). 

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de clasificaciones y revisiones](ratings-reviews-overview.md)

[Administrar clasificaciones y revisiones](manage-reviews.md)

[Configurar clasificaciones y revisiones](configure-ratings-reviews.md)

[Sincronizar clasificaciones de productos en Dynamics 365 Commerce](sync-product-ratings.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]