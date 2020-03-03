---
title: Configurar y trabajar con retenciones de pedidos del centro de llamadas
description: En este tema se describe cómo ejecutar retenciones de pedidos con Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 08c0eda418af1aa56c6cc71ca1f7f10460651bc9
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023908"
---
# <a name="configure-and-work-with-call-center-order-holds"></a><span data-ttu-id="ea3b2-103">Configurar y trabajar con retenciones de pedidos del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="ea3b2-103">Configure and work with call center order holds</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ea3b2-104">Este tema describe las características de retención del pedido que Dynamics 365 Commerce tiene para los pedidos de centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-104">This topic describes the order hold features that Dynamics 365 Commerce has for call center orders.</span></span>

## <a name="configuring-call-center-order-holds"></a><span data-ttu-id="ea3b2-105">Configuración de las retenciones de pedidos del centro de asistencia telefónica</span><span class="sxs-lookup"><span data-stu-id="ea3b2-105">Configuring call center order holds</span></span>

<span data-ttu-id="ea3b2-106">Para usar las características de retención de pedido del centro de asistencia telefónica, primero debe definir códigos de retención.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-106">To use the call center order hold features, you must first define hold codes.</span></span> <span data-ttu-id="ea3b2-107">Para crear un conjunto de códigos de retención definido por el usuario, basado en sus requisitos empresariales, vaya **Ventas y marketing** \> **Configuración** \> **Pedidos de ventas** \> **Códigos de bloqueo del pedido**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-107">To create a set of user-defined hold codes, based on your business requirements, go to **Sales and marketing** \> **Setup** \> **Sales orders** \> **Order hold codes**.</span></span> <span data-ttu-id="ea3b2-108">Puede indicar opcionalmente uno de los códigos de bloqueo como código de retención predeterminado configurando la opción **Valor predeterminado del pedido de ventas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-108">You can optionally flag one of the hold codes as the default hold code by setting the **Default for sales order** option to **Yes** for it.</span></span> <span data-ttu-id="ea3b2-109">Esto código de retención se usará en cualquier momento en que un pedido de ventas se ponga en espera.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-109">This hold code will be used any time that a sales order is put on hold.</span></span> <span data-ttu-id="ea3b2-110">Si un pedido de ventas ha reservado inventario, y las reservas se deben quitar automáticamente si el pedido está en espera por un motivo determinado, establezca la opción **Quitar las reservas de inventario** en **Sí** de los códigos de motivo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-110">If a sales order has reserved inventory, and the reservations must be automatically removed if the order is put on hold for a particular reason, set the **Remove inventory reservations** option to **Yes** for the reason codes.</span></span>

<span data-ttu-id="ea3b2-111">Para especificar el tipo de nota que se capturará cuando los usuarios que ponen un pedido de ventas en espera especifiquen notas opcionales, vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes** y, a continuación, en la ficha desplegable **Configurar ventas**, en la pestaña **General**, establezca el campo **Tipo de nota**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-111">To specify the type of note that will be captured when users who put a sales order on hold enter optional notes, go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**, and then, on the **Sales setup** FastTab, on the **General** tab, set the **Note type** field.</span></span> <span data-ttu-id="ea3b2-112">Use el campo **Estado del pedido de ventas retenido** para definir el color que se usará para resaltar los pedidos de ventas que están en espera cuando se vean en la página **Servicio al cliente**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-112">Use the **On Hold sales order status** field to define the color that will be used to highlight sales orders that are on hold when they are viewed on the **Customer service** page.</span></span>

