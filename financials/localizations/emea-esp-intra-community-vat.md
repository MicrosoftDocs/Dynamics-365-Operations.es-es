---
title: "IVA intracomunitario para España"
description: "Este tema proporciona información sobre la funcionalidad dedicada al impuesto sobre el valor añadido intracomunitario (IVA). Explica cómo se activa la funcionalidad, cómo se calculan e imprimen los importes de IVA intracomunitarios, y revisa los importes de IVA intracomunitarios que se han registrado."
author: Anasyash
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271523
ms.search.region: Spain
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5d5ad4d5b1141e6f7d76e06f2335465cad1161ce
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="intra-community-vat-for-spain"></a><span data-ttu-id="b3db9-104">IVA intracomunitario para España</span><span class="sxs-lookup"><span data-stu-id="b3db9-104">Intra-community VAT for Spain</span></span>
[!include[banner](../includes/banner.md)]


<span data-ttu-id="b3db9-105">Este tema proporciona información sobre la funcionalidad dedicada al impuesto sobre el valor añadido intracomunitario (IVA).</span><span class="sxs-lookup"><span data-stu-id="b3db9-105">This topic provides information about the functionality for intra-community value-added tax (VAT).</span></span> <span data-ttu-id="b3db9-106">Explica cómo se activa la funcionalidad, cómo se calculan e imprimen los importes de IVA intracomunitarios, y revisa los importes de IVA intracomunitarios que se han registrado.</span><span class="sxs-lookup"><span data-stu-id="b3db9-106">It explains how to turn on the functionality, calculate and print intra-community VAT amounts, and review intra-community VAT amounts that have been posted.</span></span>

<span data-ttu-id="b3db9-107">La información acerca del impuesto sobre el valor añadido (IVA) intracomunitario se puede calcular y registrar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b3db9-107">Information about intra-community value-added tax (VAT) can be calculated and posted automatically.</span></span> <span data-ttu-id="b3db9-108">Cuando se registra una factura de proveedor de la Unión Europea (EU), se crean dos transacciones de IVA.</span><span class="sxs-lookup"><span data-stu-id="b3db9-108">When you post a European Union (EU) vendor invoice, two VAT transactions are created.</span></span> <span data-ttu-id="b3db9-109">Una transacción de IVA se crea para los impuestos pagaderos, y otra transacción de IVA se crea para los impuestos soportados.</span><span class="sxs-lookup"><span data-stu-id="b3db9-109">One VAT transaction is created for payable sales tax, and the other VAT transaction is created for receivable sales tax.</span></span> <span data-ttu-id="b3db9-110">Antes de poder utilizar la funcionalidad del IVA intracomunitario, debe habilitar la opción **IVA intracomunitario** en la pestaña **Impuestos y contabilidad** de la página **Parámetros de proveedores** .</span><span class="sxs-lookup"><span data-stu-id="b3db9-110">Before you can use the intra-community VAT functionality, you must enable the **Intra-community VAT** option on the **Ledger and sales tax** tab of the **Accounts payable parameters** page.</span></span>

## <a name="calculating-intracommunity-vat-for-purchase-transactions"></a><span data-ttu-id="b3db9-111">Cálculo del IVA intracomunitario para las transacciones de compra</span><span class="sxs-lookup"><span data-stu-id="b3db9-111">Calculating intracommunity VAT for purchase transactions</span></span>
<span data-ttu-id="b3db9-112">Para calcular el IVA intracomunitario de las transacciones de compra, debe tener dos códigos de impuestos que tengan el mismo porcentaje de impuestos.</span><span class="sxs-lookup"><span data-stu-id="b3db9-112">To calculate intra-community VAT for purchase transactions, you must have two sales tax codes that have the same tax percentage.</span></span> <span data-ttu-id="b3db9-113">Sin embargo, un código debe tener un porcentaje de impuestos positivo, y el otro código debe tener un porcentaje de impuestos negativo.</span><span class="sxs-lookup"><span data-stu-id="b3db9-113">However, one code must have a positive tax percentage, and the other code must have a negative tax percentage.</span></span> <span data-ttu-id="b3db9-114">También debe tener un grupo de impuestos que contenga un código de impuestos positivo y un código de impuestos negativo.</span><span class="sxs-lookup"><span data-stu-id="b3db9-114">You must also have a sales tax group that contains both a positive sales tax code and a negative sales tax code.</span></span> <span data-ttu-id="b3db9-115">Seleccione la casilla de verificación **IVA intracomunitario** para la línea que tenga un código de impuestos negativo.</span><span class="sxs-lookup"><span data-stu-id="b3db9-115">Select the **Intra-community VAT** check box for the line that has a negative sales tax code.</span></span> 

