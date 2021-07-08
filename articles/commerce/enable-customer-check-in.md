---
title: Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)
description: Este tema describe cómo habilitar las notificaciones de registro de clientes en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271434"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="162cb-103">Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)</span><span class="sxs-lookup"><span data-stu-id="162cb-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="162cb-104">Este tema describe cómo habilitar las notificaciones de registro de clientes en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="162cb-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="162cb-105">En sus correos electrónicos de "pedido listo para recoger", las organizaciones pueden proporcionar un enlace o botón que permita a los clientes notificar a la tienda que están en las instalaciones y esperando que les traigan su paquete.</span><span class="sxs-lookup"><span data-stu-id="162cb-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="162cb-106">Luego, los clientes reciben una confirmación de registro y la tienda recibe una notificación como una tarea en su aplicación de PDV.</span><span class="sxs-lookup"><span data-stu-id="162cb-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="162cb-107">Esta tarea sirve como aviso para que un asociado de ventas entregue el pedido en el vehículo del cliente.</span><span class="sxs-lookup"><span data-stu-id="162cb-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="162cb-108">Por tanto, el cliente no tiene que entrar en la tienda.</span><span class="sxs-lookup"><span data-stu-id="162cb-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="162cb-109">El flujo de trabajo de registro del cliente también se puede configurar para recopilar información adicional de los clientes, como su número de plaza de estacionamiento, la marca, el modelo y el color de su vehículo, e instrucciones de entrega.</span><span class="sxs-lookup"><span data-stu-id="162cb-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="162cb-110">El encargado de la tienda minorista puede utilizar esta información para facilitar la cumplimentación de los pedidos.</span><span class="sxs-lookup"><span data-stu-id="162cb-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="162cb-111">Habilitar el registro de los clientes</span><span class="sxs-lookup"><span data-stu-id="162cb-111">Enable customer check-in</span></span>

<span data-ttu-id="162cb-112">Cuando la función de registro de cliente está activada, Commerce genera un id. de confirmación de pedido (también conocido como id. de referencia del canal).</span><span class="sxs-lookup"><span data-stu-id="162cb-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="162cb-113">También genera los id. de confirmación de pedido para pedidos que se crean a través de canales de punto de venta (PDV) o de centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="162cb-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="162cb-114">Para activar la característica de registro de cliente en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="162cb-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="162cb-115">Vaya a **Espacios de trabajo \> Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="162cb-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="162cb-116">Busque la característica **Generar un formato de id. de referencia de canal coherente en todos los canales**.</span><span class="sxs-lookup"><span data-stu-id="162cb-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="162cb-117">Seleccione la característica y, a continuación, **Habilitar ahora** en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="162cb-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="162cb-118">Crear una página de confirmación de registro</span><span class="sxs-lookup"><span data-stu-id="162cb-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="162cb-119">En su sitio de comercio electrónico, debe crear una nueva página que servirá como experiencia de confirmación del registro.</span><span class="sxs-lookup"><span data-stu-id="162cb-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="162cb-120">Mediante configuración adicional, la página también puede incluir un formulario que recopila información adicional de los clientes para facilitar el cumplimiento de los pedidos.</span><span class="sxs-lookup"><span data-stu-id="162cb-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="162cb-121">Para obtener información sobre cómo configurar la página y el módulo, consulte [Módulo de facturación de clientes](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="162cb-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="162cb-122">Configurar la plantilla de correo electrónico transaccional</span><span class="sxs-lookup"><span data-stu-id="162cb-122">Configure the transactional email template</span></span>

<span data-ttu-id="162cb-123">Debe agregar un enlace o botón **Estoy aquí** a la plantilla para el correo electrónico transaccional que los clientes reciben cuando su pedido está listo para ser recogido.</span><span class="sxs-lookup"><span data-stu-id="162cb-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="162cb-124">Los clientes utilizarán este enlace o botón para notificar a la tienda que han llegado a recoger su pedido.</span><span class="sxs-lookup"><span data-stu-id="162cb-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="162cb-125">Agregue el enlace o botón a la plantilla que está asignada al tipo de notificación **Embalaje completado** y el modo de entrega que está utilizando para a cumplimentación de pedidos en la acera.</span><span class="sxs-lookup"><span data-stu-id="162cb-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="162cb-126">En la plantilla, cree un enlace HTML o un botón que apunte a la URL de la página de confirmación de registro que creó.</span><span class="sxs-lookup"><span data-stu-id="162cb-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="162cb-127">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="162cb-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="162cb-128">Para obtener más información sobre cómo configurar plantillas de correo electrónico, consulte [Personalizar los correos electrónicos transaccionales por modo de entrega](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="162cb-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="162cb-129">Se crea una tarea de confirmación de registro en PDV</span><span class="sxs-lookup"><span data-stu-id="162cb-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="162cb-130">Después de que un cliente notifica a la tienda que está presente para la recogida, recibe una notificación de confirmación de registro y se crea una tarea en la lista de tareas en el PDV donde el cliente está recogiendo el pedido.</span><span class="sxs-lookup"><span data-stu-id="162cb-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="162cb-131">La tarea contiene toda la información del cliente y del pedido que se requiere para cumplimentar el pedido.</span><span class="sxs-lookup"><span data-stu-id="162cb-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="162cb-132">En la tarea, el campo de instrucciones muestra cualquier información que se recopiló del cliente a través del formulario de información adicional.</span><span class="sxs-lookup"><span data-stu-id="162cb-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="162cb-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="162cb-133">Additional resources</span></span>

[<span data-ttu-id="162cb-134">Módulo de registro para recogida</span><span class="sxs-lookup"><span data-stu-id="162cb-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)
