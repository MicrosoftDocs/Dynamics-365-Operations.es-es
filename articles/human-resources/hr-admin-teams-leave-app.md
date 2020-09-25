---
title: Aplicación Recursos humanos en Teams
description: Este tema presenta la aplicación Microsoft Dynamics 365 Human Resources en Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
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
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776317"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="47812-103">Aplicación Recursos humanos en Teams</span><span class="sxs-lookup"><span data-stu-id="47812-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="47812-104">La aplicación Microsoft Dynamics 365 Human Resources de Microsoft Teams permite a los empleados solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="47812-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="47812-105">Los empleados pueden interactuar con un bot para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="47812-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="47812-106">La pestaña **Tiempo libre** proporciona información más detallada.</span><span class="sxs-lookup"><span data-stu-id="47812-106">The **Time off** tab provides more detailed information.</span></span>

![Bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-admin-teams-leave-app-bot.png)

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="47812-109">Instalar y configurar</span><span class="sxs-lookup"><span data-stu-id="47812-109">Install and setup</span></span>

<span data-ttu-id="47812-110">Puede encontrar la aplicación Recursos Humanos en la tienda Teams.</span><span class="sxs-lookup"><span data-stu-id="47812-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="47812-111">Para obtener información sobre cómo instalar la aplicación Teams, consulte [Administrar solicitudes de licencia en Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="47812-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="47812-112">Para obtener información sobre la administración de permisos de aplicaciones en Teams, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="47812-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="47812-113">Habilitar notificaciones para la aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="47812-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="47812-114">Si desea que los usuarios reciban notificaciones de solicitud de permiso en la aplicación Teams, debe habilitar las notificaciones en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="47812-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="47812-115">Solo los usuarios que hayan iniciado sesión en Teams y que utilicen la aplicación Human Resources Teams recibirán notificaciones.</span><span class="sxs-lookup"><span data-stu-id="47812-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="47812-116">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="47812-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="47812-117">Seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="47812-117">Select **Links**.</span></span>

3. <span data-ttu-id="47812-118">En **Configuración**, seleccione **Parámetros del sistema**.</span><span class="sxs-lookup"><span data-stu-id="47812-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="47812-119">En la pestaña **General**, establezca **Habilitar notificaciones para la aplicación Teams** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="47812-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Habilitar las notificaciones de la aplicación Teams en los parámetros del sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="47812-121">Para activar las notificaciones de Teams para todos los usuarios, seleccione **Sí** en el aviso.</span><span class="sxs-lookup"><span data-stu-id="47812-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Habilitar notificaciones de Teams para todos los usuarios](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="47812-123">Activar o desactivar las notificaciones de Teams para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="47812-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="47812-124">Una vez que haya habilitado las notificaciones para la aplicación en la aplicación Human Resources Teams, puede activar o desactivar las notificaciones para usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="47812-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="47812-125">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="47812-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="47812-126">Seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="47812-126">Select **Links**.</span></span>

3. <span data-ttu-id="47812-127">En **Usuarios**, seleccione **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="47812-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="47812-128">Seleccione la pestaña **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="47812-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="47812-129">Establezca **Habilitar notificaciones para la aplicación Teams** en **Sí** para habilitar notificaciones para el usuario o **No** para deshabilitar las notificaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="47812-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Habilitar las notificaciones de la aplicación Teams en la pestaña Flujo de trabajo de opciones de usuario](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="47812-131">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47812-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="47812-132">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="47812-132">Known issues</span></span>

| <span data-ttu-id="47812-133">Emitir</span><span class="sxs-lookup"><span data-stu-id="47812-133">Issue</span></span> | <span data-ttu-id="47812-134">Estado</span><span class="sxs-lookup"><span data-stu-id="47812-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="47812-135">El desplazamiento horizontal no funciona en los teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="47812-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="47812-136">El desplazamiento horizontal no es un problema en iOS ni en dispositivos de escritorio.</span><span class="sxs-lookup"><span data-stu-id="47812-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="47812-137">Estamos trabajando en una solución para Android.</span><span class="sxs-lookup"><span data-stu-id="47812-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="47812-138">Error: hay un problema para encontrar un entorno al que conectarse.</span><span class="sxs-lookup"><span data-stu-id="47812-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="47812-139">Puede recibir este error incluso si ha verificado que el usuario puede acceder a uno o más entornos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="47812-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="47812-140">Además, es posible que no aparezcan todos los entornos que espera.</span><span class="sxs-lookup"><span data-stu-id="47812-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="47812-141">Hasta que solucionemos este problema, elimine el usuario y luego impórtelo nuevamente para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="47812-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="47812-142">El saldo es incorrecto si se envía tiempo libre para una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="47812-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="47812-143">La previsión no está disponible aún.</span><span class="sxs-lookup"><span data-stu-id="47812-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="47812-144">El saldo se muestra para la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="47812-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="47812-145">No se puede cancelar una solicitud **En revisión**.</span><span class="sxs-lookup"><span data-stu-id="47812-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="47812-146">Esta funcionalidad no es compatible actualmente y se agregará en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="47812-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="47812-147">La información del saldo se calcula a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="47812-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="47812-148">El sistema actualmente no muestra saldos a partir del período de acumulación, incluso si está configurado en los parámetros de Baja y Ausencia.</span><span class="sxs-lookup"><span data-stu-id="47812-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="47812-149">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="47812-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="47812-150">Servicio inteligente de comprensión del lenguaje de Microsoft (LUIS)</span><span class="sxs-lookup"><span data-stu-id="47812-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="47812-151">Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente.</span><span class="sxs-lookup"><span data-stu-id="47812-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="47812-152">La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS).</span><span class="sxs-lookup"><span data-stu-id="47812-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="47812-153">Obtenga más información sobre LUIS [aquí](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="47812-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="47812-154">El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="47812-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="47812-155">Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario.</span><span class="sxs-lookup"><span data-stu-id="47812-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="47812-156">Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada.</span><span class="sxs-lookup"><span data-stu-id="47812-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="47812-157">El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="47812-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="47812-158">Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure.</span><span class="sxs-lookup"><span data-stu-id="47812-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="47812-159">El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio.</span><span class="sxs-lookup"><span data-stu-id="47812-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="47812-160">Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="47812-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="47812-161">Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="47812-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="47812-162">Microsoft Azure Event Grid y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47812-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="47812-163">Al utilizar la función de notificaciones para la aplicación Dynamics 365 Human Resources en Teams, ciertos datos de clientes fluirán fuera de la región geográfica donde se implementa el servicio de Recursos Humanos de su inquilino.</span><span class="sxs-lookup"><span data-stu-id="47812-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="47812-164">Dynamics 365 Human Resources transmite la solicitud de licencia del empleado y los detalles de la tarea del flujo de trabajo a Microsoft Azure Event Grid y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="47812-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="47812-165">Estos datos pueden almacenarse hasta por 24 horas y procesarse en los Estados Unidos, están encriptados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicios.</span><span class="sxs-lookup"><span data-stu-id="47812-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="47812-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47812-166">See also</span></span> 

[<span data-ttu-id="47812-167">Descargar e instalar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47812-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="47812-168">Centro de ayuda de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47812-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="47812-169">Administrar solicitudes de bajas en Teams</span><span class="sxs-lookup"><span data-stu-id="47812-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

