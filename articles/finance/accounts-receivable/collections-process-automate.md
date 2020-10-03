---
title: Automatización del proceso de cobros
description: Este tema describe el proceso de configuración de estrategias de procesos de cobro que identifican automáticamente las facturas de los clientes que requieren un recordatorio por correo electrónico, una actividad de cobro (como una llamada telefónica) o una carta de cobro que se enviará al cliente.
author: panolte
manager: AnnBe
ms.date: 08/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: db59bad2ed3caf38f22bd4d6059e57747d1d983f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760655"
---
# <a name="collections-process-automation"></a><span data-ttu-id="af9a5-103">Automatización del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-103">Collections process automation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af9a5-104">Este tema describe el proceso de configuración de estrategias de procesos de cobro que identifican automáticamente las facturas de los clientes que requieren un recordatorio por correo electrónico, una actividad de cobro (como una llamada telefónica) o una carta de cobro que se enviará al cliente.</span><span class="sxs-lookup"><span data-stu-id="af9a5-104">This topic describes the process of setting up collections process strategies that automatically identify customer invoices that require an email reminder, collection activity (such as a phone call), or a collection letter to be sent to the customer.</span></span> 

<span data-ttu-id="af9a5-105">Las organizaciones dedican una cantidad significativa de tiempo a investigar informes de saldos antiguos, cuentas de clientes y facturas abiertas para determinar qué clientes deben ser contactados sobre una factura abierta o un saldo de cuenta.</span><span class="sxs-lookup"><span data-stu-id="af9a5-105">Organizations spend a significant amount of time researching aged balance reports, customer accounts, and open invoices to determine which customers need to be contacted about an open invoice or account balance.</span></span> <span data-ttu-id="af9a5-106">Esta investigación le quita tiempo al agente de cobros que dedica a comunicarse con los clientes para cobrar saldos deudores o resolver disputas de facturas.</span><span class="sxs-lookup"><span data-stu-id="af9a5-106">This research takes times away from a collection agent’s time spent communicating with customers to collect past due balances or resolving invoice disputes.</span></span> <span data-ttu-id="af9a5-107">La automatización del proceso de cobros le permite configurar un enfoque basado en estrategias para su proceso de cobros.</span><span class="sxs-lookup"><span data-stu-id="af9a5-107">Collections process automation lets you set up a strategy-based approach to your collection process.</span></span> <span data-ttu-id="af9a5-108">Esto le ayuda a aplicar las actividades de cobros de manera consistente al proporcionar recordatorios personalizados por correo electrónico o un proceso programado para enviar cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="af9a5-108">This helps you apply collection activities consistently by providing customized email reminders, or programmed process for sending collection letters.</span></span> 

## <a name="collections-process-setup"></a><span data-ttu-id="af9a5-109">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-109">Collections process setup</span></span>
<span data-ttu-id="af9a5-110">Puede usar la página **Configuración del proceso de cobros** (**Crédito y cobros > Configuración > Configuración del proceso de cobros**) para crear un proceso de cobros automatizado que programará actividades, enviará mensajes de correo electrónico y creará y publicará cartas de cobro de clientes.</span><span class="sxs-lookup"><span data-stu-id="af9a5-110">You can use the **Collections process setup** page (**Credit and collections > Setup > Collections process setup**) to create an automated collections process that will schedule activities, send email messages, and create and post customer collection letters.</span></span> <span data-ttu-id="af9a5-111">Los pasos del proceso se basan en la factura abierta principal o más antigua.</span><span class="sxs-lookup"><span data-stu-id="af9a5-111">The process steps are based on the leading or oldest open invoice.</span></span> <span data-ttu-id="af9a5-112">Cada paso utiliza esta factura para determinar qué comunicación o actividad debe realizarse con un cliente específico.</span><span class="sxs-lookup"><span data-stu-id="af9a5-112">Each step uses this invoice to determine what communication or activity should take place with a specific customer.</span></span>  

