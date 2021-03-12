---
title: Crear una clase de trabajo
description: Este procedimiento muestra cómo configurar una clase de trabajo.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0e06cd5fc6dc27f79eb39bbd78932a166e9d442
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977222"
---
# <a name="create-a-work-class"></a><span data-ttu-id="fe7a9-103">Crear una clase de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe7a9-103">Create a work class</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fe7a9-104">Este procedimiento muestra cómo configurar una clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-104">This procedure shows you how to set up a work class.</span></span> <span data-ttu-id="fe7a9-105">Las clases de trabajo se usan para dirigir y/o para limitar el tipo de líneas de pedido de trabajo que un trabajador de almacén puede procesar en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-105">Work classes are used to direct and/or limit the type of work order lines that a warehouse worker can process on a mobile device.</span></span> <span data-ttu-id="fe7a9-106">Las líneas que un trabajador puede procesar se determinan a partir de las clases de trabajo en los elementos de menú del dispositivo móvil a los que el trabajador de almacén tiene acceso y la clase de trabajo especificada en las líneas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-106">The lines that a worker can process are determined from the work classes on the mobile device menu items that the warehouse worker has access to and the work class that's specified on the work lines.</span></span> <span data-ttu-id="fe7a9-107">Las clases de trabajo también se pueden usar para validar la ubicación de colocación para una línea de pedido de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-107">Work classes can also be used to validate the put location for a work order line.</span></span> <span data-ttu-id="fe7a9-108">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-108">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="fe7a9-109">Este procedimiento va destinado al encargado de almacén.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-109">This procedure is intended for the warehouse manager.</span></span>

1. <span data-ttu-id="fe7a9-110">Vaya a Gestión de almacenes > Configurar > Trabajo > Clases de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-110">Go to Warehouse management > Setup > Work > Work classes.</span></span>
2. <span data-ttu-id="fe7a9-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-111">Click New.</span></span>
3. <span data-ttu-id="fe7a9-112">En el campo Identificador de la clase de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-112">In the Work class ID field, type a value.</span></span>
4. <span data-ttu-id="fe7a9-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="fe7a9-114">En el campo Tipo de pedido de trabajo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-114">In the Work order type field, select an option.</span></span>
6. <span data-ttu-id="fe7a9-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-115">Click New.</span></span>
7. <span data-ttu-id="fe7a9-116">En el campo Tipo de ubicación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-116">In the Location type field, type a value.</span></span>
    * <span data-ttu-id="fe7a9-117">Si selecciona un tipo de ubicación, se establece una restricción sobre dónde se pueden colocar los artículos una vez seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-117">If you select a location type, this sets a restriction on where items can be put after they've been picked.</span></span> <span data-ttu-id="fe7a9-118">Esta configuración se usa cuando una directiva de ubicación intenta resolver la ubicación, o si un trabajador del almacén indica manualmente la ubicación para el elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-118">This setting is used when a location directive tries to resolve the location, or if a warehouse worker manually provides the location for the mobile device menu item.</span></span>  
8. <span data-ttu-id="fe7a9-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fe7a9-119">Close the page.</span></span>

