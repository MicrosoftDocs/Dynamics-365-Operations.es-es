---
title: Configurar códigos de impuestos
description: Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f29442c2ef2e3d0008a74298fda218e4cbd93f8e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571592"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="e77b5-103">Configurar códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="e77b5-103">Set up sales tax codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e77b5-104">Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="e77b5-104">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="e77b5-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="e77b5-105">This task uses the USMF demo company.</span></span>



1. <span data-ttu-id="e77b5-106">Vaya a Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-106">Go to Tax > Indirect taxes > Sales tax > Sales tax codes.</span></span>
2. <span data-ttu-id="e77b5-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e77b5-107">Click New.</span></span>
3. <span data-ttu-id="e77b5-108">En el campo de código de impuestos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e77b5-108">In the Sales tax code field, type a value.</span></span>
4. <span data-ttu-id="e77b5-109">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e77b5-109">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e77b5-110">Seleccione un período de liquidación para especificar qué autoridad fiscal y en qué intervalos tienen que notificarse y pagarse estos impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-110">Select a Settlement period to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="e77b5-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e77b5-111">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="e77b5-112">Seleccione un grupo de registro para especificar las cuentas principales para registrar los impuestos en contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="e77b5-112">Select a Ledger posting group to specify the main accounts to post sales tax to the general ledger.</span></span>
8. <span data-ttu-id="e77b5-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e77b5-113">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="e77b5-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e77b5-114">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="e77b5-115">Expanda la ficha desplegable Cálculo.</span><span class="sxs-lookup"><span data-stu-id="e77b5-115">Expand the Calculation FastTab.</span></span>
    * <span data-ttu-id="e77b5-116">La ficha desplegable Cálculo tiene varios campos que controlan cómo se calcularán los importes de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-116">The Calculation FastTab has multiple fields that control how sales tax amounts will be calculated.</span></span>  
11. <span data-ttu-id="e77b5-117">En el panel de acciones, haga clic en Código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-117">On the Action Pane, click Sales tax code.</span></span>
12. <span data-ttu-id="e77b5-118">Haga clic en Valores.</span><span class="sxs-lookup"><span data-stu-id="e77b5-118">Click Values.</span></span>
13. <span data-ttu-id="e77b5-119">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e77b5-119">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="e77b5-120">Especifique el valor de este código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-120">Enter the value for this tax code.</span></span>
    * <span data-ttu-id="e77b5-121">En la ficha desplegable Cálculo, en el campo Origen, si está seleccionado el importe por unidad, el valor se multiplicará por la cantidad de la transacción para calcular el importe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-121">On the Calculation FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="e77b5-122">Si el código de impuesto no es un impuesto basado en la unidad, el valor es un porcentaje que se aplica en el origen de este código de impuesto para calcular el importe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="e77b5-122">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
15. <span data-ttu-id="e77b5-123">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e77b5-123">Click Save.</span></span>
16. <span data-ttu-id="e77b5-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e77b5-124">Close the page.</span></span>
17. <span data-ttu-id="e77b5-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e77b5-125">Click Save.</span></span>