### <a name="process-hierarchy"></a><span data-ttu-id="af9a5-113">Jerarquía de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-113">Process hierarchy</span></span>
<span data-ttu-id="af9a5-114">Cada grupo de clientes solo se puede asignar a una jerarquía de procesos.</span><span class="sxs-lookup"><span data-stu-id="af9a5-114">Each customer pool can only be assigned to one process hierarchy.</span></span> <span data-ttu-id="af9a5-115">El rango de jerarquía de este paso identifica qué proceso tendrá prioridad si un cliente está incluido en más de un grupo que tiene asignada una jerarquía de procesos.</span><span class="sxs-lookup"><span data-stu-id="af9a5-115">The hierarchy rank of this step identifies which process will take precedence if a customer is included in more than one pool that has a process hierarchy assigned.</span></span> <span data-ttu-id="af9a5-116">El identificador del grupo determina qué clientes se asignarán al proceso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-116">The pool ID determines which customers will be assigned to the process.</span></span> 

<span data-ttu-id="af9a5-117">Los días tranquilos se utilizan para garantizar que el proceso automatizado no contacte con un cliente con demasiada frecuencia.</span><span class="sxs-lookup"><span data-stu-id="af9a5-117">The quiet days are used to ensure that a customer does not get contacted too frequently by the automated process.</span></span>  <span data-ttu-id="af9a5-118">Por ejemplo, si los días tranquilos se establecen en dos, el proceso automatizado no se pondrá en contacto con un cliente durante al menos dos días, incluso si la factura principal original se ha liquidado en su totalidad.</span><span class="sxs-lookup"><span data-stu-id="af9a5-118">For example, if the quiet days are set to two, a customer will not be contacted by the automated process for at least two days, even if the original leading invoice has been settled in full.</span></span> 

<span data-ttu-id="af9a5-119">Para excluir a los clientes de la automatización del proceso si el saldo de la cuenta o el saldo de la factura es menor que un valor definido, establezca el campo **Excluir del proceso** en **Sí** y especifique el valor del importe.</span><span class="sxs-lookup"><span data-stu-id="af9a5-119">To exclude customers from the process automation if the account balance or invoice balance is less than a defined value, set the **Exclude from process** field to **Yes** and enter the amount value.</span></span>

## <a name="process-details"></a><span data-ttu-id="af9a5-120">Detalles del proceso</span><span class="sxs-lookup"><span data-stu-id="af9a5-120">Process details</span></span>
<span data-ttu-id="af9a5-121">**Descripción** se utiliza para identificar el propósito o el nombre del paso en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="af9a5-121">**Description** is used to identify the purpose or name of the step in the hierarchy.</span></span>

<span data-ttu-id="af9a5-122">**Tipo de acción** define si el paso creará una actividad, enviará un correo electrónico o creará una carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="af9a5-122">**Action type** defines if the step will create an activity, send an email, or create a collection letter.</span></span>

<span data-ttu-id="af9a5-123">**Documento comercial** define la plantilla utilizada para crear el tipo de acción.</span><span class="sxs-lookup"><span data-stu-id="af9a5-123">**Business document** defines the template used to create the action type.</span></span>  <span data-ttu-id="af9a5-124">Puede ser una plantilla de actividad, una plantilla de correo electrónico o una carta de cobro por cliente.</span><span class="sxs-lookup"><span data-stu-id="af9a5-124">This can be an activity template, an email template, or a collection letter per customer.</span></span> 

<span data-ttu-id="af9a5-125">Los tipos de acción se pueden crear antes o después de la fecha de vencimiento de la factura, según la configuración que se muestra en la columna **Días en relación con la fecha de vencimiento de la factura**.</span><span class="sxs-lookup"><span data-stu-id="af9a5-125">The action types can be created on either before or after the invoice due date, based on the setting that's displayed in the **Days in relation to the invoice due date** column.</span></span>

<span data-ttu-id="af9a5-126">Cuando selecciona un tipo de acción de correo electrónico, el destinatario se utilizará para definir si se trata de un contacto de cliente, grupo de ventas o agente de cobros.</span><span class="sxs-lookup"><span data-stu-id="af9a5-126">When you select an email action type, the recipient will be used to define if that is a customer, sales group, or collections agent contact.</span></span> <span data-ttu-id="af9a5-127">El valor en el campo **Contacto de propósito comercial** determinará qué contacto de la cuenta de ese cliente recibirá la comunicación.</span><span class="sxs-lookup"><span data-stu-id="af9a5-127">The value in the **Business purpose contact** field will then determine which contact from that customer's account will receive the communication.</span></span>

