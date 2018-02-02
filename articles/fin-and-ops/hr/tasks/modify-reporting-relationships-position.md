--- 
title: "Modificar las relaciones jerárquicas para un puesto"
description: "Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado."
author: ShielaSogge
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a9d0d9a3f278a09e89311ee75b6f95fb4f3b04cb
ms.openlocfilehash: 6e8028689d20dd1310dfb89766db3eea3218fc90
ms.contentlocale: es-es
ms.lasthandoff: 02/02/2018

---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="dba36-103">Modificar las relaciones jerárquicas para un puesto</span><span class="sxs-lookup"><span data-stu-id="dba36-103">Modify reporting relationships for a position</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="dba36-104">Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado.</span><span class="sxs-lookup"><span data-stu-id="dba36-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="dba36-105">La relación jerárquica se puede usar para enrutar documentos mediante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dba36-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="dba36-106">El procedimiento también muestra cómo asignar el empleado a jerarquías adicionales.</span><span class="sxs-lookup"><span data-stu-id="dba36-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="dba36-107">Por ejemplo, un empleado puede formar parte de un equipo de proyecto con una relación jerárquica informal con un supervisor de proyecto.</span><span class="sxs-lookup"><span data-stu-id="dba36-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="dba36-108">Las relaciones jerárquicas adicionales se pueden definir en el puesto para adaptar distintos escenarios de proyecto o matriz.</span><span class="sxs-lookup"><span data-stu-id="dba36-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="dba36-109">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="dba36-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="dba36-110">Vaya a Recursos humanos > Puestos > Puestos.</span><span class="sxs-lookup"><span data-stu-id="dba36-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="dba36-111">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="dba36-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="dba36-112">Por ejemplo, filtre el campo Puesto según un valor de "000091".</span><span class="sxs-lookup"><span data-stu-id="dba36-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="dba36-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="dba36-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="dba36-114">Expanda la sección Notifica al puesto.</span><span class="sxs-lookup"><span data-stu-id="dba36-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="dba36-115">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="dba36-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="dba36-116">En el campo Informa a, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dba36-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="dba36-117">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="dba36-117">Click Create.</span></span>
8. <span data-ttu-id="dba36-118">Expanda la sección Relaciones.</span><span class="sxs-lookup"><span data-stu-id="dba36-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="dba36-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="dba36-119">Click Add.</span></span>
10. <span data-ttu-id="dba36-120">Active la casilla de la izquierda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="dba36-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="dba36-121">En el campo Nombre de jerarquía, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dba36-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="dba36-122">Ejemplo: Proyecto</span><span class="sxs-lookup"><span data-stu-id="dba36-122">Example: Project</span></span>  
12. <span data-ttu-id="dba36-123">En el campo Notifica al puesto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="dba36-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="dba36-124">Ejemplo: 000437</span><span class="sxs-lookup"><span data-stu-id="dba36-124">Example:  000437</span></span>
13. <span data-ttu-id="dba36-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="dba36-125">Click Save.</span></span>


