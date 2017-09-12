---
title: "Resolver las discrepancias durante la conciliación de los totales de las facturas"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3f7e1261838866688c97529b0edfa1354034247b
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a><span data-ttu-id="568ca-102">Resolver las discrepancias durante la conciliación de los totales de las facturas</span><span class="sxs-lookup"><span data-stu-id="568ca-102">Resolve discrepancies during invoice totals matching</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="568ca-103">Un tipo de validación de conciliación de facturas es la conciliación de los totales de las facturas.</span><span class="sxs-lookup"><span data-stu-id="568ca-103">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="568ca-104">Para especificar que el sistema debe realizar la conciliación de totales de facturas, en la página **Parámetros de proveedores**, en la pestaña **Validación de facturas**, defina la opción **Conciliar totales de facturas** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="568ca-104">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="568ca-105">Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable.</span><span class="sxs-lookup"><span data-stu-id="568ca-105">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="568ca-106">Se comparan seis totales en la página **Detalles de la conciliación de totales de facturas**.</span><span class="sxs-lookup"><span data-stu-id="568ca-106">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="568ca-107">Si alguno de los totales se desvía del correspondiente total de pedido de compra previsto, se marca una discrepancia de conciliación.</span><span class="sxs-lookup"><span data-stu-id="568ca-107">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="568ca-108">Para revisar la factura con discrepancias de conciliación de totales, en el área de trabajo **Entrada de la factura de proveedor**, haga clic en el mosaico **Facturas pendientes**.</span><span class="sxs-lookup"><span data-stu-id="568ca-108">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="568ca-109">Luego, en el panel de acciones, en la pestaña **Revisar**, haga clic en **Detalles de conciliación**.</span><span class="sxs-lookup"><span data-stu-id="568ca-109">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="568ca-110">Si se han detectado discrepancias de conciliación, los iconos de advertencia aparecen junto al importe de la factura.</span><span class="sxs-lookup"><span data-stu-id="568ca-110">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="568ca-111">Puede ver más detalles sobre los totales en los detalles de la conciliación de totales de facturas.</span><span class="sxs-lookup"><span data-stu-id="568ca-111">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="568ca-112">Una vez haya identificado la discrepancia, es posible que deba ponerse en contacto con el proveedor si cree que la información de la factura es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="568ca-112">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="568ca-113">Dependiendo del acuerdo resultante con el proveedor, podrá llevar a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="568ca-113">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="568ca-114">Aceptar la diferencia de precio y registrar la factura con discrepancias.</span><span class="sxs-lookup"><span data-stu-id="568ca-114">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="568ca-115">El sistema se puede configurar para requerir la aprobación antes de que pueda registrar si existen discrepancias.</span><span class="sxs-lookup"><span data-stu-id="568ca-115">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="568ca-116">En este caso, debe aprobar la discrepancia en la conciliación y puede especificar de forma opcional un comentario de aprobación.</span><span class="sxs-lookup"><span data-stu-id="568ca-116">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="568ca-117">Después puede seleccionar registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="568ca-117">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="568ca-118">Revisar el importe de la factura con el importe previsto y registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="568ca-118">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="568ca-119">Solicitar un crédito previo del proveedor y una nueva factura corregida.</span><span class="sxs-lookup"><span data-stu-id="568ca-119">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="568ca-120">Para obtener más información, consulte [Investigar o resolver las excepciones](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="568ca-120">For more information, see [Research or resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>



