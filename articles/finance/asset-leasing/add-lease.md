---
title: Agregar o copiar arrendamientos (Vista previa)
description: Este tema describe cómo crear un nuevo arrendamiento introduciendo información para él en Arrendamiento de activos o copiando información de un arrendamiento existente.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 706b245971ba065bae86e31853832f721a6f9aff
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447816"
---
# <a name="add-or-copy-leases-preview"></a><span data-ttu-id="505e6-103">Agregar o copiar arrendamientos (Vista previa)</span><span class="sxs-lookup"><span data-stu-id="505e6-103">Add or copy leases (Preview)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="505e6-104">Este tema explica cómo crear un arrendamiento desde cero en Arrendamiento de activos y también cómo crear un arrendamiento copiando un arrendamiento existente.</span><span class="sxs-lookup"><span data-stu-id="505e6-104">This topic explains how to create a lease from scratch in Asset leasing, and also how to create a lease by copying an existing lease.</span></span> <span data-ttu-id="505e6-105">El proceso para crear un arrendamiento desde cero implica introducir información para el nuevo arrendamiento y luego crear una programación de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-105">The process for creating a lease from scratch involves entering information for the new lease and then creating a lease schedule.</span></span> <span data-ttu-id="505e6-106">Después de configurar al menos un arrendamiento, es posible que le resulte más fácil copiar la información de un arrendamiento existente y luego editar esa información según sea necesario para crear un nuevo contrato de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-106">After at least one lease has been set up, you might find it easier to copy the information from an existing lease and then edit that information as you require to create a new lease.</span></span>

## <a name="create-a-lease"></a><span data-ttu-id="505e6-107">Crear un arrendamiento</span><span class="sxs-lookup"><span data-stu-id="505e6-107">Create a lease</span></span>

<span data-ttu-id="505e6-108">Siga estos pasos para crear un arrendamiento en Arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="505e6-108">Follow these steps to create a lease in Asset leasing.</span></span>

1. <span data-ttu-id="505e6-109">En la página **Resumen de arrendamientos**, en el panel Acciones, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="505e6-109">On the **Lease summary** page, on the Action Pane, select **New**.</span></span>
2. <span data-ttu-id="505e6-110">Introduzca la información del arrendameinto.</span><span class="sxs-lookup"><span data-stu-id="505e6-110">Enter the lease information.</span></span> <span data-ttu-id="505e6-111">Los campos obligatorios tienen los bordes rojos.</span><span class="sxs-lookup"><span data-stu-id="505e6-111">Fields that are required have red borders.</span></span>

## <a name="create-a-lease-schedule"></a><span data-ttu-id="505e6-112">Crear una programación de arrendamiento</span><span class="sxs-lookup"><span data-stu-id="505e6-112">Create a lease schedule</span></span>

<span data-ttu-id="505e6-113">Una vez que haya terminado de introducir la información para el arrendamiento, siga estos pasos para crear una programación de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-113">After you've finished entering information for the lease, follow these steps to create a lease schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="505e6-114">Las dimensiones financieras pueden cambiar en función de las dimensiones financieras personalizadas.</span><span class="sxs-lookup"><span data-stu-id="505e6-114">The financial dimensions might change based on any custom financial dimensions.</span></span>

1. <span data-ttu-id="505e6-115">Seleccione **Crear programaciones** para generar los libros de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-115">Select **Create schedules** to generate the lease books.</span></span> <span data-ttu-id="505e6-116">Los libros de arrendamiento incluyen los programas de pago, amortización, depreciación y gastos.</span><span class="sxs-lookup"><span data-stu-id="505e6-116">The lease books include the payment, amortization, depreciation, and expense schedules.</span></span>
2. <span data-ttu-id="505e6-117">Para acceder a los libros de arrendamiento y ver las programaciones recién creadas, seleccione la pestaña **Libros**.</span><span class="sxs-lookup"><span data-stu-id="505e6-117">To access the lease books and view the newly created schedules, select the **Books** tab.</span></span>

    <span data-ttu-id="505e6-118">La página **Detalles del libro** muestra cómo se contabiliza el arrendamiento mediante los libros que le han sido asignados.</span><span class="sxs-lookup"><span data-stu-id="505e6-118">The **Book details** page shows how the lease is accounted for by the books that have been allocated to it.</span></span> <span data-ttu-id="505e6-119">Desde aquí, puede ver las programaciones de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-119">From here, you can view the lease schedules.</span></span>

    <span data-ttu-id="505e6-120">La programación de pagos contiene las entradas de la pestaña **Líneas de programación de pagos** en la página **Agregar arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="505e6-120">The payment schedule contains the inputs from the **Payment schedule lines** tab on the **Add lease** page.</span></span> <span data-ttu-id="505e6-121">Sigue pudiendo cambiar cada importe del pago y el pago variable.</span><span class="sxs-lookup"><span data-stu-id="505e6-121">You can still change each payment amount and variable payment.</span></span> <span data-ttu-id="505e6-122">El pasivo por arrendamiento se calcula en base a la programación de pagos modificada.</span><span class="sxs-lookup"><span data-stu-id="505e6-122">The lease liability is calculated based on the modified payment schedule.</span></span>

