---
title: Notificaciones de alertas del cliente por correo electrónico
description: Este tema proporciona información acerca de cómo configurar las reglas que envían notificaciones por correo electrónico para los eventos predefinidos que ocurren.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 9545731af20a96c322b4e92c17f3a46b7077295b
ms.sourcegitcommit: a13f44549ab402cfd04b600f6097ba179915f233
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "775073"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="7ab77-103">Notificaciones de alertas del cliente por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="7ab77-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="7ab77-104">En Microsoft Dynamics 365 for Finance and Operations, puede definir reglas de alertas personalizadas que siguen vistas filtradas de datos y registra automáticamente dichas notificaciones por correo electrónico cuando los eventos predefinidos aparecen.</span><span class="sxs-lookup"><span data-stu-id="7ab77-104">In Microsoft Dynamics 365 for Finance and Operations, you can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="7ab77-105">La opción para enviar notificaciones por correo electrónico está disponible para todos los tipos alertas admitidos y también se puede activar para las reglas de alertas existentes.</span><span class="sxs-lookup"><span data-stu-id="7ab77-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="7ab77-106">Puede usar los controles integrados para crear reglas de alertas que controlan las vistas filtradas guardadas de los trabajos por lotes del sistema.</span><span class="sxs-lookup"><span data-stu-id="7ab77-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="7ab77-107">Controlando el valor del campo **Estado** , también puede configurar las reglas de alertas que envían el correo electrónico cuando falla un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="7ab77-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="7ab77-108">Una vez creadas estas reglas de alertas, ya no tiene que comprobar los informes de los cambios en los datos empresariales.</span><span class="sxs-lookup"><span data-stu-id="7ab77-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="7ab77-109">En su lugar, puede dejar al servicio de detección de cambios inteligente de Finance and Operations que lo controle por usted.</span><span class="sxs-lookup"><span data-stu-id="7ab77-109">Instead, you can let the Finance and Operations intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="7ab77-110">Las alertas del cliente dependen del subsistema de correo electrónico que ofrece la integración con Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="7ab77-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="7ab77-111">Se recomienda que use el proveedor del protocolo simple de transferencia de correo (SMTP), de modo que la distribución de correo electrónico no tenga que basarse en un cliente de correo local.</span><span class="sxs-lookup"><span data-stu-id="7ab77-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="7ab77-112">Para enviar notificaciones por correo electrónico, los clientes deben configurar los servicios de correo electrónico integrados.</span><span class="sxs-lookup"><span data-stu-id="7ab77-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="7ab77-113">Las notificaciones por correo electrónico se envían a los destinatarios en nombre del propietario de las alertas.</span><span class="sxs-lookup"><span data-stu-id="7ab77-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="7ab77-114">Para obtener más información sobre cómo configurar el correo electrónico en Finance and Operations, consulte [Configurar y enviar el correo electrónico](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="7ab77-114">For more information about how to configure email in Finance and Operations, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="7ab77-115">En la imagen siguiente se muestra el cuadro **Crear regla de alertas** , que ahora incluye una opción **Enviar correo electrónico** .</span><span class="sxs-lookup"><span data-stu-id="7ab77-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="7ab77-116">[![Cree el cuadro de diálogo de la regla de alerta, donde la opción de correo electrónico de envío se establece en Sí](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="7ab77-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="7ab77-117">Cuando la opción **Enviar correo electrónico** se establece en **Sí**, las notificaciones de alertas continuarán siendo entregadas Centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="7ab77-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="7ab77-118">Plantillas de correo electrónico de notificación de alerta</span><span class="sxs-lookup"><span data-stu-id="7ab77-118">Alert notification email templates</span></span>

<span data-ttu-id="7ab77-119">El servicio registra notificaciones por correo electrónico mediante las plantillas de correo electrónico predefinidas que envían los detalles básicos de la notificación de alerta.</span><span class="sxs-lookup"><span data-stu-id="7ab77-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span>

<span data-ttu-id="7ab77-120">La siguiente imagen muestra la estructura de las notificaciones alertas cuando se reciben por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="7ab77-120">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="7ab77-121">[![Notificaciones de alerta basadas en plantillas para la creación de registros, cambios de campos y eliminación de plantilla](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="7ab77-121">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>
