---
title: Ejemplo de proceso de cartas de cobro
description: Este tema analiza un ejemplo que muestra el proceso de creación, impresión y publicación de cartas de cobranza.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021425"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="cbffa-103">Ejemplo de proceso de cartas de cobro</span><span class="sxs-lookup"><span data-stu-id="cbffa-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cbffa-104">Este tema analiza un ejemplo que muestra el proceso de creación, impresión y publicación de cartas de cobranza.</span><span class="sxs-lookup"><span data-stu-id="cbffa-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="cbffa-105">El ejemplo se basa en la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** en Crédito y cobros.</span><span class="sxs-lookup"><span data-stu-id="cbffa-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="cbffa-106">Utiliza datos de la empresa de demostración USMF y de un nuevo cliente, US-045.</span><span class="sxs-lookup"><span data-stu-id="cbffa-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="cbffa-107">Para empezar, vaya a **Clientes \> Clientes \> Todos los clientes**, seleccione **Nuevo** y luego introduzca la información requerida para crear el cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="cbffa-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="cbffa-108">Cuando haya terminado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cbffa-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="cbffa-109">Vaya a **Crédito y cobros \> Carta de cobro \> Configurar secuencia de letras de cobro** y configure la secuencia de cartas de cobro como se muestra en la siguiente tabla, que está asignada al perfil de contabilización del cliente.</span><span class="sxs-lookup"><span data-stu-id="cbffa-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="cbffa-110">Código de la carta de cobro</span><span class="sxs-lookup"><span data-stu-id="cbffa-110">Collection   letter code</span></span>      |     <span data-ttu-id="cbffa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbffa-111">Description</span></span>                           |     <span data-ttu-id="cbffa-112">Divisa</span><span class="sxs-lookup"><span data-stu-id="cbffa-112">Currency</span></span>      |     <span data-ttu-id="cbffa-113">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="cbffa-113">Main   account</span></span>        |     <span data-ttu-id="cbffa-114">Cargo en la divisa</span><span class="sxs-lookup"><span data-stu-id="cbffa-114">Fee   in currency</span></span>     |     <span data-ttu-id="cbffa-115">Mínimo sobre</span><span class="sxs-lookup"><span data-stu-id="cbffa-115">Minimum   over</span></span>        |     <span data-ttu-id="cbffa-116">Bloque de días</span><span class="sxs-lookup"><span data-stu-id="cbffa-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="cbffa-117">Carta de cobro 1</span><span class="sxs-lookup"><span data-stu-id="cbffa-117">Collection   letter 1</span></span>         |     <span data-ttu-id="cbffa-118">Segunda notificación con cargo</span><span class="sxs-lookup"><span data-stu-id="cbffa-118">Second   notification with fee</span></span>        |     <span data-ttu-id="cbffa-119">USD</span><span class="sxs-lookup"><span data-stu-id="cbffa-119">USD</span></span>           |                           |     <span data-ttu-id="cbffa-120">0,00</span><span class="sxs-lookup"><span data-stu-id="cbffa-120">0.00</span></span>                  |     <span data-ttu-id="cbffa-121">0,00</span><span class="sxs-lookup"><span data-stu-id="cbffa-121">0.00</span></span>                  |     <span data-ttu-id="cbffa-122">2</span><span class="sxs-lookup"><span data-stu-id="cbffa-122">2</span></span>                 |
|     <span data-ttu-id="cbffa-123">Carta de cobro 2</span><span class="sxs-lookup"><span data-stu-id="cbffa-123">Collection   letter 2</span></span>         |     <span data-ttu-id="cbffa-124">Segunda notificación con cargo</span><span class="sxs-lookup"><span data-stu-id="cbffa-124">Second   notification with fee</span></span>        |     <span data-ttu-id="cbffa-125">USC</span><span class="sxs-lookup"><span data-stu-id="cbffa-125">USC</span></span>           |     <span data-ttu-id="cbffa-126">403150</span><span class="sxs-lookup"><span data-stu-id="cbffa-126">403150</span></span>                |     <span data-ttu-id="cbffa-127">20.00</span><span class="sxs-lookup"><span data-stu-id="cbffa-127">20.00</span></span>                 |     <span data-ttu-id="cbffa-128">10,00</span><span class="sxs-lookup"><span data-stu-id="cbffa-128">10.00</span></span>                 |     <span data-ttu-id="cbffa-129">3</span><span class="sxs-lookup"><span data-stu-id="cbffa-129">3</span></span>                 |
|     <span data-ttu-id="cbffa-130">Cobro</span><span class="sxs-lookup"><span data-stu-id="cbffa-130">Collection</span></span>                    |     <span data-ttu-id="cbffa-131">Notificación final con cargo</span><span class="sxs-lookup"><span data-stu-id="cbffa-131">Final   notification with fee</span></span>         |     <span data-ttu-id="cbffa-132">USD</span><span class="sxs-lookup"><span data-stu-id="cbffa-132">USD</span></span>           |     <span data-ttu-id="cbffa-133">403150</span><span class="sxs-lookup"><span data-stu-id="cbffa-133">403150</span></span>                |     <span data-ttu-id="cbffa-134">50.00</span><span class="sxs-lookup"><span data-stu-id="cbffa-134">50.00</span></span>                 |     <span data-ttu-id="cbffa-135">100.00</span><span class="sxs-lookup"><span data-stu-id="cbffa-135">100.00</span></span>                |     <span data-ttu-id="cbffa-136">15</span><span class="sxs-lookup"><span data-stu-id="cbffa-136">15</span></span>                |

