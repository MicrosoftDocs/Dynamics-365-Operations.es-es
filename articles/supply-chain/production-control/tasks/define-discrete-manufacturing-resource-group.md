--- 
title: "Definir grupo de recursos para la fabricación discreta"
description: "Un grupo de recursos es un conjunto de los recursos de operaciones que corresponden normalmente a la organización física de celdas de trabajo, definidas por las líneas amarillas en la planta de producción."
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 50733e34bbf14ae2cade6822105da4d8c2120d7d
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="c94ed-103">Definir grupo de recursos para la fabricación discreta</span><span class="sxs-lookup"><span data-stu-id="c94ed-103">Define discrete manufacturing resource group</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c94ed-104">Un grupo de recursos es un conjunto de los recursos de operaciones que corresponden normalmente a la organización física de celdas de trabajo, definidas por las líneas amarillas en la planta de producción.</span><span class="sxs-lookup"><span data-stu-id="c94ed-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="c94ed-105">Este procedimiento le muestra cómo definir un grupo de recursos para el uso en producción discreta.</span><span class="sxs-lookup"><span data-stu-id="c94ed-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="c94ed-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="c94ed-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="c94ed-107">Vaya a Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="c94ed-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="c94ed-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="c94ed-108">Click New.</span></span>
3. <span data-ttu-id="c94ed-109">En el campo Grupo de recursos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="c94ed-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c94ed-111">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="c94ed-112">En el campo Unidad de producción, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="c94ed-113">Definir parámetros operativos predeterminados</span><span class="sxs-lookup"><span data-stu-id="c94ed-113">Define default operational parameters</span></span>
1. <span data-ttu-id="c94ed-114">Expanda la sección Operación.</span><span class="sxs-lookup"><span data-stu-id="c94ed-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="c94ed-115">En el campo Porcentaje de residuos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="c94ed-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="c94ed-116">En el campo Categoría de configuración, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="c94ed-117">En el campo Tiempo de ejecución, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="c94ed-118">En el campo Porcentaje de programación de operaciones, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="c94ed-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="c94ed-119">Definir horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="c94ed-119">Define operating hours</span></span>
1. <span data-ttu-id="c94ed-120">Expanda la sección Calendarios.</span><span class="sxs-lookup"><span data-stu-id="c94ed-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="c94ed-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c94ed-121">Click Add.</span></span>
3. <span data-ttu-id="c94ed-122">En el campo Calendario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="c94ed-123">Agregar recursos de operaciones</span><span class="sxs-lookup"><span data-stu-id="c94ed-123">Add operations resources</span></span>
1. <span data-ttu-id="c94ed-124">Expanda la sección Recursos.</span><span class="sxs-lookup"><span data-stu-id="c94ed-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="c94ed-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c94ed-125">Click Add.</span></span>
3. <span data-ttu-id="c94ed-126">En el campo Recurso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="c94ed-127">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="c94ed-127">Click Add.</span></span>
5. <span data-ttu-id="c94ed-128">En el campo Recurso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="c94ed-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="c94ed-129">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c94ed-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="c94ed-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c94ed-130">In the list, click the link in the selected row.</span></span>


