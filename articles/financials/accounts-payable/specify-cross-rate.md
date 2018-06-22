---
title: Especificar el tipo de cambio cruzado
description: "Este tema proporciona información sobre cambios cruzados en Microsoft Dynamics 365 for Finance and Operations."
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: 112f77738b33aae94babe0cf8e9e61ff2ea3d004
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2018

---

# <a name="specify-the-cross-rate"></a><span data-ttu-id="5460b-103">Especificar el tipo de cambio cruzado</span><span class="sxs-lookup"><span data-stu-id="5460b-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5460b-104">En este tema se explica el propósito de un tipo de cambio cruzado y cómo especificar el tipo de cambio cruzado al liquidar un pago con una factura.</span><span class="sxs-lookup"><span data-stu-id="5460b-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="5460b-105">Usar un tipo de cambio cruzado cuando se cumplan todos los criterios siguientes:</span><span class="sxs-lookup"><span data-stu-id="5460b-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="5460b-106">Está liquidando un pago con una factura.</span><span class="sxs-lookup"><span data-stu-id="5460b-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="5460b-107">La línea de pago y la línea de factura usan divisas distintas.</span><span class="sxs-lookup"><span data-stu-id="5460b-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="5460b-108">Ninguna divisa es la divisa de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="5460b-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="5460b-109">No se usará el tipo de cambio cruzado para calcular la conversión de la divisa de la transacción de pago en la divisa de contabilidad de pago.</span><span class="sxs-lookup"><span data-stu-id="5460b-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="5460b-110">En su lugar, se recuperan los tipos de cambio de las tablas de tipos de cambio para calcular el valor del importe de divisa de la transacción de pago y el importe de la divisa de contabilidad de pago.</span><span class="sxs-lookup"><span data-stu-id="5460b-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="5460b-111">Por ejemplo, la divisa de contabilidad es USD, la divisa de la factura es CAD y la divisa de pago es EUR.</span><span class="sxs-lookup"><span data-stu-id="5460b-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="5460b-112">El tipo de cambio cruzado permite especificar un tipo de cambio para convertir directamente entre dólares canadienses y euros sin tener que convertir a través de dólares estadounidenses.</span><span class="sxs-lookup"><span data-stu-id="5460b-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="5460b-113">Al seleccionar una factura y pago principal, puede especificar un tipo de cambio cruzado para la línea de factura.</span><span class="sxs-lookup"><span data-stu-id="5460b-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="5460b-114">Éste es el tipo de cambio entre divisas para esas transacciones a partir de la fecha de liquidación.</span><span class="sxs-lookup"><span data-stu-id="5460b-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="5460b-115">Vaya a una de las páginas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5460b-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="5460b-116">**Clientes > Común > Clientes > Todos los clientes**</span><span class="sxs-lookup"><span data-stu-id="5460b-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="5460b-117">**Proveedores > Común > Proveedores > Todos los proveedores**.</span><span class="sxs-lookup"><span data-stu-id="5460b-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="5460b-118">**Adquisición y abastecimiento > Común > Proveedores > Todos los proveedores.**</span><span class="sxs-lookup"><span data-stu-id="5460b-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="5460b-119">Seleccione el cliente o proveedor cuyas transacciones abiertas esté liquidando.</span><span class="sxs-lookup"><span data-stu-id="5460b-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="5460b-120">Para un cliente, en la página de lista **Todos los clientes**, vaya a **Cobrar > Liquidar transacciones abiertas**.</span><span class="sxs-lookup"><span data-stu-id="5460b-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="5460b-121">Para un proveedor, en la página de lista **Todos los proveedores**, vaya a **Factura > Liquidar transacciones abiertas**.</span><span class="sxs-lookup"><span data-stu-id="5460b-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="5460b-122">Seleccione la transacción que es el pago principal y haga clic en en **Marcar pago**.</span><span class="sxs-lookup"><span data-stu-id="5460b-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="5460b-123">Se selecciona la casilla de la columna **Marcar** y se muestra un icono de información en la columna **Pago principal**.</span><span class="sxs-lookup"><span data-stu-id="5460b-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="5460b-124">En el campo **Tipo de cambio cruzado**, especifique el tipo de cambio entre la divisa de la factura y la divisa de pago, en la fecha de liquidación.</span><span class="sxs-lookup"><span data-stu-id="5460b-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 