## <a name="business-document-details"></a><span data-ttu-id="af9a5-128">Detalles de documentos empresariales</span><span class="sxs-lookup"><span data-stu-id="af9a5-128">Business document details</span></span>
<span data-ttu-id="af9a5-129">Los detalles del documento empresarial variarán según el tipo de acción que se seleccione en los detalles del proceso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-129">The business document details will vary based on the action type that's selected in the process details.</span></span>  <span data-ttu-id="af9a5-130">Cuando el tipo de acción es una actividad, se mostrarán los detalles de la plantilla de actividad.</span><span class="sxs-lookup"><span data-stu-id="af9a5-130">When the action type is an activity, the activity template details will be shown.</span></span>  <span data-ttu-id="af9a5-131">Estos detalles incluyen el nombre de la plantilla de la actividad, el tipo de actividad que se creará, el propósito de la actividad, el número de días programados para completar la actividad y los detalles de la actividad.</span><span class="sxs-lookup"><span data-stu-id="af9a5-131">These details include the activity template name, the type of activity that will be created, the purpose of the activity, the number of days scheduled to complete the activity, and the details of the activity.</span></span>  <span data-ttu-id="af9a5-132">Esta actividad luego se vinculará a la factura principal que informa al destinatario de la acción que se necesita para completar la actividad.</span><span class="sxs-lookup"><span data-stu-id="af9a5-132">This activity will then link to the leading invoice that tells the recipient of the action that’s needed to complete the activity.</span></span>

<span data-ttu-id="af9a5-133">Si el tipo de acción es un correo electrónico en los detalles del proceso, esta sección contendrá dos fichas desplegables.</span><span class="sxs-lookup"><span data-stu-id="af9a5-133">If the action type is an email in the process details, this section will contain two FastTabs.</span></span>  <span data-ttu-id="af9a5-134">La primera se utiliza para definir el identificador de la plantilla, la descripción del correo electrónico, el idioma predeterminado, el nombre de usuario que se asignará a los mensajes de correo electrónico que se envían automáticamente y la dirección de correo electrónico de los remitentes asociados.</span><span class="sxs-lookup"><span data-stu-id="af9a5-134">The first is used to define the template ID, email description, default language, the user name that will be assigned to email messages that are automatically sent, and the associated senders email address.</span></span> <span data-ttu-id="af9a5-135">La segunda permitirá que el cuerpo del correo electrónico se cree después de que los valores en los campos **Idioma** y **Tema** se guarden seleccionando **Editar**.</span><span class="sxs-lookup"><span data-stu-id="af9a5-135">The second will allow the body of the email to be created after the values in the **Language** and **Subject** fields are saved by selecting **Edit**.</span></span>  <span data-ttu-id="af9a5-136">Esto abrirá una ventana que permite cargar contenido HTML.</span><span class="sxs-lookup"><span data-stu-id="af9a5-136">This will open a window that allows HTML content to be uploaded.</span></span> <span data-ttu-id="af9a5-137">También puede escribir el mensaje que se creó manualmente en el cuadro inferior izquierdo de la ventana.</span><span class="sxs-lookup"><span data-stu-id="af9a5-137">You can also type the message that’s created manually in the lower left box of the window.</span></span>  

> [!Note]
> <span data-ttu-id="af9a5-138">Se puede guardar un correo electrónico de Outlook con el cuerpo deseado de la comunicación en formato HTML.</span><span class="sxs-lookup"><span data-stu-id="af9a5-138">An Outlook email can be saved with the desired body of the communication in HTML format.</span></span> <span data-ttu-id="af9a5-139">Esto luego se puede cargar para implementar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="af9a5-139">This can then be uploaded to implement the template.</span></span> <br> <br> <span data-ttu-id="af9a5-140">Si se selecciona el tipo de acción de carta de cobro, no habrá una sección de detalles del documento comercial en el formulario de configuración.</span><span class="sxs-lookup"><span data-stu-id="af9a5-140">If the action type of collection letter is selected there will not be a business document detail section on the setup form.</span></span>


