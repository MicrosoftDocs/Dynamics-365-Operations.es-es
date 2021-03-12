---
title: Cambiar modo de entrega en PDV
description: En este tema se describe cómo configurar y usar el modo de cambio de la operación de entrega en PDV.
author: hhainesms
manager: annbe
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 6bfe27a7b4a768da00c67e307a0bd7e57b333d11
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965436"
---
# <a name="change-mode-of-delivery-in-pos"></a><span data-ttu-id="dd6bf-103">Cambiar modo de entrega en PDV</span><span class="sxs-lookup"><span data-stu-id="dd6bf-103">Change mode of delivery in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dd6bf-104">En este tema se describe cómo configurar y utilizar la funcionalidad "cambiar modo de entrega" en su entorno de punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="dd6bf-104">This topic describes how to set up and use the "change mode of delivery" functionality in your point of sale (POS) environment.</span></span> 

<span data-ttu-id="dd6bf-105">En Dynamics 365 Commerce versión 10.0.10 y posteriores está disponible la operación **Cambiar modo de entrega** (647) y puede agregarla a sus diseños de pantalla de PDV.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-105">In Dynamics 365 Commerce versions 10.0.10 and later, the **Change mode of delivery** operation (647) is available to add to your POS screen layouts.</span></span>

<span data-ttu-id="dd6bf-106">La característica de cambio de modo de entrega le ofrece la opción de cambiar el modo de entrega de una o más líneas de venta configuradas para el envío en la transacción de PDV.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-106">The change mode of delivery feature provides you with the option to change the mode of delivery for one or more shipment-configured sales lines on the POS transaction.</span></span> <span data-ttu-id="dd6bf-107">En versiones anteriores de Commerce, tenía que pasar por los flujos de configuración **Enviar todo** o **Enviar selección** completos si quería cambiar el modo de entrega en una línea existente que estaba configurada para el envío.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-107">In previous versions of Commerce, you had to go through the full **Ship all** or **Ship selected** configuration flows if you wanted to change the mode of delivery on an existing line that was configured for shipment.</span></span> <span data-ttu-id="dd6bf-108">Este proceso requería mucho tiempo y podía provocar cambios accidentales en el origen de la entrega o las fechas de entrega para la línea.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-108">This process was time consuming and could result in accidental changes to the delivery origin or delivery dates for the line.</span></span> <span data-ttu-id="dd6bf-109">La nueva funcionalidad proporciona un método alternativo para actualizar de forma eficiente el modo de entrega en estas líneas de venta.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-109">The new functionality provides an alternative method for efficiently updating the mode of delivery on these sales lines.</span></span>

<span data-ttu-id="dd6bf-110">Para obtener más información sobre cómo agregar una operación a un botón en la cuadrícula de botones de PDV, consulte [Diseños de pantalla para el punto de venta](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).</span><span class="sxs-lookup"><span data-stu-id="dd6bf-110">For more information about how to add an operation to a button on your POS button grid, see [Screen layouts for the point of sale](https://docs.microsoft.com/dynamics365/commerce/pos-screen-layouts).</span></span>

<span data-ttu-id="dd6bf-111">Una vez configurada esta función en PDV, al seleccionar **Cambiar modo de entrega**, se le presentará una página de lista en la que podrá elegir las líneas de la transacción para las que desea cambiar el modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-111">After this feature is configured in POS, when you select **Change mode of delivery**, you will be presented with a list page that allows you to choose the lines of the transaction that you want to change the mode of delivery for.</span></span> <span data-ttu-id="dd6bf-112">Puede elegir algunas de las líneas o todas ellas, o salir sin realizar ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-112">You can choose some or all of the lines, or exit without making any changes.</span></span> <span data-ttu-id="dd6bf-113">Las líneas de ventas que se configuraron previamente para el envío son las únicas líneas que puede cambiar de la lista.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-113">The sales lines that were previously configured for shipment are the only lines in the list that you can change.</span></span> <span data-ttu-id="dd6bf-114">Si desea cambiar una línea designada para recogida o reparto para envío, debe usar las operaciones **Enviar todo** o **Enviar selección**.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-114">If you want to change a line designated for pickup or carryout to ship, you must use the **Ship all** or **Ship selected** operations.</span></span> <span data-ttu-id="dd6bf-115">Y a la inversa, si desea cambiar una línea designada como un envío para recogida o reparto, debe usar las operaciones **Recoger todo**, **Recoger selección**, **Repartir todo** o **Repartir selección**.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-115">Conversely, if you want to change a line designated as a shipment to a pickup or carryout, you must use the  **Pickup all**, **Pickup selected**, **Carryout all**, or **Carryout selected** operations.</span></span>

<span data-ttu-id="dd6bf-116">Después de seleccionar las líneas que desea cambiar, haga clic en **Cambiar modo de entrega** para que se le pida que seleccione las opciones del modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-116">After you select the lines that you want to change, click **Change mode of delivery** to be prompted to select the delivery mode options.</span></span> <span data-ttu-id="dd6bf-117">Si seleccionó varias líneas para cambiar, el PDV solo mostrará los modos de entrega que se hayan configurado como permitidos para todos los productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-117">If you selected multiple lines to change, POS will only display modes of delivery that have been configured as allowable for all of the selected products.</span></span> <span data-ttu-id="dd6bf-118">Los modos de entrega se pueden configurar para admitir productos y direcciones de entrega específicos.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-118">Modes of delivery can be configured to support specific products and delivery addresses.</span></span> <span data-ttu-id="dd6bf-119">Si hay un modo de entrega que es aceptable para una combinación de producto y dirección pero no es aceptable para otra combinación seleccionada de producto y dirección, el modo de entrega no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-119">If there is a mode of delivery that is acceptable for one product and address combination but is not acceptable for another selected product and address combination, the mode of delivery is not available.</span></span> <span data-ttu-id="dd6bf-120">Es posible que deba seleccionar las líneas una por una y cambiar el modo de entrega para cada línea por separado si desea seleccionar un modo de entrega para un producto que no sea compatible con otro producto.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-120">You may need to select lines one by one and change the mode of delivery for each line separately if you want to select a mode of delivery for one product that is not supported by another product.</span></span>  

<span data-ttu-id="dd6bf-121">Cuando haya seleccionado el nuevo modo de entrega, se mostrará la página de transacción.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-121">After you select the new mode of delivery, the transaction page is displayed.</span></span> <span data-ttu-id="dd6bf-122">Para revisar sus nuevas selecciones de modo de entrega, seleccione la pestaña **Entrega** en la lista de transacciones.</span><span class="sxs-lookup"><span data-stu-id="dd6bf-122">To review your new delivery mode selections, select the **Delivery** tab on the transaction list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd6bf-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dd6bf-123">Additional resources</span></span>

[<span data-ttu-id="dd6bf-124">Crear pedidos de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="dd6bf-124">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="dd6bf-125">Personalizar correos electrónicos transaccionales por modo de entrega</span><span class="sxs-lookup"><span data-stu-id="dd6bf-125">Customize transactional emails by mode of delivery</span></span>](customize-email-delivery-mode.md)
