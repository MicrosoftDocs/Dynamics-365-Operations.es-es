---
title: Liberar pedidos de producción
description: Un pedido de producción liberado es una orden que se ha autorizado para producción. El término Liberado se usa para describir un estado en el ciclo de vida del pedido de producción, donde el pedido de producción está disponible para la ejecución en la planta de producción y para procesos de almacén.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc6d53fc87bac2e23c0d1e67954be02749042004
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211247"
---
# <a name="release-production-orders"></a><span data-ttu-id="d8daa-104">Liberar pedidos de producción</span><span class="sxs-lookup"><span data-stu-id="d8daa-104">Release production orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8daa-105">Un pedido de producción liberado es una orden que se ha autorizado para producción.</span><span class="sxs-lookup"><span data-stu-id="d8daa-105">A released production order is an order that has been authorized for production.</span></span> <span data-ttu-id="d8daa-106">El término Liberado se usa para describir un estado en el ciclo de vida del pedido de producción, donde el pedido de producción está disponible para la ejecución en la planta de producción y para procesos de almacén.</span><span class="sxs-lookup"><span data-stu-id="d8daa-106">The term Released is used to describe a state in the production order life cycle, where the production order is available for execution on the production shop floor and for warehouse processes.</span></span> 

<a name="characteristics-of-the-released-state"></a><span data-ttu-id="d8daa-107">Características de estado Liberado</span><span class="sxs-lookup"><span data-stu-id="d8daa-107">Characteristics of the Released state</span></span>
-------------------------------------

<span data-ttu-id="d8daa-108">El estado **Liberado** es un estado en el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d8daa-108">The **Released** state is one state in the production order life cycle.</span></span> <span data-ttu-id="d8daa-109">Los pedidos de producción que tengan estado **Liberado** están disponibles para su ejecución en la planta de producción y para los procesos de almacén.</span><span class="sxs-lookup"><span data-stu-id="d8daa-109">Production orders that are in the **Released** state are available for execution on the production shop floor and for warehouse processes.</span></span> <span data-ttu-id="d8daa-110">El estado **Liberado** tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="d8daa-110">The **Released** state has the following characteristics:</span></span>

-   <span data-ttu-id="d8daa-111">Un pedido de producción se puede cambiar al estado **Liberado** desde el pedido de producción o mediante un proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="d8daa-111">A production order can be changed to the **Released** state either from the production order or by using a batch process.</span></span> <span data-ttu-id="d8daa-112">El pedido de producción también se puede actualizar automáticamente desde los pedidos de producción planificados en firme mediante el campo **Límite de tiempo de puesta en firme** de la página **Plan maestro**.</span><span class="sxs-lookup"><span data-stu-id="d8daa-112">The production order can also be updated automatically from planned production orders that are firmed by using the **Firming time fence** field on the **Master plan** page.</span></span>
-   <span data-ttu-id="d8daa-113">El estado **Liberado** es la señal para que los operadores de planta (operadores) comiencen a ejecutar los trabajos de producción en planta.</span><span class="sxs-lookup"><span data-stu-id="d8daa-113">The **Released** state is the signal for the shop floor operators (operators) to start executing the production jobs on the shop floor.</span></span>
-   <span data-ttu-id="d8daa-114">Los papeles de producción, como las tarjetas de ruta, los trabajos de ruta y las tarjetas de trabajo proporcionan información acerca de los trabajos de producción y se pueden emitir.</span><span class="sxs-lookup"><span data-stu-id="d8daa-114">Production papers, such as route cards, route jobs, and jobs cards provide information about production jobs and can be issued.</span></span>
-   <span data-ttu-id="d8daa-115">Para los materiales físicamente reservados, el trabajo de almacén se genera para seleccionar materiales para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="d8daa-115">For materials that are physically reserved, warehouse work is generated to pick materials for the production order.</span></span>

## <a name="releasing-jobs-to-the-shop-floor"></a><span data-ttu-id="d8daa-116">Liberación de trabajos a la planta</span><span class="sxs-lookup"><span data-stu-id="d8daa-116">Releasing jobs to the shop floor</span></span>
<span data-ttu-id="d8daa-117">Después de liberar un pedido de producción, los trabajos de producción relacionados con el pedido quedan visibles y listos para su registro.</span><span class="sxs-lookup"><span data-stu-id="d8daa-117">After a production order is released, production jobs that are related to the order are visible and ready for registration.</span></span> <span data-ttu-id="d8daa-118">Los operadores pueden realizar tareas de registro de trabajos, como inicio, detención y finalización, en la página **Terminal de tarjeta de trabajo** o en la página **Dispositivo de tarjeta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d8daa-118">The operators can make job registrations, such as Start, Stop, and Completion, on either the **Job card terminal** page or the **Job card device** page.</span></span> <span data-ttu-id="d8daa-119">El tiempo y la cantidad registrados se transfieren automáticamente desde las páginas de registro a los diarios de producción para hacer un seguimiento del tiempo y la cantidad consumidos.</span><span class="sxs-lookup"><span data-stu-id="d8daa-119">The registered time and quantity are automatically transferred from the registration pages to production journals to keep track of the consumed time and quantity.</span></span>

