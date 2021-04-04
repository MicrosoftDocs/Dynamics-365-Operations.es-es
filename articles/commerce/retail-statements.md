---
title: Extractos comerciales
description: Este tema describe cómo se crean y registran los extractos.
author: ashishmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: 6bf582ff61e09ab7586108fa9270a7f485fc9ec7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254898"
---
# <a name="retail-statements"></a><span data-ttu-id="8bf37-103">Extractos comerciales</span><span class="sxs-lookup"><span data-stu-id="8bf37-103">Retail statements</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8bf37-104">En Dynamics 365 Commerce, el proceso de registro de extractos se utiliza para contabilizar las transacciones que se producen en el punto de venta (POS) o PDV moderno (MPOS) de la nube.</span><span class="sxs-lookup"><span data-stu-id="8bf37-104">In Dynamics 365 Commerce, the statement posting process is used to account for the transactions that occur in Cloud point of sale (POS) or Modern POS (MPOS).</span></span> <span data-ttu-id="8bf37-105">El proceso de registro de extractos usa la programación de distribución para extraer un conjunto de transacciones de PDV en el cliente de la central (HQ).</span><span class="sxs-lookup"><span data-stu-id="8bf37-105">The statement posting process uses the distribution schedule to pull a set of POS transactions into the headquarters (HQ) client.</span></span> <span data-ttu-id="8bf37-106">Los parámetros definidos en las páginas **Parámetros de Commerce** y **Tiendas** se usan para seleccionar las transacciones que se extraen en extractos individuales.</span><span class="sxs-lookup"><span data-stu-id="8bf37-106">The parameters that are defined on the **Commerce parameters** and **Stores** pages are used to select the transactions that are pulled into individual statements.</span></span>

<span data-ttu-id="8bf37-107">La siguiente ilustración muestra el proceso de registro de extractos.</span><span class="sxs-lookup"><span data-stu-id="8bf37-107">The following illustration shows the statement posting process.</span></span> <span data-ttu-id="8bf37-108">En este proceso, las transacciones que se registran en el PDV se transmiten al cliente mediante el programador de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bf37-108">In this process, transactions that are recorded in the POS are transmitted to the client by using the Commerce scheduler.</span></span> <span data-ttu-id="8bf37-109">Después de que el cliente reciba las transacciones, puede crear, calcular y registrar el extracto de la transacción para el almacén.</span><span class="sxs-lookup"><span data-stu-id="8bf37-109">After the client receives the transactions, you can create, calculate, and post the transaction statement for the store.</span></span>

<span data-ttu-id="8bf37-110">[![Proceso de registro de extractos](./media/retail-statements.png)](./media/retail-statements.png)</span><span class="sxs-lookup"><span data-stu-id="8bf37-110">[![Statement posting process](./media/retail-statements.png)](./media/retail-statements.png)</span></span>

## <a name="creating-and-posting-statements"></a><span data-ttu-id="8bf37-111">Crear y registrar extractos</span><span class="sxs-lookup"><span data-stu-id="8bf37-111">Creating and posting statements</span></span>

<span data-ttu-id="8bf37-112">Puede crear un extracto manualmente o mediante procesos por lotes que configure para ejecutarse periódicamente en el día.</span><span class="sxs-lookup"><span data-stu-id="8bf37-112">You can create a statement manually or by using batch processes that you set up to run periodically throughout the day.</span></span> <span data-ttu-id="8bf37-113">En ambos casos, se usan los pasos siguientes para crear y registrar extractos.</span><span class="sxs-lookup"><span data-stu-id="8bf37-113">In both cases, the following steps are used to create and post statements.</span></span>

### <a name="create-the-statement"></a><span data-ttu-id="8bf37-114">Crear el extracto</span><span class="sxs-lookup"><span data-stu-id="8bf37-114">Create the statement</span></span>

