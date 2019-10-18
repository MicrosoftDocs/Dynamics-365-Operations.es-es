---
title: Definir directivas de gastos
description: Se pueden definir políticas de gastos que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 Finance.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
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
ms.openlocfilehash: 7d3b4a8f6cf74bb1fe7e53a4dfdd607f604e16e3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187461"
---
# <a name="define-expense-policies"></a><span data-ttu-id="eafba-103">Definir directivas de gastos</span><span class="sxs-lookup"><span data-stu-id="eafba-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eafba-104">Puede definir políticas que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje.</span><span class="sxs-lookup"><span data-stu-id="eafba-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="eafba-105">Implantar políticas de gastos puede ayudarle a gestionar los gastos de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="eafba-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="eafba-106">Por ejemplo, puede configurar una directiva que indique que para los gastos en hoteles de Nueva York, el gasto de hotel por noche no puede superar los 250 USD.</span><span class="sxs-lookup"><span data-stu-id="eafba-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="eafba-107">Si un trabajador envía un informe de gastos o un pedido de viaje en los que el precio de la habitación supera este importe, el sistema notificará al</span><span class="sxs-lookup"><span data-stu-id="eafba-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="eafba-108">trabajador que se ha superado el importe de gastos de la política.</span><span class="sxs-lookup"><span data-stu-id="eafba-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="eafba-109">Puede configurar el mensaje que recibirá el trabajador al</span><span class="sxs-lookup"><span data-stu-id="eafba-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="eafba-110">definir la directiva.</span><span class="sxs-lookup"><span data-stu-id="eafba-110">define the policy.</span></span>      
        
<span data-ttu-id="eafba-111">Puede definir tres tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="eafba-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="eafba-112">Advertencia: permite que el trabajador envíe un informe de gastos o un pedido de viaje, pero el gasto se marcará para todos los aprobadores y para la creación de informes</span><span class="sxs-lookup"><span data-stu-id="eafba-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="eafba-113">más adelante.</span><span class="sxs-lookup"><span data-stu-id="eafba-113">for later reporting.</span></span>        

- <span data-ttu-id="eafba-114">Error: requiere que el trabajador revise el gasto para cumplir con la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="eafba-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="eafba-115">Justificación: requiere que el trabajador o un director especifique una justificación para exceder el importe de la directiva antes de enviar el informe de gastos o el pedido de viaje.</span><span class="sxs-lookup"><span data-stu-id="eafba-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="eafba-116">Consejos de directiva</span><span class="sxs-lookup"><span data-stu-id="eafba-116">Policy tips</span></span>
<span data-ttu-id="eafba-117">Aquí hay algunas sugerencias que pueden ayudarle cuando cree nuevas directivas para la gestión de gastos.</span><span class="sxs-lookup"><span data-stu-id="eafba-117">Here are a few suggestions that can assist you whe creating new policies for expense management.</span></span> 
* <span data-ttu-id="eafba-118">Las directivas son entran en vigor por fecha y no surtirán efecto si la directiva se crea con una fecha posterior a la fecha que el gasto produjo.</span><span class="sxs-lookup"><span data-stu-id="eafba-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="eafba-119">Por ejemplo, si crea una nueva directiva hoy para aplicar un gasto máximo de comida de 50 €, ningún gasto existente especificado ayer no será comprobado con esta directiva.</span><span class="sxs-lookup"><span data-stu-id="eafba-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="eafba-120">Al crear una directiva para una categoría de gastos que se pueda detallar, considere agregar una condición para el tipo de línea de gastos.</span><span class="sxs-lookup"><span data-stu-id="eafba-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="eafba-121">Algunas directivas como requerir un recibo puede que no tengan sentido para las líneas detalladas y se deben aplicar únicamente a la línea de encabezado o línea no detallada.</span><span class="sxs-lookup"><span data-stu-id="eafba-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="eafba-122">Cuándo evaluar directivas</span><span class="sxs-lookup"><span data-stu-id="eafba-122">When to evaluate policies</span></span>

<span data-ttu-id="eafba-123">En parámetros de gestión de gastos, hay una opción para evaluar cualquier directiva de gestión de gastos cuando se guarda una línea o cuando se envía un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="eafba-123">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="eafba-124">Si elige evaluar cuando se guarda una línea, esto garantiza que los usuarios tengan visibilidad anterior en lo que necesitan hacer para completar su informe de gastos de una vez.</span><span class="sxs-lookup"><span data-stu-id="eafba-124">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="eafba-125">Si no, se puede retrasar la evaluación de la directiva y ahorrar tiempo si hace que la validación aparezca al final, durante el envío al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eafba-125">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
