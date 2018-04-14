--- 
title: Transferir transacciones a intrastat
description: "Este procedimiento le guía por cómo configurar parámetros de intrastat y transferir transacciones a intrastat."
author: Anasyash
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3d888ed34e1a582f74f0174fad941c889edabd06
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="bc032-103">Transferir transacciones a intrastat</span><span class="sxs-lookup"><span data-stu-id="bc032-103">Transfer transactions to the Intrastat</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc032-104">Este procedimiento le guía por cómo configurar parámetros de intrastat y transferir transacciones a intrastat.</span><span class="sxs-lookup"><span data-stu-id="bc032-104">This procedure walks you through how to set up Intrastat parameters and transfer transactions to Intrastat.</span></span> <span data-ttu-id="bc032-105">Este procedimiento se creó con los datos de demostración de la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="bc032-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="create-new-and-update-existing-commodity-code"></a><span data-ttu-id="bc032-106">Crear código de mercancía nuevo y actualizar el existente</span><span class="sxs-lookup"><span data-stu-id="bc032-106">Create new and update existing commodity code</span></span>
1. <span data-ttu-id="bc032-107">Vaya a Gestión de información de productos > Configuración > Categorías y atributos > Jerarquías de categorías.</span><span class="sxs-lookup"><span data-stu-id="bc032-107">Go to Product information management > Setup > Categories and attributes > Category hierarchies.</span></span>
2. <span data-ttu-id="bc032-108">En la lista, busque o seleccione el registro "Códigos de mercancías intrastat".</span><span class="sxs-lookup"><span data-stu-id="bc032-108">In the list, find or select the record "Intrastat commodity codes."</span></span>
3. <span data-ttu-id="bc032-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bc032-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bc032-110">En el árbol, seleccione "un registro".</span><span class="sxs-lookup"><span data-stu-id="bc032-110">In the tree, select 'a record'.</span></span>
    * <span data-ttu-id="bc032-111">Por ejemplo, seleccione "Intrastat\Altavoz".</span><span class="sxs-lookup"><span data-stu-id="bc032-111">For example, select 'Intrastat\Speaker'.</span></span>  
5. <span data-ttu-id="bc032-112">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="bc032-112">Click Edit.</span></span>
6. <span data-ttu-id="bc032-113">Expanda la sección Comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="bc032-113">Expand the Foreign trade section.</span></span>
7. <span data-ttu-id="bc032-114">En el campo Unidades adicionales, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-114">In the Additional units field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-115">Por ejemplo, elija "uds".</span><span class="sxs-lookup"><span data-stu-id="bc032-115">For example, choose 'pcs'.</span></span>  
8. <span data-ttu-id="bc032-116">Seleccione Sí en el campo Peso no aplicable.</span><span class="sxs-lookup"><span data-stu-id="bc032-116">Select Yes in the Weight not applicable field.</span></span>
9. <span data-ttu-id="bc032-117">En el árbol, seleccione "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="bc032-117">In the tree, select 'Intrastat'.</span></span>
10. <span data-ttu-id="bc032-118">Haga clic en Nodo de categoría nueva.</span><span class="sxs-lookup"><span data-stu-id="bc032-118">Click New category node.</span></span>
11. <span data-ttu-id="bc032-119">En el campo Nombre, introduzca el nombre de la mercancía.</span><span class="sxs-lookup"><span data-stu-id="bc032-119">In the Name field, enter the name of commodity.</span></span>
    * <span data-ttu-id="bc032-120">Por ejemplo, escriba "Otra mercancía".</span><span class="sxs-lookup"><span data-stu-id="bc032-120">For example, type 'Other commodity'.</span></span>  
12. <span data-ttu-id="bc032-121">En el campo Código, especifique el código de la mercancía.</span><span class="sxs-lookup"><span data-stu-id="bc032-121">In the Code field, enter the commodity code.</span></span>
    * <span data-ttu-id="bc032-122">Por ejemplo, escriba "995 00 00".</span><span class="sxs-lookup"><span data-stu-id="bc032-122">For example, type '995 00 00'.</span></span>  
13. <span data-ttu-id="bc032-123">En el campo Nombre descriptivo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-123">In the Friendly name field, type a value.</span></span>
    * <span data-ttu-id="bc032-124">Por ejemplo, escriba "Otros".</span><span class="sxs-lookup"><span data-stu-id="bc032-124">For example, type 'Other'.</span></span>  
