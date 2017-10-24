--- 
title: "Configurar códigos de disposiciones"
description: "Este procedimiento se centra en la configuración de un código de disposición que se puede utilizar en un dispositivo móvil para el proceso de recepción de pedidos de devolución."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c004543188656dfd53d7539717cd6e93d0b9f47a
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-dispositions-codes"></a><span data-ttu-id="90f18-103">Configurar códigos de disposiciones</span><span class="sxs-lookup"><span data-stu-id="90f18-103">Set up dispositions codes</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="90f18-104">Este procedimiento se centra en la configuración de un código de disposición que se puede utilizar en un dispositivo móvil para el proceso de recepción de pedidos de devolución.</span><span class="sxs-lookup"><span data-stu-id="90f18-104">This procedure focuses on the setup of a disposition code that can be used on a mobile device for the return order receiving process.</span></span> <span data-ttu-id="90f18-105">Los códigos de disposición son una recopilación de reglas que se pueden usar cuando se reciben artículos.</span><span class="sxs-lookup"><span data-stu-id="90f18-105">Disposition codes are a collection of rules that can be used when items are received.</span></span> <span data-ttu-id="90f18-106">Por ejemplo, cuando un usuario usa un dispositivo móvil para recibir artículos dañados, el usuario debe escanear un código de disposición para artículos dañados.</span><span class="sxs-lookup"><span data-stu-id="90f18-106">For example, when a work user uses a mobile device to receive items that were damaged, the user must scan a disposition code for damaged items.</span></span> <span data-ttu-id="90f18-107">El estado de inventario de las mercancías recibidas, la plantilla de trabajo y la directiva de la ubicación se pueden determinar a partir del código de disposición escaneado.</span><span class="sxs-lookup"><span data-stu-id="90f18-107">The inventory status of the goods received, the work template, and the location directive can be determined from the scanned disposition code.</span></span> <span data-ttu-id="90f18-108">Para el proceso de recepción de pedido de compra y el informe de pedido de producción como proceso finalizado, es opcional usar un código de disposición.</span><span class="sxs-lookup"><span data-stu-id="90f18-108">For the purchase order receiving process and the production order report as finished process, the use of a disposition code is optional.</span></span> <span data-ttu-id="90f18-109">Para el proceso de recepción de devolución de pedido de ventas, si los artículos se registran mediante un dispositivo móvil, el uso del código de disposición es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="90f18-109">For the sales order return receiving process, if the items are registered using a mobile device, the use of disposition code is mandatory.</span></span>  <span data-ttu-id="90f18-110">Este procedimiento se creó con los datos de demostración de la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="90f18-110">This guide was created using the demo data company USMF.</span></span> <span data-ttu-id="90f18-111">Este procedimiento va destinado al encargado de almacén.</span><span class="sxs-lookup"><span data-stu-id="90f18-111">This procedure is intended for the warehouse manager.</span></span> 

1. <span data-ttu-id="90f18-112">Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Códigos de disposición.</span><span class="sxs-lookup"><span data-stu-id="90f18-112">Go to Warehouse management > Setup > Mobile device > Disposition codes.</span></span>
2. <span data-ttu-id="90f18-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="90f18-113">Click New.</span></span>
    * <span data-ttu-id="90f18-114">Cree un nuevo código de disposición que usar para las devoluciones de los clientes.</span><span class="sxs-lookup"><span data-stu-id="90f18-114">Create a new disposition code to use for customer returns.</span></span>  
3. <span data-ttu-id="90f18-115">En el campo Código de disposición, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="90f18-115">In the Disposition code field, type a value.</span></span>
4. <span data-ttu-id="90f18-116">En el campo Estado de inventario, seleccione un estado de inventario donde haya un bloqueo de inventario.</span><span class="sxs-lookup"><span data-stu-id="90f18-116">In the Inventory status field, select an inventory status where there is inventory blocking.</span></span>
    * <span data-ttu-id="90f18-117">Si utiliza USMF, seleccione Bloqueo.</span><span class="sxs-lookup"><span data-stu-id="90f18-117">If you're using USMF, select 'Blocking'.</span></span> <span data-ttu-id="90f18-118">Puede agregar un estado de inventario al código de disposición para anular el estado predeterminado que muestran las líneas de pedido.</span><span class="sxs-lookup"><span data-stu-id="90f18-118">You can add an inventory status to the disposition code to override the default status that’s on the order lines.</span></span>  
5. <span data-ttu-id="90f18-119">En el campo Plantilla de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="90f18-119">In the Work template field, type a value.</span></span>
    * <span data-ttu-id="90f18-120">Opcional: seleccione un código de plantilla de trabajo asociado a un pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="90f18-120">Optional: Select a work template code that is associated with a return order.</span></span> <span data-ttu-id="90f18-121">Si no se proporciona ningún valor, la plantilla de trabajo se resolverá con las reglas estándar configuradas en su sistema.</span><span class="sxs-lookup"><span data-stu-id="90f18-121">If no value is provided, the work template will be resolved using the standard rules configured in your system.</span></span> <span data-ttu-id="90f18-122">La selección de una plantilla de trabajo limitará los procesos con los que se puede usar este código de disposición.</span><span class="sxs-lookup"><span data-stu-id="90f18-122">Selecting a work template will limit the processes this disposition code can be used with.</span></span> <span data-ttu-id="90f18-123">Por ejemplo, si un código de disposición tiene una plantilla de trabajo con un pedido de trabajo del tipo de pedido de compra, no puede usarse para registrar artículos devueltos por los clientes.</span><span class="sxs-lookup"><span data-stu-id="90f18-123">For example, if a disposition code has a work template with a work order of type purchase order, it can’t be used to register items that are returned by customers.</span></span>  
6. <span data-ttu-id="90f18-124">En el campo Código de disposición de devolución, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="90f18-124">In the Return disposition code field, type a value.</span></span>
    * <span data-ttu-id="90f18-125">El código de disposición de devolución determina el resto del proceso del pedido de devolución para los artículos registrados.</span><span class="sxs-lookup"><span data-stu-id="90f18-125">The return disposition code determines the remainder of the return order process for the items registered.</span></span> <span data-ttu-id="90f18-126">En este ejemplo, el cliente debe recibir una nota de abono.</span><span class="sxs-lookup"><span data-stu-id="90f18-126">In this example, the customer should receive a credit note.</span></span> <span data-ttu-id="90f18-127">Agregue un código de disposición de devoluciones que contenga una acción de crédito.</span><span class="sxs-lookup"><span data-stu-id="90f18-127">Add a returns disposition code that contains an action Credit.</span></span>  


