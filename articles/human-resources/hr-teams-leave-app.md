---
title: Administrar solicitudes de baja en Teams
description: Este tema muestra cómo solicitar tiempo libre en la aplicación Dynamics 365 Human Resources en Microsoft Teams.
author: andreabichsel
ms.date: 05/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aec6d784fd6bd54297ac4204c834c7f77ed75362
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356521"
---
# <a name="manage-leave-requests-in-teams"></a>Administrar solicitudes de bajas en Teams

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La aplicación Dynamics 365 Human Resources en Microsoft Teams le permite solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre directamente en Microsoft Teams. Puede interactuar con un bot para solicitar información e iniciar una solicitud de baja. La pestaña **Tiempo libre** proporciona información más detallada. También puede enviar información a los usuarios sobre el próximo tiempo libre en Teams y chats que haya fuera de la aplicación de Human Resources.

## <a name="install-the-app"></a>Instalar la aplicación

Puede encontrar la aplicación Dynamics 365 Human Resources en la tienda de Teams.

1. En Microsoft Teams, vaya hasta la lista de aplicaciones.
 
2. Busque Dynamics 365 Human Resources y luego seleccione el icono **Recursos humanos**.

3. Seleccione el botón **Agregar** para instalar la aplicación.

Si la aplicación no inicia sesión automáticamente, seleccione la pestaña **Configuración** para iniciar sesión.

> [!NOTE]
> Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes. 

Si tiene acceso a más de una instancia de Recursos humanos, puede seleccionar a qué entorno desea conectarse en la pestaña **Configuración**.

> [!NOTE]
> Ahora la aplicación admite el rol de seguridad Administrador del sistema.
 
## <a name="use-the-bot"></a>Usar el bot

Después de la instalación de la aplicación, aparece un mensaje de bienvenida, que le permite saber los tipos de acciones que el bot puede tomar en su nombre.

> [!NOTE]
> Al interactuar por primera vez con el bot, es posible que deba iniciar sesión. Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes.

Puede pedirle al bot que:

- Ver sus saldos de bajas actuales. Por ejemplo, envíe un mensaje que diga "Ver saldos de bajas".

- Comience una solicitud de licencia por usted. Por ejemplo, envíe un mensaje que diga "Tómese un tiempo libre" o "Quiero tomarme un tiempo libre el próximo jueves y viernes" para ser más específico para solicitar una baja por el tipo de baja por vacaciones. 

  ![Iniciar una solicitud de permiso en el chat de Teams.](./media/hr-teams-leave-app-initiate.png)

- El bot de chat completará una solicitud de permiso para usted. Seleccione **Solicitar tiempo libre** y edite los detalles de su solicitud.

   Si desea enviar solicitudes de baja para varios tipos de baja para la misma fecha, seleccione la opción **Dividir el día con** opción del menú **Más opciones**. 

   Si selecciona una baja de medio día cuando la unidad de solicitud de baja está en días, puede especificar si desea solicitar tiempo libre el primer medio día o el segundo medio día seleccionando la opción **Definición de medio día** en el menú **Más opciones**.
   
   ![Definiciones de medio día.](./media/HalfDayDefinitions.png)

