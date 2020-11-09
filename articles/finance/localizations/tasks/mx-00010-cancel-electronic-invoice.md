---
title: MX-00010 Cancelar facturas electrónicas
description: Puede cancelar una factura electrónica CFDI validada y certificada anteriormente por el PAC.
author: sndray
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EInvoiceCFDIJournal_AR
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 63769dc6eabdfc782020014a8ef3177c6591454c
ms.sourcegitcommit: 4df9ca744621aafd6af6a89bf7f6fa9f94bedb00
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "4100985"
---
# <a name="mx-00010-cancel-an-electronic-invoice"></a><span data-ttu-id="984fc-103">MX-00010 Cancelar facturas electrónicas</span><span class="sxs-lookup"><span data-stu-id="984fc-103">MX-00010 Cancel an electronic invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="984fc-104">Puede cancelar una factura electrónica CFDI validada y certificada anteriormente por el PAC.</span><span class="sxs-lookup"><span data-stu-id="984fc-104">You can cancel a CFDI electronic invoice that was previously validated and certified by the PAC.</span></span> <span data-ttu-id="984fc-105">También puede cancelar una factura electrónica CFDI mediante el proceso manual.</span><span class="sxs-lookup"><span data-stu-id="984fc-105">You can also cancel a CFDI electronic invoice by using the manual process.</span></span>

## <a name="cancel-a-cfdi-electronic-invoice"></a><span data-ttu-id="984fc-106">Cancelación de una factura electrónica CFDI</span><span class="sxs-lookup"><span data-stu-id="984fc-106">Cancel a CFDI electronic invoice</span></span>
1. <span data-ttu-id="984fc-107">Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).</span><span class="sxs-lookup"><span data-stu-id="984fc-107">Go to Accounts receivable > Inquiries and reports > CFDI (electronic invoices).</span></span>
2. <span data-ttu-id="984fc-108">Seleccione una factura electrónica con estado Aprobada.</span><span class="sxs-lookup"><span data-stu-id="984fc-108">Select an electronic invoice with a status of Approved.</span></span>
3. <span data-ttu-id="984fc-109">Haga clic en el vínculo del número de factura para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="984fc-109">Click the invoice number link to see the details.</span></span>
4. <span data-ttu-id="984fc-110">En el panel de acciones, haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="984fc-110">On the Action Pane, click Functions.</span></span>
5. <span data-ttu-id="984fc-111">Haga clic en Cancelar CFDI.</span><span class="sxs-lookup"><span data-stu-id="984fc-111">Click Cancel CFDI.</span></span>
6. <span data-ttu-id="984fc-112">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="984fc-112">Close the page.</span></span>
7. <span data-ttu-id="984fc-113">Vaya a Clientes > Facturas > Facturas electrónicas > Proceso de exportar/importar factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="984fc-113">Go to Accounts receivable > Invoices > E-Invoices > Export/import electronic invoice process.</span></span>
8. <span data-ttu-id="984fc-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="984fc-114">Click OK.</span></span>
    * <span data-ttu-id="984fc-115">Cuando se confirma la cancelación, el estado de la factura electrónica cambia a Cancelada.</span><span class="sxs-lookup"><span data-stu-id="984fc-115">When the cancelation is confirmed, the status of the electronic invoice is changed to be Canceled.</span></span>  
9. <span data-ttu-id="984fc-116">Vaya a Clientes > Consultas e informes > CFDI (facturas electrónicas).</span><span class="sxs-lookup"><span data-stu-id="984fc-116">Go to Accounts receivable > Inquiries and reports > CFDI (electronic invoices).</span></span>
10. <span data-ttu-id="984fc-117">Seleccione la factura cancelada para comprobar el estado.</span><span class="sxs-lookup"><span data-stu-id="984fc-117">Select the canceled invoice to verify the status.</span></span>

>[!NOTE] 
> <span data-ttu-id="984fc-118">No puede cancelar un documento CFDI si existe un documento asociado.</span><span class="sxs-lookup"><span data-stu-id="984fc-118">You cannot cancel a CFDI document if an associated document exists.</span></span> <span data-ttu-id="984fc-119">Por ejemplo, no puede cancelar un pago por adelantado si una factura hace referencia a ese pago.</span><span class="sxs-lookup"><span data-stu-id="984fc-119">For example, you cannot cancel a prepayment if an invoice references that payment.</span></span> <span data-ttu-id="984fc-120">Primero debe cancelar los documentos asociados y luego cancelar el documento CFDI.</span><span class="sxs-lookup"><span data-stu-id="984fc-120">You first need to cancel associated documets and then cancel the CFDI document.</span></span>

## <a name="manually-cancel-a-cfdi-electronic-invoice"></a><span data-ttu-id="984fc-121">Cancelación manual de una factura electrónica CFDI</span><span class="sxs-lookup"><span data-stu-id="984fc-121">Manually cancel a CFDI electronic invoice</span></span>
1. <span data-ttu-id="984fc-122">Seleccione una factura con estado Aprobada.</span><span class="sxs-lookup"><span data-stu-id="984fc-122">Select an invoice with status Approved.</span></span>
2. <span data-ttu-id="984fc-123">En el panel de acciones, haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="984fc-123">On the Action Pane, click Functions.</span></span>
3. <span data-ttu-id="984fc-124">Haga clic en Cancelación manual.</span><span class="sxs-lookup"><span data-stu-id="984fc-124">Click Manual cancel.</span></span>
4. <span data-ttu-id="984fc-125">Especifique la fecha de cancelación.</span><span class="sxs-lookup"><span data-stu-id="984fc-125">Enter the date of cancelation.</span></span>
5. <span data-ttu-id="984fc-126">En el campo Nombre de clave de cancelación, escriba el motivo de la cancelación.</span><span class="sxs-lookup"><span data-stu-id="984fc-126">In the Cancel key name field, enter the reason for the cancelation..</span></span>
6. <span data-ttu-id="984fc-127">Haga clic en Aceptar para confirmar la cancelación de la factura electrónica.</span><span class="sxs-lookup"><span data-stu-id="984fc-127">Click OK to confirm the cancelation of the electronic invoice.</span></span>
    * <span data-ttu-id="984fc-128">El estado de la factura electrónica es Cancelación manual.</span><span class="sxs-lookup"><span data-stu-id="984fc-128">The status of electronic invoice is Manual cancel.</span></span>  