14. <span data-ttu-id="bc032-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bc032-125">Click Save.</span></span>
15. <span data-ttu-id="bc032-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bc032-126">Close the page.</span></span>

## <a name="assign-commodity-code-to-product-hierarchy-and-released-product"></a><span data-ttu-id="bc032-127">Asignar el código de mercancía a la jerarquía de productos y al producto liberado</span><span class="sxs-lookup"><span data-stu-id="bc032-127">Assign commodity code to product hierarchy and released product</span></span>
1. <span data-ttu-id="bc032-128">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="bc032-128">Use the Quick Filter to find records.</span></span> <span data-ttu-id="bc032-129">Por ejemplo, filtre el campo Nombre según el valor "ventas".</span><span class="sxs-lookup"><span data-stu-id="bc032-129">For example, filter on the Name field with a value of 'sales'.</span></span>
2. <span data-ttu-id="bc032-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bc032-130">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="bc032-131">En el árbol, expanda "un nodo de categoría".</span><span class="sxs-lookup"><span data-stu-id="bc032-131">In the tree, expand 'a category node'.</span></span>
    * <span data-ttu-id="bc032-132">Por ejemplo, expanda “Jerarquía de artículos\Audio en casa”.</span><span class="sxs-lookup"><span data-stu-id="bc032-132">For example, expand 'Sales hierarchy\Home audio'.</span></span>  
4. <span data-ttu-id="bc032-133">En el árbol, seleccione "la categoría que se debe asignar al código de la mercancía".</span><span class="sxs-lookup"><span data-stu-id="bc032-133">In the tree, select 'the category to assign to the commodity code'.</span></span>
    * <span data-ttu-id="bc032-134">Por ejemplo, seleccione “Jerarquía de artículos\Altavoces”.</span><span class="sxs-lookup"><span data-stu-id="bc032-134">For example, select 'Sales hierarchy\Home audio\Speakers.</span></span>  
5. <span data-ttu-id="bc032-135">Expanda la sección Códigos de mercancías.</span><span class="sxs-lookup"><span data-stu-id="bc032-135">Expand the Commodity codes section.</span></span>
6. <span data-ttu-id="bc032-136">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="bc032-136">Click Add.</span></span>
7. <span data-ttu-id="bc032-137">En el campo Seleccionar jerarquía, seleccione "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="bc032-137">In the Select hierarchy field, select 'Intrastat'.</span></span>
8. <span data-ttu-id="bc032-138">En la lista, busque y seleccione el código de la mercancía.</span><span class="sxs-lookup"><span data-stu-id="bc032-138">In the list, find and select the commodity code</span></span>
    * <span data-ttu-id="bc032-139">Por ejemplo, seleccione "920 20 34 Altavoz".</span><span class="sxs-lookup"><span data-stu-id="bc032-139">For example, select '920 20 34 Speaker'.</span></span>  
9. <span data-ttu-id="bc032-140">Haga clic en Seleccionar códigos.</span><span class="sxs-lookup"><span data-stu-id="bc032-140">Click SelectCodes.</span></span>
10. <span data-ttu-id="bc032-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-141">Click OK.</span></span>
11. <span data-ttu-id="bc032-142">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="bc032-142">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="bc032-143">En la lista, elija el producto liberado que asignará al código de la mercancía.</span><span class="sxs-lookup"><span data-stu-id="bc032-143">In the list, choose the released product that you will assign to the commodity code.</span></span>
    * <span data-ttu-id="bc032-144">Por ejemplo, elija "D0001".</span><span class="sxs-lookup"><span data-stu-id="bc032-144">For example, choose 'D0001'.</span></span>  
13. <span data-ttu-id="bc032-145">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="bc032-145">Click Edit.</span></span>
14. <span data-ttu-id="bc032-146">Expanda la sección Comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="bc032-146">Expand the Foreign trade section.</span></span>
15. <span data-ttu-id="bc032-147">En el campo Código intrastat de la mercancía, especifique el código de la mercancía</span><span class="sxs-lookup"><span data-stu-id="bc032-147">In the Commodity field, enter the commodity code</span></span>
    * <span data-ttu-id="bc032-148">Por ejemplo, seleccione el valor "920 20 34 Altavoz".</span><span class="sxs-lookup"><span data-stu-id="bc032-148">For example, select value '920 20 34 Speaker'.</span></span>    
