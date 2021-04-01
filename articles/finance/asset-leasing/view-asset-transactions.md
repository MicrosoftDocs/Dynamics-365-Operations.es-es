---
title: Ver transacciones de pasivos, activos y gastos
description: Este tema explica cómo ver las transacciones de un activo arrendado. Estas transacciones incluyen transacciones de pasivo por arrendamiento y transacciones de gastos de ejecución que se han registrado.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 17753087adb835b4632e929451e2cf3e2d772ed4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249542"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="653b7-104">Ver transacciones de pasivos, activos y gastos</span><span class="sxs-lookup"><span data-stu-id="653b7-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="653b7-105">Este tema explica cómo ver las transacciones de un activo arrendado.</span><span class="sxs-lookup"><span data-stu-id="653b7-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="653b7-106">Estas transacciones incluyen transacciones de pasivo por arrendamiento y transacciones de gastos de ejecución que se han registrado.</span><span class="sxs-lookup"><span data-stu-id="653b7-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="653b7-107">Los valores en libros del activo de pasivo y por derecho de uso (ROU) se utilizan en varios informes.</span><span class="sxs-lookup"><span data-stu-id="653b7-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="653b7-108">También se utilizan para calcular valores de ajuste.</span><span class="sxs-lookup"><span data-stu-id="653b7-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="653b7-109">Transacciones de pasivos</span><span class="sxs-lookup"><span data-stu-id="653b7-109">Liability transactions</span></span>

<span data-ttu-id="653b7-110">Para ver las transacciones de pasivos por arrendamiento, seleccione un arrendamiento en la página **Resumen de arrendamientos** y luego seleccione **Libros** para abrir los libros que se adjuntan al registro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="653b7-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="653b7-111">Después de que se haya registrado un reconocimiento inicial, una factura o un diario de intereses, seleccione **Transacciones de pasivo**.</span><span class="sxs-lookup"><span data-stu-id="653b7-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="653b7-112">La página **Transacciones de pasivo** muestra las transacciones que aumentan o disminuyen el pasivo por arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="653b7-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="653b7-113">Los importes negativos de esta página representan transacciones de crédito en la aplicación estándar.</span><span class="sxs-lookup"><span data-stu-id="653b7-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="653b7-114">Cualquier acumulación de intereses se muestra como valores negativos y aumenta el pasivo por arrendamiento total.</span><span class="sxs-lookup"><span data-stu-id="653b7-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="653b7-115">Cualquier ajuste de arrendamiento se muestra como valores positivos o negativos, dependiendo de la naturaleza y el impacto del libro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="653b7-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="653b7-116">El saldo total neto actual del pasivo por arrendamiento para el arrendamiento seleccionado se muestra en la parte inferior izquierda de la página.</span><span class="sxs-lookup"><span data-stu-id="653b7-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="653b7-117">Transacciones de activos</span><span class="sxs-lookup"><span data-stu-id="653b7-117">Asset transactions</span></span>

<span data-ttu-id="653b7-118">Para ver las transacciones de activos por arrendamiento, seleccione un arrendamiento en la página **Resumen de arrendamientos** y luego seleccione **Libros** para abrir los libros de arrendamiento adjuntos al registro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="653b7-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="653b7-119">A continuación, seleccione **Transacciones de activos**.</span><span class="sxs-lookup"><span data-stu-id="653b7-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="653b7-120">La página **Transacciones de activos** muestra las transacciones que aumentan o disminuyen el activo de arrendamiento y las cuentas de depreciación acumulada.</span><span class="sxs-lookup"><span data-stu-id="653b7-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="653b7-121">Los débitos se muestran como valores positivos y los créditos se muestran como valores negativos, como en la página **Transacciones de pasivos**.</span><span class="sxs-lookup"><span data-stu-id="653b7-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="653b7-122">El reconocimiento inicial publicado y el siguiente de la depreciación acumulada se muestran en la parte inferior izquierda de la página como saldo de activos.</span><span class="sxs-lookup"><span data-stu-id="653b7-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="653b7-123">Transacciones de gastos</span><span class="sxs-lookup"><span data-stu-id="653b7-123">Expenses transactions</span></span>

<span data-ttu-id="653b7-124">Para ver las transacciones de gastos por arrendamiento, seleccione un arrendamiento en la página **Resumen de arrendamientos** y luego seleccione **Libros** para abrir los libros de arrendamiento adjuntos al registro de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="653b7-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="653b7-125">A continuación, seleccione **Transacciones de gastos**.</span><span class="sxs-lookup"><span data-stu-id="653b7-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="653b7-126">La página **Transacciones de gastos** muestra todos los gastos que se han registrado contra el arrendamiento, como los gastos por intereses, los gastos de depreciación y los gastos a cargo del arrendatario en un arrendamiento de capital.</span><span class="sxs-lookup"><span data-stu-id="653b7-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]