---
title: Confirmación de lote y matrícula
description: Este tema describe cómo configurar y aplicar confirmación de lote y matrícula desde un dispositivo móvil.
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c588e6ed11d275b75133e2824f3d385048050426
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837546"
---
# <a name="batch-and-license-plate-confirmation"></a><span data-ttu-id="7883c-103">Confirmación de lote y matrícula</span><span class="sxs-lookup"><span data-stu-id="7883c-103">Batch and license plate confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7883c-104">La confirmación de lote le permite confirmar que se eligió el lote correcto en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="7883c-104">Batch confirmation allows you to confirm that the correct batch is being picked from the mobile device.</span></span> <span data-ttu-id="7883c-105">En la selección inicial del trabajo solo para los artículos *Batch-above\[ubicación\]*, donde batch-above indica que el lote supera a la ubicación en la jerarquía de la búsqueda, debe comprobar que el lote elegido se corresponde con el lote en la línea del trabajo.</span><span class="sxs-lookup"><span data-stu-id="7883c-105">On the initial pick of work for *Batch-above\[location\]* items only, where batch-above indicates that batch is placed higher than location in the search hierarchy, you must verify that the batch that is picked matches the batch on the work line.</span></span>

<span data-ttu-id="7883c-106">La confirmación de matrícula le permite confirmar que se eligió la matrícula correcta en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="7883c-106">License plate confirmation allows you to confirm that the correct license plate is being picked from the mobile device.</span></span> <span data-ttu-id="7883c-107">Al seleccionar el trabajo en una ubicación de la etapa, debe comprobar que la matrícula elegida coincide con la matrícula que está asociada al trabajo.</span><span class="sxs-lookup"><span data-stu-id="7883c-107">When picking work from a stage location, you must verify that the license plate that is picked matches the license plate that is associated with the work.</span></span> <span data-ttu-id="7883c-108">Si el trabajo se ha iniciado con la digitalización de una matrícula, este paso de confirmación se omitirá.</span><span class="sxs-lookup"><span data-stu-id="7883c-108">If the work is started by scanning a license plate, this confirmation step will be skipped.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="7883c-109">Dónde se aplica</span><span class="sxs-lookup"><span data-stu-id="7883c-109">Where it applies</span></span>

<span data-ttu-id="7883c-110">La confirmación se aplica en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7883c-110">Confirmation applies in the following scenarios:</span></span>

- <span data-ttu-id="7883c-111">La confirmación de lote se aplica a las selecciones iniciales de trabajo para los artículos superiores al lote.</span><span class="sxs-lookup"><span data-stu-id="7883c-111">Batch confirmation applies to the initial picks of work for batch above-items.</span></span>
- <span data-ttu-id="7883c-112">La confirmación de la matrícula se aplica a las selecciones de ubicaciones de la etapa.</span><span class="sxs-lookup"><span data-stu-id="7883c-112">License plate confirmation applies to picks from stage locations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7883c-113">No se admite el reabastecimiento para la confirmación de la matrícula.</span><span class="sxs-lookup"><span data-stu-id="7883c-113">Replenishment is not supported for license plate confirmation.</span></span> <span data-ttu-id="7883c-114">Al ejecutar el trabajo de reabastecimiento, no se crea ningún paso de confirmación de matrícula.</span><span class="sxs-lookup"><span data-stu-id="7883c-114">When executing replenishment work, no license plate confirmation step is created.</span></span>

## <a name="set-up-batch-and-license-plate-confirmation"></a><span data-ttu-id="7883c-115">Configurara la confirmación de lote y matrícula</span><span class="sxs-lookup"><span data-stu-id="7883c-115">Set up batch and license plate confirmation</span></span>

<span data-ttu-id="7883c-116">Puede configurar la confirmación del lote y de matrícula desde los elementos de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="7883c-116">You can configure batch and license plate confirmation from the mobile device menu items.</span></span>

1. <span data-ttu-id="7883c-117">En los elementos de menú del dispositivo móvil, especifique la configuración de la confirmación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="7883c-117">From the mobile device menu items, enter the work confirmation setup.</span></span>  
1. <span data-ttu-id="7883c-118">Seleccione la opción para la confirmación de lote o matrícula.</span><span class="sxs-lookup"><span data-stu-id="7883c-118">Select the option for either batch or license plate confirmation.</span></span> <span data-ttu-id="7883c-119">Ambas opciones están disponibles para las selecciones del tipo de trabajo que no tengan habilitada la confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="7883c-119">Both options are available for work type picks that do not have automatic confirmation enabled.</span></span>  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
