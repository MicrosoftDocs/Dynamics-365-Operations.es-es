---
title: "Secuencias numéricas"
description: "Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores."
author: MargoC
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 15461
ms.assetid: 6e19bd1d-192b-4da2-8573-84f6e1ce98ef
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5f4ff7eb8ee9b87b9d90af4d215743596555fd73
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="number-sequences"></a><span data-ttu-id="1e967-103">Secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="1e967-103">Number sequences</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1e967-104">Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que necesitan identificadores.</span><span class="sxs-lookup"><span data-stu-id="1e967-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require identifiers.</span></span> <span data-ttu-id="1e967-105">El registro de datos maestros o de transacciones que necesita un identificador se denomina *referencia*.</span><span class="sxs-lookup"><span data-stu-id="1e967-105">A master data record or transaction record that requires an identifier is referred to as a *reference*.</span></span>

<span data-ttu-id="1e967-106">Antes de poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia.</span><span class="sxs-lookup"><span data-stu-id="1e967-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="1e967-107">Se recomienda usar las páginas en **Administración de la organización** para configurar secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="1e967-107">We recommend that you use the pages in **Organization administration** to set up number sequences.</span></span> <span data-ttu-id="1e967-108">Si se requiere una configuración de módulo específica, puede usar la página de parámetros en un módulo para especificar secuencias numéricas para sus referencias.</span><span class="sxs-lookup"><span data-stu-id="1e967-108">If module-specific settings are required, you can use the parameters page in a module to specify number sequences for the references in that module.</span></span> <span data-ttu-id="1e967-109">Por ejemplo, en **Clientes** y **Proveedores**, puede configurar también grupos de secuencias numéricas para asignar secuencias numéricas específicas a proveedores o clientes concretos.</span><span class="sxs-lookup"><span data-stu-id="1e967-109">For example, in **Accounts receivable** and **Accounts payable**, you can set up number sequence groups to allocate specific number sequences to specific customers or vendors.</span></span> 

<span data-ttu-id="1e967-110">Al configurar una secuencia numérica, debe especificar un ámbito, que defina qué organización usa la secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="1e967-110">When you set up a number sequence, you must specify a scope, which defines which organization uses the number sequence.</span></span> <span data-ttu-id="1e967-111">El ámbito puede ser **Compartido**, **Empresa**, **Entidad jurídica** o **Unidad operativa**.</span><span class="sxs-lookup"><span data-stu-id="1e967-111">The scope can be **Shared**, **Company**, **Legal entity**, or **Operating unit**.</span></span> <span data-ttu-id="1e967-112">Los ámbitos **Entidad jurídica** y **Empresa** también se pueden combinar con **Período de calendario fiscal** para crear secuencias numéricas más específicas incluso.</span><span class="sxs-lookup"><span data-stu-id="1e967-112">**Legal entity** and **Company** scopes can be combined with **Fiscal calendar period** to create even more specific number sequences.</span></span> 

<span data-ttu-id="1e967-113">Los formatos de secuencia numérica constan de segmentos.</span><span class="sxs-lookup"><span data-stu-id="1e967-113">Number sequence formats consist of segments.</span></span> <span data-ttu-id="1e967-114">Las secuencias numéricas con un ámbito distinto a **Compartido** pueden contener segmentos que correspondan al ámbito.</span><span class="sxs-lookup"><span data-stu-id="1e967-114">Number sequences with a scope other than **Shared** can contain segments that correspond to the scope.</span></span> <span data-ttu-id="1e967-115">Por ejemplo, una secuencia numérica con un ámbito **Entidad jurídica** puede contener un segmento de entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="1e967-115">For example, a number sequence with a scope of **Legal entity** can contain a legal entity segment.</span></span> <span data-ttu-id="1e967-116">Al incluir un segmento de ámbito en el formato de secuencia numérica, puede identificar el ámbito de un registro concreto mirando su número.</span><span class="sxs-lookup"><span data-stu-id="1e967-116">By including a scope segment in the number sequence format, you can identify the scope of a particular record by looking at its number.</span></span> 

