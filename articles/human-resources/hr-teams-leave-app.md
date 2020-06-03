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
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 67501a1fa65493a1a23eb6176ece5be98d6e4659
ms.sourcegitcommit: 7fc0726c0a93ce6f4dafaad3232b4687f61cdc88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "3393017"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="5defd-103">Administrar solicitudes de baja en Teams</span><span class="sxs-lookup"><span data-stu-id="5defd-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5defd-104">La aplicación Microsoft Dynamics 365 Human Resources en Microsoft Teams le permite solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre directamente en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5defd-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="5defd-105">Puede interactuar con un bot para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="5defd-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="5defd-106">La pestaña **Tiempo libre** proporciona información más detallada.</span><span class="sxs-lookup"><span data-stu-id="5defd-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="5defd-107">Instalar la aplicación</span><span class="sxs-lookup"><span data-stu-id="5defd-107">Install the app</span></span>

<span data-ttu-id="5defd-108">Puede encontrar la aplicación Recursos Humanos en la tienda Teams.</span><span class="sxs-lookup"><span data-stu-id="5defd-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="5defd-109">En Microsoft Teams, seleccione los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="5defd-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Puntos suspensivos de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="5defd-111">Busque Dynamics 365 Human Resources y luego seleccione el icono **Recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="5defd-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Icono RR. HH. de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="5defd-113">Seleccione el botón **Añadir** para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5defd-113">Select the **Add** button to install the app.</span></span>

   ![Instalación de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="5defd-115">Si la aplicación no inicia sesión automáticamente, seleccione la pestaña **Configuración** para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="5defd-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Pestaña Configuración de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="5defd-117">Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes.</span><span class="sxs-lookup"><span data-stu-id="5defd-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="5defd-118">Si tiene acceso a más de una instancia de Recursos humanos, puede seleccionar a qué entorno desea conectarse en la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="5defd-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="5defd-119">La aplicación no admite actualmente el rol de seguridad del administrador del sistema y mostrará un mensaje de error si inicia sesión con una cuenta de administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="5defd-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="5defd-120">Para iniciar sesión con una cuenta diferente, en la pestaña **Configuraciones**, seleccione el botón **Cambiar cuentas** y luego inicie sesión con una cuenta de usuario que no tenga privilegios de administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="5defd-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="5defd-121">Usar el bot</span><span class="sxs-lookup"><span data-stu-id="5defd-121">Use the bot</span></span>

<span data-ttu-id="5defd-122">Después de la instalación de la aplicación, aparece un mensaje de bienvenida, que le permite saber los tipos de acciones que el bot puede tomar en su nombre.</span><span class="sxs-lookup"><span data-stu-id="5defd-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Mensaje de bienvenida del bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="5defd-124">Al interactuar por primera vez con el bot, es posible que deba iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="5defd-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="5defd-125">Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes.</span><span class="sxs-lookup"><span data-stu-id="5defd-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="5defd-126">Puede pedirle al bot que:</span><span class="sxs-lookup"><span data-stu-id="5defd-126">You can ask the bot to:</span></span>

- <span data-ttu-id="5defd-127">Muestra la información del saldo de tiempo libre para cada tipo de baja en la que esté inscrito.</span><span class="sxs-lookup"><span data-stu-id="5defd-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Balances mostrados en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="5defd-129">Mostrar detalles adicionales sobre un tipo de baja específico.</span><span class="sxs-lookup"><span data-stu-id="5defd-129">Show additional details about a specific leave type.</span></span>

   ![Detalles mostrados en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="5defd-131">Comience una solicitud de licencia por usted.</span><span class="sxs-lookup"><span data-stu-id="5defd-131">Start a leave request for you.</span></span>

   ![Solicitud de ausencia en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="5defd-133">Después de comenzar una solicitud de baja, puede ajustar los días directamente en la tarjeta, o puede seleccionar **Editar detalles** para agregar información adicional a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5defd-133">After you start a leave request, you can adjust the days right within the card, or you can select **Edit details** to add additional information to your request.</span></span>

![Solicitud de edición en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="5defd-135">Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="5defd-135">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5defd-136">También puede escribir **Guardar como borrador** para volver a ello más tarde.</span><span class="sxs-lookup"><span data-stu-id="5defd-136">You can also type **Save as draft** to come back to it later.</span></span>

![Solicitud de envío en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="5defd-138">Administrar su baja en Teams</span><span class="sxs-lookup"><span data-stu-id="5defd-138">Manage your leave in Teams</span></span>

<span data-ttu-id="5defd-139">La pestaña **Tiempo libre** le permite ver:</span><span class="sxs-lookup"><span data-stu-id="5defd-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="5defd-140">Información del saldo de cada tipo de baja en la que esté inscrito</span><span class="sxs-lookup"><span data-stu-id="5defd-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="5defd-141">Próximas solicitudes de baja</span><span class="sxs-lookup"><span data-stu-id="5defd-141">Upcoming leave requests</span></span>

- <span data-ttu-id="5defd-142">Solicitudes de tiempo libre</span><span class="sxs-lookup"><span data-stu-id="5defd-142">Time-off requests</span></span>

- <span data-ttu-id="5defd-143">Borrador de solicitudes de baja</span><span class="sxs-lookup"><span data-stu-id="5defd-143">Draft leave requests</span></span>

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="5defd-145">Crear una nueva solicitud</span><span class="sxs-lookup"><span data-stu-id="5defd-145">Create a new request</span></span>

1. <span data-ttu-id="5defd-146">Para crear una nueva solicitud de baja, seleccione **Nueva solicitud**.</span><span class="sxs-lookup"><span data-stu-id="5defd-146">To create a new leave request, select **New request**.</span></span>

   ![Nueva solicitud de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="5defd-148">Introduzca el día o días que desea tomarse y luego seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="5defd-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Adición de tiempo libre en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="5defd-150">Si corresponde, introduzca un código de razón.</span><span class="sxs-lookup"><span data-stu-id="5defd-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="5defd-151">Introduzca también cualquier comentario y agregue cualquier archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="5defd-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="5defd-152">Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="5defd-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5defd-153">También puede escribir **Guardar como borrador** para volver a ello más tarde.</span><span class="sxs-lookup"><span data-stu-id="5defd-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="5defd-154">Administrar solicitudes en borrador</span><span class="sxs-lookup"><span data-stu-id="5defd-154">Manage draft requests</span></span>

1. <span data-ttu-id="5defd-155">Seleccione la pestaña **Borradores**.</span><span class="sxs-lookup"><span data-stu-id="5defd-155">Select the **Drafts** tab.</span></span>

   ![Pestaña Borradores de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="5defd-157">Seleccione el lápiz para editar la solicitud o seleccione la papelera para eliminar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5defd-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="5defd-158">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="5defd-158">Make any necessary changes.</span></span> <span data-ttu-id="5defd-159">Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="5defd-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="5defd-160">También puede seleccionar **Guardar como borrador** para volver a ello más tarde.</span><span class="sxs-lookup"><span data-stu-id="5defd-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Borrador de edición en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a><span data-ttu-id="5defd-162">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="5defd-162">Privacy notice</span></span>

<span data-ttu-id="5defd-163">Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente.</span><span class="sxs-lookup"><span data-stu-id="5defd-163">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="5defd-164">La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS).</span><span class="sxs-lookup"><span data-stu-id="5defd-164">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="5defd-165">Obtenga más información sobre LUIS [aquí](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="5defd-165">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="5defd-166">El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="5defd-166">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="5defd-167">Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/)  de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario.</span><span class="sxs-lookup"><span data-stu-id="5defd-167">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="5defd-168">Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada.</span><span class="sxs-lookup"><span data-stu-id="5defd-168">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="5defd-169">El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5defd-169">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5defd-170">Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure.</span><span class="sxs-lookup"><span data-stu-id="5defd-170">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="5defd-171">El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio.</span><span class="sxs-lookup"><span data-stu-id="5defd-171">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="5defd-172">Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="5defd-172">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="5defd-173">Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5defd-173">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="5defd-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5defd-174">See also</span></span>

[<span data-ttu-id="5defd-175">Descargar e instalar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5defd-175">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="5defd-176">Centro de ayuda de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5defd-176">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="5defd-177">Aplicación Recursos humanos en Teams</span><span class="sxs-lookup"><span data-stu-id="5defd-177">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