## <a name="fasttab-reference"></a><span data-ttu-id="af9a5-141">Referencia a la ficha desplegable</span><span class="sxs-lookup"><span data-stu-id="af9a5-141">FastTab reference</span></span>
<span data-ttu-id="af9a5-142">Las siguientes tablas enumeran las páginas y los campos desde los que se puede acceder a las fichas desplegables, junto con una descripción de la información en esa pestaña.</span><span class="sxs-lookup"><span data-stu-id="af9a5-142">The following tables list the pages and fields that the specified FastTabs can be accessed from, along with a description of the information in that tab.</span></span> 

### <a name="process-hierarchy"></a><span data-ttu-id="af9a5-143">Jerarquía de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-143">Process hierarchy</span></span>

|     <span data-ttu-id="af9a5-144">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-144">Page</span></span>                                                  |     <span data-ttu-id="af9a5-145">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-145">Field</span></span>                         |     <span data-ttu-id="af9a5-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-146">Description</span></span>                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     <span data-ttu-id="af9a5-147">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-147">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-148">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-148">Process automation</span></span>       |                                   |     <span data-ttu-id="af9a5-149">Cree y administre procesos de cobros basados en asignaciones de grupos de clientes.</span><span class="sxs-lookup"><span data-stu-id="af9a5-149">Create and   manage collections processes based on customer pool assignments.</span></span>                                                                                                                             |
|     <span data-ttu-id="af9a5-150">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-150">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-151">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-151">Process automation</span></span>       |     <span data-ttu-id="af9a5-152">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="af9a5-152">Hierarchy</span></span>                     |     <span data-ttu-id="af9a5-153">Define la prioridad de la automatización de procesos para asignar un cliente si pertenecen a varios grupos.</span><span class="sxs-lookup"><span data-stu-id="af9a5-153">Defines the   priority of process automation to assign a customer if they belong in multiple pools.</span></span>                                                                                                   |
|     <span data-ttu-id="af9a5-154">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-154">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-155">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-155">Process automation</span></span>       |     <span data-ttu-id="af9a5-156">Id. de grupo</span><span class="sxs-lookup"><span data-stu-id="af9a5-156">Pool ID</span></span>                       |     <span data-ttu-id="af9a5-157">Las consultas que definen un grupo de registros de clientes.</span><span class="sxs-lookup"><span data-stu-id="af9a5-157">Queries that   define a group of customer records.</span></span>                                                                                                                                                        |
|     <span data-ttu-id="af9a5-158">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-158">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-159">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-159">Process automation</span></span>       |     <span data-ttu-id="af9a5-160">Días tranquilos</span><span class="sxs-lookup"><span data-stu-id="af9a5-160">Quiet days</span></span>                    |     <span data-ttu-id="af9a5-161">Limite la frecuencia con que un paso de proceso puede completarse.</span><span class="sxs-lookup"><span data-stu-id="af9a5-161">Limit how frequently a process step can be completed.</span></span> <span data-ttu-id="af9a5-162">Por ejemplo, si se establecen dos días tranquilos, el siguiente paso del proceso no ocurrirá durante al menos dos días si cambia la factura principal.</span><span class="sxs-lookup"><span data-stu-id="af9a5-162">For example, if two quiet days are set the next process step will not   occur for at least two days if the leading invoice changes.</span></span>     |
|     <span data-ttu-id="af9a5-163">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-163">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-164">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-164">Process automation</span></span>       |     <span data-ttu-id="af9a5-165">Excluir del proceso</span><span class="sxs-lookup"><span data-stu-id="af9a5-165">Exclude from   Process</span></span>        |     <span data-ttu-id="af9a5-166">Seleccionando ya sea **Saldo antiguo del cliente menor que** o **Importe de la factura menor que** excluirá a un cliente de la automatización del proceso si no se cumplen los criterios del valor.</span><span class="sxs-lookup"><span data-stu-id="af9a5-166">Selecting either **Customer aging balance less than** or **Invoice amount less than** will exclude a customer from the process automation if the value criteria is not met.</span></span>                                   |