## <a name="printing-intracommunity-vat-on-a-purchase-invoice"></a><span data-ttu-id="b3db9-116">Imprimir IVA intracomunitario en una factura de compra</span><span class="sxs-lookup"><span data-stu-id="b3db9-116">Printing intracommunity VAT on a purchase invoice</span></span>
<span data-ttu-id="b3db9-117">Para imprimir el IVA intracomunitario en una factura de compra, active la opción **Imprimir impuesto de UE en facturas españolas** en la pestaña **Factura** de la página **Configuración de formulario** (**Proveedores** &gt; **Configuración** &gt; **Formularios** &gt; **Configuración de formulario**).</span><span class="sxs-lookup"><span data-stu-id="b3db9-117">To print intra-community VAT on a purchase invoice, enable the **Print EU sales tax on Spanish invoices** option on the **Invoice** tab of the **Form setup** page (**Accounts payable** &gt; **Setup** &gt; **Forms** &gt; **Form setup**).</span></span>

## <a name="printing-invoices-that-have-intracommunity-vat-amounts"></a><span data-ttu-id="b3db9-118">Impresión de facturas que tienen importes de IVA intracomunitarios</span><span class="sxs-lookup"><span data-stu-id="b3db9-118">Printing invoices that have intracommunity VAT amounts</span></span>
<span data-ttu-id="b3db9-119">Para imprimir facturas de compra y facturas intracomunitarias que tienen importes de IVA intracomunitarios, en la página de la factura de proveedor, en la pestaña **Proceso** , haga clic en **Configuración de impresión** &gt; **Opciones de impresión**.</span><span class="sxs-lookup"><span data-stu-id="b3db9-119">To print purchase invoices and intra-community invoices that have intra-community VAT amounts, on the vendor invoice page, on the **Process** tab, click **Print setup** &gt; **Print options**.</span></span> <span data-ttu-id="b3db9-120">En el cuadro de diálogo **Opciones de impresión**, habilite las opciones **Imprimir factura** e **Imprimir autofactura intracomunitaria** .</span><span class="sxs-lookup"><span data-stu-id="b3db9-120">In the **Print options** dialog box, enable the **Print invoice** and **Print intra-community invoice** options.</span></span>

## <a name="reviewing-posted-intracommunity-vat-amounts"></a><span data-ttu-id="b3db9-121">Revisar importes de IVA intracomunitarios enviados</span><span class="sxs-lookup"><span data-stu-id="b3db9-121">Reviewing posted intracommunity VAT amounts</span></span>
<span data-ttu-id="b3db9-122">Para revisar los importes de IVA intracomunitarios registrados, ejecute la consulta de impuestos registrados (**Impuestos** &gt; **Consultas e informes** &gt; **Consultas de impuestos** &gt; **Impuestos registrados**).</span><span class="sxs-lookup"><span data-stu-id="b3db9-122">To review the intra-community VAT amounts that have been posted, run the Posted sales tax query (**Tax** &gt; **Inquiries and reports** &gt; **Sales tax inquiries** &gt; **Posted sales tax**).</span></span> <span data-ttu-id="b3db9-123">En la página **Impuestos registrados** , en la pestaña **General** , si se selecciona la casilla de verificación **IVA intracomunitario**, la transacción de impuestos es una transacción de IVA intracomunitario.</span><span class="sxs-lookup"><span data-stu-id="b3db9-123">On the **Posted sales tax** page, on the **General** tab, if the **Intra-community VAT** check box is selected, the tax transaction is an intra-community VAT transaction.</span></span> <span data-ttu-id="b3db9-124">Los libros de IVA de España se deben configurar para que las transacciones de IVA soportadas y repercutidas se reflejen en las secciones adecuadas.</span><span class="sxs-lookup"><span data-stu-id="b3db9-124">Spanish VAT books must be set up so that posted payable and receivable VAT transactions are reflected in the appropriate sections.</span></span> <span data-ttu-id="b3db9-125">Para configurar los libros de IVA para España, haga clic en **Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Libros de IVA españoles**.</span><span class="sxs-lookup"><span data-stu-id="b3db9-125">To set up Spanish VAT books, click **Tax** &gt; **Setup** &gt; **Sales tax** &gt; **Spanish VAT books**.</span></span> <span data-ttu-id="b3db9-126">Para obtener más información, vea el modelo 340 de declaración de IVA de España.</span><span class="sxs-lookup"><span data-stu-id="b3db9-126">For more information, see VAT 340 Modelo declaration for Spain.</span></span>



