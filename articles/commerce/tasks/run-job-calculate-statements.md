---
title: Configurar y ejecutar trabajo para calcular extractos
description: Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 973236acca0cb8c0d57171e4bb9d4daaa7faaf38
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141209"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="a6410-103">Configurar y ejecutar trabajo para calcular extractos</span><span class="sxs-lookup"><span data-stu-id="a6410-103">Configure and run job to calculate statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a6410-104">Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="a6410-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="a6410-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="a6410-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="a6410-106">Vaya a Todos los espacios de trabajo > Operaciones financieras de tiendas.</span><span class="sxs-lookup"><span data-stu-id="a6410-106">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="a6410-107">Haga clic en Calcular extractos.</span><span class="sxs-lookup"><span data-stu-id="a6410-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="a6410-108">Seleccione una tienda concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="a6410-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="a6410-109">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="a6410-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="a6410-110">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a6410-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="a6410-111">Seleccione "Sí" en Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="a6410-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="a6410-112">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="a6410-112">Click Recurrence.</span></span>
6. <span data-ttu-id="a6410-113">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="a6410-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="a6410-114">Especifique una hora en el campo Hora inicial.</span><span class="sxs-lookup"><span data-stu-id="a6410-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="a6410-115">Seleccione la opción No hay fecha final.</span><span class="sxs-lookup"><span data-stu-id="a6410-115">Select the No end date option.</span></span>
9. <span data-ttu-id="a6410-116">En el campo PatternUnit, especifique "Days".</span><span class="sxs-lookup"><span data-stu-id="a6410-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="a6410-117">En el campo Por, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a6410-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="a6410-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a6410-118">Click OK.</span></span>
12. <span data-ttu-id="a6410-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a6410-119">Click OK.</span></span>