<span data-ttu-id="ea3b2-113">Para crear un conjunto opcional de códigos de motivo de espera, vaya a **Retail y Commerce** \> **Configuración del canal** \> **Códigos de información**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-113">To create an optional set of hold reason codes, go to **Retail and Commerce** \> **Channel setup** \> **Info codes**.</span></span> <span data-ttu-id="ea3b2-114">Estos códigos de información se pueden usar como código de motivo secundario para refinar el código de bloqueo principal.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-114">These info codes can be used as a secondary reason code to further define the main hold code.</span></span> <span data-ttu-id="ea3b2-115">Seleccione **Nuevo** para crear un conjunto de códigos de motivos, y después seleccione **Subcódigos** para definir la lista de motivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-115">Select **New** to create a reason code set, and then select **Subcodes** to define the list of additional reasons.</span></span> <span data-ttu-id="ea3b2-116">Para vincular los códigos de información que defina al canal de centro de asistencia telefónica, vaya **Retail y Commerce** \> **Canales** \> **Centros de asistencia telefónica** \> **Todos los centros de asistencia telefónica**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-116">To link any info codes that you define to the call center channel, go to **Retail and Commerce** \> **Channels** \> **Call centers** \> **All call centers**.</span></span> <span data-ttu-id="ea3b2-117">En la ficha desplegable **General**, establezca el campo **Código de bloqueo**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-117">On the **General** FastTab, set the **Hold code** field.</span></span>

## <a name="putting-orders-on-hold"></a><span data-ttu-id="ea3b2-118">Retener pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="ea3b2-118">Putting orders on hold</span></span>

<span data-ttu-id="ea3b2-119">Los pedidos que los usuarios del centro de asistencia telefónica crean en el programa de Commerce de back-office pueden retenerse manual o automáticamente en situaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-119">Orders that call center users create in the back-office Commerce program can be manually put on hold manually or automatically in specific situations.</span></span>

<span data-ttu-id="ea3b2-120">Durante la entrada de pedidos, pero antes de enviar y confirmar pedidos, los usuarios del centro de asistencia telefónica podrían desear poner un pedido en espera para evitar que se entregue al almacén para continuar el proceso.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-120">During order entry, but before order submission and confirmation, call center users might want to manually put an order on hold to prevent it from being released to the warehouse for further processing.</span></span> <span data-ttu-id="ea3b2-121">Por ejemplo, puede que el cliente que realiza el pedido no esté listo para confirmarlo o puede que falten datos críticos para procesar el pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-121">For example, the customer who is placing the order might not be ready to commit to it, or critical data that is required in order to process the order might be missing.</span></span>

<span data-ttu-id="ea3b2-122">En la página entrada de pedidos, el usuario del centro de asistencia telefónica puede poner un pedido en espera mediante la opción **Bloqueos del pedido** en la pestaña **Pedido de ventas** del menú de entrada de pedidos.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-122">On the order entry page, the call center user can put an order on hold by using the **Order holds** option on the **Sales order** tab of the order entry menu.</span></span> <span data-ttu-id="ea3b2-123">De manera alternativa, el usuario puede seleccionar el elemento de menú **Bloqueo** en la página **Resumen de pedido de ventas** que aparece al seleccionar **Completado** en un pedido de ventas del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-123">Alternatively, the user can select the **Hold** menu item on the **Sales order summary** page that appears when he or she selects **Complete** on a call center sales order.</span></span>

<span data-ttu-id="ea3b2-124">En ambos casos, la página **Bloqueos del pedido** aparece.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-124">In both cases, the **Order holds** page appears.</span></span> <span data-ttu-id="ea3b2-125">El usuario puede entonces seleccionar **Nuevo** para crear un bloqueo para el pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-125">The user can then select **New** to create a hold for the order.</span></span> <span data-ttu-id="ea3b2-126">En el campo **Código de bloqueo**, el usuario debe seleccionar el código que mejor describe el motivo del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-126">In the **Hold code** field, the user should select the code that best describes the reason for the hold.</span></span> <span data-ttu-id="ea3b2-127">En el campo **Código de motivo**, el usuario puede seleccionar opcionalmente un código adicional para proporcionar un segundo nivel de descripción de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-127">In the **Reason code** field, the user can optionally select an additional code to provide a second level of description of the hold.</span></span>

<span data-ttu-id="ea3b2-128">En la ficha desplegable **Notas**, en el campo **Notas de bloqueo**, el usuario puede especificar notas adicionales, de texto libre, para proporcionar contexto adicional o información acerca del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-128">On the **Notes** FastTab, in the **Hold Notes** field, the user can enter additional, free-form notes to provide additional context or information about the hold.</span></span> <span data-ttu-id="ea3b2-129">Estas notas pueden ayudar a otros usuarios que revisen el pedido bloqueado o trabajen con él más adelante.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-129">These notes can help other users who review or work with the hold order later.</span></span>

