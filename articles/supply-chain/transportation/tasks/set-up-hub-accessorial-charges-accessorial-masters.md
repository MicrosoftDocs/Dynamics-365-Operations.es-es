---
title: Configuración de cargos adicionales del centro y listas maestras de cargos adicionales
description: Este procedimiento muestra cómo crear cargos adicionales maestros para un centro y cómo usarlos para crear un cargo adicional del centro.
author: ShylaThompson
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f4c0d3af96e6ef6735b01165a49c1450b3b633b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837578"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a><span data-ttu-id="9b231-103">Configuración de cargos adicionales del centro y listas maestras de cargos adicionales</span><span class="sxs-lookup"><span data-stu-id="9b231-103">Set up hub accessorial charges and accessorial masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9b231-104">Este procedimiento muestra cómo crear cargos adicionales maestros para un centro y cómo usarlos para crear un cargo adicional del centro.</span><span class="sxs-lookup"><span data-stu-id="9b231-104">This procedure shows how to create an accessorial master for a hub and use that master to create a hub accessorial charge.</span></span> <span data-ttu-id="9b231-105">El procedimiento usa el grupo de datos USMF.</span><span class="sxs-lookup"><span data-stu-id="9b231-105">The procedure uses the USMF dataset.</span></span> <span data-ttu-id="9b231-106">Esta configuración normalmente la realiza el coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="9b231-106">This set up will typically be done by a transportation coordinator.</span></span>


## <a name="set-up-a-hub-master"></a><span data-ttu-id="9b231-107">Configurar un centro maestro</span><span class="sxs-lookup"><span data-stu-id="9b231-107">Set up a hub master</span></span>
1. <span data-ttu-id="9b231-108">Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales maestros.</span><span class="sxs-lookup"><span data-stu-id="9b231-108">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="9b231-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9b231-109">Click New.</span></span>
3. <span data-ttu-id="9b231-110">En el campo Cargos adicionales maestros, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9b231-110">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="9b231-111">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9b231-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="9b231-112">En el campo Tipo de cargos adicionales, seleccione Centro.</span><span class="sxs-lookup"><span data-stu-id="9b231-112">In the Accessorial type field, select 'Hub'.</span></span>
6. <span data-ttu-id="9b231-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9b231-113">Click Save.</span></span>
7. <span data-ttu-id="9b231-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9b231-114">Close the page.</span></span>

## <a name="set-up-a-hub-accessorial-charge"></a><span data-ttu-id="9b231-115">Configuración de un cargo adicional del centro</span><span class="sxs-lookup"><span data-stu-id="9b231-115">Set up a hub accessorial charge</span></span>
1. <span data-ttu-id="9b231-116">Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales del centro.</span><span class="sxs-lookup"><span data-stu-id="9b231-116">Go to Transportation management > Setup > Rating > Hub accessorial charges.</span></span>
2. <span data-ttu-id="9b231-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9b231-117">Click New.</span></span>
3. <span data-ttu-id="9b231-118">En el campo Id. de cargos adicionales del centro, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9b231-118">In the Hub accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="9b231-119">En el campo Centro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9b231-119">In the Hub field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9b231-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9b231-120">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="9b231-121">En el campo Posición del centro, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="9b231-121">In the Hub position field, select an option.</span></span>
    * <span data-ttu-id="9b231-122">Puede crear el cargo como recogida o como entrega.</span><span class="sxs-lookup"><span data-stu-id="9b231-122">You can either create the charge as a pickup or drop-off.</span></span> <span data-ttu-id="9b231-123">En función de lo que se seleccione, el cargo se aplicará al segmento de transporte correspondiente en la ruta.</span><span class="sxs-lookup"><span data-stu-id="9b231-123">Depending on your selection the charge will be applied to the corresponding transportation segment on your route.</span></span>  
7. <span data-ttu-id="9b231-124">En el campo Cargos adicionales maestros, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9b231-124">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9b231-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9b231-125">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9b231-126">Seleccione los cargos maestros que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="9b231-126">Select the master you just created.</span></span>  
9. <span data-ttu-id="9b231-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9b231-127">Click Save.</span></span>
10. <span data-ttu-id="9b231-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9b231-128">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]