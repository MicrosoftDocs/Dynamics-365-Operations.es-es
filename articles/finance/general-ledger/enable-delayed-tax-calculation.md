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
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d4ce0343ac766b30d532be0866a381dc520fd462
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447707"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="36d65-103">Habilitar el cálculo de impuestos retrasado en diarios</span><span class="sxs-lookup"><span data-stu-id="36d65-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="36d65-104">Este tema explica cómo puede retrasar el cálculo de impuestos en los diarios.</span><span class="sxs-lookup"><span data-stu-id="36d65-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="36d65-105">Esta capacidad ayuda a mejorar el rendimiento de los cálculos de impuestos cuando existen muchas líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="36d65-106">De forma predeterminada, los importes de impuestos en las líneas de diario se calculan siempre que se actualicen los campos relacionados con impuestos.</span><span class="sxs-lookup"><span data-stu-id="36d65-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="36d65-107">Estos campos incluyen los campos para los grupos de impuestos y los grupos de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="36d65-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="36d65-108">Cualquier actualización a una línea de diario hace que las cantidades de impuestos se recalculen para todas las líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="36d65-109">Aunque este comportamiento ayude al usuario a tener en cuenta los importes de impuestos calculados en tiempo real, también puede afectar al rendimiento si el número de líneas de diario es muy grande.</span><span class="sxs-lookup"><span data-stu-id="36d65-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="36d65-110">La característica retrasa del cálculo de impuestos le permite retrasar el cálculo del impuesto sobre los diarios y por tanto ayuda a corregir problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="36d65-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="36d65-111">Cuando esta función está activada, las cantidades de impuestos sólo se calcularán cuando el usuario seleccione **Impuestos** o registre el diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="36d65-112">Se puede retrasar el cálculo de impuestos en tres niveles:</span><span class="sxs-lookup"><span data-stu-id="36d65-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="36d65-113">Entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="36d65-113">Legal entity</span></span>
- <span data-ttu-id="36d65-114">Nombre del diario</span><span class="sxs-lookup"><span data-stu-id="36d65-114">Journal name</span></span>
- <span data-ttu-id="36d65-115">Cabecera de diario</span><span class="sxs-lookup"><span data-stu-id="36d65-115">Journal header</span></span>

<span data-ttu-id="36d65-116">El sistema da prioridad al valor de la cabecera de diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="36d65-117">De forma predeterminada, este valor se toma del nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="36d65-118">De forma predeterminada, el valor del nombre del diario se toma del valor de la página **Parámetros de contabilidad general** cuando se crea el nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="36d65-119">En las secciones siguientes se explica cómo activar el cálculo en retraso de impuestos para las entidades jurídicas, los nombres de diario y las cabeceras de diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="36d65-120">Active el cálculo retrasado de impuestos en el nivel de entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="36d65-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="36d65-121">Vaya a **Contabilidad general \> Configuración de contabilidad \> Parámetros de Contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="36d65-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="36d65-122">En la pestaña **Impuestos**, en la ficha desplegable **General**, establezca la opción **Cálculo de impuestos retrasado** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="36d65-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagen de los parámetros de contabilidad general](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="36d65-124">Active el cálculo retrasado de impuestos en el nivel de nombre de diario</span><span class="sxs-lookup"><span data-stu-id="36d65-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="36d65-125">Vaya a **Contabilidad general \> Configuración de diario \> Nombres de diarios**.</span><span class="sxs-lookup"><span data-stu-id="36d65-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="36d65-126">En la ficha desplegable **General**, en la sección **Impuestos**, establezca la opción **Cálculo de impuestos retrasado** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="36d65-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagen de los nombres de diario](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="36d65-128">Active el cálculo retrasado de impuestos en el nivel de encabezado de diario</span><span class="sxs-lookup"><span data-stu-id="36d65-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="36d65-129">Vaya a **Contabilidad general \> Movimientos de diario \> Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="36d65-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="36d65-130">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="36d65-130">Select **New**.</span></span>
3. <span data-ttu-id="36d65-131">Seleccione un nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="36d65-131">Select a journal name.</span></span>
4. <span data-ttu-id="36d65-132">En la pestaña **Configuración** , establezca la opción **Cálculo Retrasado de impuestos** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="36d65-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Imagen general de la página del diario](media/delayed-tax-calculation-journal-header.png)