### <a name="process-details"></a><span data-ttu-id="af9a5-167">Detalles del proceso</span><span class="sxs-lookup"><span data-stu-id="af9a5-167">Process details</span></span>
|     <span data-ttu-id="af9a5-168">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-168">Page</span></span>                                                  |     <span data-ttu-id="af9a5-169">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-169">Field</span></span>                                         |      <span data-ttu-id="af9a5-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-170">Description</span></span>                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     <span data-ttu-id="af9a5-171">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-171">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-172">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-172">Process automation</span></span>       |                                                   |     <span data-ttu-id="af9a5-173">Defina los pasos emprendidos en función de la factura principal.</span><span class="sxs-lookup"><span data-stu-id="af9a5-173">Define the steps   taken based on the leading invoice.</span></span>                                                                                                |
|                                                           |     <span data-ttu-id="af9a5-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-174">Description</span></span>                                   |     <span data-ttu-id="af9a5-175">Campo de texto libre utilizado para proporcionar un nombre y/o una descripción del paso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-175">Free text   field used for providing a name and/or description of the step.</span></span>                                                                           |
|                                                           |     <span data-ttu-id="af9a5-176">Tipo de acción</span><span class="sxs-lookup"><span data-stu-id="af9a5-176">Action type</span></span>                                   |     <span data-ttu-id="af9a5-177">Actividad, correo electrónico o carta de cobro que se creará en el paso del proceso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-177">Activity,   email, or collection letter that will be created by the process step.</span></span>                                                                     |
|                                                           |     <span data-ttu-id="af9a5-178">Documento empresarial</span><span class="sxs-lookup"><span data-stu-id="af9a5-178">Business   document</span></span>                           |     <span data-ttu-id="af9a5-179">Define la actividad o plantilla de correo electrónico que se utiliza durante el paso del proceso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-179">Defines the   activity or email template that is used during the process step.</span></span>                                                                        |
|                                                           |     <span data-ttu-id="af9a5-180">Cuándo</span><span class="sxs-lookup"><span data-stu-id="af9a5-180">When</span></span>                                          |     <span data-ttu-id="af9a5-181">Define si el paso del proceso ocurrirá antes o después de la fecha de vencimiento de la factura principal junto con el campo **Días en relación con la fecha de vencimiento de la factura**.</span><span class="sxs-lookup"><span data-stu-id="af9a5-181">Defines if   the process step will occur before or after the leading invoice due date   along with the **Days in relation to invoice due date** field.</span></span>        |
|                                                           |     <span data-ttu-id="af9a5-182">Días en relación con la fecha de vencimiento de la factura</span><span class="sxs-lookup"><span data-stu-id="af9a5-182">Days in   relation to invoice due date</span></span>        |     <span data-ttu-id="af9a5-183">Junto con el campo **Cuándo** identifica el tiempo del paso del proceso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-183">Together   with the **When** field it identifies the timing of the process step.</span></span>                                                                          |
|                                                           |     <span data-ttu-id="af9a5-184">Destinatario</span><span class="sxs-lookup"><span data-stu-id="af9a5-184">Recipient</span></span>                                     |     <span data-ttu-id="af9a5-185">Identifica si se enviará un correo electrónico a un cliente, grupo de ventas o contacto del agente de cobros.</span><span class="sxs-lookup"><span data-stu-id="af9a5-185">Identifies   if an email will be sent to a Customer, Sales group, or Collections Agent contact.</span></span>                                                   |
|                                                           |     <span data-ttu-id="af9a5-186">Contacto para propósito comercial</span><span class="sxs-lookup"><span data-stu-id="af9a5-186">Business   purpose contact</span></span>                    |     <span data-ttu-id="af9a5-187">Determina qué dirección de correo electrónico del destinatario se utiliza en las comunicaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="af9a5-187">Determines   which recipient’s email address is used in email communications.</span></span>                                                                                 |

