---
title: Calcular y ajustar los impuestos en una factura de proveedor
description: Si el documento de origen inicial muestra diferentes importes de impuestos según los calcula, puede ajustar dichos importes antes del registro.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 803c038d907b68a3c72a83a3e035c4e08b8a8661
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545180"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a><span data-ttu-id="ca49a-103">Calcular y ajustar los impuestos en una factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="ca49a-103">Calculate and adjust sales tax on a vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca49a-104">Si el documento de origen inicial muestra diferentes importes de impuestos según los calcula, puede ajustar dichos importes antes del registro.</span><span class="sxs-lookup"><span data-stu-id="ca49a-104">If the original source document displays different tax amounts as calculated, you can adjust those amounts before posting.</span></span> <span data-ttu-id="ca49a-105">Esta tarea usa la empresa de demostración DEMF.</span><span class="sxs-lookup"><span data-stu-id="ca49a-105">This task uses the DEMF demo company.</span></span>

1. <span data-ttu-id="ca49a-106">Vaya a Proveedores > Facturas > Diario de facturas.</span><span class="sxs-lookup"><span data-stu-id="ca49a-106">Go to Accounts payable > Invoices > Invoice journal.</span></span>
2. <span data-ttu-id="ca49a-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ca49a-107">Click New.</span></span>
3. <span data-ttu-id="ca49a-108">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca49a-108">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ca49a-109">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca49a-109">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ca49a-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca49a-110">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ca49a-111">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="ca49a-111">Click Lines.</span></span>
7. <span data-ttu-id="ca49a-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca49a-112">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="ca49a-113">En el campo Cuenta, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="ca49a-113">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="ca49a-114">En el campo Factura, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ca49a-114">In the Invoice field, type a value.</span></span>
10. <span data-ttu-id="ca49a-115">En el campo Crédito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="ca49a-115">In the Credit field, enter a number.</span></span>
11. <span data-ttu-id="ca49a-116">En el campo Cuenta de contrapartida, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="ca49a-116">In the Offset account field, specify the desired values.</span></span>
12. <span data-ttu-id="ca49a-117">Haga clic en Impuestos.</span><span class="sxs-lookup"><span data-stu-id="ca49a-117">Click Sales tax.</span></span>
13. <span data-ttu-id="ca49a-118">En el campo Importe total real de impuestos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="ca49a-118">In the Total actual sales tax amount field, enter a number.</span></span>
14. <span data-ttu-id="ca49a-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ca49a-119">Click OK.</span></span>
15. <span data-ttu-id="ca49a-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ca49a-120">Click Save.</span></span>
16. <span data-ttu-id="ca49a-121">Haga clic en Impuestos.</span><span class="sxs-lookup"><span data-stu-id="ca49a-121">Click Sales tax.</span></span>
17. <span data-ttu-id="ca49a-122">En la ficha Ajuste, los importes de impuestos se pueden ajustar por código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="ca49a-122">On the Adjustment tab, the sales tax amounts can be adjusted per sales tax code.</span></span>
18. <span data-ttu-id="ca49a-123">Haga clic en Restablecer importes reales a partir de los importes calculados.</span><span class="sxs-lookup"><span data-stu-id="ca49a-123">Click Reset actual from calculated amounts.</span></span>
19. <span data-ttu-id="ca49a-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ca49a-124">Click OK.</span></span>
20. <span data-ttu-id="ca49a-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="ca49a-125">Click Save.</span></span>

