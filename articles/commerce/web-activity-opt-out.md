---
title: Optar por no participar en la recopilación de eventos de actividad web
description: Este tema explica cómo puede permitir que los visitantes de su sitio web opten por no participar en la recopilación de eventos de actividad web en Microsoft Dynamics 365 Commerce.
author: aamiral
manager: AnnBe
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4b0e48307527a8fea729d8dfdcdbc6337be0faf1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415554"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Optar por no participar en la recopilación de eventos de actividad web
[!include [banner](includes/banner.md)]

Este tema explica cómo puede permitir que los clientes opten por no participar en la recopilación de eventos de actividad web en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Dynamics 365 Commerce permite a los administradores de sitios analizar la actividad web de los usuarios de sus sitios de comercio electrónico. De esa manera, pueden conocer mejor cómo se usan sus sitios y pueden optimizar los sitios para proporcionar una experiencia de usuario mejorada y cumplir con los objetivos comerciales.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Maneras para que los administradores implementen una experiencia de no participación

Los administradores tienen tres maneras de implementar una experiencia de no participación.

### <a name="opt-out-on-behalf-of-users"></a>Optar por no participar en nombre de los usuarios

En la gestión de cuentas de la Central de Commerce (HQ), los administradores pueden optar por no participar en nombre de los usuarios.

1. En el cliente HQ, en la página **Todos los clientes**, busque y seleccione un cliente.
1. En la página de detalles del cliente, en la ficha desplegable **Minorista**, en la sección **Privacidad**, establezca la opción **No seguir la actividad web** en **Sí**.

    ![Configuración de privacidad](media/Disablepersonalizationpart2.png)

1. Haga clic en **Guardar** y, a continuación, cierre la página.

### <a name="module-based-opt-out-experience"></a>Experiencia de exclusión voluntaria basada en módulos

Los administradores pueden permitir que los usuarios autenticados opten ellos mismos por no participar en la recopilación de eventos de actividad web. Para proporcionar esta experiencia de exclusión, agregue el módulo de exclusión del usuario a las páginas de perfil de la cuenta del cliente.

### <a name="custom-extensions"></a>Extensiones personalizadas

Los administradores pueden crear sus propias extensiones para administrar la experiencia de exclusión voluntaria para los usuarios. Para más información, consulte [Llamar a las API de Retail Server](e-commerce-extensibility/call-retail-server-apis.md) y [Extensibilidad de canal en línea](e-commerce-extensibility/overview.md).