### <a name="business-process-activity-template-details"></a><span data-ttu-id="af9a5-188">Detalles de la plantilla de actividad de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="af9a5-188">Business process activity template details</span></span> 
|     <span data-ttu-id="af9a5-189">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-189">Page</span></span>                                                  |     <span data-ttu-id="af9a5-190">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-190">Field</span></span>                     |      <span data-ttu-id="af9a5-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-191">Description</span></span>                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     <span data-ttu-id="af9a5-192">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-192">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-193">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-193">Process automation</span></span>       |                               |     <span data-ttu-id="af9a5-194">Sección del proceso de configuración que identifica los detalles de la plantilla de actividad.</span><span class="sxs-lookup"><span data-stu-id="af9a5-194">Section of   the setup process that identifies the details of the activity template.</span></span>                                                                      |
|     <span data-ttu-id="af9a5-195">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-195">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-196">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-196">Process automation</span></span>       |     <span data-ttu-id="af9a5-197">Plantilla de actividades</span><span class="sxs-lookup"><span data-stu-id="af9a5-197">Activity   template</span></span>       |     <span data-ttu-id="af9a5-198">Identifica el tipo, el propósito, la cantidad de días para completar y proporciona detalles sobre la actividad que se creará durante un paso del proceso de actividad.</span><span class="sxs-lookup"><span data-stu-id="af9a5-198">Identifies   the type, purpose, number of days to complete, and provides details about the   activity that will be created during an activity process step.</span></span>       |

### <a name="business-document-email-template-details"></a><span data-ttu-id="af9a5-199">Detalles de plantilla de correo electrónico de documento empresarial</span><span class="sxs-lookup"><span data-stu-id="af9a5-199">Business document email template details</span></span> 
|     <span data-ttu-id="af9a5-200">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-200">Page</span></span>                                                  |     <span data-ttu-id="af9a5-201">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-201">Field</span></span>     |      <span data-ttu-id="af9a5-202">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-202">Description</span></span>                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     <span data-ttu-id="af9a5-203">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-203">Collections   process setup</span></span> <br> <span data-ttu-id="af9a5-204">Automatización de procesos</span><span class="sxs-lookup"><span data-stu-id="af9a5-204">Process automation</span></span>       |               |     <span data-ttu-id="af9a5-205">Identifica la descripción del correo electrónico, el idioma predeterminado, el nombre del remitente y la dirección de correo electrónico que se crearán durante un paso del proceso de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="af9a5-205">Identifies   the email description, default language, senders name, and email address that will be   created during an email process step.</span></span>        |


### <a name="collections-history"></a><span data-ttu-id="af9a5-206">Historial de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-206">Collections history</span></span> 
|     <span data-ttu-id="af9a5-207">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-207">Page</span></span>                              |     <span data-ttu-id="af9a5-208">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-208">Field</span></span>     |      <span data-ttu-id="af9a5-209">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-209">Description</span></span>                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     <span data-ttu-id="af9a5-210">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-210">Collections   process setup</span></span>       |               |     <span data-ttu-id="af9a5-211">Ver el historial reciente de la jerarquía de procesos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="af9a5-211">View the   recent history for the selected process hierarchy.</span></span>     |

### <a name="collection-process-assignment"></a><span data-ttu-id="af9a5-212">Asignación del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-212">Collection process assignment</span></span>
|     <span data-ttu-id="af9a5-213">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-213">Page</span></span>                              |     <span data-ttu-id="af9a5-214">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-214">Field</span></span>     |      <span data-ttu-id="af9a5-215">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-215">Description</span></span>                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     <span data-ttu-id="af9a5-216">Configuración del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-216">Collections   process setup</span></span>       |               |     <span data-ttu-id="af9a5-217">Vea los clientes asignados a un proceso de cobros.</span><span class="sxs-lookup"><span data-stu-id="af9a5-217">View   customers assigned to a collections process.</span></span>  
|     <span data-ttu-id="af9a5-218">Asignación manual</span><span class="sxs-lookup"><span data-stu-id="af9a5-218">Manual assignment</span></span>               |               |     <span data-ttu-id="af9a5-219">Vea los clientes que se han asignado manualmente a un proceso o seleccione los clientes para asignarlos a un proceso.</span><span class="sxs-lookup"><span data-stu-id="af9a5-219">View customers that have been manually assigned to a process or select customers to be assigned to a process.</span></span> |
|     <span data-ttu-id="af9a5-220">Vista previa de la asignación del proceso</span><span class="sxs-lookup"><span data-stu-id="af9a5-220">Preview process assignment</span></span>      |               |     <span data-ttu-id="af9a5-221">Obtenga una vista previa de los clientes que se asignarán a una estrategia cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="af9a5-221">Preview the customers that will be assigned to a strategy when it is run.</span></span>   |
|     <span data-ttu-id="af9a5-222">Obtener vista previa de asignación de clientes</span><span class="sxs-lookup"><span data-stu-id="af9a5-222">Preview customer assignment</span></span>     |               |     <span data-ttu-id="af9a5-223">Vea la estrategia que se le asigna a un cliente específico.</span><span class="sxs-lookup"><span data-stu-id="af9a5-223">View the strategy that a specific customer is assigned.</span></span>    |
 