<span data-ttu-id="8bf37-115">Este paso identifica la tienda para la que se ha creado el extracto manualmente.</span><span class="sxs-lookup"><span data-stu-id="8bf37-115">This step identifies the store that the statement is manually created for.</span></span> <span data-ttu-id="8bf37-116">Si configura un proceso por lotes, puede crear automáticamente extractos para todas las tiendas, en función de una programación que defina.</span><span class="sxs-lookup"><span data-stu-id="8bf37-116">If you configure a batch process, you can automatically create statements for all stores, based on a schedule that you define.</span></span>

### <a name="calculate-the-statement"></a><span data-ttu-id="8bf37-117">Calcular el extracto</span><span class="sxs-lookup"><span data-stu-id="8bf37-117">Calculate the statement</span></span>

<span data-ttu-id="8bf37-118">En este paso, las líneas de transacción están seleccionadas según los criterios definidos para cada tienda en las páginas **Parámetros de Commerce** y **Tiendas**.</span><span class="sxs-lookup"><span data-stu-id="8bf37-118">In this step, the transaction lines are selected based on criteria that are defined for each store on the **Commerce parameters** and **Stores** pages.</span></span> <span data-ttu-id="8bf37-119">En estas páginas, puede definir los criterios y especificar cómo se calculan las transacciones.</span><span class="sxs-lookup"><span data-stu-id="8bf37-119">On these pages, you define the criteria and specify how the transactions are calculated.</span></span> <span data-ttu-id="8bf37-120">Para ver una lista de las transacciones incluidas en el extracto antes de calcular el extracto, use la página **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="8bf37-120">To view a list of the transactions that are included in the statement before you calculate the statement, use the **Transactions** page.</span></span>

<span data-ttu-id="8bf37-121">Un cálculo de extracto usa declaraciones de formas de pago de las cajas registradoras como importe contado.</span><span class="sxs-lookup"><span data-stu-id="8bf37-121">Statement calculation uses tender declarations from the registers as the counted amount.</span></span> <span data-ttu-id="8bf37-122">También puede escribir el importe contado manualmente.</span><span class="sxs-lookup"><span data-stu-id="8bf37-122">Alternatively, you can enter the counted amount manually.</span></span> <span data-ttu-id="8bf37-123">El extracto muestra la diferencia entre el importe de venta de las transacciones y el importe contado real en todos los métodos de pago.</span><span class="sxs-lookup"><span data-stu-id="8bf37-123">The statement shows the difference between the sales amount for the transactions and the actual counted amount in all payment methods.</span></span> <span data-ttu-id="8bf37-124">El extracto se registra únicamente si esta diferencia es inferior a la diferencia de registro máxima que se ha definido para la tienda.</span><span class="sxs-lookup"><span data-stu-id="8bf37-124">The statement is posted only if this difference is less than the maximum posting difference that is defined for the store.</span></span>

> [!NOTE]
> <span data-ttu-id="8bf37-125">El proceso de cálculo de extractos usa la secuencia numérica global.</span><span class="sxs-lookup"><span data-stu-id="8bf37-125">The statement calculation process uses the global number sequence.</span></span>

<span data-ttu-id="8bf37-126">Al calcular un extracto, el cálculo incluye las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bf37-126">When you calculate a statement, the calculation includes the following tasks:</span></span>

