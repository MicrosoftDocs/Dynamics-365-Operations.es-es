---
title: Característica de factura dividida
description: Este tema describe la configuración y la característica para dividir facturas por dirección de entrega y número de cuenta de impuestos (TAN).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023573"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="3d0f9-103">Característica de factura dividida</span><span class="sxs-lookup"><span data-stu-id="3d0f9-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d0f9-104">Este tema describe la configuración y la característica para dividir facturas por dirección de entrega y número de cuenta de impuestos (TAN).</span><span class="sxs-lookup"><span data-stu-id="3d0f9-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="3d0f9-105">En la página **Parámetros de proveedores**, en la pestaña **General**, seleccione las casillas **Recepción de producto** o **Factura** para registrar y dividir una recepción o factura de producto que tiene diferentes direcciones de entrega y TAN en la página **Pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="3d0f9-106">La factura registrada se dividirá por dirección de entrega y TAN.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="3d0f9-107">En la pestaña **Actualización conjunta**, en ficha desplegable **Dividir por**, en la fila **Información de entrega**, establezca las opciones **Confirmación**, **Lista de selección**, **Albarán** o **Factura** a **Sí** para registrar y dividir una confirmación, lista de selección, albarán o factura donde se definen diferentes direcciones de entrega y TAN para diferentes líneas de factura en la página **Pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="3d0f9-108">La factura se dividirá primero por dirección de entrega y después por TAN.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="3d0f9-109">Si ninguna opción para **Información de entrega** se ha establecido como **Sí**, la factura se registrará como una sola factura.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="3d0f9-110">No se producirá ninguna división de facturas.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="3d0f9-111">Para dividir y registrar un albarán donde las líneas de la factura tienen diferentes direcciones de entrega y TAN, debe establecer la opción **Albarán** para **Información de entrega** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="3d0f9-112">Para dividir y registrar una factura donde las líneas de la factura tienen diferentes direcciones de entrega y TAN, debe establecer la opción **Factura** para **Información de entrega** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="3d0f9-113">Para dividir y registrar una factura donde las líneas de la factura tienen diferentes direcciones de entrega, pero el mismo TAN, debe establecer la opción **Factura** para **Información de entrega** a **No**.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="3d0f9-114">La factura se dividirá por dirección de entrega.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="3d0f9-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d0f9-115">Example</span></span>

<span data-ttu-id="3d0f9-116">En este ejemplo, la opción **Factura** para **Información de entrega** se establece en **Sí** en la pestaña **Actualización conjunta** de la página **Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="3d0f9-117">Se registra una factura de compra que tiene la siguiente configuración para direcciones de entrega y TAN en las líneas:</span><span class="sxs-lookup"><span data-stu-id="3d0f9-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="3d0f9-118">**Línea de artículo 1:** dirección de entrega 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="3d0f9-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="3d0f9-119">**Línea de artículo 2:** dirección de entrega 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="3d0f9-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="3d0f9-120">**Línea de artículo 3:** dirección de entrega 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="3d0f9-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="3d0f9-121">**Línea de artículo 4:** dirección de entrega 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="3d0f9-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="3d0f9-122">En este caso, la factura original se divide en dos facturas y se registra de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3d0f9-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="3d0f9-123">La factura 1 se registra para la línea de artículo 1 y la línea de artículo 2, ya que ambas líneas tienen la misma dirección de entrega y TAN.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="3d0f9-124">La factura 2 se registra para la línea de artículo 3.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="3d0f9-125">La factura 3 se registra para la línea de artículo 4.</span><span class="sxs-lookup"><span data-stu-id="3d0f9-125">Invoice 3 is posted for item line 4.</span></span>
