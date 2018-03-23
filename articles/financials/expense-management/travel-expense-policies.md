---
title: Definir directivas de gastos
description: Puede definir las directivas de gastos que los trabajadores deben seguir al insertar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: b52fe81015a324bde07f387b42b834b79dc7c2da
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2018

---

# <a name="expense-policies"></a><span data-ttu-id="29ad4-103">Directivas de gastos</span><span class="sxs-lookup"><span data-stu-id="29ad4-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="29ad4-104">Puede definir políticas que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje.</span><span class="sxs-lookup"><span data-stu-id="29ad4-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="29ad4-105">Implantar políticas de gastos puede ayudarle a gestionar los gastos de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="29ad4-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="29ad4-106">Por ejemplo, puede configurar una directiva que indique que para los gastos en hoteles de Nueva York, el gasto de hotel por noche no puede superar los 250 USD.</span><span class="sxs-lookup"><span data-stu-id="29ad4-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="29ad4-107">Si un trabajador envía un informe de gastos o un pedido de viaje en los que el precio de la habitación supera este importe, el sistema notificará al</span><span class="sxs-lookup"><span data-stu-id="29ad4-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="29ad4-108">trabajador que se ha superado el importe de gastos de la política.</span><span class="sxs-lookup"><span data-stu-id="29ad4-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="29ad4-109">Puede configurar el mensaje que recibirá el trabajador al</span><span class="sxs-lookup"><span data-stu-id="29ad4-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="29ad4-110">definir la directiva.</span><span class="sxs-lookup"><span data-stu-id="29ad4-110">define the policy.</span></span>      
        
<span data-ttu-id="29ad4-111">Puede definir tres tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="29ad4-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="29ad4-112">Advertencia: permite que el trabajador envíe un informe de gastos o un pedido de viaje, pero el gasto se marcará para todos los aprobadores y para la creación de informes</span><span class="sxs-lookup"><span data-stu-id="29ad4-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
<span data-ttu-id="29ad4-113">más adelante.</span><span class="sxs-lookup"><span data-stu-id="29ad4-113">for later reporting.</span></span>        

- <span data-ttu-id="29ad4-114">Error: requiere que el trabajador revise el gasto para cumplir con la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="29ad4-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="29ad4-115">Justificación: requiere que el trabajador o un director especifique una justificación para exceder el importe de la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="29ad4-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        
 
 <span data-ttu-id="29ad4-116">También puede configurar un intervalo de fechas para el que estarán vigentes las directivas de gastos.</span><span class="sxs-lookup"><span data-stu-id="29ad4-116">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="29ad4-117">Por ejemplo, las tarifas aéreas entre Dinamarca</span><span class="sxs-lookup"><span data-stu-id="29ad4-117">For example, airline fares for flights between Denmark</span></span>      
 <span data-ttu-id="29ad4-118">y Nueva York pueden resultar caras durante la época de vacaciones.</span><span class="sxs-lookup"><span data-stu-id="29ad4-118">and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="29ad4-119">Puede definir una regla de gastos que restrinja el</span><span class="sxs-lookup"><span data-stu-id="29ad4-119">You can define a flight expense rule that restricts the</span></span>      
 <span data-ttu-id="29ad4-120">coste de los vuelos a Nueva York a un límite de 5000 DKK y especificar que esta regla estará en vigor del 15 de marzo</span><span class="sxs-lookup"><span data-stu-id="29ad4-120">cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and</span></span>      
 <span data-ttu-id="29ad4-121">al 15 de septiembre.</span><span class="sxs-lookup"><span data-stu-id="29ad4-121">September 15.</span></span>

