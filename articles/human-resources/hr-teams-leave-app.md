---
title: Administrar solicitudes de baja en Teams
description: Este tema muestra cómo solicitar tiempo libre en la aplicación Dynamics 365 Human Resources en Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b3daa76385518ad4c7150fa93ce33be0351bfd57
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428837"
---
# <a name="manage-leave-requests-in-teams"></a>Administrar solicitudes de baja en Teams

[!include [banner](includes/preview-feature.md)]

La aplicación Microsoft Dynamics 365 Human Resources en Microsoft Teams le permite solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre directamente en Microsoft Teams. Puede interactuar con un bot para solicitar información. La pestaña **Tiempo libre** proporciona información más detallada.

## <a name="install-the-app"></a>Instalar la aplicación

Puede encontrar la aplicación Recursos Humanos en la tienda Teams.

1. En Microsoft Teams, seleccione los puntos suspensivos.

   ![Puntos suspensivos de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. Busque Dynamics 365 Human Resources y luego seleccione el icono **Recursos humanos**.

   ![Icono RR. HH. de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. Seleccione el botón **Añadir** para instalar la aplicación.

   ![Instalación de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-in-store.png)

Si la aplicación no inicia sesión automáticamente, seleccione la pestaña **Configuración** para iniciar sesión.

![Pestaña Configuración de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes. 

Si tiene acceso a más de una instancia de Recursos humanos, puede seleccionar a qué entorno desea conectarse en la pestaña **Configuración**.

> [!WARNING]
> La aplicación no admite actualmente el rol de seguridad del administrador del sistema y mostrará un mensaje de error si inicia sesión con una cuenta de administrador del sistema. Para iniciar sesión con una cuenta diferente, en la pestaña **Configuraciones**, seleccione el botón **Cambiar cuentas** y luego inicie sesión con una cuenta de usuario que no tenga privilegios de administrador del sistema.
 
## <a name="use-the-bot"></a>Usar el bot

Después de la instalación de la aplicación, aparece un mensaje de bienvenida, que le permite saber los tipos de acciones que el bot puede tomar en su nombre.

![Mensaje de bienvenida del bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> Al interactuar por primera vez con el bot, es posible que deba iniciar sesión. Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes.

Puede pedirle al bot que:

- Muestra la información del saldo de tiempo libre para cada tipo de baja en la que esté inscrito.

   ![Balances mostrados en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- Mostrar detalles adicionales sobre un tipo de baja específico.

   ![Detalles mostrados en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-details.png)

- Comience una solicitud de licencia por usted.

   ![Solicitud de ausencia en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-request.png)
 
Después de comenzar una solicitud de baja, puede ajustar los días directamente en la tarjeta, o puede seleccionar **Editar detalles** para agregar información adicional a la solicitud.

![Solicitud de edición en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-edit.png)
 
Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación. También puede escribir **Guardar como borrador** para volver a ello más tarde.

![Solicitud de envío en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Administrar su baja en Teams

La pestaña **Tiempo libre** le permite ver:

- Información del saldo de cada tipo de baja en la que esté inscrito

- Próximas solicitudes de baja

- Solicitudes de tiempo libre

- Borrador de solicitudes de baja

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Crear una nueva solicitud

1. Para crear una nueva solicitud de baja, seleccione **Nueva solicitud**.

   ![Nueva solicitud de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Introduzca el día o días que desea tomarse y luego seleccione **Añadir**.

   ![Adición de tiempo libre en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Si corresponde, introduzca un código de razón. Introduzca también cualquier comentario y agregue cualquier archivo adjunto.

4. Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación. También puede escribir **Guardar como borrador** para volver a ello más tarde.

### <a name="manage-draft-requests"></a>Administrar solicitudes en borrador

1. Seleccione la pestaña **Borradores**.

   ![Pestaña Borradores de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. Seleccione el lápiz para editar la solicitud o seleccione la papelera para eliminar la solicitud.

3. Realice los cambios necesarios. Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación. También puede seleccionar **Guardar como borrador** para volver a ello más tarde.

   ![Borrador de edición en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a>Aviso de privacidad

Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente. La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS). Obtenga más información sobre LUIS [aquí](https://www.luis.ai/). El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso). Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/)  de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario. 

Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada. El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources. Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure. 

El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio. Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Consulte también

[Descargar e instalar Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centro de ayuda de Microsoft Teams](https://support.office.com/teams)</br>
[Aplicación Recursos humanos en Teams](hr-admin-teams-leave-app.md)
