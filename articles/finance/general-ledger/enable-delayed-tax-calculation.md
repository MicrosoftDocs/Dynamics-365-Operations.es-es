---
title: Habilitar el cálculo de impuestos retrasado en el diario
description: Este tema explica cómo usar la función **Habilitar el cálculo de impuestos retrasado en el diario** para mejorar el rendimiento del cálculo de impuestos cuando el volumen de las líneas de diario es muy grande.
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
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179741"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="d7d64-103">Habilitar el cálculo de impuestos retrasado en el diario</span><span class="sxs-lookup"><span data-stu-id="d7d64-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d7d64-104">Este tema explica cómo usar la función **Habilitar el cálculo de impuestos retrasado en el diario** para mejorar el rendimiento del cálculo de impuestos cuando el volumen de las líneas de diario es muy grande.</span><span class="sxs-lookup"><span data-stu-id="d7d64-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="d7d64-105">El comportamiento actual del cálculo de impuestos en diario se activa en tiempo real cuando el usuario actualiza los campos relacionados con impuestos, por ejemplo grupo de impuestos/grupo de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="d7d64-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="d7d64-106">Todas las actualizaciones en el nivel de línea de diario recalculan el importe de los impuestos en todas las líneas de diario.</span><span class="sxs-lookup"><span data-stu-id="d7d64-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="d7d64-107">Ayuda al usuario a consultar el importe de impuestos calculado en tiempo real, pero también podría elevar la degradación del rendimiento si el volumen de líneas de diario es muy elevado.</span><span class="sxs-lookup"><span data-stu-id="d7d64-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="d7d64-108">Esta característica proporciona una opción para retrasar el cálculo de impuestos para solucionar la degradación de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d7d64-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="d7d64-109">Si está activada esta función, el importe de impuestos sólo se calculará cuando el usuario haga clic en el comando "Impuestos" o registra en el diario.</span><span class="sxs-lookup"><span data-stu-id="d7d64-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="d7d64-110">El usuario puede activar o desactivar el parámetro en tres niveles:</span><span class="sxs-lookup"><span data-stu-id="d7d64-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="d7d64-111">Por entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="d7d64-111">By legal entity</span></span>
- <span data-ttu-id="d7d64-112">Por nombre del diario</span><span class="sxs-lookup"><span data-stu-id="d7d64-112">By journal name</span></span>
- <span data-ttu-id="d7d64-113">Por encabezado de diario</span><span class="sxs-lookup"><span data-stu-id="d7d64-113">By journal header</span></span>

<span data-ttu-id="d7d64-114">El sistema tomará el valor de parámetro de la cabecera de diario como valor final.</span><span class="sxs-lookup"><span data-stu-id="d7d64-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="d7d64-115">El valor de parámetro de la cabecera de diario se tomará predeterminadamente del nombre de diario.</span><span class="sxs-lookup"><span data-stu-id="d7d64-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="d7d64-116">El valor de parámetro en el nombre de diario se tomará predeterminadamente del parámetro de contabilidad general cuando se crea el nombre del diario.</span><span class="sxs-lookup"><span data-stu-id="d7d64-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="d7d64-117">Los campos "Importe real de impuestos" y "Importe de impuestos calculado" del diario estarán ocultos si está activado este parámetro.</span><span class="sxs-lookup"><span data-stu-id="d7d64-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="d7d64-118">El propósito es no confundir al usuario porque el valor de estos dos campos siempre mostrará 0 antes de que el usuario desencadene el cálculo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="d7d64-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="d7d64-119">Habilitar el cáculo de impuestos retrasado por entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="d7d64-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="d7d64-120">Vaya a **Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general**</span><span class="sxs-lookup"><span data-stu-id="d7d64-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="d7d64-121">Haga clic en **Impuestos**</span><span class="sxs-lookup"><span data-stu-id="d7d64-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="d7d64-122">En la ficha rápida **General**, busque el parámetro **Cálculo retrasado de impuestos** y actívelo o desactívelo.</span><span class="sxs-lookup"><span data-stu-id="d7d64-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="d7d64-123">Habilitar el cálculo de impuestos retrasado por nombre de diario</span><span class="sxs-lookup"><span data-stu-id="d7d64-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="d7d64-124">Vaya a **Contabilidad general > Configuración de diario > Nombres de diarios**</span><span class="sxs-lookup"><span data-stu-id="d7d64-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="d7d64-125">En la ficha rápida **General**, busque el parámetro **Cálculo retrasado de impuestos** y actívelo o desactívelo.</span><span class="sxs-lookup"><span data-stu-id="d7d64-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="d7d64-126">Habilitar el cálculo de impuestos retrasado por diario</span><span class="sxs-lookup"><span data-stu-id="d7d64-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="d7d64-127">Vaya a **Contabilidad general > Movimientos de diario > Diarios generales**</span><span class="sxs-lookup"><span data-stu-id="d7d64-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="d7d64-128">Haga clic en **Nuevo**</span><span class="sxs-lookup"><span data-stu-id="d7d64-128">Click **New**</span></span>
3. <span data-ttu-id="d7d64-129">Seleccione un nombre de diario</span><span class="sxs-lookup"><span data-stu-id="d7d64-129">Select a journal name</span></span>
4. <span data-ttu-id="d7d64-130">Haga clic en **Configurar**</span><span class="sxs-lookup"><span data-stu-id="d7d64-130">Click **Setup**</span></span>
5. <span data-ttu-id="d7d64-131">Busque el parámetro **Cálculo retrasado de impuestos** y actívelo o desactívelo.</span><span class="sxs-lookup"><span data-stu-id="d7d64-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
