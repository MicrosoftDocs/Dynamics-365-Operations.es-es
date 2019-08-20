---
title: Crear un perfil de ubicación
description: Cada ubicación en el almacén requiere un perfil de ubicación asociado que describa las propiedades de la ubicación, por ejemplo, si la ubicación permite artículos mezclados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: a9e1217a1105e1d53fc937f927e066e392f1ef14
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847336"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="6e7bb-103">Crear un perfil de ubicación</span><span class="sxs-lookup"><span data-stu-id="6e7bb-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e7bb-104">Cada ubicación en el almacén requiere un perfil de ubicación asociado que describa las propiedades de la ubicación, por ejemplo, si la ubicación permite artículos mezclados.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-104">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="6e7bb-105">En este procedimiento crearemos un perfil para una ubicación que no requiere el control del número de matrícula.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-105">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="6e7bb-106">Habilitaremos artículos mezclados y los estados de inventario mezclados, y permitiremos el recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-106">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="6e7bb-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-107">You can use this procedure in the USMF demo data company.</span></span>

1. <span data-ttu-id="6e7bb-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-108">Click New.</span></span>
2. <span data-ttu-id="6e7bb-109">En el campo Id. de perfil de ubicación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-109">In the Location profile ID field, type a value.</span></span>
3. <span data-ttu-id="6e7bb-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="6e7bb-111">En el campo Formato de ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-111">In the Location format field, enter or select a value.</span></span>
5. <span data-ttu-id="6e7bb-112">En el campo Tipo de ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-112">In the Location type field, enter or select a value.</span></span>
6. <span data-ttu-id="6e7bb-113">En el campo Id. de perfil de administración de muelles, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-113">In the Dock management profile ID field, enter or select a value.</span></span>
7. <span data-ttu-id="6e7bb-114">Seleccione Sí en el campo Permitir artículos combinados.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-114">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="6e7bb-115">Seleccione Sí en el campo Permitir estados de inventario combinados.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-115">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="6e7bb-116">Seleccione Sí en el campo Permitir recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-116">Select Yes in the Allow cycle counting field.</span></span>
10. <span data-ttu-id="6e7bb-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-117">Click Save.</span></span>
11. <span data-ttu-id="6e7bb-118">Vaya a Gestión de almacenes > Configurar > Almacén > Perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="6e7bb-118">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>