16. <span data-ttu-id="bc032-149">En el campo Porcentaje de gastos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="bc032-149">In the Charges percentage field, enter a number.</span></span>
    * <span data-ttu-id="bc032-150">Por ejemplo, escriba "3".</span><span class="sxs-lookup"><span data-stu-id="bc032-150">For example, enter '3'.</span></span>  
17. <span data-ttu-id="bc032-151">En el campo País o región, escriba o seleccione un país o una región de origen</span><span class="sxs-lookup"><span data-stu-id="bc032-151">In the Country/region field, enter or select a country or region of origin</span></span>
    * <span data-ttu-id="bc032-152">Por ejemplo, seleccione "AUT".</span><span class="sxs-lookup"><span data-stu-id="bc032-152">For example, select 'AUT'.</span></span>  
18. <span data-ttu-id="bc032-153">Expanda la sección Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="bc032-153">Expand the Manage inventory section.</span></span>
19. <span data-ttu-id="bc032-154">En el campo Peso neto, escriba un peso en kg.</span><span class="sxs-lookup"><span data-stu-id="bc032-154">In the Net weight field, enter a weight in kg.</span></span>
    * <span data-ttu-id="bc032-155">Por ejemplo, escribe "2,5".</span><span class="sxs-lookup"><span data-stu-id="bc032-155">For example, enter '2.5'.</span></span>  
20. <span data-ttu-id="bc032-156">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bc032-156">Click Save.</span></span>

## <a name="set-up-intrastat-transaction-codes-and-foreign-trade-parameters"></a><span data-ttu-id="bc032-157">Configurar los códigos de transacción intrastat y los parámetros de comercio exterior</span><span class="sxs-lookup"><span data-stu-id="bc032-157">Set up Intrastat transaction codes and foreign trade parameters</span></span>
1. <span data-ttu-id="bc032-158">Vaya a Impuesto > Configurar > Comercio exterior > Códigos de transacción</span><span class="sxs-lookup"><span data-stu-id="bc032-158">Go to Tax > Setup > Foreign trade > Transaction codes</span></span>
2. <span data-ttu-id="bc032-159">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bc032-159">Click New.</span></span>
3. <span data-ttu-id="bc032-160">En el campo Código de transacción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-160">In the Transaction code field, type a value.</span></span>
    * <span data-ttu-id="bc032-161">Por ejemplo, especifique “21" para el código de transacción que se usa como devolución.</span><span class="sxs-lookup"><span data-stu-id="bc032-161">For example, enter '21' for the transaction code used as return.</span></span>  
4. <span data-ttu-id="bc032-162">En el campo Nombre, escriba el nombre del código de la transacción.</span><span class="sxs-lookup"><span data-stu-id="bc032-162">In the Name field, type the name of transaction code.</span></span>
    * <span data-ttu-id="bc032-163">Por ejemplo, especifique "Devolución".</span><span class="sxs-lookup"><span data-stu-id="bc032-163">For example, enter 'Return'.</span></span>  
5. <span data-ttu-id="bc032-164">En el campo Importe estadístico, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="bc032-164">In the Statistical amount field, select an option.</span></span>
    * <span data-ttu-id="bc032-165">Por ejemplo, seleccione “Vacía” que indica que el valor estadístico que se notificará para las transacciones con el código de transacción de “21 "será siempre cero.</span><span class="sxs-lookup"><span data-stu-id="bc032-165">For example, select 'Empty' which indicates that the Statistical value to be reported for transactions with Transaction code of "21" will always be zero.</span></span>  
