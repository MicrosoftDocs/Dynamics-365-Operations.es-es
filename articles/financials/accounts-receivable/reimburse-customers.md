---
title: Reembolsar a clientes
description: "En este artículo se explica cómo crear transacciones de reembolso de un grupo de clientes. Si un cliente tiene un saldo de crédito, puede reembolsar al cliente por el importe del saldo."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 36e7e684e207e13baffa7eefd13e8e4a29d99914
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="reimburse-customers"></a><span data-ttu-id="af4a8-104">Reembolsar a clientes</span><span class="sxs-lookup"><span data-stu-id="af4a8-104">Reimburse customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af4a8-105">En este artículo se explica cómo crear transacciones de reembolso de un grupo de clientes.</span><span class="sxs-lookup"><span data-stu-id="af4a8-105">This article explains how to create reimbursement transactions for a group of customers.</span></span> <span data-ttu-id="af4a8-106">Si un cliente tiene un saldo de crédito, puede reembolsar al cliente por el importe del saldo.</span><span class="sxs-lookup"><span data-stu-id="af4a8-106">If a customer has a credit balance, you can reimburse the customer for the amount of the balance.</span></span> 

<span data-ttu-id="af4a8-107">La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="af4a8-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="af4a8-108">Requisito previo</span><span class="sxs-lookup"><span data-stu-id="af4a8-108">Prerequisite</span></span>                                                            | <span data-ttu-id="af4a8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="af4a8-109">Description</span></span>                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="af4a8-110">Especifique el importe mínimo de reembolso para la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="af4a8-110">Specify the minimum reimbursement amount for the legal entity.</span></span>          | <span data-ttu-id="af4a8-111">En la página **Parámetros de clientes**, en el área **General**, en el campo **Reembolso mínimo**, especifique el importe mínimo que se puede reembolsar paras los sobrepagos del cliente.</span><span class="sxs-lookup"><span data-stu-id="af4a8-111">On the **Accounts receivable parameters** page, in the **General** area, in the **Minimum reimbursement** field, enter the minimum amount that can be reimbursed for customer overpayments.</span></span> |
| <span data-ttu-id="af4a8-112">Opcional: agregar una cuenta de proveedor a cada cliente que se puede reembolsar.</span><span class="sxs-lookup"><span data-stu-id="af4a8-112">Optional: Add a vendor account to each customer that can be reimbursed.</span></span> | <span data-ttu-id="af4a8-113">En la página **Clientes**, en la ficha desplegable **Detalles varios**, en el campo **Cuenta de proveedor**, seleccione la cuenta de proveedor para el cliente.</span><span class="sxs-lookup"><span data-stu-id="af4a8-113">On the **Customers** page, on the **Miscellaneous details** FastTab, in the **Vendor account** field, select the vendor account for the customer.</span></span>                                           |

<span data-ttu-id="af4a8-114">Cuando crea transacciones de reembolso, se crea una factura de proveedor para el importe del saldo de crédito.</span><span class="sxs-lookup"><span data-stu-id="af4a8-114">When you create reimbursement transactions, a vendor invoice is created for the amount of the credit balance.</span></span> <span data-ttu-id="af4a8-115">El proceso de reembolso quita el saldo de crédito para la cuenta de cliente y crea un saldo pendiente para la cuenta de proveedor que corresponde al cliente.</span><span class="sxs-lookup"><span data-stu-id="af4a8-115">The reimbursement process removes the credit balance for the customer account and creates a balance due for the vendor account that corresponds to the customer.</span></span>

1.  <span data-ttu-id="af4a8-116">En Clientes, ejecute el proceso **Reembolso**.</span><span class="sxs-lookup"><span data-stu-id="af4a8-116">In Accounts receivable, run the **Reimbursement** process.</span></span>
2.  <span data-ttu-id="af4a8-117">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="af4a8-117">Follow one of these steps:</span></span>
    -   <span data-ttu-id="af4a8-118">Para reembolsar cuentas de cliente específicas, haga clic en **Seleccionar** y especifique las cuentas en la consulta.</span><span class="sxs-lookup"><span data-stu-id="af4a8-118">To reimburse specific customer accounts, click **Select**, and specify the customer accounts in the query.</span></span>
    -   <span data-ttu-id="af4a8-119">Para reembolsar todas las cuentas de cliente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af4a8-119">To reimburse all customer accounts, click **OK**.</span></span>

    <span data-ttu-id="af4a8-120">Los importes de crédito se transfieren a las cuentas de proveedor de los clientes y se procesan como pagos normales.</span><span class="sxs-lookup"><span data-stu-id="af4a8-120">The credit amounts are transferred to the vendor accounts of the customers and are processed as ordinary payments.</span></span> <span data-ttu-id="af4a8-121">Si un cliente no dispone de cuenta de proveedor, el programa creará automáticamente una cuenta de proveedor plantilla para dicho cliente.</span><span class="sxs-lookup"><span data-stu-id="af4a8-121">If a customer doesn't have a vendor account, a one-time vendor account is automatically created for the customer.</span></span>
3.  <span data-ttu-id="af4a8-122">Para ver las transacciones de reembolso creadas, use la página **Reembolso**.</span><span class="sxs-lookup"><span data-stu-id="af4a8-122">To view the reimbursement transactions that were created, use the **Reimbursement** page.</span></span>
4.  <span data-ttu-id="af4a8-123">En Proveedores, cree un pago para las facturas de proveedor que se crearon por el proceso de reembolso.</span><span class="sxs-lookup"><span data-stu-id="af4a8-123">In Accounts payable, create a payment for the vendor invoices that were created by the reimbursement process.</span></span>





