---
title: Crear un elemento de menú del dispositivo móvil para la consolidación del número de matrícula
description: Este procedimiento muestra cómo crear un elemento de menú del dispositivo móvil para el trabajo de consolidación de la matrícula de entidad.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dc52284473f3e3275675b608386641c8570218b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217135"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a><span data-ttu-id="597b6-103">Crear un elemento de menú del dispositivo móvil para la consolidación del número de matrícula</span><span class="sxs-lookup"><span data-stu-id="597b6-103">Create a mobile device menu item for license plate consolidation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="597b6-104">Este procedimiento muestra cómo crear un elemento de menú del dispositivo móvil para el trabajo de consolidación de la matrícula de entidad.</span><span class="sxs-lookup"><span data-stu-id="597b6-104">This procedure shows you how to create a mobile device menu item for license plate consolidation work.</span></span> <span data-ttu-id="597b6-105">Esto permite a los trabajadores del almacén consolidar artículos de una matrícula de entidad de almacén con los artículos de otra matrícula de entidad de almacén dentro de la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="597b6-105">This enables warehouse workers to consolidate items on one license plate with items on another license place within the same location.</span></span> <span data-ttu-id="597b6-106">Por ejemplo, es posible que utilicen esto si los pasos subsiguientes fueran iguales en ambos pedidos de trabajo, de modo que el trabajo sólo deba realizarse para los artículos combinados.</span><span class="sxs-lookup"><span data-stu-id="597b6-106">For example, they might use this if subsequent staging steps were the same on both work orders, so that the work only needs to be performed once for the merged items.</span></span> <span data-ttu-id="597b6-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="597b6-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="597b6-108">La tarea la realizará normalmente el responsable del almacén.</span><span class="sxs-lookup"><span data-stu-id="597b6-108">The task would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="597b6-109">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="597b6-109">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

1. <span data-ttu-id="597b6-110">Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Elementos de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="597b6-110">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="597b6-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="597b6-111">Click New.</span></span>
3. <span data-ttu-id="597b6-112">En el campo Nombre del elemento de menú, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="597b6-112">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="597b6-113">En el campo Título, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="597b6-113">In the Title field, type a value.</span></span>
5. <span data-ttu-id="597b6-114">En el campo Modo, seleccione "Indirecto".</span><span class="sxs-lookup"><span data-stu-id="597b6-114">In the Mode field, select 'Indirect'.</span></span>
6. <span data-ttu-id="597b6-115">En el campo Código de actividad, seleccione "Consolidar matrículas".</span><span class="sxs-lookup"><span data-stu-id="597b6-115">In the Activity code field, select 'Consolidate license plates'.</span></span>