6. <span data-ttu-id="bc032-166">Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="bc032-166">Go to Tax > Setup > Foreign trade > Foreign trade parameters</span></span>
7. <span data-ttu-id="bc032-167">En el campo Código de transacción, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-167">In the Transaction code field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-168">Por ejemplo, seleccione "'11".</span><span class="sxs-lookup"><span data-stu-id="bc032-168">For example, select '11'.</span></span>  
8. <span data-ttu-id="bc032-169">En el campo Nota de abono, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-169">In the Credit note field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-170">Este valor también identifica la devolución física.</span><span class="sxs-lookup"><span data-stu-id="bc032-170">This value also identifies the physical return.</span></span> <span data-ttu-id="bc032-171">La nota de abono para la devolución física se transferirá en el diario de Intrastat con la dirección opuesta.</span><span class="sxs-lookup"><span data-stu-id="bc032-171">The credit note for the physical return will be transferred in the Intrastat journal with opposite direction.</span></span> <span data-ttu-id="bc032-172">Por ejemplo, la devolución de llegada se transfiere como distribución.</span><span class="sxs-lookup"><span data-stu-id="bc032-172">For example, the return of arrival is transferred as dispatch.</span></span>   <span data-ttu-id="bc032-173">De lo contrario, la nota de abono se considera una corrección y se transfiere con la misma dirección y signo opuesto.</span><span class="sxs-lookup"><span data-stu-id="bc032-173">Otherwise, the credit note is considered a correction and is transferred with the same direction and opposite sign.</span></span> <span data-ttu-id="bc032-174">Por ejemplo, la corrección de llegada se transfiere como llegada con importe negativo y el indicador activa se establece en “Corrección”.</span><span class="sxs-lookup"><span data-stu-id="bc032-174">For example, the correction of arrival is transferred as an arrival with negative amount and the active flag is set to "Correction".</span></span>  
9. <span data-ttu-id="bc032-175">Expanda la sección Transferir.</span><span class="sxs-lookup"><span data-stu-id="bc032-175">Expand the Transfer section.</span></span>
10. <span data-ttu-id="bc032-176">Seleccione Sí en el campo Artículos con código de mercancía.</span><span class="sxs-lookup"><span data-stu-id="bc032-176">Select Yes in the Items with commodity code field.</span></span>
    * <span data-ttu-id="bc032-177">Seleccione esta opción para transferir solo las transacciones con un código de mercancía asignado.</span><span class="sxs-lookup"><span data-stu-id="bc032-177">Select this option to transfer only the transactions with a commodity code assigned.</span></span> <span data-ttu-id="bc032-178">Las transacciones sin un código de mercancía no se transferirán a intrastat.</span><span class="sxs-lookup"><span data-stu-id="bc032-178">Transactions without a commodity code won't be transferred to Intrastat.</span></span>  
11. <span data-ttu-id="bc032-179">En el campo Transferir cuando se cumpla el criterio para, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="bc032-179">In the Transfer when meeting criterion for field, select an option.</span></span>
    * <span data-ttu-id="bc032-180">Por ejemplo, seleccione "Uno de los seleccionados”.</span><span class="sxs-lookup"><span data-stu-id="bc032-180">For example, select 'One of the selected'.</span></span>  
12. <span data-ttu-id="bc032-181">Expanda la sección Jerarquía de códigos de mercancías.</span><span class="sxs-lookup"><span data-stu-id="bc032-181">Expand the Commodity code hierarchy section.</span></span>
13. <span data-ttu-id="bc032-182">Haga clic en la ficha Propiedades de país/región.</span><span class="sxs-lookup"><span data-stu-id="bc032-182">Click the Country/region properties tab.</span></span>
14. <span data-ttu-id="bc032-183">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bc032-183">Click New.</span></span>
15. <span data-ttu-id="bc032-184">En el campo País o región, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-184">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-185">Por ejemplo: seleccione el valor "FRA".</span><span class="sxs-lookup"><span data-stu-id="bc032-185">For example, select the value 'FRA'.</span></span>  
16. <span data-ttu-id="bc032-186">En el campo Código intrastat, especifique el código ISO para el país.</span><span class="sxs-lookup"><span data-stu-id="bc032-186">In the Intrastat code field, enter the ISO code for the country.</span></span>
    * <span data-ttu-id="bc032-187">Por ejemplo, escriba "FR".</span><span class="sxs-lookup"><span data-stu-id="bc032-187">For example, type 'FR'.</span></span>  
17. <span data-ttu-id="bc032-188">En el campo Tipo de país/región, seleccione "UE".</span><span class="sxs-lookup"><span data-stu-id="bc032-188">In the Country/region type field, select 'EU'.</span></span>
18. <span data-ttu-id="bc032-189">Haga clic en la ficha Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="bc032-189">Click the Number sequences tab.</span></span>

