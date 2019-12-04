---
title: Modificar las relaciones jerárquicas para un puesto
description: Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a1afd2c1cdc2ebaa303030d01b3bbe5fd2af44f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179876"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="78773-103">Modificar las relaciones jerárquicas para un puesto</span><span class="sxs-lookup"><span data-stu-id="78773-103">Modify reporting relationships for a position</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78773-104">Este procedimiento muestra cómo cambiar la relación jerárquica para un empleado.</span><span class="sxs-lookup"><span data-stu-id="78773-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="78773-105">La relación jerárquica se puede usar para enrutar documentos mediante el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78773-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="78773-106">El procedimiento también muestra cómo asignar el empleado a jerarquías adicionales.</span><span class="sxs-lookup"><span data-stu-id="78773-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="78773-107">Por ejemplo, un empleado puede formar parte de un equipo de proyecto con una relación jerárquica informal con un supervisor de proyecto.</span><span class="sxs-lookup"><span data-stu-id="78773-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="78773-108">Las relaciones jerárquicas adicionales se pueden definir en el puesto para adaptar distintos escenarios de proyecto o matriz.</span><span class="sxs-lookup"><span data-stu-id="78773-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="78773-109">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="78773-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="78773-110">Vaya a Recursos humanos > Puestos > Puestos.</span><span class="sxs-lookup"><span data-stu-id="78773-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="78773-111">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="78773-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="78773-112">Por ejemplo, filtre el campo Puesto según un valor de "000091".</span><span class="sxs-lookup"><span data-stu-id="78773-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="78773-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78773-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="78773-114">Expanda la sección Notifica al puesto.</span><span class="sxs-lookup"><span data-stu-id="78773-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="78773-115">Haga clic en Nueva para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="78773-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="78773-116">En el campo Informa a, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78773-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="78773-117">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="78773-117">Click Create.</span></span>
8. <span data-ttu-id="78773-118">Expanda la sección Relaciones.</span><span class="sxs-lookup"><span data-stu-id="78773-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="78773-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="78773-119">Click Add.</span></span>
10. <span data-ttu-id="78773-120">Active la casilla de la izquierda de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="78773-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="78773-121">En el campo Nombre de jerarquía, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78773-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="78773-122">Ejemplo: Proyecto</span><span class="sxs-lookup"><span data-stu-id="78773-122">Example: Project</span></span>  
12. <span data-ttu-id="78773-123">En el campo Notifica al puesto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78773-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="78773-124">Ejemplo: 000437</span><span class="sxs-lookup"><span data-stu-id="78773-124">Example:  000437</span></span>
13. <span data-ttu-id="78773-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="78773-125">Click Save.</span></span>
