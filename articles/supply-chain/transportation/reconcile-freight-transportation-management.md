---
title: Conciliar el flete en la administración del transporte
description: En este tema se describe el proceso de conciliación de flete.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e1680572f1ba9816c9ec45ef52498cab1f45247
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206228"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="3d83a-103">Conciliar el flete en la administración del transporte</span><span class="sxs-lookup"><span data-stu-id="3d83a-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d83a-104">En este tema se describe el proceso de conciliación de flete.</span><span class="sxs-lookup"><span data-stu-id="3d83a-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="3d83a-105">La conciliación de flete se puede realizar manualmente o se puede configurar para que se produzca automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3d83a-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="3d83a-106">Para usar la conciliación de flete automático, debe configurar un maestro de auditoría donde pueda definir los criterios que determinan qué albaranes de flete se concilian automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3d83a-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="3d83a-107">El proceso de conciliación de flete</span><span class="sxs-lookup"><span data-stu-id="3d83a-107">The freight reconciliation process</span></span>
<span data-ttu-id="3d83a-108">Las tasas de flete se calculan por el motor de velocidad que está asociado al transportista de envío pertinente.</span><span class="sxs-lookup"><span data-stu-id="3d83a-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="3d83a-109">Cuando se confirma una carga, se genera un albarán de flete y las tasas de flete se transfieren a él.</span><span class="sxs-lookup"><span data-stu-id="3d83a-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="3d83a-110">Las tasas de flete se distribuyen como gastos varios al documento de origen pertinente (pedido de compra, pedido de ventas o pedido de transferencia), en función de la configuración que se utiliza para el proceso de facturación normal.</span><span class="sxs-lookup"><span data-stu-id="3d83a-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="3d83a-111">El proceso de conciliación de flete (que también se conoce como el proceso de conciliación) puede iniciarse tan pronto como llega la factura de flete del transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="3d83a-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="3d83a-112">La factura se puede recibir de manera electrónica o en papel.</span><span class="sxs-lookup"><span data-stu-id="3d83a-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="3d83a-113">Si la factura en papel se recibe, puede generar una factura electrónica mediante el albarán de flete como plantilla.</span><span class="sxs-lookup"><span data-stu-id="3d83a-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="3d83a-114">[![Proceso de conciliación de flete](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="3d83a-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="3d83a-115">Conciliación manual</span><span class="sxs-lookup"><span data-stu-id="3d83a-115">Manual reconciliation</span></span>
<span data-ttu-id="3d83a-116">Si está conciliando el flete manualmente, deben conciliar cada línea de factura con la línea o líneas del albarán de flete para la carga que se factura.</span><span class="sxs-lookup"><span data-stu-id="3d83a-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="3d83a-117">Esto se hace conciliando en la página **Conciliación de albaranes de flete y facturas**.</span><span class="sxs-lookup"><span data-stu-id="3d83a-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="3d83a-118">Si el importe de la línea de factura no coincide con el importe del albarán de flete, debe seleccionar un motivo de conciliación para la diferencia.</span><span class="sxs-lookup"><span data-stu-id="3d83a-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="3d83a-119">Si hay varios motivos para la conciliación, puede dividir el importe no conciliado entre ellos.</span><span class="sxs-lookup"><span data-stu-id="3d83a-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="3d83a-120">El motivo de conciliación determina cómo se registran los importes de diferencia en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="3d83a-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="3d83a-121">Cuando se contabiliza la conciliación de todo el importe de la factura, se envía para aprobación y, a continuación, se registra el diario.</span><span class="sxs-lookup"><span data-stu-id="3d83a-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="3d83a-122">En la ilustración siguiente se muestra cómo generar una factura de flete y realizar la conciliación de flete.</span><span class="sxs-lookup"><span data-stu-id="3d83a-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span> 
<span data-ttu-id="3d83a-123">[![Tareas de conciliación de flete](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="3d83a-123">[![Freight reconcilation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="3d83a-124">Conciliación automática</span><span class="sxs-lookup"><span data-stu-id="3d83a-124">Automatic reconciliation</span></span>
<span data-ttu-id="3d83a-125">Para utilizar la conciliación automática, debe especificar la programación de conciliación y las facturas y los transportistas de envío que se utilizarán.</span><span class="sxs-lookup"><span data-stu-id="3d83a-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="3d83a-126">La conciliación de las líneas de factura y los albaranes de flete se realiza según la configuración del tipo de albarán de flete y el maestro de auditoría.</span><span class="sxs-lookup"><span data-stu-id="3d83a-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="3d83a-127">Tras la ejecución de la conciliación automática, debe controlar todas las facturas que el sistema no puede conciliar.</span><span class="sxs-lookup"><span data-stu-id="3d83a-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="3d83a-128">A continuación, debe procesar estas facturas manualmente para poder registrar todas las facturas para el pago.</span><span class="sxs-lookup"><span data-stu-id="3d83a-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>