## <a name="set-up-modes-of-delivery-and-rules-for-including-charges-in-intrastat"></a><span data-ttu-id="bc032-190">Configurar los modos de entrega y las reglas para incluir gastos en intrastat</span><span class="sxs-lookup"><span data-stu-id="bc032-190">Set up Modes of delivery and rules for including charges in Intrastat</span></span>
1. <span data-ttu-id="bc032-191">Vaya a Ventas y marketing > Configurar > Distribución > Modos de entrega</span><span class="sxs-lookup"><span data-stu-id="bc032-191">Go to Sales and marketing > Setup > Distribution > Modes of delivery</span></span>
2. <span data-ttu-id="bc032-192">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="bc032-192">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="bc032-193">Por ejemplo, seleccione "20 Air".</span><span class="sxs-lookup"><span data-stu-id="bc032-193">For example, select '20 Air'.</span></span>  
3. <span data-ttu-id="bc032-194">Expanda la sección Comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="bc032-194">Expand the Foreign trade section.</span></span>
4. <span data-ttu-id="bc032-195">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="bc032-195">Click Edit.</span></span>
5. <span data-ttu-id="bc032-196">En el campo Transporte, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-196">In the Transport field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-197">Por ejemplo, seleccione "'02".</span><span class="sxs-lookup"><span data-stu-id="bc032-197">For example, select '02'.</span></span>  
6. <span data-ttu-id="bc032-198">Vaya a Clientes > Configuración de cargos > Código de gastos.</span><span class="sxs-lookup"><span data-stu-id="bc032-198">Go to Accounts receivable > Charges setup > Charges code.</span></span>
7. <span data-ttu-id="bc032-199">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="bc032-199">Use the Quick Filter to find records.</span></span> <span data-ttu-id="bc032-200">Por ejemplo, filtre el campo Código de gastos según el valor "flete".</span><span class="sxs-lookup"><span data-stu-id="bc032-200">For example, filter on the Charges code field with a value of 'freight'.</span></span>
8. <span data-ttu-id="bc032-201">Expanda la sección Comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="bc032-201">Expand the Foreign trade section.</span></span>
9. <span data-ttu-id="bc032-202">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="bc032-202">Click Edit.</span></span>
10. <span data-ttu-id="bc032-203">Seleccione Sí en el campo Valor de la factura de intrastat.</span><span class="sxs-lookup"><span data-stu-id="bc032-203">Select Yes in the Intrastat invoice value field.</span></span>
    * <span data-ttu-id="bc032-204">El importe se transferirá al campo Gastos de factura y se resumirá con el importe transferido en el campo Importe de la factura.</span><span class="sxs-lookup"><span data-stu-id="bc032-204">The amount will be transferred to the  Invoice charges field and will be summarized with the amount transferred in the Invoice amount field.</span></span>    <span data-ttu-id="bc032-205">Seleccione Sí en el campo Valor estadístico de intrastat si el importe de los cambios se tiene que transferir al campo Gastos estadísticos y resumirse con el Importe estadístico.</span><span class="sxs-lookup"><span data-stu-id="bc032-205">Select Yes in the Intrastat statistical value field if the amount of changes need to be transferred to the field Statistical charges and summarized with Statistical amount.</span></span>  

## <a name="sell-products-for-eu-customers"></a><span data-ttu-id="bc032-206">Vender productos para los clientes de la UE</span><span class="sxs-lookup"><span data-stu-id="bc032-206">Sell products for EU customers</span></span>
1. <span data-ttu-id="bc032-207">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="bc032-207">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="bc032-208">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bc032-208">Click New.</span></span>
3. <span data-ttu-id="bc032-209">En el campo Cuenta de cliente, seleccione un cliente de UE.</span><span class="sxs-lookup"><span data-stu-id="bc032-209">In the Customer account field, select an EU customer</span></span>
    * <span data-ttu-id="bc032-210">Por ejemplo, seleccione "DE-012 Litware Retail".</span><span class="sxs-lookup"><span data-stu-id="bc032-210">For example, select "DE-012 Litware Retail".</span></span>  
