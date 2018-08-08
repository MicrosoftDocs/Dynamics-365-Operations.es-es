---
title: Actualizaciones de facturas para devoluciones
description: "Esta funcionalidad también admite los procesos empresariales de muchas organizaciones que deciden que la misma persona facture pedidos de devolución y de ventas a la vez."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2f962641f7fdae18a360567d6f37348fabbfc302
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---


# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="7018d-103">Actualizaciones de facturas para devoluciones</span><span class="sxs-lookup"><span data-stu-id="7018d-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7018d-104">Un pedido de devolución es un tipo de pedido de ventas marcado como artículo devuelto.</span><span class="sxs-lookup"><span data-stu-id="7018d-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="7018d-105">Por lo tanto, la página de lista **Todos los pedidos de venta** se usa para generar facturas para los pedidos de devolución en lugar del formulario **Pedidos de devolución**.</span><span class="sxs-lookup"><span data-stu-id="7018d-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="7018d-106">Esta funcionalidad también admite los procesos empresariales de muchas organizaciones que deciden que la misma persona facture pedidos de devolución y de ventas a la vez.</span><span class="sxs-lookup"><span data-stu-id="7018d-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="7018d-107">Dado que la factura para un artículo devuelto es para un importe negativo, se denomina nota de abono.</span><span class="sxs-lookup"><span data-stu-id="7018d-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="7018d-108">Al configurar la actualización de factura para el procesamiento por lotes, el pedido de ventas del tipo **Pedido devuelto** debe tener un estado de línea de devolución de **Recibido**, lo que indica que el albarán del pedido se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="7018d-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="7018d-109">Registrar una factura para un pedido de devolución</span><span class="sxs-lookup"><span data-stu-id="7018d-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="7018d-110">Haga clic en **Clientes** \> **Común** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="7018d-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="7018d-111">Seleccione un pedido de ventas para el que se muestra **Pedido devuelto** en el campo **Tipo de pedido**.</span><span class="sxs-lookup"><span data-stu-id="7018d-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="7018d-112">En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, haga clic en **Factura**.</span><span class="sxs-lookup"><span data-stu-id="7018d-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="7018d-113">En la pestaña **Parámetros**, seleccione la casilla de verificación **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="7018d-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="7018d-114">Revise la información del formulario y realice los cambios pertinentes.</span><span class="sxs-lookup"><span data-stu-id="7018d-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="7018d-115">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7018d-115">Click **OK**.</span></span> <span data-ttu-id="7018d-116">La nota de abono se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="7018d-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="7018d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7018d-117">See also</span></span>

[<span data-ttu-id="7018d-118">Actualizaciones de albaranes para devoluciones</span><span class="sxs-lookup"><span data-stu-id="7018d-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  