<span data-ttu-id="cbffa-137">La siguiente ilustración muestra la información que está en la tabla, tal como aparecería en la página **Cartas de cobro**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="cbffa-138">[![Configuración de una secuencia de cartas de cobro](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="cbffa-139">Ahora debe establecer los dos parámetros necesarios para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cbffa-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="cbffa-140">Vaya a **Crédito y cobros \> Configuración \> Parámetros de clientes** y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-141">En la pestaña **Cobros**, establezca la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="cbffa-142">Asegúrese de que el campo **Crear carta de cobro por** está configurado en **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="cbffa-143">[![Configuración de parámetros de clientes para cobros de créditos](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="cbffa-144">Vaya a **Clientes \> Facturas \> Todas las facturas de servicios**, seleccione **Nuevo** y luego siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-145">En el campo **Cuenta de cliente**, seleccione **US-045**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="cbffa-146">En el campo **Fecha de factura**, especifique **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="cbffa-147">En el campo **Fecha de vencimiento**, escriba **16/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="cbffa-148">En la ficha desplegable **Líneas de factura**, en el campo **Cuenta principal**, introduzca **401100**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="cbffa-149">En el campo **Precio unitario**, escriba **500.00**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="cbffa-150">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-150">Select **Post**.</span></span>

    <span data-ttu-id="cbffa-151">Ahora debe introducir dos notas de crédito para el cliente.</span><span class="sxs-lookup"><span data-stu-id="cbffa-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="cbffa-152">Seleccione **Nueva** y, a continuación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-153">En el campo **Cuenta de cliente**, seleccione **US-045**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="cbffa-154">En el campo **Fecha de factura**, especifique **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="cbffa-155">En el campo **Fecha de vencimiento**, escriba **16/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="cbffa-156">En la ficha desplegable **Líneas de factura**, en el campo **Cuenta principal**, introduzca **401100**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="cbffa-157">En el campo **Precio unitario**, escriba **-100,00**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="cbffa-158">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-158">Select **Post**.</span></span>

5. <span data-ttu-id="cbffa-159">Repita el paso 4, pero introduzca **-200,00** en el campo **Precio unitario**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="cbffa-160">Vaya a **Clientes \> Clientes \> Todos los clientes** y seleccione el cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="cbffa-161">Luego, en el Panel de acciones, seleccione **Transacciones \> Transacciones** para revisar las transacciones del cliente que registró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="cbffa-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="cbffa-162">[![Revisión de las transacciones de clientes registrados](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="cbffa-163">Ahora debe crear cartas de cobro para el cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="cbffa-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="cbffa-164">Vaya a **Crédito y cobros \> Carta de cobro \> Crear cartas de cobro**, y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-165">Seleccione las opciones **Factura** y **Nota de crédito** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="cbffa-166">Por defecto, el campo **Carta de cobro** debe establecerse en **Cobro por cliente**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="cbffa-167">En el campo **Fecha de carta de cobro**, especifique **19/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="cbffa-168">En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego, en el campo **Cuenta de cliente**, agregue al cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="cbffa-169">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-169">Select **OK**.</span></span>
    5. <span data-ttu-id="cbffa-170">Seleccione **Aceptar** para crear cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cbffa-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="cbffa-171">Vaya a **Crédito y cobros \> Carta de cobro \> Revisar y procesar cartas de cobro**, y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-172">Tenga en cuenta que el código de la carta de cobro tanto en el encabezado como en las líneas de transacción es **Carta de cobro 1**, porque esta carta de cobro es la primera carta de cobro de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="cbffa-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="cbffa-173">(Para ver las líneas de transacción, es posible que deba seleccionar la ficha desplegable **Transacciones**).</span><span class="sxs-lookup"><span data-stu-id="cbffa-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="cbffa-174">[![Verificar que aparezca el mismo código de letra de cobro en el encabezado y las líneas](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="cbffa-175">En el panel de acciones, seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="cbffa-176">En el campo **Fecha de registro**, especifique **19/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="cbffa-177">Ahora debe crear cartas de cobro de nuevo para el cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="cbffa-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="cbffa-178">Vaya a **Crédito y cobros \> Carta de cobro \> Crear cartas de cobro**, y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-179">Seleccione las opciones **Factura** y **Nota de crédito** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="cbffa-180">Por defecto, el campo **Carta de cobro** debe establecerse en **Cobro por cliente**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="cbffa-181">En el campo **Fecha de carta de cobro**, especifique **23/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="cbffa-182">En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego, en el campo **Cuenta de cliente**, agregue al cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="cbffa-183">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-183">Select **OK**.</span></span>
    5. <span data-ttu-id="cbffa-184">Seleccione **Aceptar** para crear cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cbffa-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="cbffa-185">Vaya a **Crédito y cobros \> Carta de cobro \> Revisar y procesar cartas de cobro**, y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-186">Observe que el código de la carta de cobro en el encabezado es **Carta de cobro 1**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="cbffa-187">Sin embargo, el código en las líneas de transacción es **Carta de cobro 2**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="cbffa-188">[![Compruebe que aparezcan códigos de letra de cobro diferentes en el encabezado y las líneas](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="cbffa-189">Los códigos difieren porque la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** está en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="cbffa-190">No registre esta carta de cobro.</span><span class="sxs-lookup"><span data-stu-id="cbffa-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="cbffa-191">Vaya a **Crédito y cobros \> Configuración \> Parámetros de clientes** y luego, en la pestaña **Cobros**, establezca la opción **Ignorar pagos y notas de crédito al calcular el código de la carta de cobro** en **No**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="cbffa-192">[![Establecimiento de la opción Ignorar pagos y notas de crédito al calcular el código de carta de cobro en No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="cbffa-193">Ahora debe crear cartas de cobro de nuevo para el cliente US-045.</span><span class="sxs-lookup"><span data-stu-id="cbffa-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="cbffa-194">Vaya a **Crédito y cobros \> Carta de cobro \> Crear cartas de cobro**, y siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="cbffa-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="cbffa-195">Seleccione las opciones **Factura** y **Nota de crédito** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="cbffa-196">Por defecto, el campo **Carta de cobro** debe establecerse en **Cobro por cliente**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="cbffa-197">En el campo **Fecha de carta de cobro**, especifique **23/1/2021**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="cbffa-198">En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** y luego, en el campo **Cuenta de cliente**, agregue al cliente **US-045**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="cbffa-199">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-199">Select **OK**.</span></span>
    5. <span data-ttu-id="cbffa-200">Seleccione **Aceptar** para crear cartas de cobro.</span><span class="sxs-lookup"><span data-stu-id="cbffa-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="cbffa-201">Vaya a **Créditos y cobros \> Carta de cobro \> Revisar y procesar cartas de cobro** y observe que el código de la carta de cobro tanto en el encabezado como en las líneas de transacción es **Carta de cobro 2**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="cbffa-202">[![Volver a mostrar que aparece el mismo código de letra de cobro en el encabezado y las líneas](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="cbffa-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="cbffa-203">Los mismos códigos aparecen en ambos lugares porque la opción **Ignorar los pagos y las notas de crédito al calcular el código de la carta de cobro** está en **No**.</span><span class="sxs-lookup"><span data-stu-id="cbffa-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>
