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
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1930999604fb2605a88bad9a5972afd3579976a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975119"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="410bc-103">Definir grupo de recursos para la fabricación discreta</span><span class="sxs-lookup"><span data-stu-id="410bc-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="410bc-104">Un grupo de recursos es un conjunto de los recursos de operaciones que corresponden normalmente a la organización física de celdas de trabajo, definidas por las líneas amarillas en la planta de producción.</span><span class="sxs-lookup"><span data-stu-id="410bc-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="410bc-105">Este procedimiento le muestra cómo definir un grupo de recursos para el uso en producción discreta.</span><span class="sxs-lookup"><span data-stu-id="410bc-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="410bc-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="410bc-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="410bc-107">Vaya a Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="410bc-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="410bc-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="410bc-108">Click New.</span></span>
3. <span data-ttu-id="410bc-109">En el campo Grupo de recursos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="410bc-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="410bc-111">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="410bc-112">En el campo Unidad de producción, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="410bc-113">Definir parámetros operativos predeterminados</span><span class="sxs-lookup"><span data-stu-id="410bc-113">Define default operational parameters</span></span>
1. <span data-ttu-id="410bc-114">Expanda la sección Operación.</span><span class="sxs-lookup"><span data-stu-id="410bc-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="410bc-115">En el campo Porcentaje de residuos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="410bc-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="410bc-116">En el campo Categoría de configuración, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="410bc-117">En el campo Tiempo de ejecución, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="410bc-118">En el campo Porcentaje de programación de operaciones, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="410bc-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="410bc-119">Definir horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="410bc-119">Define operating hours</span></span>
1. <span data-ttu-id="410bc-120">Expanda la sección Calendarios.</span><span class="sxs-lookup"><span data-stu-id="410bc-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="410bc-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="410bc-121">Click Add.</span></span>
3. <span data-ttu-id="410bc-122">En el campo Calendario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="410bc-123">Agregar recursos de operaciones</span><span class="sxs-lookup"><span data-stu-id="410bc-123">Add operations resources</span></span>
1. <span data-ttu-id="410bc-124">Expanda la sección Recursos.</span><span class="sxs-lookup"><span data-stu-id="410bc-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="410bc-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="410bc-125">Click Add.</span></span>
3. <span data-ttu-id="410bc-126">En el campo Recurso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="410bc-127">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="410bc-127">Click Add.</span></span>
5. <span data-ttu-id="410bc-128">En el campo Recurso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="410bc-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="410bc-129">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="410bc-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="410bc-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="410bc-130">In the list, click the link in the selected row.</span></span>