4. <span data-ttu-id="bc032-211">Expanda la sección Entrega.</span><span class="sxs-lookup"><span data-stu-id="bc032-211">Expand the Delivery section.</span></span>
5. <span data-ttu-id="bc032-212">En el campo Entrega, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-212">In the Mode of delivery field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-213">Por ejemplo, seleccione "20 Air".</span><span class="sxs-lookup"><span data-stu-id="bc032-213">For example, select '20 Air'.</span></span>  
6. <span data-ttu-id="bc032-214">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-214">Click OK.</span></span>
7. <span data-ttu-id="bc032-215">Coloque el cursor en la primera fila de las líneas de pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="bc032-215">Place the cursor on the first row of sales order lines.</span></span>
8. <span data-ttu-id="bc032-216">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-216">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-217">Por ejemplo, seleccione "D001".</span><span class="sxs-lookup"><span data-stu-id="bc032-217">For example, select 'D001'.</span></span>  
9. <span data-ttu-id="bc032-218">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="bc032-218">Expand the Line details section.</span></span>
10. <span data-ttu-id="bc032-219">Haga clic en la ficha Comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="bc032-219">Click the Foreign trade tab.</span></span>
    * <span data-ttu-id="bc032-220">El transporte se rellena automáticamente desde el modo de entrega elegido.</span><span class="sxs-lookup"><span data-stu-id="bc032-220">The transport is filled automatically from the chosen Mode of delivery.</span></span>  
11. <span data-ttu-id="bc032-221">En el campo Puerto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-221">In the Port field, enter or select a value.</span></span>
12. <span data-ttu-id="bc032-222">Haga clic en Operaciones financieras.</span><span class="sxs-lookup"><span data-stu-id="bc032-222">Click Financials.</span></span>
    * <span data-ttu-id="bc032-223">Según la configuración, este importe se incluirá en el Valor de la factura de intrastat.</span><span class="sxs-lookup"><span data-stu-id="bc032-223">As per the settings, this amount will be included in Intrastat invoice value.</span></span>  
13. <span data-ttu-id="bc032-224">Haga clic en Mantener gastos.</span><span class="sxs-lookup"><span data-stu-id="bc032-224">Click Maintain charges.</span></span>
14. <span data-ttu-id="bc032-225">En el campo Código de gastos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-225">In the Charges code field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-226">Por ejemplo, seleccione "FLETE".</span><span class="sxs-lookup"><span data-stu-id="bc032-226">For example, select 'FREIGHT'.</span></span>  
15. <span data-ttu-id="bc032-227">Active la casilla Conservar.</span><span class="sxs-lookup"><span data-stu-id="bc032-227">Select the Keep check box.</span></span>
16. <span data-ttu-id="bc032-228">En el campo Valor de gastos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="bc032-228">In the Charges value field, enter a number.</span></span>
    * <span data-ttu-id="bc032-229">Por ejemplo, escribe "10".</span><span class="sxs-lookup"><span data-stu-id="bc032-229">For example, enter '10'.</span></span>  
17. <span data-ttu-id="bc032-230">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bc032-230">Click Save.</span></span>
18. <span data-ttu-id="bc032-231">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bc032-231">Close the page.</span></span>
19. <span data-ttu-id="bc032-232">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="bc032-232">On the Action Pane, click Invoice.</span></span>
20. <span data-ttu-id="bc032-233">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="bc032-233">Click Invoice.</span></span>
21. <span data-ttu-id="bc032-234">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="bc032-234">Expand the Parameters section.</span></span>
22. <span data-ttu-id="bc032-235">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="bc032-235">In the Quantity field, select 'All'.</span></span>
23. <span data-ttu-id="bc032-236">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="bc032-236">Expand the Setup section.</span></span>
24. <span data-ttu-id="bc032-237">En el campo Fecha de la factura, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="bc032-237">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="bc032-238">Por ejemplo, escriba "31-01-2015".</span><span class="sxs-lookup"><span data-stu-id="bc032-238">For example, enter '2015-01-31'.</span></span>  
25. <span data-ttu-id="bc032-239">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-239">Click OK.</span></span>
26. <span data-ttu-id="bc032-240">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-240">Click OK.</span></span>
27. <span data-ttu-id="bc032-241">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bc032-241">Close the page.</span></span>
28. <span data-ttu-id="bc032-242">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bc032-242">Click New.</span></span>
29. <span data-ttu-id="bc032-243">En el campo Cuenta de cliente, seleccione un cliente de UE.</span><span class="sxs-lookup"><span data-stu-id="bc032-243">In the Customer account field, select an EU customer.</span></span>
    * <span data-ttu-id="bc032-244">Por ejemplo, seleccione "DE-013 Trey Wholesales"</span><span class="sxs-lookup"><span data-stu-id="bc032-244">For example, select 'DE-013 Trey Wholesales'</span></span>  