<span data-ttu-id="ea3b2-130">Una vez especificada y guardada la información de bloqueo, el usuario puede cerrar la página **Bloqueos del pedido**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-130">After the hold information is entered and saved, the user can close the **Order holds** page.</span></span> <span data-ttu-id="ea3b2-131">A continuación se devuelve al usuario a la página de entrada de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-131">The user is then returned to the sales order entry page.</span></span> <span data-ttu-id="ea3b2-132">Si no se requieren ninguna otra acción en el pedido de ventas, el usuario puede cerrar la página de entrada de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-132">If no further actions are required on the sales order, the user can close the sales order entry page.</span></span>

<span data-ttu-id="ea3b2-133">Si el indicador **Habilitar finalización de pedidos** está activado en el canal del centro de asistencia telefónica, el pago no tiene que aplicarse a un pedido que se haya puesto en espera.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-133">If the **Enable order completion** flag is turned on in the call center channel, payment doesn't have to applied to an order that is put on hold.</span></span> <span data-ttu-id="ea3b2-134">Por el contrario, para un pedido de ventas que no esté en espera, el usuario no puede salir de la página de entrada de pedidos de ventas hasta que no se haya aplicado el pago.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-134">By contrast, for a sales order that isn't put on hold, users can't leave the sales order entry page until payment is applied.</span></span> <span data-ttu-id="ea3b2-135">Por supuesto, se exigirá el pago antes de liberar el bloqueo del pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-135">Of course, payment will be required before the order hold is released.</span></span>

