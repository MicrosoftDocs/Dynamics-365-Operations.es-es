---
title: Ventanas de plazo
description: Puede usar ventanas de plazo para optimizar la programación de líneas de pedido de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d79e3d3756b8dc402d6f293437209b2e108be38e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437013"
---
# <a name="time-windows"></a><span data-ttu-id="73fa5-103">Ventanas de plazo</span><span class="sxs-lookup"><span data-stu-id="73fa5-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73fa5-104">Puede usar ventanas de plazo para optimizar la programación de líneas de pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="73fa5-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="73fa5-105">Puede configurar el sistema de modo que cree automáticamente pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="73fa5-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="73fa5-106">De acuerdo con los criterios especificados por una ventana de plazo, puede conectar tantas líneas de pedido de servicio como sean posibles con la menor cantidad de pedidos de servicio como sea posible.</span><span class="sxs-lookup"><span data-stu-id="73fa5-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="73fa5-107">Las ventanas de plazo definen el tiempo que se puede alejar una línea de pedido de servcio de su fecha calculada.</span><span class="sxs-lookup"><span data-stu-id="73fa5-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="73fa5-108">La fecha calculada es la fecha en la que debía realizarse la línea de pedido de servicio de acuerdo con la programación.</span><span class="sxs-lookup"><span data-stu-id="73fa5-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="73fa5-109">La fecha se basa en la configuración del intervalo y del período de servicio que definió en la página **Crear pedidos de servicio** .</span><span class="sxs-lookup"><span data-stu-id="73fa5-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="73fa5-110">Para definir una ventana de plazo mediante los valores de la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="73fa5-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="73fa5-111">Método</span><span class="sxs-lookup"><span data-stu-id="73fa5-111">Method</span></span> | <span data-ttu-id="73fa5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="73fa5-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="73fa5-113">Semana</span><span class="sxs-lookup"><span data-stu-id="73fa5-113">Week</span></span>   | <span data-ttu-id="73fa5-114">La fecha a la que se puede trasladar la línea de pedido de servicio puede ser cualquier día de la misma semana que la fecha calculada inicial.</span><span class="sxs-lookup"><span data-stu-id="73fa5-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="73fa5-115">Mes</span><span class="sxs-lookup"><span data-stu-id="73fa5-115">Month</span></span>  | <span data-ttu-id="73fa5-116">La fecha a la que se puede trasladar la línea de pedido de servicio puede ser cualquier día abierto del mismo mes que la fecha calculada inicial.</span><span class="sxs-lookup"><span data-stu-id="73fa5-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="73fa5-117">Por ejemplo, la fecha calculada para una línea de pedido de servicio es el 15 de febrero de 2017.</span><span class="sxs-lookup"><span data-stu-id="73fa5-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="73fa5-118">La línea de pedido de servicio se puede programar para cualquier día de la semana entre el 1 de febrero y el 28 de febrero de 2017.</span><span class="sxs-lookup"><span data-stu-id="73fa5-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="73fa5-119">Manual</span><span class="sxs-lookup"><span data-stu-id="73fa5-119">Manual</span></span> | <span data-ttu-id="73fa5-120">Puede definir el número máximo de días anteriores o posteriores a la fecha inicial calculada que se puede trasladar la línea de pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="73fa5-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="73fa5-121">Si no se especifica ninguna ventana de plazo para una línea de acuerdo de servicio, la línea de pedido de servicio derivada del acuerdo de servicio se debe ejecutar en la fecha exacta para la que se programó originalmente.</span><span class="sxs-lookup"><span data-stu-id="73fa5-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="73fa5-122">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="73fa5-122">Related topics</span></span>

[<span data-ttu-id="73fa5-123">Crear ventanas de plazo</span><span class="sxs-lookup"><span data-stu-id="73fa5-123">Create time windows</span></span>](create-time-windows.md)

