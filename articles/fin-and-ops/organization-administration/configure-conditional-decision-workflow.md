---
title: Configurar decisiones condicionales en un flujo de trabajo
description: "Use el siguiente procedimiento para configurar las propiedades de una decisión condicional."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 64e8b2ed5c538cb982f9f03c1db24e38472be868
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="5eaeb-103">Configurar decisiones condicionales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5eaeb-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5eaeb-104">Use el siguiente procedimiento para configurar las propiedades de una decisión condicional.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="5eaeb-105">Una decisión condicional es un punto en el que un flujo de trabajo se divide en dos ramas.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="5eaeb-106">Para configurar una decisión condicional, en el editor de flujo de trabajo, haga clic con el botón derecho en la decisión condicional y, a continuación, haga clic en **Propiedades** para abrir el formulario **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="5eaeb-107">Asignar un nombre a una decisión</span><span class="sxs-lookup"><span data-stu-id="5eaeb-107">Name a decision</span></span>
<span data-ttu-id="5eaeb-108">Siga estos pasos para asignar un nombre a una decisión condicional.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-108">Follow these steps to enter a name for a conditional decision.</span></span>
1.  <span data-ttu-id="5eaeb-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="5eaeb-110">En el campo **Nombre**, escriba un nombre único para la decisión condicional.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="5eaeb-111"> Establecimiento de condiciones</span><span class="sxs-lookup"><span data-stu-id="5eaeb-111">Set conditions</span></span>
<span data-ttu-id="5eaeb-112">Para decidir la rama que se usa, el sistema evalúa el documento enviado para determinar si cumple con determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>
1.  <span data-ttu-id="5eaeb-113">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-113">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="5eaeb-114">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-114">Click **Add condition**.</span></span>
3.  <span data-ttu-id="5eaeb-115">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-115">Enter a condition.</span></span>
4.  <span data-ttu-id="5eaeb-116">Escriba condiciones adicionales, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-116">Enter additional conditions, if they are required.</span></span>
5.  <span data-ttu-id="5eaeb-117">Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5eaeb-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>
    1.  <span data-ttu-id="5eaeb-118">Haga clic en **Probar** para abrir el formulario **Probar la condición del flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2.  <span data-ttu-id="5eaeb-119">Seleccione un registro del área **Comprobar condición** del formulario.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-119">Select a record in the **Validate condition** area of the form.</span></span>
    3.  <span data-ttu-id="5eaeb-120">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-120">Click **Test**.</span></span> <span data-ttu-id="5eaeb-121">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4.  <span data-ttu-id="5eaeb-122">Haga clic en **Aceptar** o en **Cancelar** para regresar al formulario **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5eaeb-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>






