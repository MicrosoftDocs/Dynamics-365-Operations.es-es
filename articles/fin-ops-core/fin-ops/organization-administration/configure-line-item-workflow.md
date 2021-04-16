---
title: Configuración de flujos de trabajo de elementos
description: Este tema explica cómo configurar un elemento de flujo de trabajo de elementos.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84da7080542b4cc2ecc487b0a1331482fb69b998
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747914"
---
# <a name="configure-line-item-workflows"></a><span data-ttu-id="c109f-103">Configuración de flujos de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="c109f-103">Configure line-item workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c109f-104">Este tema explica cómo configurar un elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="c109f-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="c109f-105">Para configurar un elemento de flujo de trabajo de elementos, en el editor de flujo de trabajo, haga clic con el botón derecho en el elemento y, a continuación, haga clic en **Propiedades** para abrir la página de **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c109f-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="c109f-106">A continuación use los siguientes procedimientos para configurar las propiedades del elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="c109f-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="c109f-107">Asignación de un nombre al elemento de flujo de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="c109f-107">Name the line-item workflow element</span></span>

<span data-ttu-id="c109f-108">Siga estos pasos para asignar un nombre al elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="c109f-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1. <span data-ttu-id="c109f-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="c109f-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c109f-110">En el campo **Nombre**, escriba un nombre único para el elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="c109f-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="c109f-111">Especificación de si todos los elementos de línea se procesan con el mismo flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c109f-111">Specify whether the same workflow is used to process all line items</span></span>

<span data-ttu-id="c109f-112">Siga estos pasos para especificar si el mismo flujo de trabajo se usa para procesar todos los elementos de línea de un documento.</span><span class="sxs-lookup"><span data-stu-id="c109f-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1. <span data-ttu-id="c109f-113">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="c109f-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="c109f-114">Si el mismo flujo de trabajo procesa todos los artículos de línea de un documento, haga clic en **Invocar un solo flujo de trabajo para todos los artículos de línea**.</span><span class="sxs-lookup"><span data-stu-id="c109f-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="c109f-115">A continuación, seleccione el flujo de trabajo que se va a usar para procesar los elementos de línea.</span><span class="sxs-lookup"><span data-stu-id="c109f-115">Then select the workflow to use to process the line items.</span></span>
3. <span data-ttu-id="c109f-116">Si un flujo de trabajo específico procesa los elementos de línea que cumplen un conjunto de condiciones concreto, haga clic en **Invocar un flujo de trabajo para cada artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="c109f-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="c109f-117">A continuación, siga estos pasos para definir el conjunto de condiciones:</span><span class="sxs-lookup"><span data-stu-id="c109f-117">Then follow these steps to define the set of conditions:</span></span>

    1. <span data-ttu-id="c109f-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c109f-118">Click **Add**.</span></span>
    2. <span data-ttu-id="c109f-119">En la tabla, seleccione la condición.</span><span class="sxs-lookup"><span data-stu-id="c109f-119">Select the condition in the table.</span></span>
    3. <span data-ttu-id="c109f-120">En la pestaña **Nombre de condición**, escriba un nombre para el conjunto de condiciones que está definiendo.</span><span class="sxs-lookup"><span data-stu-id="c109f-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4. <span data-ttu-id="c109f-121">Haga clic en **Agregar condición** para escribir una condición.</span><span class="sxs-lookup"><span data-stu-id="c109f-121">Click **Add condition** to enter a condition.</span></span>
    5. <span data-ttu-id="c109f-122">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="c109f-122">Enter any additional conditions that are required.</span></span>
    6. <span data-ttu-id="c109f-123">Para comprobar que el conjunto de condiciones definido se ha configurado correctamente, haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="c109f-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="c109f-124">En la página **Probar condición de flujo de trabajo**, en el área **Validar condición**, seleccione un registro y haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="c109f-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="c109f-125">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.</span><span class="sxs-lookup"><span data-stu-id="c109f-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="c109f-126">Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c109f-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="c109f-127">En la pestaña **Flujo de trabajo**, seleccione el flujo de trabajo para procesar los elementos de línea que cumplan con el conjunto de condiciones definido.</span><span class="sxs-lookup"><span data-stu-id="c109f-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]