30. <span data-ttu-id="bc032-245">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-245">Click OK.</span></span>
31. <span data-ttu-id="bc032-246">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-246">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="bc032-247">Por ejemplo, seleccione "D0001".</span><span class="sxs-lookup"><span data-stu-id="bc032-247">For example, select 'D0001'.</span></span>  
32. <span data-ttu-id="bc032-248">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bc032-248">Click Save.</span></span>
33. <span data-ttu-id="bc032-249">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="bc032-249">Click Invoice.</span></span>
34. <span data-ttu-id="bc032-250">En el campo Fecha de la factura, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="bc032-250">In the Invoice date field, enter a date.</span></span>
    * <span data-ttu-id="bc032-251">Por ejemplo, especifique la fecha "31-01-2015".</span><span class="sxs-lookup"><span data-stu-id="bc032-251">For example, enter the date '2015-01-31'.</span></span>  
35. <span data-ttu-id="bc032-252">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-252">Click OK.</span></span>
36. <span data-ttu-id="bc032-253">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-253">Click OK.</span></span>

## <a name="transfer-transactions-to-the-intrastat"></a><span data-ttu-id="bc032-254">Transferir transacciones a intrastat</span><span class="sxs-lookup"><span data-stu-id="bc032-254">Transfer transactions to the Intrastat</span></span>
1. <span data-ttu-id="bc032-255">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="bc032-255">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
2. <span data-ttu-id="bc032-256">Haga clic en Transferir.</span><span class="sxs-lookup"><span data-stu-id="bc032-256">Click Transfer.</span></span>
3. <span data-ttu-id="bc032-257">Seleccione Sí en el campo Factura del cliente.</span><span class="sxs-lookup"><span data-stu-id="bc032-257">Select Yes in the Customer invoice field.</span></span>
4. <span data-ttu-id="bc032-258">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="bc032-258">Click Filter.</span></span>
5. <span data-ttu-id="bc032-259">En la lista, marque la fila con Fecha</span><span class="sxs-lookup"><span data-stu-id="bc032-259">In the list, mark the row with Date</span></span>
6. <span data-ttu-id="bc032-260">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bc032-260">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="bc032-261">Por ejemplo, escriba el filtro para el período de enero de 2015 (el valor exacto depende del formato de fecha): 1/1/2015..31/1/2015</span><span class="sxs-lookup"><span data-stu-id="bc032-261">For example, enter the filter for the period January 2015 (the exact value depends on your date format): 1/1/2015..1/31/2015</span></span>  
7. <span data-ttu-id="bc032-262">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-262">Click OK.</span></span>
8. <span data-ttu-id="bc032-263">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bc032-263">Click OK.</span></span>
9. <span data-ttu-id="bc032-264">En la lista, busque y seleccione el registro transferido.</span><span class="sxs-lookup"><span data-stu-id="bc032-264">In the list, find and selected the transferred record.</span></span>
10. <span data-ttu-id="bc032-265">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="bc032-265">Click the General tab.</span></span>
    * <span data-ttu-id="bc032-266">Revise los datos transferidos, incluidos el país o la región de destino/envío, el país de origen, el peso, la cantidad, la cantidad en unidades adicionales, la mercancía, el código de transacción, los importes de factura y los importes estadísticos.</span><span class="sxs-lookup"><span data-stu-id="bc032-266">Review transferred data, including country\region of destination/dispatch, country of origin, weight, quantity, quantity in additional units, commodity, transaction code, invoice amounts and statistical amounts.</span></span>   <span data-ttu-id="bc032-267">Puede modificar los datos, si procede.</span><span class="sxs-lookup"><span data-stu-id="bc032-267">You can modify data if necessary.</span></span>  


