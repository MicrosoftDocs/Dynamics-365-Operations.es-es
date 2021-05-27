---
title: El rendimiento del cálculo de impuestos afecta las transacciones
description: Este tema proporciona información de resolución de problemas relacionada con el rendimiento del cálculo de impuestos y su efecto en las transacciones.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6fce4e2cb8c5507769533a875e23ccc4531abf51
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020148"
---
# <a name="tax-calculation-performance-affects-transactions"></a><span data-ttu-id="77941-103">El rendimiento del cálculo de impuestos afecta las transacciones</span><span class="sxs-lookup"><span data-stu-id="77941-103">Tax calculation performance affects transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="77941-104">A veces, una transacción se ve afectada por problemas de rendimiento que tiene el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-104">Sometimes, a transaction is affected by performance issues that tax calculation is having.</span></span> <span data-ttu-id="77941-105">Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="77941-105">To troubleshoot this issue, follow the steps in the following sections as required.</span></span>

## <a name="review-the-transaction-line-count"></a><span data-ttu-id="77941-106">Revisar la cuenta de líneas de la transacción</span><span class="sxs-lookup"><span data-stu-id="77941-106">Review the transaction line count</span></span>

<span data-ttu-id="77941-107">Determine si la transacción tiene una gran cantidad de líneas (por ejemplo, más de varios cientos).</span><span class="sxs-lookup"><span data-stu-id="77941-107">Determine whether the transaction has a large number of lines (for example, more than several hundred).</span></span> <span data-ttu-id="77941-108">Si no es así, pase a la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="77941-108">If it doesn't, move on to the next section.</span></span> <span data-ttu-id="77941-109">Si la transacción tiene varios cientos de líneas, retrase el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-109">If the transaction does have several hundred lines, delay the tax calculation.</span></span> <span data-ttu-id="77941-110">Para más información, vea [Habilitar el cálculo de impuestos diferido en diarios](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="77941-110">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span> 

<span data-ttu-id="77941-111">A continuación, puede determinar si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="77941-111">Next, you can determine whether any of the following conditions are met:</span></span>