### <a name="parameters"></a><span data-ttu-id="af9a5-224">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af9a5-224">Parameters</span></span>
|     <span data-ttu-id="af9a5-225">Página</span><span class="sxs-lookup"><span data-stu-id="af9a5-225">Page</span></span>                                                                  |     <span data-ttu-id="af9a5-226">Campo</span><span class="sxs-lookup"><span data-stu-id="af9a5-226">Field</span></span>                                             |      <span data-ttu-id="af9a5-227">Descripción</span><span class="sxs-lookup"><span data-stu-id="af9a5-227">Description</span></span>                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     <span data-ttu-id="af9a5-228">Parámetros de clientes > Automatización del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-228">Accounts   receivable parameters > Collections process automation</span></span>     |     <span data-ttu-id="af9a5-229">Porcentaje de clientes por tarea por lotes</span><span class="sxs-lookup"><span data-stu-id="af9a5-229">Percentage   of customers per batch task</span></span>          |     <span data-ttu-id="af9a5-230">Configuración para determinar el número de tareas por lotes por proceso de automatización.</span><span class="sxs-lookup"><span data-stu-id="af9a5-230">Setting to   determine the number of batch tasks per automation process.</span></span>                                          |
|     <span data-ttu-id="af9a5-231">Parámetros de clientes > Automatización del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-231">Accounts   receivable parameters > Collections process automation</span></span>     |     <span data-ttu-id="af9a5-232">Registrar cartas de cobro automáticamente</span><span class="sxs-lookup"><span data-stu-id="af9a5-232">Post   Collection letters automatically</span></span>           |     <span data-ttu-id="af9a5-233">Los tipos de acciones de cartas de cobro publicarán la carta durante la automatización.</span><span class="sxs-lookup"><span data-stu-id="af9a5-233">Collection   letter action types will post the letter during the automation.</span></span>                                      |
|     <span data-ttu-id="af9a5-234">Parámetros de clientes > Automatización del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-234">Accounts   receivable parameters > Collections process automation</span></span>     |     <span data-ttu-id="af9a5-235">Crear actividades para la automatización</span><span class="sxs-lookup"><span data-stu-id="af9a5-235">Create   activities for automation</span></span>                |     <span data-ttu-id="af9a5-236">Cree y cierre actividades para tipos de acciones que no sean actividades para ver todos los pasos automatizados realizados en una cuenta.</span><span class="sxs-lookup"><span data-stu-id="af9a5-236">Create and   close activities for non-activity action types to view all automated steps   taken on an account.</span></span>        |
|     <span data-ttu-id="af9a5-237">Parámetros de clientes > Automatización del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-237">Accounts   receivable parameters > Collections process automation</span></span>     |     <span data-ttu-id="af9a5-238">Días para mantener la automatización del proceso de cobros</span><span class="sxs-lookup"><span data-stu-id="af9a5-238">Days to keep   collections process automation</span></span>     |     <span data-ttu-id="af9a5-239">Define el número de días que se almacena el historial de colecciones.</span><span class="sxs-lookup"><span data-stu-id="af9a5-239">Defines the   number of days collections history is stored.</span></span>                                                       |