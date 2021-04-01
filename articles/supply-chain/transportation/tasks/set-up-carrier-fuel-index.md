---
title: Configuración de un índice de combustible de transportista
description: Esta guía muestra cómo crear una región de índice de combustible, un índice de combustible y un índice de combustible de transportista.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 09dc948e673bb8be49ac81e5ad2b20bc6c62b286
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233664"
---
# <a name="set-up-a-carrier-fuel-index"></a><span data-ttu-id="01d73-103">Configuración de un índice de combustible de transportista</span><span class="sxs-lookup"><span data-stu-id="01d73-103">Set up a carrier fuel index</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01d73-104">Esta guía muestra cómo crear una región de índice de combustible, un índice de combustible y un índice de combustible de transportista.</span><span class="sxs-lookup"><span data-stu-id="01d73-104">This guide shows how to create a fuel index region, a fuel index and a carrier fuel index.</span></span> <span data-ttu-id="01d73-105">La región de índice de combustible especifica a qué región se debe aplicar el índice de combustible, y el índice de combustible especifica un precio por combustible para un período de tiempo concreto.</span><span class="sxs-lookup"><span data-stu-id="01d73-105">The fuel index region specifies which region the fuel index should apply to, and the fuel index specifies a fuel price for a particular period of time.</span></span> <span data-ttu-id="01d73-106">Para reflejar el cambio de precios de combustible en el tiempo, puede asociar varios índices de combustible con un transportista.</span><span class="sxs-lookup"><span data-stu-id="01d73-106">To reflect the change in fuel prices over time, you can associate multiple fuel indexes with a carrier.</span></span>  <span data-ttu-id="01d73-107">Estas tareas las realiza normalmente el coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="01d73-107">These tasks are normally done by a transportation coordinator.</span></span> <span data-ttu-id="01d73-108">Puede utilizar este procedimiento con la empresa de datos de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="01d73-108">You can use this procedure in demo data company USMF or using your own data.</span></span>


## <a name="create-a-fuel-index-region"></a><span data-ttu-id="01d73-109">Creación de una región de índice de combustible</span><span class="sxs-lookup"><span data-stu-id="01d73-109">Create a fuel index region</span></span>
1. <span data-ttu-id="01d73-110">Vaya a Administración de transporte > Configuración > Índices de combustible > Regiones de índice de combustible.</span><span class="sxs-lookup"><span data-stu-id="01d73-110">Go to Transportation management > Setup > Fuel indexes > Fuel index regions.</span></span>
    * <span data-ttu-id="01d73-111">Primero es necesario crear las distintas regiones donde se opera y calcular diferentes suplementos por combustible.</span><span class="sxs-lookup"><span data-stu-id="01d73-111">First you have to create the different regions, where you operate and calculate different fuel surcharges.</span></span>  
2. <span data-ttu-id="01d73-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="01d73-112">Click New.</span></span>
3. <span data-ttu-id="01d73-113">En el campo Región, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01d73-113">In the Region field, type a value.</span></span>
4. <span data-ttu-id="01d73-114">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01d73-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="01d73-115">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="01d73-115">Click Save.</span></span>

## <a name="create-a-fuel-index"></a><span data-ttu-id="01d73-116">Crear un índice de combustible</span><span class="sxs-lookup"><span data-stu-id="01d73-116">Create a fuel index</span></span>
1. <span data-ttu-id="01d73-117">Vaya a Administración de transporte > Configuración > Índices de combustible > Índices de combustible.</span><span class="sxs-lookup"><span data-stu-id="01d73-117">Go to Transportation management > Setup > Fuel indexes > Fuel indexes.</span></span>
    * <span data-ttu-id="01d73-118">Para las regiones configuradas es necesario introducir los precios reales del combustible.</span><span class="sxs-lookup"><span data-stu-id="01d73-118">For the regions you have set up you need to enter the current prices for the fuel.</span></span>  
2. <span data-ttu-id="01d73-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="01d73-119">Click New.</span></span>
3. <span data-ttu-id="01d73-120">En el campo Región, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="01d73-120">In the Region field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="01d73-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01d73-121">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="01d73-122">En el campo Precio por litro, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="01d73-122">In the Price per gallon field, enter a number.</span></span>
6. <span data-ttu-id="01d73-123">En el campo Fecha y hora iniciales de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="01d73-123">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="01d73-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="01d73-124">Click Save.</span></span>

## <a name="create-a-carrier-fuel-index"></a><span data-ttu-id="01d73-125">Creación de un índice de combustible de transportista</span><span class="sxs-lookup"><span data-stu-id="01d73-125">Create a Carrier fuel index</span></span>
1. <span data-ttu-id="01d73-126">Vaya a Administración de transporte > Configuración > Índices de combustible > Índices de combustible del transportista.</span><span class="sxs-lookup"><span data-stu-id="01d73-126">Go to Transportation management > Setup > Fuel indexes > Carrier fuel indexes.</span></span>
2. <span data-ttu-id="01d73-127">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="01d73-127">Click New.</span></span>
3. <span data-ttu-id="01d73-128">En el campo Índice de combustible del transportista, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01d73-128">In the Carrier fuel index field, type a value.</span></span>
4. <span data-ttu-id="01d73-129">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="01d73-129">In the Description field, type a value.</span></span>
5. <span data-ttu-id="01d73-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="01d73-130">Click New.</span></span>
6. <span data-ttu-id="01d73-131">En el campo Fecha y hora iniciales de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="01d73-131">In the Effective start date and time field, enter a date and time.</span></span>
7. <span data-ttu-id="01d73-132">En el campo Precio por litro de origen, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="01d73-132">In the PPG From field, enter a number.</span></span>
    * <span data-ttu-id="01d73-133">En este ejemplo, puede definir el campo Precio por litro de origen en "1.95".</span><span class="sxs-lookup"><span data-stu-id="01d73-133">In this example, you can set PPG From field to 1.95.</span></span>  
8. <span data-ttu-id="01d73-134">En el campo Precio por litro de destino, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="01d73-134">In the PPG To field, enter a number.</span></span>
    * <span data-ttu-id="01d73-135">En este ejemplo, puede definir el campo Precio por litro de origen en "2".</span><span class="sxs-lookup"><span data-stu-id="01d73-135">In this example you can set the PPG To field to 2.</span></span>  
9. <span data-ttu-id="01d73-136">En el campo Porcentaje, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="01d73-136">In the Percentage field, enter a number.</span></span>
    * <span data-ttu-id="01d73-137">En este ejemplo, puede definir el porcentaje en "3".</span><span class="sxs-lookup"><span data-stu-id="01d73-137">In this example you can set the percentage to 3.</span></span>  
10. <span data-ttu-id="01d73-138">En el campo Divisa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="01d73-138">In the Currency field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="01d73-139">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="01d73-139">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="01d73-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="01d73-140">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="01d73-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="01d73-141">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]