## <a name="route-cards"></a><span data-ttu-id="d8daa-120">Tarjetas de ruta</span><span class="sxs-lookup"><span data-stu-id="d8daa-120">Route cards</span></span>
<span data-ttu-id="d8daa-121">Las tarjetas de ruta proporcionan una visión general de la información proveniente de las configuraciones de ruta y operaciones y de los métodos de programación de trabajos y operaciones.</span><span class="sxs-lookup"><span data-stu-id="d8daa-121">A route card provides an overview of information that comes from route and operation setups, and from operation and job scheduling methods.</span></span>

## <a name="route-jobs"></a><span data-ttu-id="d8daa-122">Trabajos de ruta</span><span class="sxs-lookup"><span data-stu-id="d8daa-122">Route jobs</span></span>
<span data-ttu-id="d8daa-123">Los trabajos de ruta enumeran todos los trabajos de una operación detalladamente e incluyen los tiempos de configuración, procesamiento, cola y transporte.</span><span class="sxs-lookup"><span data-stu-id="d8daa-123">A route job lists each job of an operation in detail, and includes setup, process, queue, and transportation times.</span></span> <span data-ttu-id="d8daa-124">Por ejemplo, una operación tal como la pintura puede requerir trabajos individuales como, por ejemplo, el momento de configuración, el tiempo de ejecución para el proceso de pintura y el tiempo en cola para el secado.</span><span class="sxs-lookup"><span data-stu-id="d8daa-124">For example, an operation such as painting might require individual jobs, such as setup time, run time for the painting process, and queue time for drying.</span></span>

## <a name="job-cards"></a><span data-ttu-id="d8daa-125">Tarjetas de trabajo</span><span class="sxs-lookup"><span data-stu-id="d8daa-125">Job cards</span></span>
<span data-ttu-id="d8daa-126">En las tarjetas de trabajo se enumeran los números de trabajo individuales de una operación en particular.</span><span class="sxs-lookup"><span data-stu-id="d8daa-126">A job card lists the individual job numbers of a particular operation.</span></span> <span data-ttu-id="d8daa-127">Aparece un trabajo en cada página.</span><span class="sxs-lookup"><span data-stu-id="d8daa-127">One job appears on each page.</span></span> <span data-ttu-id="d8daa-128">Los trabajos incluidos en las tarjetas de trabajo y sus tiempos estimados provienen de la información de configuración de la ruta y la operación.</span><span class="sxs-lookup"><span data-stu-id="d8daa-128">The jobs that are included on a job card, and their estimated times, come from the route and operation setup information.</span></span> <span data-ttu-id="d8daa-129">Desde una tarjeta de trabajo puede abrir la página **Líneas de diario de producción**, **tarjeta de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d8daa-129">From a job card, you can open the **Production journal lines**, **job card** page.</span></span> <span data-ttu-id="d8daa-130">Las personas que ejecutan recursos de operaciones pueden proporcionar comentarios sobre el proceso de producción.</span><span class="sxs-lookup"><span data-stu-id="d8daa-130">People who run operations resources can provide feedback about the production process.</span></span> <span data-ttu-id="d8daa-131">Existen cambios en los que se especifican las estadísticas y la información de consumo como, por ejemplo, la cantidad de error.</span><span class="sxs-lookup"><span data-stu-id="d8daa-131">There are fields where you can enter consumption statistics and information such as the error quantity.</span></span>

## <a name="warehouse-work-for-raw-material-picking"></a><span data-ttu-id="d8daa-132">Trabajo de almacén para selección de materiales</span><span class="sxs-lookup"><span data-stu-id="d8daa-132">Warehouse work for raw material picking</span></span>
<span data-ttu-id="d8daa-133">El trabajo para seleccionar de materia prima se genera durante el proceso de liberación.</span><span class="sxs-lookup"><span data-stu-id="d8daa-133">Work for raw material picking is generated during release.</span></span> <span data-ttu-id="d8daa-134">El trabajo solo se genera para la cantidad de materiales que se ha reservado físicamente para el pedido de producción antes de que el pedido se liberara.</span><span class="sxs-lookup"><span data-stu-id="d8daa-134">Work is generated only for the quantity of materials that was physically reserved for the production order before the order was released.</span></span> <span data-ttu-id="d8daa-135">Se requiere la configuración siguiente para generar el trabajo de almacén para seleccionar materias primas:</span><span class="sxs-lookup"><span data-stu-id="d8daa-135">The following setup is required to generate warehouse work for raw material picking:</span></span>

-   <span data-ttu-id="d8daa-136">Un directorio de ubicación para seleccionar materias primas que determine en qué ubicación de almacén seleccionar los materiales.</span><span class="sxs-lookup"><span data-stu-id="d8daa-136">A location directive for raw materials picking that determines which warehouse location to pick the materials in</span></span>
-   <span data-ttu-id="d8daa-137">Una plantilla de oleada para materias primas, donde se hayan configurado directivas de ejecución del trabajo de almacén.</span><span class="sxs-lookup"><span data-stu-id="d8daa-137">A wave template for raw materials, where policies for the execution of warehouse work are configured</span></span>
-   <span data-ttu-id="d8daa-138">Una ubicación de entrada de producción que determine dónde se colocan los materiales.</span><span class="sxs-lookup"><span data-stu-id="d8daa-138">A production input location that determines where materials are put</span></span>




