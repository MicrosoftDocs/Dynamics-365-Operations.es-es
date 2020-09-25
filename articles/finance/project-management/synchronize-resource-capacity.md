---
title: Sincronizar la capacidad de recursos
description: Este tema proporciona información sobre cómo sincronizar la capacidad de un recurso en calendarios y proyectos.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760652"
---
# <a name="synchronize-resource-capacity"></a><span data-ttu-id="9d5e2-103">Sincronizar la capacidad de recursos</span><span class="sxs-lookup"><span data-stu-id="9d5e2-103">Synchronize resource capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d5e2-104">Los procesos para la sincronización de recursos ayudan a garantizar que la información del calendario y del calendario de base se integren lentamente en la programación de recursos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-104">The processes for resource synchronization help guarantee that information for the calendar and base calendar trickles down into project resource scheduling.</span></span> <span data-ttu-id="9d5e2-105">Si se modifica el calendario, los procesos realizan las actualizaciones necesarias a la programación de recursos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-105">If the calendar is changed, the processes make the required updates to the scheduling of project resources.</span></span> <span data-ttu-id="9d5e2-106">Igualmente, los procesos también le permitirán mejorar el rendimiento, ya que la información de recursos del calendario se sincroniza previamente.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-106">The processes also help improve performance, because the calendar's resource information is synchronized in advance.</span></span> <span data-ttu-id="9d5e2-107">Por lo tanto, verá con más frecuencia actualizaciones de información con la programación de recursos.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-107">Therefore, updates to resource scheduling information occur more quickly.</span></span> <span data-ttu-id="9d5e2-108">Se recomienda la programación de los procesos como lote en lugar de uno cada vez.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-108">We recommend that you schedule the processes as a batch instead of one at a time.</span></span> <span data-ttu-id="9d5e2-109">De no ser así, existe el riesgo de que alguien olvidará las fechas inclusivas en las que la información se sincronizó por última vez.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-109">Otherwise, there is a risk that someone will forget the inclusive dates when the information was last synchronized.</span></span> <span data-ttu-id="9d5e2-110">Si no se usan fechas inclusivas, pueden producir huecos durante la sincronización de fecha.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-110">If inclusive dates aren't used, gaps can occur during date synchronization.</span></span>

![Sincronización de calendario](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a><span data-ttu-id="9d5e2-112">Sincronizar acumulaciones de capacidad de recursos</span><span class="sxs-lookup"><span data-stu-id="9d5e2-112">Synchronize resource capacity roll-ups</span></span>

<span data-ttu-id="9d5e2-113">El proceso de sincronización está diseñado para sincronizar toda la información del calendario de recursos.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-113">The synchronization process is designed to synchronize all resource calendar information.</span></span> <span data-ttu-id="9d5e2-114">Esta información incluye la información del calendario base sobre los cambios realizados en la tabla de la capacidad del calendario de recursos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-114">This information includes base calendar information about any changes to the project's Resource calendar capacity table.</span></span> <span data-ttu-id="9d5e2-115">Si se agregan nuevos recursos en el proyecto, la sincronización ayuda a garantizar que la información actualizada del calendario está disponible.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-115">If new resources are added in the project, synchronization helps guarantee that the updated calendar information is available.</span></span> <span data-ttu-id="9d5e2-116">Esta sincronización se puede realizar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-116">This synchronization can be done at any time.</span></span>

<span data-ttu-id="9d5e2-117">Recomendamos que use un lote.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-117">We recommend that you use a batch.</span></span> <span data-ttu-id="9d5e2-118">Las opciones están disponibles durante la sincronización de reservas de capacidades.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-118">The options are available during synchronization of capacity reservations.</span></span>

1. <span data-ttu-id="9d5e2-119">Seleccione **Administración de proyectos y contabilidad** &gt; **Periódico** &gt; **Sincronización de capacidad** &gt; **Sincronizar acumulaciones de capacidad de recursos**.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-119">Select **Project management and accounting** &gt; **Periodic** &gt; **Capacity synchronization** &gt; **Synchronize resources capacity roll-ups**.</span></span>
2. <span data-ttu-id="9d5e2-120">Configure las opciones de la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-120">Set the options in the following table.</span></span>

    | <span data-ttu-id="9d5e2-121">Opción</span><span class="sxs-lookup"><span data-stu-id="9d5e2-121">Option</span></span>      | <span data-ttu-id="9d5e2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d5e2-122">Description</span></span> |
    |-------------|-------------|
    | <span data-ttu-id="9d5e2-123">Código del período</span><span class="sxs-lookup"><span data-stu-id="9d5e2-123">Period code</span></span> | <span data-ttu-id="9d5e2-124">De forma opcional, puede seleccionar el código del intervalo de fechas del libro de contabilidad general para establecer las fechas inicial y final del proceso de sincronización de la acumulación de capacidad de recursos.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-124">Optionally select the General ledger date interval code to set the start and end dates for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="9d5e2-125">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="9d5e2-125">Start date</span></span>  | <span data-ttu-id="9d5e2-126">Especifique la fecha inicial del proceso de sincronización de acumulación de capacidad de recursos.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-126">Enter the start date for the synchronization process for resource capacity roll-ups.</span></span> |
    | <span data-ttu-id="9d5e2-127">Fecha de finalización</span><span class="sxs-lookup"><span data-stu-id="9d5e2-127">End date</span></span>    | <span data-ttu-id="9d5e2-128">Especifique la fecha final del proceso de sincronización de acumulación de capacidad de recursos.</span><span class="sxs-lookup"><span data-stu-id="9d5e2-128">Enter the end date for the synchronization process for resource capacity roll-ups.</span></span> |

<span data-ttu-id="9d5e2-129">[![Proceso de sincronización](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span><span class="sxs-lookup"><span data-stu-id="9d5e2-129">[![Synchronization process](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)</span></span>
