---
title: Definir directivas de gastos
description: Se pueden definir directivas de gastos que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 Finance.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389724"
---
# <a name="define-expense-policies"></a><span data-ttu-id="dccf0-103">Definir directivas de gastos</span><span class="sxs-lookup"><span data-stu-id="dccf0-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dccf0-104">Puede definir directivas que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje.</span><span class="sxs-lookup"><span data-stu-id="dccf0-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="dccf0-105">Implantar directivas de gastos puede ayudarle a gestionar los gastos de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="dccf0-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="dccf0-106">Por ejemplo, puede configurar una directiva que indique que para los gastos en hoteles de Nueva York, el gasto de hotel por noche no puede superar los 250 USD.</span><span class="sxs-lookup"><span data-stu-id="dccf0-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="dccf0-107">Si un trabajador envía un informe de gastos o un pedido de viaje en los que el precio de la habitación supera este importe, el sistema notificará al</span><span class="sxs-lookup"><span data-stu-id="dccf0-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="dccf0-108">trabajador que se ha superado el importe de gastos de la directiva.</span><span class="sxs-lookup"><span data-stu-id="dccf0-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="dccf0-109">Puede configurar el mensaje que recibirá el trabajador al</span><span class="sxs-lookup"><span data-stu-id="dccf0-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="dccf0-110">definir la directiva.</span><span class="sxs-lookup"><span data-stu-id="dccf0-110">define the policy.</span></span>      
        
<span data-ttu-id="dccf0-111">Puede definir tres tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="dccf0-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="dccf0-112">Advertencia: permite que el trabajador envíe un informe de gastos o un pedido de viaje, pero el gasto se marcará para todos los aprobadores y para la creación de informes</span><span class="sxs-lookup"><span data-stu-id="dccf0-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="dccf0-113">más adelante.</span><span class="sxs-lookup"><span data-stu-id="dccf0-113">for later reporting.</span></span>        

- <span data-ttu-id="dccf0-114">Error: requiere que el trabajador revise el gasto para cumplir con la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="dccf0-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="dccf0-115">Justificación: requiere que el trabajador o un director especifique una justificación para exceder el importe de la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="dccf0-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="dccf0-116">Consejos de directiva</span><span class="sxs-lookup"><span data-stu-id="dccf0-116">Policy tips</span></span>
<span data-ttu-id="dccf0-117">Aquí hay algunas sugerencias que pueden ayudarle al crear nuevas directivas para la gestión de gastos.</span><span class="sxs-lookup"><span data-stu-id="dccf0-117">Here are a few suggestions that can assist you when creating new policies for expense management.</span></span> 
* <span data-ttu-id="dccf0-118">Las directivas son entran en vigor por fecha y no surtirán efecto si la directiva se crea con una fecha posterior a la fecha que el gasto produjo.</span><span class="sxs-lookup"><span data-stu-id="dccf0-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="dccf0-119">Por ejemplo, si crea una nueva directiva hoy para aplicar un gasto máximo de comida de 50 €, ningún gasto existente especificado ayer no será comprobado con esta directiva.</span><span class="sxs-lookup"><span data-stu-id="dccf0-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="dccf0-120">Al crear una directiva para una categoría de gastos que se pueda detallar, considere agregar una condición para el tipo de línea de gastos.</span><span class="sxs-lookup"><span data-stu-id="dccf0-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="dccf0-121">Algunas directivas como requerir un recibo puede que no tengan sentido para las líneas detalladas y se deben aplicar únicamente a la línea de encabezado o línea no detallada.</span><span class="sxs-lookup"><span data-stu-id="dccf0-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 
* <span data-ttu-id="dccf0-122">Las directivas de gestión de gastos se evalúan contra la entidad de origen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dccf0-122">Expense management policies are evaluated against the source entity by default.</span></span> <span data-ttu-id="dccf0-123">Para escenarios de empresas vinculadas, puede configurar la directiva para que, en lugar de ello, se evalúe en función de la entidad de destino (entidad prestataria).</span><span class="sxs-lookup"><span data-stu-id="dccf0-123">For intercompany scenarios, you can set the policy to be evaluated against the destination entity (borrowing entity) instead.</span></span> <span data-ttu-id="dccf0-124">Para ejecutar las directivas contra la entidad de destino, active la función "Evaluar directiva de gastos contra entidad jurídica prestataria" en el espacio de trabajo **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="dccf0-124">To run the policies against the destination entity, turn on the "Evaluate Expense policy against borrowing legal entity" feature in the **Feature Management** workspace.</span></span>

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="dccf0-125">Cuándo evaluar directivas</span><span class="sxs-lookup"><span data-stu-id="dccf0-125">When to evaluate policies</span></span>

<span data-ttu-id="dccf0-126">En parámetros de gestión de gastos, hay una opción para evaluar cualquier directiva de gestión de gastos cuando se guarda una línea o cuando se envía un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="dccf0-126">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="dccf0-127">Si elige evaluar cuando se guarda una línea, esto garantiza que los usuarios tengan visibilidad anterior en lo que necesitan hacer para completar su informe de gastos de una vez.</span><span class="sxs-lookup"><span data-stu-id="dccf0-127">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="dccf0-128">Si no, se puede retrasar la evaluación de la directiva y ahorrar tiempo si hace que la validación aparezca al final, durante el envío al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dccf0-128">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
