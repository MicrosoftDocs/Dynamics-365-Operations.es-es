---
title: Aplicación Recursos humanos en Teams
description: Este tema presenta la aplicación Microsoft Dynamics 365 Human Resources en Microsoft Teams.
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
ms.openlocfilehash: 423ec36a73e8af9d915c5cfe16bd4d552448e2b6
ms.sourcegitcommit: d1541831d556b722a71aed442043ffb4a4576d87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "3388125"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="5e0c2-103">Aplicación Recursos humanos en Teams</span><span class="sxs-lookup"><span data-stu-id="5e0c2-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5e0c2-104">La aplicación Microsoft Dynamics 365 Human Resources de Microsoft Teams permite a los empleados solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="5e0c2-105">Los empleados pueden interactuar con un bot para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="5e0c2-106">La pestaña **Tiempo libre** proporciona información más detallada.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-106">The **Time off** tab provides more detailed information.</span></span>

![Bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-admin-teams-leave-app-bot.png)

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="5e0c2-109">Instalar y configurar</span><span class="sxs-lookup"><span data-stu-id="5e0c2-109">Install and setup</span></span>

<span data-ttu-id="5e0c2-110">Puede encontrar la aplicación Recursos Humanos en la tienda Teams.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="5e0c2-111">Para obtener información sobre cómo instalar la aplicación Teams, consulte [Administrar solicitudes de licencia en Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="5e0c2-112">Para obtener información sobre la administración de permisos de aplicaciones en Teams, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="5e0c2-113">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="5e0c2-113">Known issues</span></span>

| <span data-ttu-id="5e0c2-114">Emitir</span><span class="sxs-lookup"><span data-stu-id="5e0c2-114">Issue</span></span> | <span data-ttu-id="5e0c2-115">Estado</span><span class="sxs-lookup"><span data-stu-id="5e0c2-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="5e0c2-116">El saldo es incorrecto si se envía tiempo libre para una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-116">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="5e0c2-117">La previsión no está disponible aún.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-117">Forecasting isn't yet available.</span></span> <span data-ttu-id="5e0c2-118">El saldo se muestra para la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-118">The balance displays for the current date.</span></span> |
| <span data-ttu-id="5e0c2-119">Al reducir el número de horas que se requieren en una solicitud existente, el **Saldo restante** baja en lugar subir.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-119">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="5e0c2-120">Abordaremos este problema conocido en el futuro.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-120">We'll address this known issue in the future.</span></span> <span data-ttu-id="5e0c2-121">La visualización es incorrecta, pero los importes correctos se ajustan en el momento del envío.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-121">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="5e0c2-122">Dos tarjetas **Próximo tiempo libre** se muestran para las mismas fechas.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-122">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="5e0c2-123">Las tarjetas representan envíos individuales.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-123">The cards represent individual submissions.</span></span> <span data-ttu-id="5e0c2-124">Continuaremos recibiendo comentarios y haciendo ajustes.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-124">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="5e0c2-125">No se puede cancelar una solicitud **En revisión**.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-125">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="5e0c2-126">Esta funcionalidad no es compatible actualmente y se agregará en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-126">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="5e0c2-127">La información del saldo se calcula a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-127">Balance information is calculated as of today.</span></span> | <span data-ttu-id="5e0c2-128">El sistema actualmente no muestra saldos a partir del período de acumulación, incluso si está configurado en los parámetros de Baja y Ausencia.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-128">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="5e0c2-129">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="5e0c2-129">Privacy notice</span></span>

<span data-ttu-id="5e0c2-130">Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-130">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="5e0c2-131">La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-131">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="5e0c2-132">Obtenga más información sobre LUIS [aquí](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-132">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="5e0c2-133">El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-133">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="5e0c2-134">Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/)  de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-134">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="5e0c2-135">Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-135">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="5e0c2-136">El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-136">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="5e0c2-137">Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-137">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="5e0c2-138">El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio.</span><span class="sxs-lookup"><span data-stu-id="5e0c2-138">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="5e0c2-139">Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-139">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="5e0c2-140">Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="5e0c2-140">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="5e0c2-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e0c2-141">See also</span></span> 

[<span data-ttu-id="5e0c2-142">Descargar e instalar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e0c2-142">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="5e0c2-143">Centro de ayuda de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5e0c2-143">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="5e0c2-144">Administrar solicitudes de baja en Teams</span><span class="sxs-lookup"><span data-stu-id="5e0c2-144">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