- <span data-ttu-id="8bf37-127">Marque las transacciones que no se incluyeron en un cálculo de extracto anterior para el intervalo de fechas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8bf37-127">For the selected date range, mark transactions that weren't included in a previous statement calculation.</span></span>
- <span data-ttu-id="8bf37-128">Calcule los importes totales especificados como forma de pago en las transacciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8bf37-128">Calculate the total amounts that were tendered in the selected transactions.</span></span> <span data-ttu-id="8bf37-129">Los resultados se muestran en las líneas de extracto, en función del método de extracto:</span><span class="sxs-lookup"><span data-stu-id="8bf37-129">The results are shown on the statement lines, depending on the statement method:</span></span>

    - <span data-ttu-id="8bf37-130">Si el método de extracto es **Total**, se crea una línea por cada método de pago en las transacciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="8bf37-130">If the statement method is **Total**, a line is created for each payment method in the selected transactions.</span></span>
    - <span data-ttu-id="8bf37-131">Si el método de extracto es **Personal**, se creará una línea para cada método de pago en las transacciones que realice el empleado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8bf37-131">If the statement method is **Staff**, a line is created for each payment method in transactions that were performed by the selected staff member.</span></span>
    - <span data-ttu-id="8bf37-132">Si el método de extracto es **Terminal del PDV**, se creará una línea para cada método de pago en las transacciones que se realicen en el registro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8bf37-132">If the statement method is **POS terminal**, a line is created for each payment method in transactions that were performed on the selected register.</span></span>
    - <span data-ttu-id="8bf37-133">Si el método de extracto es **Turno**, se creará una línea para cada método de pago en las transacciones que se realicen durante un turno.</span><span class="sxs-lookup"><span data-stu-id="8bf37-133">If the statement method is **Shift**, a line is created for each payment method in transactions that were performed during a shift.</span></span>

<span data-ttu-id="8bf37-134">Si la casilla **Dividir por método de extracto** está seleccionada en la página **Tiendas**, se crea un extracto independiente en función del valor seleccionado en el campo **Método de extracto** .</span><span class="sxs-lookup"><span data-stu-id="8bf37-134">If the **Split by Statement method** check box is selected on the **Stores** page, a separate statement is created based on the value that is selected in the **Statement method** field.</span></span>

<span data-ttu-id="8bf37-135">Si el horario de operaciones de la tienda se extiende más allá de la medianoche, puede configurar un registro de extractos de modo que se base en el final de la jornada laboral en lugar del final del día de calendario.</span><span class="sxs-lookup"><span data-stu-id="8bf37-135">If your store's operating hours extend past midnight, you can configure statement posting so that it's based on the end of the business day instead of the end of the calendar day.</span></span>

<span data-ttu-id="8bf37-136">En la página **Tiendas**, en la ficha desplegable **Extracto/cierre**, en el campo **Final del día laboral**, especifique la hora en que debe registrarse la última transacción para que se incluya en el extracto del día laboral.</span><span class="sxs-lookup"><span data-stu-id="8bf37-136">On the **Stores** page, on the **Statement/closing** FastTab, in the **End of business day** field, enter the time that the last transaction must be recorded to be included in the business day's statement.</span></span> <span data-ttu-id="8bf37-137">Active la casilla **Registrar como día laboral** para registrar las transacciones dentro del mismo día laboral.</span><span class="sxs-lookup"><span data-stu-id="8bf37-137">Select the **Post as business day** check box to post the transactions within the same business day.</span></span> <span data-ttu-id="8bf37-138">Cuando se registra el extracto, las transacciones que se registran dentro mismo día laboral se pueden incluir en el mismo pedido de ventas, incluso si algunas transacciones se producen antes de la medianoche y otras después de la medianoche.</span><span class="sxs-lookup"><span data-stu-id="8bf37-138">When the statement is posted, transactions that are recorded within the same business day can be included on the same sales order, even if some transactions occur before midnight and other transactions occur after midnight.</span></span>

#### <a name="example-post-a-statement-for-a-business-day-that-extends-over-two-calendar-days"></a><span data-ttu-id="8bf37-139">Ejemplo: registre un extracto para un día laboral que se extienda más de dos días de calendario</span><span class="sxs-lookup"><span data-stu-id="8bf37-139">Example: Post a statement for a business day that extends over two calendar days</span></span>

