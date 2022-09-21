---
title: Módulo Chat de Commerce con omnicanal para Customer Service
description: Este artículo describe el módulo Chat de Commerce con omnicanal para Customer Service en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: b8eaed3eb015e96b1db6fa2297c341ea9d3ff8ad
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473819"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Módulo Chat de Commerce con omnicanal para Customer Service

[!include [banner](includes/banner.md)]

Este artículo describe el módulo *Chat de Commerce con omnicanal para Customer Service* en Microsoft Dynamics 365 Commerce.

En el lanzamiento de la versión 10.0.29 de Commerce, se agregó un nuevo módulo Chat de Commerce con omnicanal para Customer Service a la biblioteca del módulo Commerce. La función de chat de Commerce brinda a los clientes de comercio electrónico las capacidades de chat de la Plataforma omnicanal para Dynamics 365 Customer Service, que incluye soporte de agente en vivo para ayudar a abordar las consultas de los clientes, brindar servicio al cliente y facilitar las ventas para los clientes de Commerce.

La función de chat de Commerce permite a los minoristas lograr estos objetivos:

- Aumente el compromiso personalizado con los clientes para ayudar a mejorar la retención de clientes.
- Mejore el servicio al cliente a través de la integración de agentes humanos y chatbots de autoservicio.
- Ayude a los agentes a ganar experiencia a través del perfil del cliente, los pedidos y los datos de compra en tiempo real que impulsan las mejoras operativas y el compromiso.
- Mejorar la satisfacción general del cliente para ayudar a aumentar las ventas.

Las siguientes capacidades están disponibles como parte de la función de chat de Commerce:

- Chat de Commerce con omnicanal para Customer Service
- La suma del **Centro de llamadas de Commerce** como una pestaña de aplicación en la experiencia del agente en la Plataforma omnicanal para Dynamics 365 Customer Service

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Requisitos previos de Omnicanal para Customer Service

Como requisito previo, debe configurar el chat en el widget de la Administración de la plataforma omnicanal para Customer Service y obtener algunos de los parámetros para configurar la experiencia de chat de Commerce. Para obtener instrucciones, consulte [Configurar un canal de chat](/dynamics365/customer-service/set-up-chat-widget).

Después de configurar el chat en el widget de la Administración de la plataforma omnicanal para Customer Service, obtendrá una secuencia de comandos similar al siguiente ejemplo.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

Copie este script, porque necesitará los valores que contiene para configurar el módulo de chat.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Campos obligatorios del Chat de Commerce con omnicanal para Customer Service

La siguiente tabla muestra los valores de secuencia de comandos del widget Administración de la plataforma omnicanal para Customer Service que se requieren para configurar el módulo Chat de Commerce con omnicanal para Customer Service.

| Propiedad del widget | Description |
| ------------- |--------------|
| Origen de la secuencia de comandos | El valor de **scr** en el script del widget de chat. |
| Id. de aplicación de datos | El valor de **data-app-id** en el script del widget de chat. |
| Id. de organización de datos | El valor de **data-org-id** en el script del widget de chat. |
| URL de organización de datos | El valor de **data-org-url** en el script del widget de chat. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>Configure la experiencia de chat de Commerce para su sitio de comercio electrónico

Una forma recomendada de implementar la experiencia de chat para su sitio de comercio electrónico es agregar el módulo Chat de Commerce con omnicanal para Customer Service al fragmento de encabezado compartido que se usa en las páginas de su sitio de comercio electrónico.

Para agregar el módulo de chat al fragmento del encabezado del sitio en el generador de sitios de Commerce, siga estos pasos.

1. En el generador de sitios para su sitio, vaya a **Fragmentos**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Seleccione un fragmento**, seleccione el módulo **Chat de Commerce con omnicanal para Customer Service**, ingrese un nombre para el fragmento y luego seleccione **OK**.
1. En la vista de esquema, seleccione la ranura **Conector de chat Msdyn365 cs**.
1. En la página **Propiedades de chat** de la derehca, siga estos pasos:

    1. En el campo **Origen de script**, ingrese el valor **src** que obtuvo del script de Omnicanal para Customer Service.
    1. En el campo **Id. de aplicación de datos**, ingrese el valor **data-app-id** que obtuvo del script de Omnicanal para Customer Service.
    1. En el campo **Id. de organización de datos**, ingrese el valor **data-org-id** que obtuvo del script de Omnicanal para Customer Service.
    1. En el campo **URL de organización de datos**, ingrese el valor **data-org-url** que obtuvo del script de Omnicanal para Customer Service.

    ![Creación de un fragmento de módulo Chat de Commerce en el creador de sitios de Commerce.](media/Commerce-chat-creating-new-fragment.png)

