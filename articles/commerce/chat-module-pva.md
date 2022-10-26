---
title: Módulo Chat de Commerce con Power Virtual Agents
description: Este artículo describe el Chat de Commerce con Power Virtual Agents módulo que integra Microsoft Power Virtual Agents con sitios web de Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691079"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Módulo Chat de Commerce con Power Virtual Agents

[!include [banner](includes/banner.md)]

Este artículo describe el Chat de Commerce con Power Virtual Agents módulo que integra Microsoft Power Virtual Agents con sitios web de Dynamics 365 Commerce.

El chat de Commerce con Power Virtual Agents permite a los clientes de comercio electrónico de Dynamics 365 utilizar capacidades de bot de chat de Power Virtual Agents para manejar sus consultas. A partir de Dynamics 365 Commerce 10.0.30, esta función se puede incorporar en sitios web de comercio electrónico mediante el chat de comercio con el módulo Power Virtual Agents que forma parte de la biblioteca de módulos de Commerce.

El chat de Commerce con Power Virtual Agents ayuda a las empresas a lograr los siguientes objetivos:

- Aumentar el compromiso personalizado con sus consumidores y mejorar la retención.
- Mejorar el servicio al cliente a través de la integración de chatbots de autoservicio.
- Aumentar la satisfacción general del cliente y, por lo tanto, aumentar las ventas.

> [!NOTE]
> Para conocer las diferencias entre Plataforma omnicanal para Customer Service de Dynamics 365 y Power Virtual Agents, vea [Descripción general de los módulos de chat de Commerce](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a>Requisitos previos para usar Power Virtual Agents

Para usar el chat de Commerce con Power Virtual Agents, primero debe crear un bot de chat de Power Virtual Agents para su sitio web de comercio electrónico. Para obtener instrucciones, consulte [Crear un bot de agente virtual poderoso](/power-virtual-agents/authoring-first-bot).

Después de configurar el chatbot, debe copiar los valores de parámetros de chatbot **ID de bot** e **ID de inquilino** para configurar la experiencia de chat de Commerce. Para obtener información sobre cómo copiar estos valores, consulte [Recuperar los parámetros del bot de Power Virtual Agents](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters).

## <a name="configure-your-e-commerce-site"></a>Configurar el sitio de comercio electrónico 

Una forma recomendada de implementar la experiencia de chat para su sitio de comercio electrónico es agregar el módulo Chat de Commerce con Power Virtual Agents al fragmento de encabezado compartido que se usa en las páginas de su sitio de comercio electrónico.

Para agregar el módulo de chat al fragmento del encabezado del sitio en el generador de sitios de Commerce, siga estos pasos.

1. En el generador de sitios de Commerce para su sitio, vaya a **Fragmentos**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Seleccione un fragmento**, seleccione el módulo **Chat de Commerce con Power Virtual Agents**, ingrese un nombre para el fragmento y luego seleccione **Aceptar**.
1. En la vista de esquema, seleccione la ranura **Conector de chat de pva Msdyn365**.
1. En la página Propiedades de la derecha, siga estos pasos:

    1. Bajo **Parámetros de bots**, en el campo **URL de CDN de chat web de Bot Framework**, deje el valor predeterminado (por ejemplo, `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. En el campo **URL de autenticación de Direct Line de Bot Framework**, deje el valor predeterminado (por ejemplo, `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. En el campo **ID de bot**, ingrese el **ID de bot** de Power Virtual Agents que copió en la sección [Requisitos previos para usar Power Virtual Agents](#prereq).
    1. En el campo **ID de inquilino**, ingrese el valor de **ID de inquilino** que copió.

1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.
1. Ir **Fragmentos** y abra el fragmento de encabezado de su sitio.
1. En la franja del módulo **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el fragmento de chat creado anteriormente y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.

## <a name="proactive-chat-parameters"></a>Parámetros de chat proactivos

Para obtener una lista completa de los parámetros de configuración de chat proactivos, consulte [Parámetros de chat proactivos del módulo de chat de Commerce](chat-proactive-chat-parameters.md).

> [!NOTE]
> Actualmente, Power Virtual Agents no admite la autenticación de Azure Active Directory B2C (Azure AD B2C). Solo admite llamadas Retail Cloud Scale Unit (RCSU) anónimas para obtener la disponibilidad del producto o interactuar con otras API anónimas. Las llamadas a API autenticadas a través de los chatbots de Power Virtual Agents requieren un inicio de sesión explícito del cliente.

## <a name="additional-resources"></a>Recursos adicionales

[Información general de las características de chat de Commerce](commerce-chat-overview.md)

[Módulo Chat de Commerce con omnicanal para Customer Service](commerce-chat-module.md)

[Parámetros de chat proactivos del módulo Chat de Commerce](chat-proactive-chat-parameters.md)
