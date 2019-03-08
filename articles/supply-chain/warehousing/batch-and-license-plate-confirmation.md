---
title: Confirmación de lote y matrícula
description: Este tema describe cómo configurar y aplicar confirmación de lote y matrícula desde un dispositivo móvil.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: efab5b11782fd2344fb5f532272007d187c1465b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "344234"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="88b66-103">Confirmación de lote y matrícula</span><span class="sxs-lookup"><span data-stu-id="88b66-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88b66-104">La confirmación de lote le permite confirmar que se eligió el lote correcto en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="88b66-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="88b66-105">En la selección inicial del trabajo solo para los artículos superiores al lote, donde superior al lote indica que el lote supera a la ubicación en la jerarquía de la búsqueda, debe comprobar que el lote elegido se corresponde con el lote en la línea del trabajo.</span><span class="sxs-lookup"><span data-stu-id="88b66-105">On the initial pick of work for batch above-items only, where batch above indicates that batch ranges higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span> 

<span data-ttu-id="88b66-106">La confirmación de matrícula le permite confirmar que se eligió la matrícula correcta en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="88b66-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="88b66-107">Al seleccionar el trabajo en una ubicación de la etapa, debe comprobar que la matrícula elegida coincide con la matrícula que está asociada al trabajo.</span><span class="sxs-lookup"><span data-stu-id="88b66-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="88b66-108">Si el trabajo se ha iniciado con la digitalización de una matrícula, este paso de confirmación se omitirá.</span><span class="sxs-lookup"><span data-stu-id="88b66-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="88b66-109">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="88b66-109">Where it applies</span></span>
<span data-ttu-id="88b66-110">La confirmación se aplica en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="88b66-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="88b66-111">La confirmación de lote se aplica a las selecciones iniciales de trabajo para los artículos superiores al lote.</span><span class="sxs-lookup"><span data-stu-id="88b66-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="88b66-112">La confirmación de la matrícula se aplica a las selecciones de ubicaciones de la etapa.</span><span class="sxs-lookup"><span data-stu-id="88b66-112">License plate confirmation applies to picks from stage locations.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="88b66-113">Configurara la confirmación de lote y matrícula</span><span class="sxs-lookup"><span data-stu-id="88b66-113">Set up batch and license plate confirmation</span></span>
<span data-ttu-id="88b66-114">Puede configurar la confirmación del lote y de matrícula desde los elementos de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="88b66-114">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>  
1.  <span data-ttu-id="88b66-115">En los elementos de menú del dispositivo móvil, especifique la configuración de la confirmación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="88b66-115">From the mobile device menu items, enter the work confirmation setup.</span></span>  
2.  <span data-ttu-id="88b66-116">Seleccione la opción para la confirmación de lote o matrícula.</span><span class="sxs-lookup"><span data-stu-id="88b66-116">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="88b66-117">Ambas opciones están disponibles para las selecciones del tipo de trabajo que no tengan habilitada la confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="88b66-117">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  
