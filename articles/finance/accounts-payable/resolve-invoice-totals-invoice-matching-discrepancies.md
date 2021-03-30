---
title: Visión general de la resolución de discrepancias durante la conciliación de los totales de las facturas
description: Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable.
author: abruer
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTotalPriceTolerance
audience: Application User
ms.reviewer: roschlom
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0635f388dba16a1e4374f0915fbab5b88c3b76ab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227459"
---
# <a name="resolve-discrepancies-during-invoice-totals-matching-overview"></a><span data-ttu-id="2ad89-103">Visión general de la resolución de discrepancias durante la conciliación de los totales de las facturas</span><span class="sxs-lookup"><span data-stu-id="2ad89-103">Resolve discrepancies during invoice totals matching overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ad89-104">Un tipo de validación de conciliación de facturas es la conciliación de los totales de las facturas.</span><span class="sxs-lookup"><span data-stu-id="2ad89-104">One type of invoice matching validation is invoice totals matching.</span></span> <span data-ttu-id="2ad89-105">Para especificar que el sistema debe realizar la conciliación de totales de facturas, en la página **Parámetros de proveedores**, en la pestaña **Validación de facturas**, defina la opción **Conciliar totales de facturas** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2ad89-105">To specify that the system should perform invoice totals matching, on the **Accounts payable parameters** page, on the **Invoice validation** tab, set the **Match invoice totals** option **Yes**.</span></span> 

<span data-ttu-id="2ad89-106">Puede usar la conciliación de totales de factura para asegurarse de que los importes totales de factura no se desvían de los importes planificados más de la desviación aceptable.</span><span class="sxs-lookup"><span data-stu-id="2ad89-106">You can use invoice totals matching to help guarantee that total invoice amounts don't deviate from expected amounts by more than an acceptable variance.</span></span> <span data-ttu-id="2ad89-107">Se comparan seis totales en la página **Detalles de la conciliación de totales de facturas**.</span><span class="sxs-lookup"><span data-stu-id="2ad89-107">Six totals are compared on the **Invoice totals matching details** page.</span></span> <span data-ttu-id="2ad89-108">Si alguno de los totales se desvía del correspondiente total de pedido de compra previsto, se marca una discrepancia de conciliación.</span><span class="sxs-lookup"><span data-stu-id="2ad89-108">If any one of the totals deviates from the expected corresponding purchase order total, a matching discrepancy is flagged.</span></span> 

<span data-ttu-id="2ad89-109">Para revisar la factura con discrepancias de conciliación de totales, en el área de trabajo **Entrada de la factura de proveedor**, haga clic en el mosaico **Facturas pendientes**.</span><span class="sxs-lookup"><span data-stu-id="2ad89-109">To review the invoice that has the totals matching discrepancies, in the **Vendor invoice entry** workspace, click the **Pending invoices** tile.</span></span> <span data-ttu-id="2ad89-110">Luego, en el panel de acciones, en la pestaña **Revisar**, haga clic en **Detalles de conciliación**.</span><span class="sxs-lookup"><span data-stu-id="2ad89-110">Then, on the Action Pane, on the **Review** tab, click **Matching details**.</span></span> <span data-ttu-id="2ad89-111">Si se han detectado discrepancias de conciliación, los iconos de advertencia aparecen junto al importe de la factura.</span><span class="sxs-lookup"><span data-stu-id="2ad89-111">If matching discrepancies have been detected, warning icons appear next to the invoice amount.</span></span> <span data-ttu-id="2ad89-112">Puede ver más detalles sobre los totales en los detalles de la conciliación de totales de facturas.</span><span class="sxs-lookup"><span data-stu-id="2ad89-112">You can view more detail about the totals by viewing the invoice totals matching details.</span></span> 

<span data-ttu-id="2ad89-113">Una vez haya identificado la discrepancia, es posible que deba ponerse en contacto con el proveedor si cree que la información de la factura es incorrecta.</span><span class="sxs-lookup"><span data-stu-id="2ad89-113">After you identify a discrepancy, you might have to contact the vendor if you think that the information on the invoice is incorrect.</span></span> <span data-ttu-id="2ad89-114">Dependiendo del acuerdo resultante con el proveedor, podrá llevar a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="2ad89-114">Depending on the resulting agreement with the vendor, you can then take one of these actions:</span></span>

-   <span data-ttu-id="2ad89-115">Aceptar la diferencia de precio y registrar la factura con discrepancias.</span><span class="sxs-lookup"><span data-stu-id="2ad89-115">Accept the price difference, and post the invoice that has matching discrepancies.</span></span> <span data-ttu-id="2ad89-116">El sistema se puede configurar para requerir la aprobación antes de que pueda registrar si existen discrepancias.</span><span class="sxs-lookup"><span data-stu-id="2ad89-116">Your system might be set up to require approval before it can post if there are matching discrepancies.</span></span> <span data-ttu-id="2ad89-117">En este caso, debe aprobar la discrepancia en la conciliación y puede especificar de forma opcional un comentario de aprobación.</span><span class="sxs-lookup"><span data-stu-id="2ad89-117">In this case, you must approve the matching discrepancy and can optionally enter an approval comment.</span></span> <span data-ttu-id="2ad89-118">Después puede seleccionar registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="2ad89-118">You can then select to post the invoice.</span></span>
-   <span data-ttu-id="2ad89-119">Revisar el importe de la factura con el importe previsto y registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="2ad89-119">Revise the invoice amount to the expected amount, and post the invoice.</span></span>
-   <span data-ttu-id="2ad89-120">Solicitar un crédito previo del proveedor y una nueva factura corregida.</span><span class="sxs-lookup"><span data-stu-id="2ad89-120">Request a full credit and a new, corrected invoice from the vendor.</span></span>

<span data-ttu-id="2ad89-121">Para obtener más información, consulte [Investigar o resolver las excepciones](tasks/research-resolve-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="2ad89-121">For more information, see [Research/Resolve exceptions](tasks/research-resolve-exceptions.md).</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]