- <span data-ttu-id="77941-112">Hay transacciones de importación de archivos grandes.</span><span class="sxs-lookup"><span data-stu-id="77941-112">There are import transactions from large files.</span></span>
- <span data-ttu-id="77941-113">Varias sesiones procesan el mismo cálculo de impuestos sobre transacciones al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="77941-113">Multiple sessions process the same transaction tax calculation at the same time.</span></span>
- <span data-ttu-id="77941-114">La transacción tiene varias líneas y las vistas se actualizan en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="77941-114">The transaction has multiple lines, and the views are updated in real time.</span></span> <span data-ttu-id="77941-115">Por ejemplo, el campo **Importe del impuesto calculado** en la página **Diario general** se actualiza en tiempo real cuando se cambian los campos de una línea.</span><span class="sxs-lookup"><span data-stu-id="77941-115">For example, the **Calculated sales tax amount** field on the **General journal** page is updated in real time when a line's fields are changed.</span></span>

   <span data-ttu-id="77941-116">[![Campo de importe de impuesto calculado en la página de asientos de diario](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span><span class="sxs-lookup"><span data-stu-id="77941-116">[![Calculated sales tax amount field on the Jounal voucher page](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)</span></span>

<span data-ttu-id="77941-117">Si se cumple alguna de estas condiciones, retrase el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-117">If any of these conditions are met, delay the tax calculation.</span></span>

## <a name="review-the-call-stack"></a><span data-ttu-id="77941-118">Revisar la pila de llamadas</span><span class="sxs-lookup"><span data-stu-id="77941-118">Review the call stack</span></span>

<span data-ttu-id="77941-119">Revise la pila de llamadas para determinar si se llama varias veces al cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-119">Review the call stack to determine whether tax calculation is called multiple times.</span></span> <span data-ttu-id="77941-120">Si no es así, pase a la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="77941-120">If it isn't, move on to the next section.</span></span> <span data-ttu-id="77941-121">Si se llama a la pila de llamadas varias veces, siga estos pasos para ayudar a reducir los tiempos de cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-121">If the call stack is called multiple times, follow these steps to help reduce the tax calculation times.</span></span>

1. <span data-ttu-id="77941-122">Si el diario ha considerado la transacción, retrase el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-122">If the journal has considered the transaction, delay the tax calculation.</span></span> <span data-ttu-id="77941-123">Para más información, vea [Habilitar el cálculo de impuestos diferido en diarios](enable-delayed-tax-calculation.md).</span><span class="sxs-lookup"><span data-stu-id="77941-123">For more information, see [Enable delayed tax calculation on journals](enable-delayed-tax-calculation.md).</span></span>
2. <span data-ttu-id="77941-124">Si la transacción es una orden de compra y la versión de la aplicación es posterior a 10.0.15, puede retrasar el cálculo de impuestos hasta el cálculo final habilitando la distribución para **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span><span class="sxs-lookup"><span data-stu-id="77941-124">If the transaction is a purchase order, and the application version is later than 10.0.15, you can delay the tax calculation until the final calculation by enabling the flighting for **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch**.</span></span>

## <a name="review-the-call-stack-timeline"></a><span data-ttu-id="77941-125">Revisar la escala de tiempo de la pila de llamadas</span><span class="sxs-lookup"><span data-stu-id="77941-125">Review the call stack timeline</span></span>

<span data-ttu-id="77941-126">Revise la línea de tiempo de la pila de llamadas para determinar si existen los siguientes problemas.</span><span class="sxs-lookup"><span data-stu-id="77941-126">Review the call stack timeline to determine whether the following issues exist.</span></span> <span data-ttu-id="77941-127">Si existen, habilite los paquetes piloto para **TaxUncommittedDoIsolateScopeFlighting** para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="77941-127">If they do, enable the flighting for **TaxUncommittedDoIsolateScopeFlighting** to fix the issue.</span></span>

- <span data-ttu-id="77941-128">La transacción hace que el sistema deje de responder hasta que finalice la sesión.</span><span class="sxs-lookup"><span data-stu-id="77941-128">The transaction causes the system to stop responding until the session ends.</span></span> <span data-ttu-id="77941-129">Por tanto, la transacción no puede calcular el resultado de impuestos.</span><span class="sxs-lookup"><span data-stu-id="77941-129">Therefore, the transaction can't calculate the tax result.</span></span> <span data-ttu-id="77941-130">La siguiente ilustración muestra el cuadro de mensaje "Sesión finalizada" que recibe.</span><span class="sxs-lookup"><span data-stu-id="77941-130">The following illustration shows the "Session ended" message box that you receive.</span></span>

    <span data-ttu-id="77941-131">[![Mensaje de sesión terminada](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span><span class="sxs-lookup"><span data-stu-id="77941-131">[![Session ended message](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)</span></span>

- <span data-ttu-id="77941-132">Los métodos **TaxUncommitted** llevan más tiempo que otros métodos.</span><span class="sxs-lookup"><span data-stu-id="77941-132">The **TaxUncommitted** methods take more time than other methods.</span></span> <span data-ttu-id="77941-133">Por ejemplo, en la siguiente ilustración, el método **TaxUncommitted::updateTaxUncommitted()** tarda 43.347,42 segundos, pero otros métodos tardan 0,09 segundos.</span><span class="sxs-lookup"><span data-stu-id="77941-133">For example, in the following illustration, the **TaxUncommitted::updateTaxUncommitted()** method takes 43,347.42 seconds, but other methods take 0.09 seconds.</span></span>

    <span data-ttu-id="77941-134">[![Duraciones del método](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span><span class="sxs-lookup"><span data-stu-id="77941-134">[![Method durations](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)</span></span>

## <a name="customizing-and-calling-tax-calculation"></a><span data-ttu-id="77941-135">Personalización y llamada al cálcuo de impuestos</span><span class="sxs-lookup"><span data-stu-id="77941-135">Customizing and calling tax calculation</span></span>

<span data-ttu-id="77941-136">Cuando personalice, no llame al cálculo de impuestos al **insertar()** o **actualizar()** el método para cada línea.</span><span class="sxs-lookup"><span data-stu-id="77941-136">When you customize, don't call tax calculation at the **insert()** or **update()** method for each line.</span></span> <span data-ttu-id="77941-137">El cálculo de impuestos debe llamarse a nivel de transacción.</span><span class="sxs-lookup"><span data-stu-id="77941-137">Tax calculation should be called at the transaction level.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="77941-138">Determinar si existe personalización</span><span class="sxs-lookup"><span data-stu-id="77941-138">Determine whether customization exists</span></span>

<span data-ttu-id="77941-139">Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización.</span><span class="sxs-lookup"><span data-stu-id="77941-139">If you've completed the steps in the previous sections but have found no issue, determine whether customization exists.</span></span> <span data-ttu-id="77941-140">Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.</span><span class="sxs-lookup"><span data-stu-id="77941-140">If no customization exists, create a Microsoft service request for further support.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