4. <span data-ttu-id="505e6-123">Una vez que haya terminado de revisar la programación de pagos, seleccione **Confirmar programación**.</span><span class="sxs-lookup"><span data-stu-id="505e6-123">After you've finished reviewing the payment schedule, select **Confirm schedule**.</span></span> <span data-ttu-id="505e6-124">Una vez confirmada la programación, el arrendamiento ya no está disponible para su edición.</span><span class="sxs-lookup"><span data-stu-id="505e6-124">After the schedule is confirmed, the lease is no longer available for editing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="505e6-125">El sistema calcula automáticamente el plazo del arrendamiento a partir de las líneas de programación de pagos en la página **Agregar arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="505e6-125">The system automatically calculates the lease term from the payment schedule lines on the **Add lease** page.</span></span>
    >
    > <span data-ttu-id="505e6-126">Para calcular el plazo del arrendamiento en meses, el sistema encuentra la diferencia entre la fecha de inicio y la fecha de finalización para una línea de programación de pagos específica.</span><span class="sxs-lookup"><span data-stu-id="505e6-126">To calculate the lease term in months, the system finds the difference between the start date and the end date for a specific payment schedule line.</span></span> <span data-ttu-id="505e6-127">Luego pasa a la siguiente línea de programación de pagos y vuelve a encontrar la diferencia.</span><span class="sxs-lookup"><span data-stu-id="505e6-127">It then moves to the next payment schedule line and finds the difference again.</span></span> <span data-ttu-id="505e6-128">Finalmente, el sistema suma todos los importes para determinar el plazo del arrendamiento en meses.</span><span class="sxs-lookup"><span data-stu-id="505e6-128">Finally, the system sums all the amounts to determine the lease term in months.</span></span>

5. <span data-ttu-id="505e6-129">Para ver los gastos por intereses del período calculados, abra la página **Programación de amortización de pasivos**.</span><span class="sxs-lookup"><span data-stu-id="505e6-129">To view the calculated period interest expenses, open the **Liability amortization schedule** page.</span></span> <span data-ttu-id="505e6-130">Para ver la depreciación lineal calculada, abra la página **Programa de depreciación de activos**.</span><span class="sxs-lookup"><span data-stu-id="505e6-130">To view calculated straight-line depreciation, open the **Asset depreciation schedule** page.</span></span>
6. <span data-ttu-id="505e6-131">Una vez que haya terminado de revisar la cantidad calculada, puede crear el movimiento de diario de reconocimiento inicial en la página **Reconocimiento inicial**.</span><span class="sxs-lookup"><span data-stu-id="505e6-131">After you've finished reviewing the calculated amount, you can create the initial recognition journal entry on the **Initial recognition** page.</span></span> <span data-ttu-id="505e6-132">Recibe un mensaje que indica que se ha creado el diario.</span><span class="sxs-lookup"><span data-stu-id="505e6-132">You receive a message that states that the journal has been created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="505e6-133">El movimiento de diario no se registra en el Libro mayor hasta que lo registre manualmente.</span><span class="sxs-lookup"><span data-stu-id="505e6-133">The journal entry isn't posted to General ledger until you manually post the entry.</span></span>

7. <span data-ttu-id="505e6-134">Para revisar la entrada de reconocimiento inicial propuesta antes de publicarla, seleccione **Diario de arrendamiento de activos**.</span><span class="sxs-lookup"><span data-stu-id="505e6-134">To review the proposed initial recognition entry before you post it, select **Asset leasing journal**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="505e6-135">El diario de arrendamiento de activos no se puede crear manualmente.</span><span class="sxs-lookup"><span data-stu-id="505e6-135">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="505e6-136">Se crea automáticamente cuando se crean las programaciones de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-136">It's automatically created when lease schedules are created.</span></span>

