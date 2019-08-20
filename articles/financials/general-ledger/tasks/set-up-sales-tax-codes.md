---
title: Configurar códigos de impuestos
description: Este tema explica cómo configurar códigos de impuestos en Dynamics 365 for Finance and Operations.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3419c6b569093d717158e80bd9bc01054d82bff9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834839"
---
# <a name="set-up-sales-tax-codes"></a><span data-ttu-id="f6195-103">Configurar códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="f6195-103">Set up sales tax codes</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f6195-104">Este tema explica cómo configurar códigos de impuestos en Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f6195-104">This topic explains how to set up sales tax codes in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f6195-105">Los códigos de impuestos se crean para cada impuesto indirecto o arancel que la entidad jurídica está obligada a calcular, recaudar y pagar a las autoridades fiscales.</span><span class="sxs-lookup"><span data-stu-id="f6195-105">Sales tax codes are created for every indirect tax or duty that the legal entity is obligated to calculate, collect, and pay to sales tax authorities.</span></span>

<span data-ttu-id="f6195-106">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="f6195-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="f6195-107">Vaya al **panel de navegación > Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="f6195-107">Go to **Navigation pane > Tax > Indirect taxes > Sales tax > Sales tax codes**.</span></span>
2. <span data-ttu-id="f6195-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f6195-108">Select **New**.</span></span>
3. <span data-ttu-id="f6195-109">En el campo de **código de impuestos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f6195-109">In the **Sales tax code** field, type a value.</span></span>
4. <span data-ttu-id="f6195-110">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f6195-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="f6195-111">Seleccione un **período de liquidación** abriendo la lista desplegable para especificar qué autoridad fiscal y en qué intervalos tienen que notificarse y pagarse estos impuestos.</span><span class="sxs-lookup"><span data-stu-id="f6195-111">Select a **Settlement period** by opening the pull-down list to specify which Sales tax authority and in which intervals this sales tax needs to be reported and paid.</span></span>
6. <span data-ttu-id="f6195-112">Seleccione un **grupo de registro** para especificar las cuentas principales para registrar los impuestos en contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="f6195-112">Select a **Ledger posting group** to specify the main accounts to post sales tax to the general ledger.</span></span>
7. <span data-ttu-id="f6195-113">Expanda la ficha desplegable **Cálculo**.</span><span class="sxs-lookup"><span data-stu-id="f6195-113">Expand the **Calculation** FastTab.</span></span> <span data-ttu-id="f6195-114">Tiene varios campos que controlan cómo se calcularán los importes de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f6195-114">This includes multiple fields that control how sales tax amounts will be calculated.</span></span> <span data-ttu-id="f6195-115">Complete estos campos según convenga.</span><span class="sxs-lookup"><span data-stu-id="f6195-115">Fill these fields out as needed.</span></span>  
8. <span data-ttu-id="f6195-116">En el **Panel de acciones** en la parte superior de la interfaz, seleccione **Código de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="f6195-116">On the **Action Pane** at the top of the interface, select **Sales tax code**.</span></span>
9. <span data-ttu-id="f6195-117">Seleccione **Valores**.</span><span class="sxs-lookup"><span data-stu-id="f6195-117">Select **Values**.</span></span>
10. <span data-ttu-id="f6195-118">Escriba el valor para este código de impuestos en la columna **valor** .</span><span class="sxs-lookup"><span data-stu-id="f6195-118">Enter the value for this tax code in the **value** column.</span></span>
    - <span data-ttu-id="f6195-119">En la ficha desplegable **Cálculo**, en el campo Origen, si está seleccionado el importe por unidad, el valor se multiplicará por la cantidad de la transacción para calcular el importe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f6195-119">On the **Calculation** FastTab, in the Origin field, if Amount per unit is selected, the value will be multiplied by the quantity on the transaction to calculate the sales tax amount.</span></span>  <span data-ttu-id="f6195-120">Si el código de impuesto no es un impuesto basado en la unidad, el valor es un porcentaje que se aplica en el origen de este código de impuesto para calcular el importe de impuestos.</span><span class="sxs-lookup"><span data-stu-id="f6195-120">If the tax code is not a unit based tax, the value is a percentage that is applied on the Origin for this tax code to calculate the sales tax amount.</span></span>     
11. <span data-ttu-id="f6195-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6195-121">Select **Save**.</span></span>
12. <span data-ttu-id="f6195-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f6195-122">Close the page.</span></span>
13. <span data-ttu-id="f6195-123">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6195-123">Select **Save**.</span></span>

