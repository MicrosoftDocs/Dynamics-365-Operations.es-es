---
title: Crear un perfil de ubicación
description: Este tema explica cómo crear un perfil de ubicación en Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46aa1001c21ae39c158062444303ca02c0f41a45
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866988"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="4eb80-103">Crear un perfil de ubicación</span><span class="sxs-lookup"><span data-stu-id="4eb80-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4eb80-104">Este tema explica cómo crear un perfil de ubicación en Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4eb80-104">This topic explains how to create a location profile in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="4eb80-105">Cada ubicación en el almacén requiere un perfil de ubicación asociado que describa las propiedades de la ubicación, por ejemplo, si la ubicación permite artículos mezclados.</span><span class="sxs-lookup"><span data-stu-id="4eb80-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="4eb80-106">En este procedimiento crearemos un perfil para una ubicación que no requiere el control del número de matrícula.</span><span class="sxs-lookup"><span data-stu-id="4eb80-106">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="4eb80-107">Habilitaremos artículos mezclados y los estados de inventario mezclados, y permitiremos el recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="4eb80-107">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="4eb80-108">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="4eb80-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="4eb80-109">En el Panel de exploración, vaya a **Módulos > Gestión de almacenes > Configuración > Almacén >Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="4eb80-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="4eb80-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4eb80-110">Select **New**.</span></span>
3. <span data-ttu-id="4eb80-111">En el campo **Id. de perfil de ubicación**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4eb80-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="4eb80-112">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4eb80-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="4eb80-113">En el campo **Formato de ubicación**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4eb80-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="4eb80-114">En el campo **Tipo de ubicación**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4eb80-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="4eb80-115">En el campo **Id. de perfil de administración de muelles**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="4eb80-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="4eb80-116">Seleccione **Sí** en el campo **Permitir artículos combinados**.</span><span class="sxs-lookup"><span data-stu-id="4eb80-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="4eb80-117">Seleccione **Sí** en el campo **Permitir estados de inventario combinados**.</span><span class="sxs-lookup"><span data-stu-id="4eb80-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="4eb80-118">Seleccione **Sí** en el campo **Permitir recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="4eb80-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="4eb80-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4eb80-119">Select **Save**.</span></span>