8. <span data-ttu-id="505e6-137">Cuando haya terminado de revisar la entrada del diario de reconocimiento inicial y esté listo para publicarlo, seleccione **Publicar** para reconocer el activo por derecho de uso (ROU) y el pasivo por arrendamiento en el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="505e6-137">When you've finished reviewing the initial recognition journal entry and are ready to post it, select **Post** to recognize the right-of-use (ROU) asset and lease liability in General ledger.</span></span>

## <a name="copy-a-lease"></a><span data-ttu-id="505e6-138">Copiar arrendamiento</span><span class="sxs-lookup"><span data-stu-id="505e6-138">Copy a lease</span></span>

<span data-ttu-id="505e6-139">El arrendamiento de activos le permite copiar los detalles de un arrendamiento para crear un nuevo arrendamiento que tenga la misma información.</span><span class="sxs-lookup"><span data-stu-id="505e6-139">Asset leasing lets you copy the details of a lease to create a new lease that has the same information.</span></span> <span data-ttu-id="505e6-140">A continuación, puede cambiar los campos de arrendamiento antes de crear las programaciones para el arrendamiento copiado.</span><span class="sxs-lookup"><span data-stu-id="505e6-140">You can then change the lease fields before you create the schedules for the copied lease.</span></span>

1. <span data-ttu-id="505e6-141">En la página **Resumen de arrendamiento**, seleccione el arrendamiento a copiar y, a continuación, en el Panel de acciones, seleccione **Copiar arrendamiento**.</span><span class="sxs-lookup"><span data-stu-id="505e6-141">On the **Lease summary** page, select the lease to copy, and then, on the Action Pane, select **Copy lease**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="505e6-142">Si el parámetro **Manual** está desactivado para la secuencia numérica de los id. de arrendamiento, el siguiente número de la secuencia se genera automáticamente como id. de arrendamiento del arrendamiento copiado.</span><span class="sxs-lookup"><span data-stu-id="505e6-142">If the **Manual** parameter is turned off for the number sequence for lease IDs, the next number in the sequence is automatically generated as the lease ID of the copied lease.</span></span> <span data-ttu-id="505e6-143">Si el parámetro **Manual** está activado, recibe un mensaje que le solicita introducir el id. de arrendamiento antes de proceder a copiar el arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-143">If the **Manual** parameter is turned on, you receive a message that prompts you to enter the lease ID before you proceed to copy the lease.</span></span>

2. <span data-ttu-id="505e6-144">Seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="505e6-144">Select **Copy**.</span></span> <span data-ttu-id="505e6-145">Los detalles del arrendamiento del arrendamiento seleccionado se copian a un nuevo arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-145">The lease details from the selected lease are copied to a new lease.</span></span> <span data-ttu-id="505e6-146">Luego, puede editar los detalles del nuevo contrato de arrendamiento antes de guardarlo y crear las programaciones de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-146">You can then edit the details of the new lease before you save it and create the lease schedules.</span></span>

## <a name="asset-leasing-journal"></a><span data-ttu-id="505e6-147">Diario de arrendamientos de activos</span><span class="sxs-lookup"><span data-stu-id="505e6-147">Asset leasing journal</span></span>

<span data-ttu-id="505e6-148">Todos los movimientos de diario que se crean en Arrendamiento de activos se incluyen en el diario de Arrendamiento de activos.</span><span class="sxs-lookup"><span data-stu-id="505e6-148">All journal entries that are created in Asset leasing are contained in the Asset leasing journal.</span></span> <span data-ttu-id="505e6-149">En la página **Diario de arrendamiento de activos** (**Arrendamiento de activos \> Entradas de diario \> Diario de arrendamiento de activos**), puede filtrar por estado de publicación, ver entradas de diario específicas y los comprobantes, y registrar entradas de diario no publicadas.</span><span class="sxs-lookup"><span data-stu-id="505e6-149">On the **Asset leasing journal** page (**Asset leasing \> Journal entries \> Asset leasing journal**), you can filter by posting status, view specific journal entries and the vouchers, and post unposted journal entries.</span></span>

> [!NOTE]
> <span data-ttu-id="505e6-150">El diario de arrendamiento de activos no se puede crear manualmente.</span><span class="sxs-lookup"><span data-stu-id="505e6-150">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="505e6-151">Se crea automáticamente cuando se crean las programaciones de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="505e6-151">It's automatically created when lease schedules are created.</span></span>