- Cuando haya terminado de editar los detalles de su solicitud de permiso, seleccione **Enviar** para enviarlo para su aprobación.

  ![Enviar solicitud de licencia.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Administrar su baja en Teams

La pestaña **Tiempo libre** le permite ver: 

- Información del saldo de cada tipo de baja en la que esté inscrito

- Próximas solicitudes de baja

- Solicitudes de tiempo libre

- Borrador de solicitudes de baja
 
### <a name="create-a-new-request"></a>Crear una nueva solicitud

1. Para crear una nueva solicitud de baja, seleccione **Nueva solicitud**.

2. Introduzca el día o días que desea tomarse y luego seleccione **Agregar**.

   ![Adición de tiempo libre en la aplicación de bajas de Recursos Humanos en Teams.](./media/TimeOffHours.png)

3. Si corresponde, introduzca un código de razón. Introduzca también cualquier comentario y agregue cualquier archivo adjunto.

4. Si desea enviar solicitudes de baja para varios tipos de baja para la misma fecha, seleccione la opción **Dividir el día con** del menú **Más opciones**.

5. Seleccione la opción **Definición de medio día** para especificar si desea solicitar el primer medio día libre o el segundo medio día libre. Esta opción está disponible cuando la unidad de solicitud de baja está en días y el monto solicitado es de 0,5 días.

6. Cuando haya terminado de Introducir información, introduzca **Enviar** para enviarlo para su aprobación. También puede introducir **Guardar como borrador** para volver a ello más tarde.

### <a name="manage-draft-requests"></a>Administrar solicitudes en borrador

1. Seleccione la pestaña **Borradores**.

2. Seleccione el lápiz para editar la solicitud o seleccione la papelera para eliminar la solicitud.

3. Realice los cambios necesarios. Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación. También puede seleccionar **Guardar como borrador** para volver a ello más tarde.
   
### <a name="respond-to-teams-notifications"></a>Responder a notificaciones de Teams

Cuando usted o un trabajador del que es aprobador envíen una solicitud de baja, recibirá una notificación en la aplicación Human Resources en Teams. Puede seleccionar la notificación para verla. Las notificaciones también aparecen en el área **Chat**.

Si es un aprobador, puede seleccionar **Aprobar** o **Denegar** en la notificación. También puede proporcionar un mensaje opcional.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Enviar información sobre el próximo tiempo libre a sus compañeros de trabajo

Después de instalar la aplicación Recursos humanos para Teams, puede enviar fácilmente información sobre su próximo tiempo libre a sus compañeros de trabajo a través de Teams o chats.

1. En un equipo o chat de Teams, seleccione el botón Recursos humanos debajo de la ventana de chat.

   ![Botón de recursos humanos bajo la ventana de chat.](./media/hr-teams-leave-app-chat-button.png)

2. Seleccione la solicitud de baja que desea compartir. Si desea compartir un borrador de solicitud de baja, primero seleccione **Borradores**.

Su solicitud de baja se mostrará en el chat.

Si compartió un borrador de solicitud, se mostrará como un borrador.

## <a name="view-your-teams-leave-calendar"></a>Ver el calendario de bajas de su equipo

Si es un director con subordinados directos, puede ver el tiempo libre aprobado y pendiente de su equipo.

1. En la aplicación Human Resources en Teams, seleccione **Tiempo libre**.

2. Seleccione **Calendario del equipo**. El calendario muestra el tiempo libre aprobado y pendiente de sus subordinados directos.

   > [!NOTE]
   > Si no puede ver el calendario del equipo, pídale a su administrador que lo habilite. Para obtener más información consulte [Instalar y configurar](hr-admin-teams-leave-app.md#install-and-setup).

## <a name="supported-languages"></a>Idiomas admitidos

La aplicación Dynamics 365 Human Resources en Teams admite los siguientes idiomas:

| ID de configuración regional | Idioma |
| --- | --- |
| de-DE | Alemán (Alemania) |
| es-ES | Español (España) |
| es-MX | Español (México) |
| fr-CA | Francés (Canadá) |
| fr-FR | Francés (Francia) |
| it-IT | Italiano (Italia) |
| nl-NL | Neerlandés (Países Bajos) |
| pt-BR | Portugués (Brasil) |
| tr-TR | Turco (Turquía) |
| zh-CN | Chino (Simplificado) |

## <a name="troubleshooting"></a>Solución de problemas

Si tiene problemas para iniciar sesión o utilizar la aplicación Dynamics 365 Human Resources Teams, intente seguir estas instrucciones de solución de problemas. Si sigue teniendo problemas después de la resolución de problemas, comuníquese con Soporte. Para obtener más información, consulte [Obtener soporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>No puedo iniciar sesión en la aplicación de recursos humanos en Teams

Si no puede iniciar sesión en la aplicación, es posible que la cuenta que está usando para iniciar sesión en Microsoft Teams no está asociado con un registro de empleado en Dynamics 365 Human Resources. Comuníquese con el administrador del sistema para asegurarse de que su registro de empleado esté asociado correctamente.

### <a name="translations-dont-display-correctly"></a>Las traducciones no se muestran correctamente

Si las traducciones no se muestran como se esperaba, asegúrese de que el idioma que seleccione en Teams coincida con el idioma seleccionado en las **Opciones de usuario** de Human Resources.

En Teams, mire **Idioma de la aplicación** en **Ajustes**.

![Configuración de Teams.](./media/hr-teams-leave-app-settings.png)

En Human Resources, seleccione **Ajustes** y luego seleccione **Opciones de usuario**. Verifique que el campo **Idioma** coincide con el campo **Idioma de la aplicación** en Teams.

![Opciones de usuario de Human Resources.](./media/hr-teams-leave-app-user-options.png)

Si aún tiene problemas de traducción, háganoslo saber. Para obtener información, consulte [Obtener soporte técnico para aplicaciones de Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Error al aprobar solicitudes de licencia en la aplicación Human Resources en Teams

Si recibe un error cuando intenta aprobar solicitudes de permiso en la aplicación Teams, intente los siguientes pasos de solución de problemas:

1. Verifique que la cuenta que está usando para iniciar sesión en Microsoft Teams es la misma que usa para acceder a Dynamics 365 Human Resources.

2. Verifique que es un aprobador válido para la solicitud al verificar la configuración del flujo de trabajo para la aprobación de la licencia. Para obtener más información sobre los flujos de trabajo de solicitud de licencia, consulte [Crear un flujo de trabajo de solicitud de licencia](hr-leave-and-absence-workflow.md).

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>Los aprobadores de bajas no reciben mensajes de chat de Teams para aprobar solicitudes de bajas

1. Asegúrese de que las notificaciones estén habilitadas para el entorno y el usuario. Para más información, vea [Habilitar notificaciones para la aplicación Human Resources en Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) y [Activar o desactivar las notificaciones para usuarios individuales](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).

2. Asegúrese de que los usuarios estén conectados en la pestaña **Chats** con las mismas credenciales que utilizan para aprobar solicitudes de baja. Utilice los mensajes "cerrar sesión" y luego "iniciar sesión" para iniciar sesión con las credenciales correctas.

3. Si el problema persiste, verifique el estado del trabajo por lotes del sistema Business Events como administrador del sistema. Si está en una etapa de espera o ejecución, vuelva a consultar en unos minutos. Si el estado permanece sin cambios, registre un vale de soporte para que nuestro equipo pueda ayudar a resolver el problema.

## <a name="known-accessibility-issues"></a>Problemas de accesibilidad conocidos

La aplicación Human Resources en Teams tiene los siguientes problemas de accesibilidad en los que estamos trabajando para solucionarlos en futuras versiones.

| Emitir | Solución alternativa o explicación |
| --- | --- |
| Hacer zoom al 400 % en el escritorio oculta algunos de los botones de acción de la vista. | Recomendamos usar una lupa en su lugar hasta que podamos admitir este nivel de zoom. |
| En la pestaña **Tiempo libre**, VoiceOver anuncia la acción de un botón mientras se lee el encabezado de la cuadrícula de tiempo libre. | El encabezado y los elementos de la cuadrícula están agrupados por año y se pueden contraer. VoiceOver interpreta esto como un elemento procesable, pero no lo es. |
| En la pestaña **Tiempo libre**, hay un gesto adicional de deslizar rápidamente al navegar a **Código de razón** en una nueva solicitud. | No hay ningún control oculto al que esté intentando obtener acceso la navegación por deslizamiento. |
| En la pestaña **Tiempo libre**, si desliza el dedo mientras el calendario está abierto, terminará fuera del control en lugar de en la parte superior de una nueva solicitud o mientras edita una solicitud. | Al llegar a **Ir a hoy**, considérelo como el final del control y deslice el dedo en la dirección inversa para volver a la parte superior. |
| En la pestaña **Chat**, el foco vuelve a la parte superior cuando introduce una fecha mientras usa la herramienta de asistencia o la navegación del teclado. | Desplácese con el tabulador hasta que llegue a su área de entrada de nuevo. |

## <a name="privacy-notice"></a>Aviso de privacidad

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Servicio inteligente de comprensión del lenguaje de Microsoft (LUIS)

Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente. La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS). Obtenga más información sobre LUIS [aquí](https://www.luis.ai/). El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso). Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario. 

Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada. El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources. Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure. 

El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio. Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid y Azure Cosmos DB

Al utilizar la característica de notificaciones para la aplicación Dynamics 365 Human Resources en Microsoft Teams, algunos datos de clientes saldrán de la región geográfica donde se implementa el servicio de Recursos Humanos del inquilino.

Dynamics 365 Human Resources transmite la solicitud de licencia del empleado y los detalles de la tarea del flujo de trabajo a Microsoft Azure Event Grid y Microsoft Teams. Estos datos pueden almacenarse en Microsoft Azure Event Grid hasta por 24 horas y se procesarán en los Estados Unidos, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicios. Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).

Mientras conversa con el bot de chat en la aplicación de Recursos Humanos, el contenido de la conversación puede almacenarse en Azure Cosmos DB y transmitirse a Microsoft Teams. Estos datos pueden almacenarse en Azure Cosmos DB durante un máximo de 24 horas y pueden procesarse fuera de la región geográfica donde se implementa el servicio de Recursos Humanos de su inquilino, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicio. Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).
 
Para restringir el acceso a la aplicación de Recursos Humanos en Microsoft Teams para su organización o para usuarios de su organización, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Consulte también

[Descargar e instalar Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centro de ayuda de Microsoft Teams](https://support.office.com/teams)</br>
[Aplicación Human Resources en Teams](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
