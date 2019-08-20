---
title: Crear una plantilla de registro para facilitar la entrada de datos
description: Este procedimiento demuestra la creación de plantillas de registro para no tener que especificar los valores de campo que se utilizan a menudo explícitamente para cada registro nuevo.
author: margoc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, SysRecordInfo, SysRecordTemplatePromptOnCreate
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b2ba56b6146f2495fb6a53c3cef9f549b1ad837
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848216"
---
# <a name="create-a-record-template-to-facilitate-data-entry"></a><span data-ttu-id="c044b-103">Crear una plantilla de registro para facilitar la entrada de datos</span><span class="sxs-lookup"><span data-stu-id="c044b-103">Create a record template to facilitate data entry</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c044b-104">Este procedimiento demuestra la creación de plantillas de registro para no tener que especificar los valores de campo que se utilizan a menudo explícitamente para cada registro nuevo.</span><span class="sxs-lookup"><span data-stu-id="c044b-104">This procedure demonstrates how to create a record template so that field values that are used often do not have to be entered explicitly for each new record.</span></span> <span data-ttu-id="c044b-105">En este procedimiento, usted creará un registro nuevo para los nuevos portátiles que deberán agregarse a sus activos fijos.</span><span class="sxs-lookup"><span data-stu-id="c044b-105">In this procedure, you’ll create a new record for new laptops that should be added to your fixed assets.</span></span> <span data-ttu-id="c044b-106">Este procedimiento usa la empresa de muestra USMF.</span><span class="sxs-lookup"><span data-stu-id="c044b-106">This procedure uses the USMF sample company.</span></span>

1. <span data-ttu-id="c044b-107">Vaya a Activos fijos > Activos fijos > Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="c044b-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="c044b-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c044b-108">Click New.</span></span>
3. <span data-ttu-id="c044b-109">En el campo Grupo de activos fijos, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="c044b-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-110">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c044b-111">Por ejemplo, especifique “Portátil corporativo del cliente potencial”.</span><span class="sxs-lookup"><span data-stu-id="c044b-111">For example, enter 'Corporate lead laptop'.</span></span>  
5. <span data-ttu-id="c044b-112">En el campo Nombre de búsqueda, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-112">In the Search name field, type a value.</span></span>
    * <span data-ttu-id="c044b-113">Por ejemplo, especifique "portátil".</span><span class="sxs-lookup"><span data-stu-id="c044b-113">For example, enter 'laptop.'</span></span>  
6. <span data-ttu-id="c044b-114">Expanda la sección Información técnica.</span><span class="sxs-lookup"><span data-stu-id="c044b-114">Expand the Technical information section.</span></span>
7. <span data-ttu-id="c044b-115">En el campo Fabricación, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-115">In the Make field, type a value.</span></span>
8. <span data-ttu-id="c044b-116">En el campo Modelo, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-116">In the Model field, type a value.</span></span>
9. <span data-ttu-id="c044b-117">En el campo Año del modelo, introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-117">In the Model year field, type a value.</span></span>
10. <span data-ttu-id="c044b-118">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="c044b-118">On the Action Pane, click Options.</span></span>
11. <span data-ttu-id="c044b-119">Haga clic en Información de registro.</span><span class="sxs-lookup"><span data-stu-id="c044b-119">Click Record info.</span></span>
12. <span data-ttu-id="c044b-120">Haga clic en Plantilla de usuario.</span><span class="sxs-lookup"><span data-stu-id="c044b-120">Click User template.</span></span>
13. <span data-ttu-id="c044b-121">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-121">In the Name field, type a value.</span></span>
    * <span data-ttu-id="c044b-122">Por ejemplo, especifique “Portátil corporativo”.</span><span class="sxs-lookup"><span data-stu-id="c044b-122">For example, enter 'Corporate laptop.'</span></span>  
14. <span data-ttu-id="c044b-123">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c044b-123">In the Description field, type a value.</span></span>
    * <span data-ttu-id="c044b-124">Por ejemplo, especifique “Portátil corporativo”.</span><span class="sxs-lookup"><span data-stu-id="c044b-124">For example, enter 'Corporate laptop'.</span></span>  
15. <span data-ttu-id="c044b-125">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="c044b-125">Click OK.</span></span>
16. <span data-ttu-id="c044b-126">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="c044b-126">Click Close.</span></span>