<span data-ttu-id="ea3b2-136">Además, los usuarios del centro de asistencia telefónica pueden colocar un bloqueo manual de fraudes en los pedidos que sean sospechosos por algún motivo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-136">Additionally, call center users can put a manual fraud hold on orders that are suspicious for some reason.</span></span> <span data-ttu-id="ea3b2-137">Los pedidos también pueden ponerse en espera automáticamente cuando coincidan con los criterios y las reglas de fraude activos.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-137">Orders can also be put on hold automatically when they match active fraud criteria and rules.</span></span> <span data-ttu-id="ea3b2-138">Para obtener más información acerca de este tipo de bloqueo de pedido, consulte [Configurar alertas de fraude](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).</span><span class="sxs-lookup"><span data-stu-id="ea3b2-138">For more information on about this type of order hold, see [Set up fraud alerts](https://docs.microsoft.com/dynamics365/unified-operations/retail/set-up-fraud-alerts).</span></span>

## <a name="viewing-and-managing-orders-that-are-on-hold"></a><span data-ttu-id="ea3b2-139">Visualización y gestión de los pedidos que están en espera</span><span class="sxs-lookup"><span data-stu-id="ea3b2-139">Viewing and managing orders that are on hold</span></span>

### <a name="viewing-hold-information-for-a-single-sales-order"></a><span data-ttu-id="ea3b2-140">Ver información en espera de un único pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="ea3b2-140">Viewing hold information for a single sales order</span></span>

<span data-ttu-id="ea3b2-141">En la página **Servicio al cliente**, los usuarios pueden visualmente identificar los pedidos que están en espera, dado que las líneas de pedido se destacan de un color específico.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-141">On the **Customer service** page, users can visually identify orders that are on hold, because the order lines are highlighted in a specific color.</span></span> <span data-ttu-id="ea3b2-142">Este color se define en el campo **Estado del pedido de ventas retenido** en la página **Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-142">This color is defined by the **On Hold sales order status** field on the **Accounts receivable parameters** page.</span></span>

> [!NOTE]
> <span data-ttu-id="ea3b2-143">Si la línea está seleccionada en la página, el color de resalte no está visible.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-143">If the line is selected on the page, the highlight color isn't visible.</span></span>

<span data-ttu-id="ea3b2-144">Los usuarios también pueden ver la información detallada de estado de un pedido de ventas para saber si el pedido está en espera.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-144">Users can also view detailed status information for a sales order to learn whether the order is on hold.</span></span> <span data-ttu-id="ea3b2-145">La información del estado detallada se puede acceder desde la página **Todos los pedidos de ventas** o **Servicio al cliente**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-145">The detailed status information can be accessed from the **All sales orders** or **Customer service** page.</span></span> <span data-ttu-id="ea3b2-146">Si un pedido está en espera, el indicador **No procesar** se establece para él, y el campo **Estado detallado** muestra el estado **en espera** o **Bloqueo de fraudes**, en función de la situación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-146">If an order is on hold, the **Do not process** flag is set for it, and the **Detailed status** field shows a status of either **On Hold** or **Fraud Hold**, depending on the scenario.</span></span>

<span data-ttu-id="ea3b2-147">Para ver los detalles de un bloqueo de pedido individual, los usuarios pueden abrir una vista detallada de la página **Bloqueo del pedido** de la página **Servicio al cliente**, mediante el menú **Opciones** del pedido seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-147">To view the details of an individual order hold, users can open a detailed view of the **Order hold** page from the **Customer service** page, by using the **Options** menu for the selected order.</span></span> <span data-ttu-id="ea3b2-148">Los usuarios también pueden acceder a esta vista desde la página **Todo el pedido de ventas**, seleccionando el elemento de menú **Bloqueos del pedido** en la pestaña **pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-148">Users can also access this view from the **All sales order** page, by selecting the **Order holds** menu item on the **Sales order** tab.</span></span>

### <a name="viewing-all-orders-that-are-on-hold"></a><span data-ttu-id="ea3b2-149">Visualización de todos los pedidos que están en espera</span><span class="sxs-lookup"><span data-stu-id="ea3b2-149">Viewing all orders that are on hold</span></span>

<span data-ttu-id="ea3b2-150">Para ver todos los pedidos que se han colocado en bloqueo manual o automático, vaya a **Retail y Commerce** \> **Clientes** \> **Bloqueos del pedido**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-150">To view all orders that have been put on manual or automatic hold, go to **Retail and Commerce** \> **Customers** \> **Order holds**.</span></span>

<span data-ttu-id="ea3b2-151">El banco de trabajo **bloqueos de pedido** proporciona una lista de todos los pedidos que están en espera debido a acciones de retención manuales o relacionadas con fraude.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-151">The **Order holds** workbench provides a list view of all orders that are on hold because of manual or fraud-related hold actions.</span></span> <span data-ttu-id="ea3b2-152">Aprovechándose de las opciones de filtrado y de ordenación estándar de la página, los usuarios pueden crear vistas con las que pueden trabajar o gestionar códigos de bloqueo específicos cuya revisión esté bajo su responsabilidad.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-152">By taking advantage of the standard filtering and sorting options on the page, users can create views that let them work with or manage specific hold codes that they are responsible for reviewing.</span></span> <span data-ttu-id="ea3b2-153">El banco de trabajo **Bloqueos de pedido** también indica el número de días que el pedido ha estado en espera.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-153">The **Order holds** workbench also indicates the number of days that an order has been on hold.</span></span> <span data-ttu-id="ea3b2-154">Esta información puede ayudar a los usuarios a dar prioridad a la cola.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-154">This information can help users prioritize the queue.</span></span>

<span data-ttu-id="ea3b2-155">Para obtener una visión más detallada de los pedidos que están en espera, los usuarios pueden hacer clic en la opción **Bloqueo del pedido** del menú.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-155">To get a more detailed view of the orders that are on hold, users can click the **Order hold** option on the menu.</span></span> <span data-ttu-id="ea3b2-156">Esta información que proporciona información sobre el cliente, todas las notas que se han aplicado al pedido, el cliente o a la acción de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-156">This view providing information about the customer, any notes that have been applied to the order, customer, or hold action.</span></span> <span data-ttu-id="ea3b2-157">La vista también proporciona detalles sobre el motivo de un bloqueo automático, si el pedido se puso en espera porque coincidió con una regla de fraude.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-157">The view also provides details about the reason for an automatic hold, if the order was put on hold because it matched a fraud rule.</span></span>

<span data-ttu-id="ea3b2-158">En la vista de la lista y la vista detallada de la página **Bloqueos del pedido**, los usuarios pueden ver o editar información adicional relacionada con el pedido, como los pagos, los totales, y las notas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-158">From both the list view and the detailed view of the **Order holds** page, users can view or edit additional order-related information, such as payments, totals, and notes.</span></span>

<span data-ttu-id="ea3b2-159">Las opciones de la pestaña **Retener finalización de la compra** pueden ser útiles si varios usuarios de su empresa trabajan en la cola de bloqueo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-159">The options on the **Hold checkout** tab might be useful if multiple users in your company work on the hold queue at the same time.</span></span> <span data-ttu-id="ea3b2-160">Si selecciona la opción **Desproteger**, los usuarios pueden indicar que trabajan para revisar y para investigar el bloqueo del pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-160">By selecting the **Check out** option, users can indicate that they are working to review and investigate the order hold.</span></span> <span data-ttu-id="ea3b2-161">De esta manera, otros usuarios no perderán el tiempo intentando hacer el mismo trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-161">In this way, other users don't waste time by trying to do the same work.</span></span> <span data-ttu-id="ea3b2-162">En la vista detallada de la página **Bloqueos del pedido**, los usuarios pueden ver información sobre la fecha y la hora de desprotección, y el usuario que desprotegió el registro de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-162">From the detailed view of the **Order holds** page, users can view information about the checkout date and time, and the user who checked out the hold record.</span></span>

<span data-ttu-id="ea3b2-163">Después de que se desproteja un registro de bloqueo, solo el usuario que lo desprotegió puede borrar el desbloqueo.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-163">After a hold record is checked out, only the user who checked it out can clear the checkout.</span></span> <span data-ttu-id="ea3b2-164">Esta restricción se ha creado para evitar que los usuarios tomen los registros donde otros usuarios ya están trabajando.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-164">This restriction is intended to prevent users from taking records that other users are already working on.</span></span> <span data-ttu-id="ea3b2-165">Para liberar un pedido de nuevo a la cola para que otros usuarios puedan trabajar con él, el usuario que desprotegió el registro selecciona la opción **Liberar desprotección**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-165">To release an order back to the queue so that other users can work on it, the user who checked out the record selects the **Clear checkout** option.</span></span>

> [!NOTE]
> <span data-ttu-id="ea3b2-166">El bloqueo no se libera cuando se libera la desprotección.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-166">The hold isn't released when the checkout is cleared.</span></span>

<span data-ttu-id="ea3b2-167">En algunos casos, como cuando un usuario está enfermo o ha dejado de trabajar para la empresa, es posible que los registros que dicho usuario ha desprotegido deban reasignarse a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-167">In some situations, such as when a user is out sick or has left the company, records that are checked out to that user might have to be reassigned to another user.</span></span> <span data-ttu-id="ea3b2-168">Un administrador puede reasignar los registros mediante la opción **Anular finalización de la compra**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-168">A manager can reassign records by using the **Override checkout** option.</span></span>

## <a name="releasing-orders-that-are-on-hold"></a><span data-ttu-id="ea3b2-169">Liberar pedidos que están en espera</span><span class="sxs-lookup"><span data-stu-id="ea3b2-169">Releasing orders that are on hold</span></span>

<span data-ttu-id="ea3b2-170">En la vista de la lista y la vista detallada de la página **Bloqueos del pedido**, la pestaña **Liberar retención** contiene las opciones que se usan para liberar un bloqueo del pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-170">In both the list view and the detailed view of the **Order holds** page, the **Clear hold** tab contains the options that are used to release an order hold.</span></span> <span data-ttu-id="ea3b2-171">Utilice la opción **Liberar retención** para liberar un pedido del código de bloqueo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-171">Use the **Clear holds** option to release an order from the selected hold code.</span></span>

<span data-ttu-id="ea3b2-172">Los pedidos de centro de asistencia telefónica requieren un pago.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-172">Call center orders require payment.</span></span> <span data-ttu-id="ea3b2-173">Por lo tanto, un bloqueo no se puede liberar completamente si el pago no se ha aplicado al pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-173">Therefore, a hold can't be fully cleared if payment hasn't been applied to the order.</span></span> <span data-ttu-id="ea3b2-174">En la página **Parámetros de centro de asistencia telefónica**, en la pestaña **Bloqueos**, asegúrese de que el parámetro **Enviar cuando se libere** esté activada.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-174">On the **Call center parameters** page, on the **Holds** tab, make sure that the **Submit when cleared** parameter is turned on.</span></span> <span data-ttu-id="ea3b2-175">Este valor ayuda a garantizar que un pedido de bloqueo liberado siga la lógica de envío del pedido correcta para validar y autorizar pagos.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-175">This setting helps guarantee that a cleared hold order goes through the correct order submission logic to validate and authorize payments.</span></span> <span data-ttu-id="ea3b2-176">Si faltan pagos, el usuario recibe un error, y el código de bloqueo no se libera.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-176">If payments are missing, the user receives an error, and the hold code isn't cleared.</span></span>

<span data-ttu-id="ea3b2-177">Si el parámetro **Enviar cuando se libere** no se ha establecido, los usuarios deben seleccionar la opción **Liberar y enviar** en el menú **Liberar bloqueo** para ayudar a garantizar que el pedido pase todas las validaciones necesarias de pago.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-177">If the **Submit when cleared** parameter hasn't been set, users should select the **Clear and submit** option on the **Clear hold** menu to help guarantee that the order goes through all the required payment validations.</span></span> <span data-ttu-id="ea3b2-178">Si el envío del pedido falla cuando el indicador **Habilitar finalización de pedidos** está activado en el canal de centro de asistencia telefónica, el pedido se libera de su estado de bloqueo, pero de los indicadores **No procesar** seguirán establecidos.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-178">If order submission fails when the **Enable order completion** flag is turned on in the call center channel, the order is released from its hold status, but the **Do not process** flag remains set.</span></span> <span data-ttu-id="ea3b2-179">Por lo tanto, el pedido no se libera al almacén hasta que se hayan aplicado y se hayan validado los pagos correctos.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-179">Therefore, the order isn't released to the warehouse until correct payments have been applied and validated.</span></span>

<span data-ttu-id="ea3b2-180">Si los usuarios desean liberar un bloqueo pero realizar cambios adicionales al pedido antes de que este se haya liberado para continuar el proceso, pueden seleccionar la opción **Liberar y modificar**.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-180">If users want to clear a hold but make additional changes to the order before it's released for further processing, they can select the **Clear and modify** option.</span></span> <span data-ttu-id="ea3b2-181">Esta opción permite quitar el bloqueo codificado y abre los detalles del pedido de ventas de modo que los usuarios puedan realizar cambios adicionales al pedido.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-181">This option removes the hold code and opens the sales order details so that users can make additional changes to the order.</span></span> <span data-ttu-id="ea3b2-182">Los usuarios también pueden aplicar el pago y enviar el pedido de ventas con la lógica de validación del pago cuando el indicador **Habilitar finalización de pedidos** está activada en el canal del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-182">Users can also apply payment and submit the sales order through payment validation logic when the **Enable order completion** flag is turned on in the call center channel.</span></span>

## <a name="reporting-options"></a><span data-ttu-id="ea3b2-183">Opciones del informe</span><span class="sxs-lookup"><span data-stu-id="ea3b2-183">Reporting options</span></span>

<span data-ttu-id="ea3b2-184">Vaya a **Retail y Commerce** \> **Consultas e informes** \> **Informes de centro de asistencia telefónica** \> **Informe de bloqueos del pedido** para ejecutar un informe acerca de los bloqueos del pedido por intervalo de fechas, código de espera, u otros criterios relacionados.</span><span class="sxs-lookup"><span data-stu-id="ea3b2-184">Go to **Retail and Commerce** \> **Inquiries and reports** \> **Call center reports** \> **Order holds report** to run a report about order holds by date range, hold code, or other related criteria.</span></span>