1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.
1. Ir **Fragmentos** y abra el fragmento de encabezado de su sitio.
1. En la franja del módulo **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el fragmento de chat creado anteriormente y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>Agregue la Commerce headquarters como una pestaña de aplicación para Omnicanal para Customer Service

Puede agregar una pestaña de aplicación para la Commerce headquarters en Omnicanal para Customer Service. Los agentes en vivo pueden usar la interfaz de usuario para la experiencia del agente Omnichannel for Customer Service para acceder fácilmente al módulo Dynamics 365 Commerce Customer Service que contiene información contextual del cliente junto con la información de sus órdenes de venta. Además, los agentes de atención al cliente pueden realizar nuevos pedidos, iniciar devoluciones y verificar la información del estado de los pedidos.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Cree una nueva pestaña de aplicación que cargue la Commerce headquarters en un módulo iFrame 

Para crear una nueva pestaña de aplicación que cargue la Commerce headquarters en un módulo iFrame, siga estos pasos.

1. Abra [Power Apps Maker Portal](https://make.powerapps.com).
1. En el panel de navegación de la izquierda, seleccione **Aplicaciones**.
1. Seleccione **Centro de administración de Customer Service**.
1. Vaya a **Experiencia del agente**.
1. Para **Plantillas de pestañas de aplicaciones**, seleccione **Administrar**.
1. Crear una nueva pestaña de aplicación de tipo **Sitio web de terceros**. Para instrucciones, vea [Administrar plantillas de pestañas de aplicación](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. Bajo **Parámetros**, en el campo **Valor** del parámetro **URL**, ingrese la siguiente URL, donde `<YourOrganizationHeadquartersURL>` y `<LegalEntityname>` se reemplazan con los valores apropiados. Omnicanal Customer Service lee **{AccountNumber}** en el contexto del chat. Por lo tanto, deje **{AccountNumber}** como está.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Deje el valor del campo **Valor** del parámetro **datos** en blanco.

![Cree una pestaña de aplicación en Dynamics 365 Omnichannel Customer Service.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Habilite una nueva pestaña de aplicación para agentes de clientes en Dynamics 365 Omnichannel for Customer Service

Para habilitar una nueva pestaña de aplicación para agentes de clientes en Dynamics 365 Omnichannel for Customer Service, siga estos pasos.
    
1. Abra [Power Apps Maker Portal](https://make.powerapps.com).
1. En el panel de navegación de la izquierda, seleccione **Aplicaciones**.
1. Seleccione **Centro de administración de Customer Service**.
1. Ir **Atención al cliente \> Flujos de trabajo**.
1. Abra el flujo de trabajo que ha creado para sus agentes y luego, en **Ajustes avanzados**, seleccione **Sesiones predeterminadas**.
1. Bajo **Pestañas de la aplicación**, seleccione **Agregar pestaña de aplicación existente** y luego agregue la nueva pestaña de la aplicación que creó anteriormente. Este paso garantiza que aparecerá una pestaña de aplicación que cargue la Commerce headquarters en un módulo iFrame cuando un agente reciba una llamada de chat entrante desde su sitio web de comercio electrónico.

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Agregar variables de contexto en Dynamics 365 Omnichannel for Customer Service

Para agregar variables de contexto en Dynamics 365 Omnichannel for Customer Service, siga estos pasos.

1. Abra [Power Apps Maker Portal](https://make.powerapps.com).
1. En el panel de navegación de la izquierda, seleccione **Aplicaciones**.
1. Seleccione **Centro de administración de Customer Service**.
1. Ir **Atención al cliente \> Flujos de trabajo**.
1. Abra el flujo de trabajo que ha creado para sus agentes y luego, en **Ajustes avanzados**, vaya a la sección **Variable de contexto**.
1. Seleccione **Editar** y luego agregue **AccountNumber** como una variable de contexto del tipo **texto**. Esta variable ayudará a la Commerce headquarters a cargar información de clientes con números de cuenta coincidentes.

> [!NOTE]
> Si desea leer las direcciones de correo electrónico y los nombres de los usuarios que iniciaron sesión desde un canal de comercio electrónico, puede agregar **Correo electrónico** y **Nombre** como variables de contexto de tipo **texto**, además de la variable de contexto **AccountNumber** .
