---
title: Cancelar la recopilación de eventos de actividades web
description: Este artículo explica cómo puede permitir que los visitantes de su sitio web opten por no participar en la recopilación de eventos de actividad web en Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: 81343f5033366484140f73fcc313ecd9f35e7d47
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286735"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Cancelar la recopilación de eventos de actividades web
[!include [banner](includes/banner.md)]

Este artículo explica cómo puede permitir que los clientes opten por no participar en la recopilación de eventos de actividad web en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce permite a los administradores de sitios analizar la actividad web de los usuarios de sus sitios de comercio electrónico. De esa manera, pueden conocer mejor cómo se usan sus sitios y pueden optimizar los sitios para proporcionar una experiencia de usuario mejorada y cumplir con los objetivos comerciales.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Maneras para que los administradores implementen una experiencia de no participación

Los administradores tienen tres maneras de implementar una experiencia de no participación.

### <a name="opt-out-on-behalf-of-users"></a>Optar por no participar en nombre de los usuarios

En la gestión de cuentas de la Central de Commerce (HQ), los administradores pueden optar por no participar en nombre de los usuarios.

1. En el cliente HQ, en la página **Todos los clientes**, busque y seleccione un cliente.
1. En la página de detalles del cliente, en la ficha desplegable **Minorista**, en la sección **Privacidad**, establezca la opción **No seguir la actividad web** en **Sí**.

    ![Configuración de privacidad.](media/Disablepersonalizationpart2.png)

1. Haga clic en **Guardar** y, a continuación, cierre la página.

### <a name="module-based-opt-out-experience"></a>Experiencia de exclusión voluntaria basada en módulos

Los administradores pueden permitir que los usuarios autenticados opten ellos mismos por no participar en la recopilación de eventos de actividad web. Para proporcionar esta experiencia de exclusión, agregue el módulo de exclusión del usuario a las páginas de perfil de la cuenta del cliente.

### <a name="custom-extensions"></a>Extensiones personalizadas

Los administradores pueden crear sus propias extensiones para administrar la experiencia de exclusión voluntaria para los usuarios. Para más información, consulte [Llamar a las API de Retail Server](e-commerce-extensibility/call-retail-server-apis.md) y [Extensibilidad de canal en línea](e-commerce-extensibility/overview.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
