---
title: Especificación de impuestos por informe de transacción contable
description: Este tema explica cómo usar la especificación de impuestos por libro mayor de la transacción contable que desea ver e imprimir información sobre transacciones contables que los impuestos se calcularán para.
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 75913edcbac0151d5d27d866ff5430b194c62738
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815269"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="9170f-103">Especificación de impuestos por informe de transacción contable</span><span class="sxs-lookup"><span data-stu-id="9170f-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="9170f-104">Este tema explica cómo usar la **Especificación de impuestos por libro mayor de la transacción contable** que desea ver e imprimir información sobre transacciones contables que los impuestos se calcularán para.</span><span class="sxs-lookup"><span data-stu-id="9170f-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="9170f-105">Cuentas de impuestos contra cuentas no fiscales</span><span class="sxs-lookup"><span data-stu-id="9170f-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="9170f-106">El informe **Especificación de impuestos por transacción de libro mayor** muestra las transacciones de impuestos para las cuentas de impuestos y las no fiscales.</span><span class="sxs-lookup"><span data-stu-id="9170f-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="9170f-107">Estas cuentas se clasifican así:</span><span class="sxs-lookup"><span data-stu-id="9170f-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="9170f-108">**Cuenta de impuestos**- Una cuenta se considera una cuenta de impuestos cuando se registra una transacción de impuestos, y la cuenta principal en la línea de diario **Impuestos** es una cuenta de impuestos, como una cuenta de impuestos repercutidos o una cuenta de impuestos soportados.</span><span class="sxs-lookup"><span data-stu-id="9170f-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="9170f-109">**Cuenta no fiscal**- Una cuenta se considera una cuenta no fiscal cuando se registra una transacción de impuestos, y la cuenta principal en la transacción original es una cuenta no fiscal, como una cuenta de ingresos o de gastos.</span><span class="sxs-lookup"><span data-stu-id="9170f-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="9170f-110">Para las cuentas de impuestos, las columnas **Origen**, **Impuestos soportados** e **Impuesto repercutidos** en el informe muestran **0** (cero).</span><span class="sxs-lookup"><span data-stu-id="9170f-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="9170f-111">Para las cuentas no fiscales, las columnas muestran importes.</span><span class="sxs-lookup"><span data-stu-id="9170f-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="9170f-112">Filtrar los datos del informe</span><span class="sxs-lookup"><span data-stu-id="9170f-112">Filtering the data on the report</span></span>

<span data-ttu-id="9170f-113">Cuando genere el informe, los siguientes campos predeterminados estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="9170f-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="9170f-114">Puede usar estos campos para filtrar los datos que se muestran en el informe.</span><span class="sxs-lookup"><span data-stu-id="9170f-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="9170f-115">Campo</span><span class="sxs-lookup"><span data-stu-id="9170f-115">Field</span></span>                      | <span data-ttu-id="9170f-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9170f-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="9170f-117">Fecha</span><span class="sxs-lookup"><span data-stu-id="9170f-117">Date</span></span>                       | <span data-ttu-id="9170f-118">Use los campos en las secciones **De** y **A** para definir un intervalo de fechas para las transacciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="9170f-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="9170f-119">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="9170f-119">Main account</span></span>               | <span data-ttu-id="9170f-120">Use los campos en las secciones **De** y **A** para definir un intervalo de cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="9170f-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="9170f-121">Código de impuestos</span><span class="sxs-lookup"><span data-stu-id="9170f-121">Sales tax code</span></span>             | <span data-ttu-id="9170f-122">Use los campos en las secciones **De** y **A** para definir un intervalo de códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="9170f-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="9170f-123">Agrupación</span><span class="sxs-lookup"><span data-stu-id="9170f-123">Grouping</span></span>                   | <span data-ttu-id="9170f-124">Seleccione si se debe agrupar por cuenta contable o código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="9170f-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="9170f-125">Subtotal por código de impuestos</span><span class="sxs-lookup"><span data-stu-id="9170f-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="9170f-126">Establezca esta opción a **Sí** para mostrar los subtotales por código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="9170f-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="9170f-127">Solo totales</span><span class="sxs-lookup"><span data-stu-id="9170f-127">Totals only</span></span>                | <span data-ttu-id="9170f-128">Establezca esta opción a **Sí** para mostrar únicamente los totales.</span><span class="sxs-lookup"><span data-stu-id="9170f-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="9170f-129">Solo cuentas principales</span><span class="sxs-lookup"><span data-stu-id="9170f-129">Main accounts only</span></span>         | <span data-ttu-id="9170f-130">Establezca esta opción a **Sí** para incluir sólo las cuentas principales en el informe.</span><span class="sxs-lookup"><span data-stu-id="9170f-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="9170f-131">Mostrar únicamente las cuentas no fiscales en el informe</span><span class="sxs-lookup"><span data-stu-id="9170f-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="9170f-132">Para mostrar únicamente las cuentas no fiscales en el informe, configure una condición de filtro, como un asterisco (\*), como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="9170f-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![Informe que muestra cuentas no fiscales](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]