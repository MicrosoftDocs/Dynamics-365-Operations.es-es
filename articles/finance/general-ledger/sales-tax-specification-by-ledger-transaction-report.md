---
title: Especificación de impuestos por informe de transacción contable
description: Este tema explica cómo usar la especificación de impuestos por libro mayor de la transacción contable que desea ver e imprimir información sobre transacciones contables que los impuestos se calcularán para.
author: ericwang
manager: Ann Beebe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 438a640124e778b839c660f5e161efa22c319af0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447456"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a><span data-ttu-id="97728-103">Especificación de impuestos por informe de transacción contable</span><span class="sxs-lookup"><span data-stu-id="97728-103">Sales tax specification by ledger transaction report</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="97728-104">Este tema explica cómo usar la **Especificación de impuestos por libro mayor de la transacción contable** que desea ver e imprimir información sobre transacciones contables que los impuestos se calcularán para.</span><span class="sxs-lookup"><span data-stu-id="97728-104">This topic explains how to use the **Sales tax specification by ledger transaction** report to view and print information about ledger transactions that sales tax is calculated for.</span></span>

## <a name="tax-accounts-vs-non-tax-accounts"></a><span data-ttu-id="97728-105">Cuentas de impuestos contra cuentas no fiscales</span><span class="sxs-lookup"><span data-stu-id="97728-105">Tax accounts vs. non-tax accounts</span></span>

<span data-ttu-id="97728-106">El informe **Especificación de impuestos por transacción de libro mayor** muestra las transacciones de impuestos para las cuentas de impuestos y las no fiscales.</span><span class="sxs-lookup"><span data-stu-id="97728-106">The **Sales tax specification by ledger transaction** report shows tax transactions for both tax accounts and non-tax accounts.</span></span> <span data-ttu-id="97728-107">Estas cuentas se clasifican así:</span><span class="sxs-lookup"><span data-stu-id="97728-107">These accounts are categorized in the following way:</span></span>

- <span data-ttu-id="97728-108">**Cuenta de impuestos**- Una cuenta se considera una cuenta de impuestos cuando se registra una transacción de impuestos, y la cuenta principal en la línea de diario **Impuestos** es una cuenta de impuestos, como una cuenta de impuestos repercutidos o una cuenta de impuestos soportados.</span><span class="sxs-lookup"><span data-stu-id="97728-108">**Tax account** – An account is considered a tax account when a tax transaction is posted, and the main account on the **Sales Tax** journal line is a tax account, such as a sales tax payable account or a sales tax receivable account.</span></span>
- <span data-ttu-id="97728-109">**Cuenta no fiscal**- Una cuenta se considera una cuenta no fiscal cuando se registra una transacción de impuestos, y la cuenta principal en la transacción original es una cuenta no fiscal, como una cuenta de ingresos o de gastos.</span><span class="sxs-lookup"><span data-stu-id="97728-109">**Non-tax account** – An account is considered a non-tax account when a tax transaction is posted, and the main account on the original transaction is a non-tax account, such as a revenue account or an expense account.</span></span>

<span data-ttu-id="97728-110">Para las cuentas de impuestos, las columnas **Origen**, **Impuestos soportados** e **Impuesto repercutidos** en el informe muestran **0** (cero).</span><span class="sxs-lookup"><span data-stu-id="97728-110">For tax accounts, the **Origin**, **Sales tax receivable**, and **Sales tax payable** columns on the report show **0** (zero).</span></span> <span data-ttu-id="97728-111">Para las cuentas no fiscales, las columnas muestran importes.</span><span class="sxs-lookup"><span data-stu-id="97728-111">For non-tax accounts, those columns show amounts.</span></span>

## <a name="filtering-the-data-on-the-report"></a><span data-ttu-id="97728-112">Filtrar los datos del informe</span><span class="sxs-lookup"><span data-stu-id="97728-112">Filtering the data on the report</span></span>

