---
title: Calcular y ajustar los impuestos en una factura de proveedor
description: En este tema se explica cómo ajustar los impuestos para una factura de proveedor en Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2f3521f7bc56659fc6f7a6d47f581ddbfea16523
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139976"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="3b8b1-103">Calcular y ajustar los impuestos en una factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="3b8b1-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b8b1-104">En este tema se explica cómo ajustar los impuestos para una factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-104">This topic explains how to adjust sales tax on a vendor invoice.</span></span> <span data-ttu-id="3b8b1-105">Si el documento de origen inicial muestra diferentes importes de impuestos según los calcula, puede ajustar dichos importes antes del registro.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-105">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="3b8b1-106">Esta tarea usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-106">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="3b8b1-107">En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Diario de facturas**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-107">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice journal**.</span></span>
2. <span data-ttu-id="3b8b1-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-108">Select **New**.</span></span>
3. <span data-ttu-id="3b8b1-109">En el campo **Nombre** de la nueva fila, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-109">In the **Name** field of the new row, select an option in the drop-down menu.</span></span>
4. <span data-ttu-id="3b8b1-110">En el panel de acciones, seleccione **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-110">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="3b8b1-111">En el campo **Cuenta**, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-111">In the **Account** field, specify the desired values.</span></span>
6. <span data-ttu-id="3b8b1-112">En el campo **Factura**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="3b8b1-113">En el campo **Crédito**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-113">In the **Credit** field, enter a number.</span></span>
8. <span data-ttu-id="3b8b1-114">En el campo **Cuenta de contrapartida**, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-114">In the **Offset account** field, specify the desired values.</span></span>
9. <span data-ttu-id="3b8b1-115">Seleccione **Impuestos**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-115">Select **Sales tax**.</span></span>
10. <span data-ttu-id="3b8b1-116">En el campo **Importe total real de impuestos**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-116">In the **Total actual sales tax amount** field, enter a number.</span></span>
11. <span data-ttu-id="3b8b1-117">En la ficha **Ajuste**, los importes de impuestos se pueden ajustar por código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-117">On the **Adjustment** tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
12. <span data-ttu-id="3b8b1-118">Seleccione **Restablecer importes reales a partir de los importes calculados**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-118">Select **Reset actual from calculated amounts**.</span></span>
13. <span data-ttu-id="3b8b1-119">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-119">Select **OK**.</span></span>
14. <span data-ttu-id="3b8b1-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3b8b1-120">Select **Save**.</span></span>

