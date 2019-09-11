---
title: Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación
description: En este tema se explica cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb690769a33f88e63ab8f54cec69a5e927fd324c
ms.sourcegitcommit: 6545bef4584d72dd7789f2d3935cf00ac8f489b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "1871014"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="1fcff-103">Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación</span><span class="sxs-lookup"><span data-stu-id="1fcff-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1fcff-104">En este tema se explica cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.</span><span class="sxs-lookup"><span data-stu-id="1fcff-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="1fcff-105">Crear y registrar una factura</span><span class="sxs-lookup"><span data-stu-id="1fcff-105">Create and post and invoice</span></span>
1. <span data-ttu-id="1fcff-106">En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Registro de facturas**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="1fcff-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-107">Select **New**.</span></span>
3. <span data-ttu-id="1fcff-108">Seleccione el nombre del registro de facturas que desee usar.</span><span class="sxs-lookup"><span data-stu-id="1fcff-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="1fcff-109">Seleccione **Líneas** para abrir el registro y especificar las líneas de gastos.</span><span class="sxs-lookup"><span data-stu-id="1fcff-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="1fcff-110">Seleccione un proveedor.</span><span class="sxs-lookup"><span data-stu-id="1fcff-110">Select a vendor.</span></span> <span data-ttu-id="1fcff-111">Por ejemplo, escriba o seleccione `US-104`.</span><span class="sxs-lookup"><span data-stu-id="1fcff-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="1fcff-112">En el campo **Factura**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1fcff-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="1fcff-113">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1fcff-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="1fcff-114">En el campo **Crédito**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="1fcff-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="1fcff-115">En el campo **Aprobado por**, seleccione un aprobador en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="1fcff-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="1fcff-116">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="1fcff-117">Aprobar una factura</span><span class="sxs-lookup"><span data-stu-id="1fcff-117">Approve an invoice</span></span>
1. <span data-ttu-id="1fcff-118">En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Aprobación de facturas**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="1fcff-119">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-119">Select **New**.</span></span>
3. <span data-ttu-id="1fcff-120">Seleccione el nombre del diario de aprobación de facturas que desee usar.</span><span class="sxs-lookup"><span data-stu-id="1fcff-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="1fcff-121">Seleccione **Líneas** para mostrar una página donde podrá seleccionar las facturas que desea aprobar.</span><span class="sxs-lookup"><span data-stu-id="1fcff-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="1fcff-122">Seleccione **Buscar asientos** para mostrar todas las facturas que están listas para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="1fcff-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="1fcff-123">Marque la factura que ha creado, después haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="1fcff-124">Los asientos que seleccionó arriba se mueven en esta lista después de que los seleccione.</span><span class="sxs-lookup"><span data-stu-id="1fcff-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="1fcff-125">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-125">Select **OK**.</span></span>
8. <span data-ttu-id="1fcff-126">Seleccione el campo del **número de cuenta** para agregar una cuenta de gastos en la factura.</span><span class="sxs-lookup"><span data-stu-id="1fcff-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="1fcff-127">Especifique un número de cuenta y salga del campo con el tabulador.</span><span class="sxs-lookup"><span data-stu-id="1fcff-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="1fcff-128">Por ejemplo, escriba `600120`.</span><span class="sxs-lookup"><span data-stu-id="1fcff-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="1fcff-129">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="1fcff-129">Select **Post**.</span></span>
11. <span data-ttu-id="1fcff-130">Seleccione **Asiento** para ver las entradas que se han registrado.</span><span class="sxs-lookup"><span data-stu-id="1fcff-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="1fcff-131">La cuenta de factura pendiente de aprobación se anula y se reemplaza con la cuenta de gastos real.</span><span class="sxs-lookup"><span data-stu-id="1fcff-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

