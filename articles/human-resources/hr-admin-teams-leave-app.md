---
title: Aplicación Recursos humanos en Teams
description: Este tema presenta la aplicación Microsoft Dynamics 365 Human Resources en Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e714be06984f399235f0799ef077a92deae64d9e
ms.sourcegitcommit: b0aa724a18ab1fbb5a62925f048c54b2c676ebf4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "4476086"
---
# <a name="human-resources-app-in-teams"></a>Aplicación Recursos humanos en Teams

[!include [banner](includes/preview-feature.md)]

La aplicación Microsoft Dynamics 365 Human Resources de Microsoft Teams permite a los empleados solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre en Microsoft Teams. Los empleados pueden interactuar con un bot para solicitar información. La pestaña **Tiempo libre** proporciona información más detallada. Además, pueden enviar información a los usuarios sobre el próximo tiempo libre a través de equipos y chats que haya fuera de la aplicación de Human Resources.

![Bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-admin-teams-leave-app-bot.png)

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Tarjeta de solicitud de baja de recursos humanos](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Instalar y configurar

Puede encontrar la aplicación Recursos Humanos en la tienda Teams. Para obtener información sobre cómo instalar la aplicación Teams, consulte [Administrar solicitudes de licencia en Teams](hr-teams-leave-app.md).

Para obtener información sobre la administración de permisos de aplicaciones en Teams, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Habilitar notificaciones para la aplicación Human Resources en Teams

Si desea que los usuarios reciban notificaciones de solicitud de permiso en la aplicación Teams, debe habilitar las notificaciones en Human Resources.

>[!NOTE]
>Solo los usuarios que hayan iniciado sesión en Teams y que utilicen la aplicación Human Resources Teams recibirán notificaciones.

1. En Human Resources, seleccione **Administración del sistema**.

2. Seleccione **Vínculos**.

3. En **Configuración**, seleccione **Parámetros del sistema**.

4. En la pestaña **General**, establezca **Habilitar notificaciones para la aplicación Teams** en **Sí**.

   ![Habilitar las notificaciones de la aplicación Teams en los parámetros del sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Para activar las notificaciones de Teams para todos los usuarios, seleccione **Sí** en el aviso.

   ![Habilitar notificaciones de Teams para todos los usuarios](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Activar o desactivar las notificaciones de Teams para usuarios individuales

Una vez que haya habilitado las notificaciones para la aplicación en la aplicación Human Resources Teams, puede activar o desactivar las notificaciones para usuarios individuales.

1. En Human Resources, seleccione **Administración del sistema**.

2. Seleccione **Vínculos**.

3. En **Usuarios**, seleccione **Opciones de usuario**.

4. Seleccione la pestaña **Flujo de trabajo**.

5. Establezca **Habilitar notificaciones para la aplicación Teams** en **Sí** para habilitar notificaciones para el usuario o **No** para deshabilitar las notificaciones para el usuario.

   ![Habilitar las notificaciones de la aplicación Teams en la pestaña Flujo de trabajo de opciones de usuario](./media/hr-admin-teams-leave-app-notifications.png)

6. Seleccione **Guardar**.

## <a name="known-issues"></a>Problemas conocidos

| Emitir | Estado |
| --- | --- |
| El saldo es incorrecto si se envía tiempo libre para una fecha futura. | La previsión no está disponible aún. El saldo se muestra para la fecha actual. |
| No se puede cancelar una solicitud **En revisión**. | Esta funcionalidad no es compatible actualmente y se agregará en una versión futura. |
| La información del saldo se calcula a partir de hoy. | El sistema actualmente no muestra saldos a partir del período de acumulación, incluso si está configurado en los parámetros de Baja y Ausencia. |

## <a name="troubleshooting"></a>Solución de problemas

Si un usuario tiene problemas para iniciar sesión o utilizar la aplicación Equipos de recursos humanos, intente seguir estas instrucciones de solución de problemas. Si sigue teniendo problemas después de la resolución de problemas, comuníquese con Soporte. Para obtener más información, consulte [Obtener soporte](hr-admin-troubleshooting-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>No puedo iniciar sesión en la aplicación de recursos humanos en Teams

Si un usuario se comunica con usted porque no puede iniciar sesión en la aplicación, verifique que el usuario tenga un registro de empleado asociado en Human Resources.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Error al aprobar solicitudes de licencia en la aplicación Human Resources en Teams

Si un usuario recibe un error mientras intenta aprobar solicitudes de permiso en la aplicación Teams, realice los siguientes pasos de solución de problemas:

1. Verifique que su cuenta de Teams sea la misma que usan para acceder a Human Resources.

2. Verifique que son un aprobador válido para la solicitud al verificar la configuración del flujo de trabajo para la aprobación de la licencia. Para obtener más información sobre los flujos de trabajo de solicitud de licencia, consulte [Crear un flujo de trabajo de solicitud de licencia](hr-leave-and-absence-workflow.md).

## <a name="privacy-notice"></a>Aviso de privacidad

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Servicio inteligente de comprensión del lenguaje de Microsoft (LUIS)

Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente. La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS). Obtenga más información sobre LUIS [aquí](https://www.luis.ai/). El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso). Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario. 

Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada. El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources. Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure. 

El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio. Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid y Azure Cosmos DB

Al utilizar la característica de notificaciones para la aplicación Dynamics 365 Human Resources en Microsoft Teams, algunos datos de clientes saldrán de la región geográfica donde se implementa el servicio de Recursos Humanos del inquilino.

Dynamics 365 Human Resources transmite la solicitud de licencia del empleado y los detalles de la tarea del flujo de trabajo a Microsoft Azure Event Grid y Microsoft Teams. Estos datos pueden almacenarse en Microsoft Azure Event Grid hasta por 24 horas y se procesarán en los Estados Unidos, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicios. Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).

Mientras conversa con el bot de chat en la aplicación de Recursos Humanos, el contenido de la conversación puede almacenarse en Azure Cosmos DB y transmitirse a Microsoft Teams. Estos datos pueden almacenarse en Azure Cosmos DB durante un máximo de 24 horas y pueden procesarse fuera de la región geográfica donde se implementa el servicio de Recursos Humanos de su inquilino, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicio. Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).
 
Para restringir el acceso a la aplicación de Recursos Humanos en Microsoft Teams para su organización o para usuarios de su organización, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Consulte también 

[Descargar e instalar Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centro de ayuda de Microsoft Teams](https://support.office.com/teams)</br>
[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]