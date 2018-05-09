---
title: "Configuración de un flujo de trabajo de elementos"
description: "Este tema explica cómo configurar un elemento de flujo de trabajo de elementos."
author: sericks007
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1d36ec599250f62c523e8d538a37cada9b223007
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="configure-a-line-item-workflow"></a><span data-ttu-id="11f43-103">Configuración de un flujo de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="11f43-103">Configure a line-item workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11f43-104">Este tema explica cómo configurar un elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="11f43-104">This topic explains how to configure a line-item workflow element.</span></span>

<span data-ttu-id="11f43-105">Para configurar un elemento de flujo de trabajo de elementos, en el editor de flujo de trabajo, haga clic con el botón derecho en el elemento y, a continuación, haga clic en **Propiedades** para abrir la página de **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="11f43-105">To configure a line-item workflow element, in the workflow editor, right-click the element, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="11f43-106">A continuación use los siguientes procedimientos para configurar las propiedades del elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="11f43-106">Then use the following procedures to configure the properties of the line-item workflow element.</span></span>

## <a name="name-the-line-item-workflow-element"></a><span data-ttu-id="11f43-107">Asignación de un nombre al elemento de flujo de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="11f43-107">Name the line-item workflow element</span></span>
<span data-ttu-id="11f43-108">Siga estos pasos para asignar un nombre al elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="11f43-108">Follow these steps to enter a name for the line-item workflow element.</span></span>

1.  <span data-ttu-id="11f43-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="11f43-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="11f43-110">En el campo **Nombre**, escriba un nombre único para el elemento de flujo de trabajo de elementos.</span><span class="sxs-lookup"><span data-stu-id="11f43-110">In the **Name** field, enter a unique name for the line-item workflow element.</span></span>

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a><span data-ttu-id="11f43-111">Especificación de si todos los elementos de línea se procesan con el mismo flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="11f43-111">Specify whether the same workflow is used to process all line items</span></span>
<span data-ttu-id="11f43-112">Siga estos pasos para especificar si el mismo flujo de trabajo se usa para procesar todos los elementos de línea de un documento.</span><span class="sxs-lookup"><span data-stu-id="11f43-112">Follow these steps to specify whether the same workflow is used to process all the line items on a document.</span></span>

1.  <span data-ttu-id="11f43-113">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="11f43-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="11f43-114">Si el mismo flujo de trabajo procesa todos los artículos de línea de un documento, haga clic en **Invocar un solo flujo de trabajo para todos los artículos de línea**.</span><span class="sxs-lookup"><span data-stu-id="11f43-114">If the same workflow should process all the line items on a document, click **Invoke a single workflow for all line-items**.</span></span> <span data-ttu-id="11f43-115">A continuación, seleccione el flujo de trabajo que se va a usar para procesar los elementos de línea.</span><span class="sxs-lookup"><span data-stu-id="11f43-115">Then select the workflow to use to process the line items.</span></span>
3.  <span data-ttu-id="11f43-116">Si un flujo de trabajo específico procesa los elementos de línea que cumplen un conjunto de condiciones concreto, haga clic en **Invocar un flujo de trabajo para cada artículo de línea**.</span><span class="sxs-lookup"><span data-stu-id="11f43-116">If a specific workflow should process line items that meet a specific set of conditions, click **Invoke a workflow for each line-item**.</span></span> <span data-ttu-id="11f43-117">A continuación, siga estos pasos para definir el conjunto de condiciones:</span><span class="sxs-lookup"><span data-stu-id="11f43-117">Then follow these steps to define the set of conditions:</span></span>
    1.  <span data-ttu-id="11f43-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="11f43-118">Click **Add**.</span></span>
    2.  <span data-ttu-id="11f43-119">En la tabla, seleccione la condición.</span><span class="sxs-lookup"><span data-stu-id="11f43-119">Select the condition in the table.</span></span>
    3.  <span data-ttu-id="11f43-120">En la pestaña **Nombre de condición**, escriba un nombre para el conjunto de condiciones que está definiendo.</span><span class="sxs-lookup"><span data-stu-id="11f43-120">On the **Condition name** tab, enter a name for the set of conditions that you're defining.</span></span>
    4.  <span data-ttu-id="11f43-121">Haga clic en **Agregar condición** para escribir una condición.</span><span class="sxs-lookup"><span data-stu-id="11f43-121">Click **Add condition** to enter a condition.</span></span>
    5.  <span data-ttu-id="11f43-122">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="11f43-122">Enter any additional conditions that are required.</span></span>
    6.  <span data-ttu-id="11f43-123">Para comprobar que el conjunto de condiciones definido se ha configurado correctamente, haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="11f43-123">To verify that the set of conditions that you entered is configured correctly, click **Test**.</span></span> <span data-ttu-id="11f43-124">En la página **Probar condición de flujo de trabajo**, en el área **Validar condición**, seleccione un registro y haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="11f43-124">On the **Test workflow condition** page, in the **Validate condition** area, select a record, and then click **Test**.</span></span> <span data-ttu-id="11f43-125">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.</span><span class="sxs-lookup"><span data-stu-id="11f43-125">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span> <span data-ttu-id="11f43-126">Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="11f43-126">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

    <span data-ttu-id="11f43-127">En la pestaña **Flujo de trabajo**, seleccione el flujo de trabajo para procesar los elementos de línea que cumplan con el conjunto de condiciones definido.</span><span class="sxs-lookup"><span data-stu-id="11f43-127">On the **Workflow** tab, select the workflow select the workflow to use to process line items that meet the set of conditions that you defined.</span></span>





