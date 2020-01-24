---
title: Habilitar el cálculo de impuestos retrasado en diarios
description: Este tema explica cómo activar la función de Cálculo de impuestos retrasados para ayudar a mejorar el rendimiento del cálculo de impuestos cuando el número de las líneas de diario es muy grande.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: ed8e5f930bbb6b0fb570ba1eb23c0816210c1814
ms.sourcegitcommit: bfd6142569196a060e3f37893c78f00c40a2a18c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946175"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="7dca9-103">Habilitar el cálculo de impuestos retrasado en diarios</span><span class="sxs-lookup"><span data-stu-id="7dca9-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="7dca9-104">Este tema explica cómo puede retrasar el cálculo de impuestos en los diarios.</span><span class="sxs-lookup"><span data-stu-id="7dca9-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="7dca9-105">Esta capacidad ayuda a mejorar el rendimiento de los cálculos de impuestos cuando existen muchas líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="7dca9-106">De forma predeterminada, los importes de impuestos en las líneas de diario se calculan siempre que se actualicen los campos relacionados con impuestos.</span><span class="sxs-lookup"><span data-stu-id="7dca9-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="7dca9-107">Estos campos incluyen los campos para los grupos de impuestos y los grupos de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="7dca9-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="7dca9-108">Cualquier actualización a una línea de diario hace que las cantidades de impuestos se recalculen para todas las líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="7dca9-109">Aunque este comportamiento ayude al usuario a tener en cuenta los importes de impuestos calculados en tiempo real, también puede afectar al rendimiento si el número de líneas de diario es muy grande.</span><span class="sxs-lookup"><span data-stu-id="7dca9-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="7dca9-110">La característica retrasa del cálculo de impuestos le permite retrasar el cálculo del impuesto sobre los diarios y por tanto ayuda a corregir problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7dca9-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="7dca9-111">Cuando esta función está activada, las cantidades de impuestos sólo se calcularán cuando el usuario seleccione **Impuestos** o registre el diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="7dca9-112">Se puede retrasar el cálculo de impuestos en tres niveles:</span><span class="sxs-lookup"><span data-stu-id="7dca9-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="7dca9-113">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="7dca9-113">Legal entity</span></span>
- <span data-ttu-id="7dca9-114">Nombre del diario</span><span class="sxs-lookup"><span data-stu-id="7dca9-114">Journal name</span></span>
- <span data-ttu-id="7dca9-115">Cabecera de diario</span><span class="sxs-lookup"><span data-stu-id="7dca9-115">Journal header</span></span>

<span data-ttu-id="7dca9-116">El sistema da prioridad al valor de la cabecera de diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="7dca9-117">De forma predeterminada, este valor se toma del nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="7dca9-118">De forma predeterminada, el valor del nombre del diario se toma del valor de la página **Parámetros de contabilidad general** cuando se crea el nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="7dca9-119">En las secciones siguientes se explica cómo activar el cálculo en retraso de impuestos para las entidades jurídicas, los nombres de diario y las cabeceras de diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="7dca9-120">Active el cálculo retrasado de impuestos en el nivel de entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="7dca9-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="7dca9-121">Vaya a **Contabilidad general \> Configuración de contabilidad \> Parámetros de Contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="7dca9-122">En la pestaña **Impuestos**, en la ficha desplegable **General**, establezca la opción **Cálculo de impuestos retrasado** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagen de los parámetros de contabilidad general](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="7dca9-124">Active el cálculo retrasado de impuestos en el nivel de nombre de diario</span><span class="sxs-lookup"><span data-stu-id="7dca9-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="7dca9-125">Vaya a **Contabilidad general \> Configuración de diario \> Nombres de diarios**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="7dca9-126">En la ficha desplegable **General**, en la sección **Impuestos**, establezca la opción **Cálculo de impuestos retrasado** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagen de los nombres de diario](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="7dca9-128">Active el cálculo retrasado de impuestos en el nivel de encabezado de diario</span><span class="sxs-lookup"><span data-stu-id="7dca9-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="7dca9-129">Vaya a **Contabilidad general \> Movimientos de diario \> Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="7dca9-130">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-130">Select **New**.</span></span>
3. <span data-ttu-id="7dca9-131">Seleccione un nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="7dca9-131">Select a journal name.</span></span>
4. <span data-ttu-id="7dca9-132">En la pestaña **Configuración** , establezca la opción **Cálculo Retrasado de impuestos** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="7dca9-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagen general de la página del diario](media/delayed-tax-calculation-journal-header.png)