<span data-ttu-id="8bf37-140">Una tienda está abierta entre las 8:00 y las 3:00, y la casilla **Registrar como día laboral** se selecciona en la configuración de la tienda.</span><span class="sxs-lookup"><span data-stu-id="8bf37-140">A store is open between 8:00 AM and 3:00 AM, and the **Post as business day** check box is selected in the store's configuration.</span></span> <span data-ttu-id="8bf37-141">El 31 de mayo, el almacén registra transacciones entre las 8:00 y la medianoche.</span><span class="sxs-lookup"><span data-stu-id="8bf37-141">On May 31, the store records transactions between 8:00 AM and midnight.</span></span> <span data-ttu-id="8bf37-142">El almacén también registra transacciones entre las 00:01 y las 3:00 el 1 de junio.</span><span class="sxs-lookup"><span data-stu-id="8bf37-142">The store also records transactions between 12:01 AM and 3:00 AM on June 1.</span></span>

<span data-ttu-id="8bf37-143">Si el almacén registra el extracto para el cierre del día laborable, el pedido de ventas que se genera incluye todas las transacciones registradas entre las 8:00 y las 3:00., aunque se hayan realizado transacciones en dos días, el 31 de mayo y el 1 de junio.</span><span class="sxs-lookup"><span data-stu-id="8bf37-143">When the store posts its statement for the close of the business day, the sales order that is generated includes all transactions that were recorded between the business hours of 8:00 AM and 3:00 AM, even though the transactions occurred on two days, May 31 and June 1.</span></span>

<span data-ttu-id="8bf37-144">Si la casilla **Registrar como día laboral** se desactiva para la misma tienda, se generan pedidos de ventas independientes cuando el almacén registra el extracto para el cierre del día laboral.</span><span class="sxs-lookup"><span data-stu-id="8bf37-144">If the **Post as business day** check box is cleared for the same store, separate sales orders are generated when the store posts its statement for the close of the business day.</span></span> <span data-ttu-id="8bf37-145">Un pedido de ventas incluye las transacciones registradas entre las 8:00 y la medianoche del 31 de mayo, y el segundo pedido de ventas incluye las transacciones registradas entre las 00:01 y las 3:00 del 1 de junio.</span><span class="sxs-lookup"><span data-stu-id="8bf37-145">One sales order includes the transactions that were recorded between the business hours of 8:00 AM and midnight on May 31, and the second sales order includes the transactions that were recorded between the business hours of 12:01 AM and 3:00 AM on June 1.</span></span>

> [!NOTE]
> <span data-ttu-id="8bf37-146">Antes de poder crear extractos, debe cerrar los turnos en el período del extracto.</span><span class="sxs-lookup"><span data-stu-id="8bf37-146">Before you can create statements, you should close the shifts in the statement period.</span></span>

### <a name="post-the-statement"></a><span data-ttu-id="8bf37-147">Registrar el extracto</span><span class="sxs-lookup"><span data-stu-id="8bf37-147">Post the statement</span></span>

<span data-ttu-id="8bf37-148">Cuando se registra un extracto, los pedidos de venta y las facturas se crean para las ventas en el extracto.</span><span class="sxs-lookup"><span data-stu-id="8bf37-148">When you post a statement, sales orders and invoices are created for the sales in the statement.</span></span>

- <span data-ttu-id="8bf37-149">Las ventas al por mayor se agregan en un pedido de ventas y se facturan para el cliente predeterminado asignado a la tienda.</span><span class="sxs-lookup"><span data-stu-id="8bf37-149">Cash and carry sales are aggregated onto one sales order, and are invoiced for the default customer who is assigned to the store.</span></span>
- <span data-ttu-id="8bf37-150">Las ventas para las que se ha agregado un cliente a la transacción en POS generan pedidos de venta y facturas independientes, una para cada cliente único.</span><span class="sxs-lookup"><span data-stu-id="8bf37-150">Sales for which a customer was added to the transaction in POS generate separate sales orders and invoices, one for each unique customer.</span></span>

<span data-ttu-id="8bf37-151">Los diarios de pago se crean automáticamente para los pagos en el extracto, y el inventario se actualiza para la tienda del PDV.</span><span class="sxs-lookup"><span data-stu-id="8bf37-151">Payment journals are automatically created for the payments in the statement, and the inventory is updated for the POS store.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]