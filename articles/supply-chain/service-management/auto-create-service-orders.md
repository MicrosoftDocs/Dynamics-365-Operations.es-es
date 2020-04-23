---
title: Crear pedidos de servicio automáticamente
description: Puede crear pedidos de servicio a partir de un acuerdo de servicio para el período válido del acuerdo de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33de4746b8011f4e7fc0ce2929c967870eeebae9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203029"
---
# <a name="automatically-create-service-orders"></a><span data-ttu-id="0542f-103">Crear pedidos de servicio automáticamente</span><span class="sxs-lookup"><span data-stu-id="0542f-103">Automatically create service orders</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="0542f-104">Puede crear pedidos de servicio a partir de un acuerdo de servicio para el período válido del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-104">You can generate service orders that are based on a service agreement for the valid period of the service agreement.</span></span>

<span data-ttu-id="0542f-105">Los pedidos de servicio que se crean a partir de un acuerdo de servicio están vinculados al acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-105">The service orders that you generate from a service agreement are all attached to the service agreement.</span></span>

<span data-ttu-id="0542f-106">Los pedidos de servicio se crean automáticamente con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="0542f-106">Service orders are generated automatically from the following settings:</span></span>

  - <span data-ttu-id="0542f-107">La configuración del intervalo del acuerdo de servicio que se especifica en las líneas del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-107">The service agreement interval that is set up in the service agreement lines.</span></span> <span data-ttu-id="0542f-108">El intervalo del acuerdo de servicio indica la frecuencia con la que se crean las líneas del pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-108">The service agreement interval indicates the frequency that service-order lines are created.</span></span> <span data-ttu-id="0542f-109">Para obtener más información, consulte [Intervalos de servicio](service-intervals.md).</span><span class="sxs-lookup"><span data-stu-id="0542f-109">For more information, see [Service intervals](service-intervals.md).</span></span>

  - <span data-ttu-id="0542f-110">El período que se especifica cuando se define el período de servicio en los campos **Fecha inicial** y **Fecha final** del formulario **Crear pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="0542f-110">The period that you specify to define the service period in the **From date** and **To date** fields in the **Create service orders** form.</span></span> <span data-ttu-id="0542f-111">Para obtener más información, vea [Crear pedidos de servicio automáticamente](create-service-orders-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="0542f-111">For more information, see [Create service orders automatically](create-service-orders-automatically.md).</span></span>

  - <span data-ttu-id="0542f-112">La opción **Combinar pedidos de servicio** en la cabecera del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-112">The **Combine service orders** option on the service agreement header.</span></span> <span data-ttu-id="0542f-113">Esta opción define si las líneas del pedido de servicio generadas a partir de un acuerdo de servicio combinan pedidos de servicio en función del empleado, tarea de servicio, objeto de servicio o acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-113">This option defines whether service order lines generated from a service agreement, combines service orders according to employee, service task, service object, or service agreement.</span></span> <span data-ttu-id="0542f-114">Para obtener más información, consulte [Combinar pedidos de servicio](combine-service-orders.md).</span><span class="sxs-lookup"><span data-stu-id="0542f-114">For more information, see [Combine service orders](combine-service-orders.md).</span></span>

  - <span data-ttu-id="0542f-115">La opción **Ventana de tiempo** de la línea del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-115">The **Time window** option on the service agreement line.</span></span> <span data-ttu-id="0542f-116">La ventana de tiempo define la distancia hasta la que puede moverse la línea de pedido de servicio en relación con la fecha calculada.</span><span class="sxs-lookup"><span data-stu-id="0542f-116">The time window defines how far a service order line can move with regard to its calculated date.</span></span> <span data-ttu-id="0542f-117">Para obtener más información, consulte [Ventanas de plazo](time-windows.md).</span><span class="sxs-lookup"><span data-stu-id="0542f-117">For more information, see [Time windows](time-windows.md).</span></span>


> [!NOTE]
> <P><span data-ttu-id="0542f-118">Si el día especificado para el pedido de servicio no está abierto en el calendario seleccionado en el formulario <STRONG>Parámetros de gestión de servicio</STRONG>, recibirá un mensaje advirtiéndole que existe un conflicto de calendario.</span><span class="sxs-lookup"><span data-stu-id="0542f-118">If the day that is specified for a service order is not open in the calendar that you have selected in the <STRONG>Service management parameters</STRONG> form, a message will indicate that there is a calendar conflict.</span></span> <span data-ttu-id="0542f-119">Puede ignorar el mensaje; el pedido de servicio se creará, aunque el día esté cerrado en el calendario.</span><span class="sxs-lookup"><span data-stu-id="0542f-119">You can safely ignore the message; the service order will be created, even though the day is closed on the calendar.</span></span></P>

## <a name="example-1"></a><span data-ttu-id="0542f-120">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0542f-120">Example 1</span></span>

<span data-ttu-id="0542f-121">El acuerdo de servicio cubre el período del 1 de enero del 2012 hasta el 31 de diciembre del 2012.</span><span class="sxs-lookup"><span data-stu-id="0542f-121">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="0542f-122">Si el período de servicio especificado en el formulario **Crear pedidos de servicio** cubre el período del 1 de noviembre del 2012 al 1 de febrero del 2013, se crearán pedidos de servicio para el período del 1 de noviembre del 2012 al 31 de diciembre del 2012.</span><span class="sxs-lookup"><span data-stu-id="0542f-122">If the service period that you specify in the **Create service orders** form is from November 1, 2012 until February 1, 2013, service orders are created from November 1, 2012 until December 31, 2012.</span></span>

## <a name="example-2"></a><span data-ttu-id="0542f-123">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="0542f-123">Example 2</span></span>

<span data-ttu-id="0542f-124">El acuerdo de servicio cubre el período del 1 de enero del 2012 hasta el 31 de diciembre del 2012.</span><span class="sxs-lookup"><span data-stu-id="0542f-124">The service agreement lasts from January 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="0542f-125">Hay dos líneas del acuerdo de servicio vinculadas al acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-125">Two service agreement lines are attached to the service agreement.</span></span> <span data-ttu-id="0542f-126">La primera línea del acuerdo de servicio incluye la fecha de inicio del 2 de enero del 2012 y la fecha final del 1 de marzo del 2012.</span><span class="sxs-lookup"><span data-stu-id="0542f-126">The first service agreement line has a starting date on January 2, 2012 and an ending date on March 1, 2012.</span></span> <span data-ttu-id="0542f-127">La segunda línea del acuerdo de servicio incluye la fecha de inicio del 1 de abril del 2012 y la fecha final del 31 de diciembre del 2012.</span><span class="sxs-lookup"><span data-stu-id="0542f-127">The second service agreement line has a starting date on April 1, 2012 and an ending date on December 31, 2012.</span></span> <span data-ttu-id="0542f-128">En el formulario **Crear pedidos de servicio**, especifica un período que cubre del 1 de octubre del 2012 al 31 de diciembre del 2012.</span><span class="sxs-lookup"><span data-stu-id="0542f-128">You specify a period in the **Create service orders** form that is from October 1, 2012 until December 31, 2012.</span></span> <span data-ttu-id="0542f-129">Por lo tanto, sólo se crearán pedidos de servicio para la segunda línea del acuerdo de servicio, ya que la fecha inicial y la fecha final de la primera línea del acuerdo de servicio es anterior al período especificado para el pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="0542f-129">Therefore, service orders are generated only for the second agreement line, because the starting date and ending date of the first agreement line are before the period that you specified for the service order.</span></span>

  


