---
title: Datos clave de facturas en el sistema de proveedores mediante el diario de aprobación
description: Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 048eda77064b6aa3f666e998a8e551d2f7adc385
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "363531"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a><span data-ttu-id="42893-103">Datos clave de facturas en el sistema de proveedores mediante el diario de aprobación</span><span class="sxs-lookup"><span data-stu-id="42893-103">Key invoice data into AP system using approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="42893-104">Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.</span><span class="sxs-lookup"><span data-stu-id="42893-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="42893-105">Crear y registrar una factura</span><span class="sxs-lookup"><span data-stu-id="42893-105">Create and post and invoice</span></span>
1. <span data-ttu-id="42893-106">Vaya a Proveedores > Facturas > Registro de facturas.</span><span class="sxs-lookup"><span data-stu-id="42893-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="42893-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="42893-107">Click New.</span></span>
3. <span data-ttu-id="42893-108">Seleccione el nombre del registro de facturas que desee usar.</span><span class="sxs-lookup"><span data-stu-id="42893-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="42893-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="42893-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="42893-110">Haga clic en las líneas para abrir el registro y especificar las líneas de gastos.</span><span class="sxs-lookup"><span data-stu-id="42893-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="42893-111">Seleccione un proveedor.</span><span class="sxs-lookup"><span data-stu-id="42893-111">Select a vendor.</span></span> <span data-ttu-id="42893-112">Por ejemplo, escriba o seleccione US-104</span><span class="sxs-lookup"><span data-stu-id="42893-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="42893-113">En el campo Factura, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="42893-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="42893-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="42893-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="42893-115">En el campo Crédito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="42893-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="42893-116">En el campo Aprobado por, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="42893-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="42893-117">Resalte un aprobador y haga clic en Seleccionar para seleccionar el aprobador.</span><span class="sxs-lookup"><span data-stu-id="42893-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="42893-118">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="42893-118">Click Post.</span></span>
13. <span data-ttu-id="42893-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="42893-119">Close the page.</span></span>
14. <span data-ttu-id="42893-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="42893-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="42893-121">Aprobar una factura</span><span class="sxs-lookup"><span data-stu-id="42893-121">Approve an invoice</span></span>
1. <span data-ttu-id="42893-122">Vaya a Proveedores > Facturas > Aprobación de facturas.</span><span class="sxs-lookup"><span data-stu-id="42893-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="42893-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="42893-123">Click New.</span></span>
3. <span data-ttu-id="42893-124">Seleccione el nombre del diario de aprobación de facturas que desee usar.</span><span class="sxs-lookup"><span data-stu-id="42893-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="42893-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="42893-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="42893-126">Haga clic en las líneas para mostrar una página donde podrá seleccionar las facturas que desea aprobar.</span><span class="sxs-lookup"><span data-stu-id="42893-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="42893-127">Seleccione Buscar asientos para mostrar todas las facturas que están listas para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="42893-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="42893-128">Marque la factura que ha creado.</span><span class="sxs-lookup"><span data-stu-id="42893-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="42893-129">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="42893-129">Click Select.</span></span>
    * <span data-ttu-id="42893-130">Los asientos que seleccionó arriba se mueven en esta lista después de que los seleccione.</span><span class="sxs-lookup"><span data-stu-id="42893-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="42893-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="42893-131">Click OK.</span></span>
10. <span data-ttu-id="42893-132">Haga clic en el campo del número de cuenta para agregar una cuenta de gastos en la factura.</span><span class="sxs-lookup"><span data-stu-id="42893-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="42893-133">Especifique un número de cuenta y salga del campo con el tabulador.</span><span class="sxs-lookup"><span data-stu-id="42893-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="42893-134">Por ejemplo, escriba 600120.</span><span class="sxs-lookup"><span data-stu-id="42893-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="42893-135">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="42893-135">Click Post.</span></span>
13. <span data-ttu-id="42893-136">Haga clic en el asiento para ver las entradas que se han registrado.</span><span class="sxs-lookup"><span data-stu-id="42893-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="42893-137">La cuenta de factura pendiente de aprobación se anula y se reemplaza con la cuenta de gastos real.</span><span class="sxs-lookup"><span data-stu-id="42893-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

