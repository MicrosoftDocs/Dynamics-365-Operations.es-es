---
title: Definir grupo de recursos para la fabricación discreta
description: Un grupo de recursos es un conjunto de los recursos de operaciones que corresponden normalmente a la organización física de celdas de trabajo, definidas por las líneas amarillas en la planta de producción.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eaccb566c04d6d4b91ea8cb046931e750a4c6eed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436557"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="6c0f3-103">Definir grupo de recursos para la fabricación discreta</span><span class="sxs-lookup"><span data-stu-id="6c0f3-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6c0f3-104">Un grupo de recursos es un conjunto de los recursos de operaciones que corresponden normalmente a la organización física de celdas de trabajo, definidas por las líneas amarillas en la planta de producción.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="6c0f3-105">Este procedimiento le muestra cómo definir un grupo de recursos para el uso en producción discreta.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="6c0f3-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="6c0f3-107">Vaya a Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="6c0f3-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-108">Click New.</span></span>
3. <span data-ttu-id="6c0f3-109">En el campo Grupo de recursos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="6c0f3-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6c0f3-111">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="6c0f3-112">En el campo Unidad de producción, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="6c0f3-113">Definir parámetros operativos predeterminados</span><span class="sxs-lookup"><span data-stu-id="6c0f3-113">Define default operational parameters</span></span>
1. <span data-ttu-id="6c0f3-114">Expanda la sección Operación.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="6c0f3-115">En el campo Porcentaje de residuos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="6c0f3-116">En el campo Categoría de configuración, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="6c0f3-117">En el campo Tiempo de ejecución, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="6c0f3-118">En el campo Porcentaje de programación de operaciones, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="6c0f3-119">Definir horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c0f3-119">Define operating hours</span></span>
1. <span data-ttu-id="6c0f3-120">Expanda la sección Calendarios.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="6c0f3-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-121">Click Add.</span></span>
3. <span data-ttu-id="6c0f3-122">En el campo Calendario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="6c0f3-123">Agregar recursos de operaciones</span><span class="sxs-lookup"><span data-stu-id="6c0f3-123">Add operations resources</span></span>
1. <span data-ttu-id="6c0f3-124">Expanda la sección Recursos.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="6c0f3-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-125">Click Add.</span></span>
3. <span data-ttu-id="6c0f3-126">En el campo Recurso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="6c0f3-127">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-127">Click Add.</span></span>
5. <span data-ttu-id="6c0f3-128">En el campo Recurso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="6c0f3-129">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6c0f3-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6c0f3-130">In the list, click the link in the selected row.</span></span>

