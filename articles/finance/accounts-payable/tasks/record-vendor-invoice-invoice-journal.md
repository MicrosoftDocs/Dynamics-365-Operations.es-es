---
title: Registrar una factura de proveedor en el diario de facturas
description: Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971837"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a><span data-ttu-id="499f1-103">Registrar una factura de proveedor en el diario de facturas</span><span class="sxs-lookup"><span data-stu-id="499f1-103">Record a vendor invoice in the invoice journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="499f1-104">Esta guía de la tarea muestra cómo registrar facturas de proveedor que no están asociadas a ningún pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="499f1-104">This task guide will show how to record vendor invoices that are not associated with purchase orders.</span></span> <span data-ttu-id="499f1-105">Algunos ejemplos de este tipo de factura incluyen los gastos para suministros o servicios.</span><span class="sxs-lookup"><span data-stu-id="499f1-105">Examples of this type of invoice include expenses for supplies or services.</span></span>  <span data-ttu-id="499f1-106">Esta grabación usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="499f1-106">This recording uses the USMF demo company.</span></span>

1. <span data-ttu-id="499f1-107">Vaya a **Panel de navegación > Módulos > Proveedores > Espacios de trabajo > Entrada de factura de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="499f1-107">Go to **Navigation pane > Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="499f1-108">En el **Panel de acciones**, haga clic en **Nuevo diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="499f1-108">On the **Action pane**, click **New invoice journal**.</span></span>
3. <span data-ttu-id="499f1-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="499f1-109">Click **New**.</span></span>
4. <span data-ttu-id="499f1-110">En el campo **Nombre**, escriba el nombre del diario o haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="499f1-110">In the **Name** field, enter the journal name or click the drop down button to open the lookup.</span></span>
5. <span data-ttu-id="499f1-111">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="499f1-111">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="499f1-112">En el **panel de acciones**, haga clic en **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="499f1-112">On the **Action pane**, click **Lines**.</span></span> <span data-ttu-id="499f1-113">En el campo **Fecha**, especifique la fecha de registro que va a actualizar la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="499f1-113">In the **Date** field, enter the posting date that will update General Ledger.</span></span>  
7. <span data-ttu-id="499f1-114">En el campo **Cuenta**, especifique la **cuenta del proveedor**.</span><span class="sxs-lookup"><span data-stu-id="499f1-114">In the **Account** field, specify the **Vendor account**.</span></span>
8. <span data-ttu-id="499f1-115">En el campo **Factura**, especifique el número de factura.</span><span class="sxs-lookup"><span data-stu-id="499f1-115">In the **Invoice** field, enter the invoice number.</span></span>
9. <span data-ttu-id="499f1-116">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="499f1-116">In the **Description** field, type a value.</span></span>
10. <span data-ttu-id="499f1-117">En el campo **Crédito**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="499f1-117">In the **Credit** field, enter a number.</span></span>
11. <span data-ttu-id="499f1-118">En el campo **Cuenta de contrapartida**, escriba el número de cuenta o haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="499f1-118">In the **Offset account** field, enter the account number or click the drop down button to open the lookup</span></span>
    * <span data-ttu-id="499f1-119">El valor predeterminado del **grupo de impuestos** proviene de la cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="499f1-119">The **Sales tax group** will be default from the vendor account.</span></span>  
    * <span data-ttu-id="499f1-120">El valor predeterminado proviene del campo **Grupo de impuestos de artículos** de la cuenta principal especificada en el campo **Cuenta de contrapartida**.</span><span class="sxs-lookup"><span data-stu-id="499f1-120">The **Item sales tax group** will be default from the main account specified in the **Offset account** field.</span></span>  
    * <span data-ttu-id="499f1-121">La **fecha de vencimiento** se calculará según las condiciones de pago.</span><span class="sxs-lookup"><span data-stu-id="499f1-121">The **Due date** will be calculated based on the Terms of payment.</span></span>  
    * <span data-ttu-id="499f1-122">El **descuento por pronto pago** proviene de la cuenta de proveedor</span><span class="sxs-lookup"><span data-stu-id="499f1-122">The **Cash discount** will default from the Vendor account.</span></span>
12. <span data-ttu-id="499f1-123">Si ha habilitado el flujo de trabajo del diario de facturas de proveedores, haga clic en **Flujo de trabajo > Enviar**.</span><span class="sxs-lookup"><span data-stu-id="499f1-123">If you have enabled Vendor invoice journal workflow, click **Workflow > Submit**.</span></span>
    * <span data-ttu-id="499f1-124">Cuando se aprueba su envío, la fecha se adelantará al primer día del próximo período abierto, si la fecha de contabilización de la transacción cae dentro de un período que está En espera o Cerrado para la contabilización del libro mayor.</span><span class="sxs-lookup"><span data-stu-id="499f1-124">When your submission is approved, the date will be advanced to the first day of the next open period, if the transaction posting date falls within a period that is On hold or Closed for ledger posting.</span></span>
12. <span data-ttu-id="499f1-125">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="499f1-125">Click **Post**.</span></span>
13. <span data-ttu-id="499f1-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="499f1-126">Close the page.</span></span>

