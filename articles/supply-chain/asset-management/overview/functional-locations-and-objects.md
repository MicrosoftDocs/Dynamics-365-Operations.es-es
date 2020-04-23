---
title: Ubicaciones funcionales y activos
description: En este tema se describen las ubicaciones técnicas y los activos en Administración de activos. Administración de activos es un módulo avanzado para gestionar activos y trabajos de mantenimiento en Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe3e82f425421acdae81a02032ac6252765e1c05
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208072"
---
# <a name="functional-locations-and-assets"></a><span data-ttu-id="53342-104">Ubicaciones funcionales y activos</span><span class="sxs-lookup"><span data-stu-id="53342-104">Functional locations and assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="53342-105">En este tema se describen las ubicaciones técnicas y los activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="53342-105">This topic describes functional locations and assets in Asset Management.</span></span> <span data-ttu-id="53342-106">Administración de activos es un módulo avanzado para gestionar activos y trabajos de mantenimiento en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="53342-106">Asset Management is an advanced module for managing assets and maintenance jobs in Dynamics 365 Supply Chain Management.</span></span>

## <a name="overview"></a><span data-ttu-id="53342-107">Información general</span><span class="sxs-lookup"><span data-stu-id="53342-107">Overview</span></span>

<span data-ttu-id="53342-108">Administración de activos está integrado de manera fluida con varios módulos con otras aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="53342-108">Asset Management is integrated seamlessly with several modules with other Finance and Operations apps.</span></span> <span data-ttu-id="53342-109">La ilustración siguiente muestra las interfaces con otros módulos.</span><span class="sxs-lookup"><span data-stu-id="53342-109">The following illustration shows the interfaces with other modules.</span></span>

![Diagrama que muestra cómo la Administración de activos interactúa con otros módulos](media/01-overview-image.png)

<span data-ttu-id="53342-111">Administración de activos permite administrar y realizar todas las tareas relacionadas con la gestión y el mantenimiento de muchos tipos de equipos de la empresa eficientemente.</span><span class="sxs-lookup"><span data-stu-id="53342-111">Asset Management lets you efficiently manage and perform all tasks that are related to managing and servicing many types of equipment in your company.</span></span> <span data-ttu-id="53342-112">Los equipos incluyen las máquinas, los equipos de producción y los vehículos.</span><span class="sxs-lookup"><span data-stu-id="53342-112">This equipment includes machines, production equipment, and vehicles.</span></span> <span data-ttu-id="53342-113">Administración de activos también admite soluciones de numerosos sectores.</span><span class="sxs-lookup"><span data-stu-id="53342-113">Asset Management also supports solutions across numerous industries.</span></span>

<span data-ttu-id="53342-114">La ilustración siguiente muestra una visión general de la funcionalidad principal que cubre Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="53342-114">The following illustration shows an overview of the main functionality that is covered by Asset Management.</span></span>

![Diagrama que muestra la funcionalidad principal en Administración de activos](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a><span data-ttu-id="53342-116">Ubicaciones funcionales y activos</span><span class="sxs-lookup"><span data-stu-id="53342-116">Functional locations and assets</span></span>

<span data-ttu-id="53342-117">Las ubicaciones funcionales se utilizan para gestionar activos en las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="53342-117">Functional locations are used to manage assets on locations.</span></span> <span data-ttu-id="53342-118">Esta administración incluye el seguimiento de los costes de los activos en las ubicaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="53342-118">This management includes tracking of asset costs on functional locations.</span></span> <span data-ttu-id="53342-119">Las ubicaciones funcionales se estructuran jerárquicamente y pueden tener sububicaciones.</span><span class="sxs-lookup"><span data-stu-id="53342-119">Functional locations are structured hierarchically, and locations can have sub-locations.</span></span> <span data-ttu-id="53342-120">La estructura de las ubicaciones funcionales es estática.</span><span class="sxs-lookup"><span data-stu-id="53342-120">The structure of functional locations is static.</span></span> <span data-ttu-id="53342-121">Es decir, las ubicaciones no pueden cambiar de lugar.</span><span class="sxs-lookup"><span data-stu-id="53342-121">In other words, locations can't change place.</span></span> <span data-ttu-id="53342-122">Los activos se pueden instalar en las ubicaciones funcionales y, según convenga, se pueden instalar en otras ubicaciones funcionales posteriormente.</span><span class="sxs-lookup"><span data-stu-id="53342-122">Assets can be installed on functional locations and, as required, can be installed on other functional locations later.</span></span>

<span data-ttu-id="53342-123">Los costes de los activos siempre siguen la ubicación del activo.</span><span class="sxs-lookup"><span data-stu-id="53342-123">Asset costs always follow the location of the asset.</span></span> <span data-ttu-id="53342-124">Es decir, si se instala un activo en una nueva ubicación funcional, el activo usa automáticamente las dimensiones financieras relacionadas con la nueva ubicación funcional.</span><span class="sxs-lookup"><span data-stu-id="53342-124">In other words, if you install an asset on a new functional location, the asset automatically uses the financial dimensions that are related to the new functional location.</span></span> <span data-ttu-id="53342-125">Por lo tanto, los costes de activo siempre están relacionados con la ubicación funcional en la que el activo está instalado actualmente.</span><span class="sxs-lookup"><span data-stu-id="53342-125">Therefore, asset costs are always related to the functional location that the asset is  currently installed on.</span></span> <span data-ttu-id="53342-126">Este control automático de las dimensiones financieras ayuda a garantizar el seguimiento completo de los costes si su empresa lleva a cabo un control de los proyectos y produce informes según las ubicaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="53342-126">This automatic handling of financial dimensions helps guarantee complete tracking of costs when your company does project controlling and reporting on functional locations.</span></span>

<span data-ttu-id="53342-127">La forma en que se crea la jerarquía de ubicaciones funcionales depende de los requisitos de la empresa para mantener el equipo interno o reparar el equipo del cliente.</span><span class="sxs-lookup"><span data-stu-id="53342-127">The way that you build your hierarchy of functional locations depends on your company's requirements for maintaining internal equipment or servicing customer equipment.</span></span> <span data-ttu-id="53342-128">En la ilustración siguiente se muestra un ejemplo de ubicaciones funcionales que se basan en ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="53342-128">The following figure shows an example of functional locations that are based on geographical locations.</span></span>

![Diagrama que muestra las ubicaciones técnicas basadas en ubicaciones geográficas](media/03-overview-image.png)

<span data-ttu-id="53342-130">En la ilustración siguiente se muestra un ejemplo de ubicaciones funcionales que se basan en clientes.</span><span class="sxs-lookup"><span data-stu-id="53342-130">The following figure shows an example of functional locations that are based on customers.</span></span>

![Diagrama que muestra las ubicaciones técnicas basadas en clientes](media/04-overview-image.png)