<span data-ttu-id="1e967-117">Además de los segmentos correspondientes a ámbitos, los formatos de secuencia numérica pueden contener segmentos **Constante** y **Alfanumérico**.</span><span class="sxs-lookup"><span data-stu-id="1e967-117">In addition to segments that correspond to scopes, number sequence formats can contain **Constant** and **Alphanumeric segments**.</span></span> <span data-ttu-id="1e967-118">Un segmento **Constante** contiene un conjunto de letras, números o símbolos que no cambian.</span><span class="sxs-lookup"><span data-stu-id="1e967-118">A **Constant** segment contains a set of letters, numbers, or symbols that does not change.</span></span> <span data-ttu-id="1e967-119">Un segmento **Alfanumérico** contiene un conjunto de letras o números que aumentan cada vez que se usa un número.</span><span class="sxs-lookup"><span data-stu-id="1e967-119">An **Alphanumeric** segment contains a set of letters or numbers that increment every time that a number is used.</span></span> <span data-ttu-id="1e967-120">Use un signo de número (\#) para representar el incremento de números y un ampersand (&) para representar un incremento de letras.</span><span class="sxs-lookup"><span data-stu-id="1e967-120">Use a number sign (\#) to represent incrementing numbers and an ampersand (&) to represent incrementing letters.</span></span> <span data-ttu-id="1e967-121">Por ejemplo, el formato \#\#\#\#\#\_2017 crea la secuencia 00001\_2017, 00002\_2017, etc.</span><span class="sxs-lookup"><span data-stu-id="1e967-121">For example, the format \#\#\#\#\#\_2017 creates the sequence 00001\_2017, 00002\_2017, and so on.</span></span>

<a name="number-sequence-examples"></a><span data-ttu-id="1e967-122">Ejemplos de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="1e967-122">Number sequence examples</span></span>
------------------------

<span data-ttu-id="1e967-123">En los siguientes ejemplos se muestra cómo usar segmentos para crear formatos de secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="1e967-123">The following examples show how to use segments to create number sequence formats.</span></span> <span data-ttu-id="1e967-124">En concreto, en los ejemplos se muestran los efectos del uso de segmentos de ámbito.</span><span class="sxs-lookup"><span data-stu-id="1e967-124">In particular, the examples demonstrate the effects of using scope segments.</span></span>

### <a name="expense-report-numbers"></a><span data-ttu-id="1e967-125">Números de informes de gastos</span><span class="sxs-lookup"><span data-stu-id="1e967-125">Expense report numbers</span></span>

<span data-ttu-id="1e967-126">En el siguiente ejemplo, los números de informe de gastos se configuran para la entidad jurídica titulada **CS**.</span><span class="sxs-lookup"><span data-stu-id="1e967-126">In the following example, expense report numbers are set up for the legal entity that is titled **CS**.</span></span> 

- <span data-ttu-id="1e967-127">**Área:** Viajes y gastos</span><span class="sxs-lookup"><span data-stu-id="1e967-127">**Area:** Travel and expense</span></span> 
- <span data-ttu-id="1e967-128">**Referencia:** Número de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="1e967-128">**Reference:** Expense report number</span></span> 
- <span data-ttu-id="1e967-129">**Ámbito:** Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="1e967-129">**Scope:** Legal entity</span></span> 
- <span data-ttu-id="1e967-130">**Entidad jurídica:** CS</span><span class="sxs-lookup"><span data-stu-id="1e967-130">**Legal entity:** CS</span></span>

| <span data-ttu-id="1e967-131">Segmentos</span><span class="sxs-lookup"><span data-stu-id="1e967-131">Segments</span></span>  | <span data-ttu-id="1e967-132">Tipo de segmento</span><span class="sxs-lookup"><span data-stu-id="1e967-132">Segment type</span></span> | <span data-ttu-id="1e967-133">Valor</span><span class="sxs-lookup"><span data-stu-id="1e967-133">Value</span></span>     |
|-----------|--------------|-----------|
| <span data-ttu-id="1e967-134">Segmento 1</span><span class="sxs-lookup"><span data-stu-id="1e967-134">Segment 1</span></span> | <span data-ttu-id="1e967-135">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="1e967-135">Legal entity</span></span> | <span data-ttu-id="1e967-136">CS</span><span class="sxs-lookup"><span data-stu-id="1e967-136">CS</span></span>        |
| <span data-ttu-id="1e967-137">Segmento 2</span><span class="sxs-lookup"><span data-stu-id="1e967-137">Segment 2</span></span> | <span data-ttu-id="1e967-138">Constante</span><span class="sxs-lookup"><span data-stu-id="1e967-138">Constant</span></span>     | <span data-ttu-id="1e967-139">-GASTO-</span><span class="sxs-lookup"><span data-stu-id="1e967-139">-EXPENSE-</span></span> |
| <span data-ttu-id="1e967-140">Segmento 3</span><span class="sxs-lookup"><span data-stu-id="1e967-140">Segment 3</span></span> | <span data-ttu-id="1e967-141">Alfanumérico</span><span class="sxs-lookup"><span data-stu-id="1e967-141">Alphanumeric</span></span> | \#\#\#\#  |

<span data-ttu-id="1e967-142">**Ejemplo del número con formato**: CS-EXPENSE-0039</span><span class="sxs-lookup"><span data-stu-id="1e967-142">**Example of formatted number**: CS-EXPENSE-0039</span></span> 

<span data-ttu-id="1e967-143">Puede configurar un formato de secuencia numérica similar para otras entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="1e967-143">You can set up a similar number sequence format for other legal entities.</span></span> <span data-ttu-id="1e967-144">Por ejemplo, para una entidad jurídica que se denomina **RW**, si cambia únicamente el valor del segmento de la entidad jurídica, el número con formato es RW-EXPENSE-0039.</span><span class="sxs-lookup"><span data-stu-id="1e967-144">For example, for a legal entity that is named **RW**, if you change only the value of the legal entity segment, the formatted number is RW-EXPENSE-0039.</span></span> <span data-ttu-id="1e967-145">También puede cambiar el formato de secuencia numérica completo para otras entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="1e967-145">You can also change the whole number sequence format for other legal entities.</span></span> <span data-ttu-id="1e967-146">Por ejemplo, puede omitir el segmento de ámbito de entidad jurídica para crear un número con formato como Exp-0001.</span><span class="sxs-lookup"><span data-stu-id="1e967-146">For example, you can omit the legal entity scope segment to create a formatted number such as Exp-0001.</span></span>

### <a name="sales-order-numbers"></a><span data-ttu-id="1e967-147">Números de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="1e967-147">Sales order numbers</span></span>

<span data-ttu-id="1e967-148">En el siguiente ejemplo, los números de pedidos de ventas se configuran para el id. de empresa **CEU**.</span><span class="sxs-lookup"><span data-stu-id="1e967-148">In the following example, sales order numbers are set up for the company ID **CEU**.</span></span> 

- <span data-ttu-id="1e967-149">**Área:** Ventas</span><span class="sxs-lookup"><span data-stu-id="1e967-149">**Area:** Sales</span></span> 
- <span data-ttu-id="1e967-150">**Referencia:** Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="1e967-150">**Reference:** Sales order</span></span> 
- <span data-ttu-id="1e967-151">**Ámbito:** Empresa</span><span class="sxs-lookup"><span data-stu-id="1e967-151">**Scope:** Company</span></span> 
- <span data-ttu-id="1e967-152">**Empresa:** CEU</span><span class="sxs-lookup"><span data-stu-id="1e967-152">**Company:** CEU</span></span>

| <span data-ttu-id="1e967-153">Segmentos</span><span class="sxs-lookup"><span data-stu-id="1e967-153">Segments</span></span>  | <span data-ttu-id="1e967-154">Tipo de segmento</span><span class="sxs-lookup"><span data-stu-id="1e967-154">Segment type</span></span> | <span data-ttu-id="1e967-155">Valor</span><span class="sxs-lookup"><span data-stu-id="1e967-155">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="1e967-156">Segmento 1</span><span class="sxs-lookup"><span data-stu-id="1e967-156">Segment 1</span></span> | <span data-ttu-id="1e967-157">Constante</span><span class="sxs-lookup"><span data-stu-id="1e967-157">Constant</span></span>     | <span data-ttu-id="1e967-158">SO-</span><span class="sxs-lookup"><span data-stu-id="1e967-158">SO-</span></span>      |
| <span data-ttu-id="1e967-159">Segmento 2</span><span class="sxs-lookup"><span data-stu-id="1e967-159">Segment 2</span></span> | <span data-ttu-id="1e967-160">Alfanumérico</span><span class="sxs-lookup"><span data-stu-id="1e967-160">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="1e967-161">**Ejemplo de número con formato**: SO-0029</span><span class="sxs-lookup"><span data-stu-id="1e967-161">**Example of formatted number**: SO-0029</span></span> 

<span data-ttu-id="1e967-162">Aunque no se incluye un segmento de ámbito en el formato, la numeración se reinicia para cada id. de empresa.</span><span class="sxs-lookup"><span data-stu-id="1e967-162">Even though a scope segment is not included in the format, numbering restarts for each company ID.</span></span> <span data-ttu-id="1e967-163">Si usa el mismo formato para todos los id. de empresa, se usan los mismos números en cada empresa.</span><span class="sxs-lookup"><span data-stu-id="1e967-163">If you use the same format for all company IDs, the same numbers are used in each company.</span></span> <span data-ttu-id="1e967-164">Por ejemplo, el número de pedido de ventas SO-0029 se usa en cada empresa.</span><span class="sxs-lookup"><span data-stu-id="1e967-164">For example, sales order number SO-0029 is used in each company.</span></span> <span data-ttu-id="1e967-165">También puede cambiar el formato de secuencia numérica completo para otros id. de empresa.</span><span class="sxs-lookup"><span data-stu-id="1e967-165">You can also change the whole number sequence format for other company IDs.</span></span>

### <a name="purchase-requisition-numbers"></a><span data-ttu-id="1e967-166">Números de solicitudes de compra</span><span class="sxs-lookup"><span data-stu-id="1e967-166">Purchase requisition numbers</span></span>

<span data-ttu-id="1e967-167">En el siguiente ejemplo, los números de solicitudes de compra son para toda la organización.</span><span class="sxs-lookup"><span data-stu-id="1e967-167">In the following example, purchase requisition numbers are organization-wide.</span></span> 

- <span data-ttu-id="1e967-168">**Área:** Compras</span><span class="sxs-lookup"><span data-stu-id="1e967-168">**Area:** Purchase</span></span> 
- <span data-ttu-id="1e967-169">**Referencia:** Solicitud de compra</span><span class="sxs-lookup"><span data-stu-id="1e967-169">**Reference:** Purchase requisition</span></span> 
- <span data-ttu-id="1e967-170">**Ámbito:** Compartido</span><span class="sxs-lookup"><span data-stu-id="1e967-170">**Scope:** Shared</span></span>

| <span data-ttu-id="1e967-171">Segmentos</span><span class="sxs-lookup"><span data-stu-id="1e967-171">Segments</span></span>  | <span data-ttu-id="1e967-172">Tipo de segmento</span><span class="sxs-lookup"><span data-stu-id="1e967-172">Segment type</span></span> | <span data-ttu-id="1e967-173">Valor</span><span class="sxs-lookup"><span data-stu-id="1e967-173">Value</span></span>    |
|-----------|--------------|----------|
| <span data-ttu-id="1e967-174">Segmento 1</span><span class="sxs-lookup"><span data-stu-id="1e967-174">Segment 1</span></span> | <span data-ttu-id="1e967-175">Constante</span><span class="sxs-lookup"><span data-stu-id="1e967-175">Constant</span></span>     | <span data-ttu-id="1e967-176">Sol</span><span class="sxs-lookup"><span data-stu-id="1e967-176">Req</span></span>      |
| <span data-ttu-id="1e967-177">Segmento 2</span><span class="sxs-lookup"><span data-stu-id="1e967-177">Segment 2</span></span> | <span data-ttu-id="1e967-178">Alfanumérico</span><span class="sxs-lookup"><span data-stu-id="1e967-178">Alphanumeric</span></span> | \#\#\#\# |

<span data-ttu-id="1e967-179">**Ejemplo de número con formato**: Req0052</span><span class="sxs-lookup"><span data-stu-id="1e967-179">**Example of formatted number**: Req0052</span></span> 

<span data-ttu-id="1e967-180">Debido a que el ámbito es **Compartido**, se usa el formato de secuencia numérica en la organización.</span><span class="sxs-lookup"><span data-stu-id="1e967-180">Because the scope is **Shared**, the number sequence format is used across the organization.</span></span> <span data-ttu-id="1e967-181">No puede configurar diferentes formatos de secuencia numérica para diferentes partes de la organización.</span><span class="sxs-lookup"><span data-stu-id="1e967-181">You cannot set up different number sequence formats for different parts of the organization.</span></span> 

<a name="performance-considerations-for-number-sequences"></a><span data-ttu-id="1e967-182">Consideraciones de rendimiento para secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="1e967-182">Performance considerations for number sequences</span></span>
-----------------------------------------------

<span data-ttu-id="1e967-183">Tenga en cuenta la siguiente información acerca de la manera en que la configuración de las secuencias numéricas puede afectar al rendimiento del sistema para poder configurar secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="1e967-183">Consider the following information about how the configuration of number sequences can affect system performance before you set up number sequences.</span></span>

### <a name="continuous-and-non-continuous-number-sequences"></a><span data-ttu-id="1e967-184">Secuencias numéricas continuas y no continuas</span><span class="sxs-lookup"><span data-stu-id="1e967-184">Continuous and non-continuous number sequences</span></span>

<span data-ttu-id="1e967-185">Las secuencias numéricas pueden ser continuas o no continuas.</span><span class="sxs-lookup"><span data-stu-id="1e967-185">Number sequences can be continuous or non-continuous.</span></span> <span data-ttu-id="1e967-186">Una secuencia numérica continua no omite ningún número aunque los números no se pueden usar secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="1e967-186">A continuous number sequence does not skip any numbers, but numbers may not be used sequentially.</span></span> <span data-ttu-id="1e967-187">Los números de una secuencia numérica no continua se usan secuencialmente pero la secuencia numérica puede omitir números.</span><span class="sxs-lookup"><span data-stu-id="1e967-187">Numbers from a non-continuous number sequence are used sequentially, but the number sequence may skip numbers.</span></span> <span data-ttu-id="1e967-188">Por ejemplo, si un usuario cancela una transacción, se genera un número, aunque no se usa.</span><span class="sxs-lookup"><span data-stu-id="1e967-188">For example, if a user cancels a transaction, a number is generated, but not used.</span></span> <span data-ttu-id="1e967-189">En una secuencia numérica continua, dicho número se recicla posteriormente.</span><span class="sxs-lookup"><span data-stu-id="1e967-189">In a continuous number sequence, that number is recycled later.</span></span> <span data-ttu-id="1e967-190">En una secuencia numérica no continua, no se usa el número.</span><span class="sxs-lookup"><span data-stu-id="1e967-190">In a non-continuous number sequence, the number is not used.</span></span> 

<span data-ttu-id="1e967-191">Las secuencias numéricas continuas se necesitan normalmente para documentos externos, como pedidos de compra, pedidos de ventas y facturas.</span><span class="sxs-lookup"><span data-stu-id="1e967-191">Continuous number sequences are typically required for external documents, such as purchase orders, sales orders, and invoices.</span></span> <span data-ttu-id="1e967-192">Sin embargo, las secuencias numéricas continuas pueden afectar de manera adversa los tiempos de respuesta del sistema porque el sistema debe solicitar un número de la base de datos cada vez que se crea un registro o documento nuevo.</span><span class="sxs-lookup"><span data-stu-id="1e967-192">However, continuous number sequences can adversely affect system response times because the system must request a number from the database every time that a new document or record is created.</span></span> 

<span data-ttu-id="1e967-193">Si usa una secuencia numérica no continua, puede habilitar **Asignación previa** en la ficha desplegable **Rendimiento** de la página **Secuencias numéricas**.</span><span class="sxs-lookup"><span data-stu-id="1e967-193">If you use a non-continuous number sequence, you can enable **Preallocation** on the **Performance** FastTab of the **Number sequences** page.</span></span> <span data-ttu-id="1e967-194">Al especificar una cantidad de números para preasignación, el sistema selecciona dichos números y los almacena en memoria.</span><span class="sxs-lookup"><span data-stu-id="1e967-194">When you specify a quantity of numbers to preallocate, the system selects those numbers and stores them in memory.</span></span> <span data-ttu-id="1e967-195">Los nuevos números se solicitan de la base de datos solo después de que se haya usado la cantidad preasignada.</span><span class="sxs-lookup"><span data-stu-id="1e967-195">New numbers are requested from the database only after the preallocated quantity has been used.</span></span> 

<span data-ttu-id="1e967-196">A menos que haya una norma legal para usar secuencias numéricas continuas, se recomienda usar las secuencias numéricas no continuas para un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1e967-196">Unless there is a regulatory requirement that you use continuous number sequences, we recommend that you use non-continuous number sequences for better performance.</span></span>

### <a name="automatic-cleanup-of-number-sequences"></a><span data-ttu-id="1e967-197">Limpieza automática de secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="1e967-197">Automatic cleanup of number sequences</span></span>

<span data-ttu-id="1e967-198">En caso de fallo eléctrico, un error de aplicación u otro error inesperado, el sistema no podrá reciclar números de manera automática para las secuencias numéricas continuas.</span><span class="sxs-lookup"><span data-stu-id="1e967-198">In case of a power failure, an application error, or other unexpected failure, the system cannot recycle numbers automatically for continuous number sequences.</span></span> <span data-ttu-id="1e967-199">Puede ejecutar el proceso de limpieza manualmente o automáticamente para recuperar los números perdidos.</span><span class="sxs-lookup"><span data-stu-id="1e967-199">You can run the cleanup process manually or automatically to recover the lost numbers.</span></span> 

<span data-ttu-id="1e967-200">Valore detenidamente el uso del servidor al planificar el proceso de limpieza.</span><span class="sxs-lookup"><span data-stu-id="1e967-200">Carefully consider server usage when you plan the cleanup process.</span></span> <span data-ttu-id="1e967-201">Es recomendable que realice la limpieza como un trabajo por lotes durante las horas de menor demanda.</span><span class="sxs-lookup"><span data-stu-id="1e967-201">We recommend that you perform the cleanup as a batch job during non-peak hours.</span></span>






