---
title: Definir directivas de gastos
description: Puede definir las directivas de gastos que los trabajadores deben seguir al insertar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a><span data-ttu-id="d33f6-103">Directivas de gastos</span><span class="sxs-lookup"><span data-stu-id="d33f6-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d33f6-104">Puede definir políticas que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje.</span><span class="sxs-lookup"><span data-stu-id="d33f6-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="d33f6-105">Implantar políticas de gastos puede ayudarle a gestionar los gastos de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="d33f6-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="d33f6-106">Por ejemplo, puede configurar una directiva que indique que para los gastos en hoteles de Nueva York, el gasto de hotel por noche no puede superar los 250 USD.</span><span class="sxs-lookup"><span data-stu-id="d33f6-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="d33f6-107">Si un empleado envía un informe de gastos o una solicitud de viaje en el cual la tarifa de la habitación supera este importe, el sistema notificará al usuario que ha superado el importe de gastos de la directiva.</span><span class="sxs-lookup"><span data-stu-id="d33f6-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="d33f6-108">Puede configurar el mensaje que recibirá el trabajador al definir la directiva.</span><span class="sxs-lookup"><span data-stu-id="d33f6-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="d33f6-109">Puede definir tres tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="d33f6-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="d33f6-110">Advertencia: permite que el trabajador envíe un informe de gastos o un pedido de viaje, pero el gasto se marcará para todos los aprobadores y para la creación de informes</span><span class="sxs-lookup"><span data-stu-id="d33f6-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="d33f6-111">más adelante.</span><span class="sxs-lookup"><span data-stu-id="d33f6-111">for later reporting.</span></span> 
 - <span data-ttu-id="d33f6-112">Error: requiere que el trabajador revise el gasto para cumplir con la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="d33f6-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="d33f6-113">Justificación: requiere que el trabajador o un director especifique una justificación para exceder el importe de la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="d33f6-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="d33f6-114">También puede configurar un intervalo de fechas para el que estarán vigentes las directivas de gastos.</span><span class="sxs-lookup"><span data-stu-id="d33f6-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="d33f6-115">Por ejemplo, las tarifas aéreas entre Dinamarca y Nueva York pueden resultar caras durante la época de vacaciones.</span><span class="sxs-lookup"><span data-stu-id="d33f6-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="d33f6-116">Puede definir una regla de gastos de vuelos que restrinja el coste de los vuelos a la ciudad de Nueva York a un límite de 5000 DKK y especificar que esta regla estará en vigencia desde el 15 de marzo hasta el 15 de septiembre.</span><span class="sxs-lookup"><span data-stu-id="d33f6-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 