<span data-ttu-id="97728-113">Cuando genere el informe, los siguientes campos predeterminados estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="97728-113">When you generate the report, the following default fields are available.</span></span> <span data-ttu-id="97728-114">Puede usar estos campos para filtrar los datos que se muestran en el informe.</span><span class="sxs-lookup"><span data-stu-id="97728-114">You can use these fields to filter the data that is shown on the report.</span></span>

| <span data-ttu-id="97728-115">Campo</span><span class="sxs-lookup"><span data-stu-id="97728-115">Field</span></span>                      | <span data-ttu-id="97728-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="97728-116">Description</span></span> |
|----------------------------|-------------|
| <span data-ttu-id="97728-117">Fecha</span><span class="sxs-lookup"><span data-stu-id="97728-117">Date</span></span>                       | <span data-ttu-id="97728-118">Use los campos en las secciones **De** y **A** para definir un intervalo de fechas para las transacciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="97728-118">Use the fields in the **From** and **To** sections to define a date range for the tax transactions.</span></span> |
| <span data-ttu-id="97728-119">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="97728-119">Main account</span></span>               | <span data-ttu-id="97728-120">Use los campos en las secciones **De** y **A** para definir un intervalo de cuentas principales.</span><span class="sxs-lookup"><span data-stu-id="97728-120">Use the fields in the **From** and **To** sections to define a range of main accounts.</span></span> |
| <span data-ttu-id="97728-121">Código de impuestos</span><span class="sxs-lookup"><span data-stu-id="97728-121">Sales tax code</span></span>             | <span data-ttu-id="97728-122">Use los campos en las secciones **De** y **A** para definir un intervalo de códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="97728-122">Use the fields in the **From** and **To** sections to define a range of sales tax codes.</span></span> |
| <span data-ttu-id="97728-123">Agrupación</span><span class="sxs-lookup"><span data-stu-id="97728-123">Grouping</span></span>                   | <span data-ttu-id="97728-124">Seleccione si se debe agrupar por cuenta contable o código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="97728-124">Select whether the report should be grouped by ledger account or sales tax code.</span></span> |
| <span data-ttu-id="97728-125">Subtotal por código de impuestos</span><span class="sxs-lookup"><span data-stu-id="97728-125">Subtotal by sales tax code</span></span> | <span data-ttu-id="97728-126">Establezca esta opción a **Sí** para mostrar los subtotales por código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="97728-126">Set this option to **Yes** to show subtotals by sales tax code.</span></span> |
| <span data-ttu-id="97728-127">Solo totales</span><span class="sxs-lookup"><span data-stu-id="97728-127">Totals only</span></span>                | <span data-ttu-id="97728-128">Establezca esta opción a **Sí** para mostrar únicamente los totales.</span><span class="sxs-lookup"><span data-stu-id="97728-128">Set this option to **Yes** to show only totals.</span></span> |
| <span data-ttu-id="97728-129">Solo cuentas principales</span><span class="sxs-lookup"><span data-stu-id="97728-129">Main accounts only</span></span>         | <span data-ttu-id="97728-130">Establezca esta opción a **Sí** para incluir sólo las cuentas principales en el informe.</span><span class="sxs-lookup"><span data-stu-id="97728-130">Set this option to **Yes** to include only main accounts on the report.</span></span> |

## <a name="showing-only-non-tax-accounts-on-the-report"></a><span data-ttu-id="97728-131">Mostrar únicamente las cuentas no fiscales en el informe</span><span class="sxs-lookup"><span data-stu-id="97728-131">Showing only non-tax accounts on the report</span></span>

<span data-ttu-id="97728-132">Para mostrar únicamente las cuentas no fiscales en el informe, configure una condición de filtro, como un asterisco (\*), como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="97728-132">To show only non-tax accounts on the report, set up a filter condition, such as an asterisk (\*), as shown in the following illustration.</span></span>

![Informe que muestra cuentas no fiscales](media/taxspecperledgertrans.png)
