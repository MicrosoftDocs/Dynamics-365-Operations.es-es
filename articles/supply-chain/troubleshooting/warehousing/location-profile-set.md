---
title: El perfil de ubicación no permite el inventario negativo, pero se permite el inventario negativo disponible
description: La opción Permitir inventario negativo para el perfil de ubicación está establecida en No, pero el sistema aún permite el inventario negativo disponible.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 356d2dd7853bf93250e14eb9bd28a8a145794584
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026879"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a><span data-ttu-id="c3370-103">El perfil de ubicación no permite el inventario negativo, pero se permite el inventario negativo disponible</span><span class="sxs-lookup"><span data-stu-id="c3370-103">Location profile disallows negative inventory, but negative on-hand inventory is permitted</span></span>

<span data-ttu-id="c3370-104">Número de KB: 4613622</span><span class="sxs-lookup"><span data-stu-id="c3370-104">KB number: 4613622</span></span>

## <a name="symptoms"></a><span data-ttu-id="c3370-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="c3370-105">Symptoms</span></span>

<span data-ttu-id="c3370-106">La opción **Permitir inventario negativo** para el perfil de ubicación está establecida en *No*, pero el sistema aún permite el inventario negativo disponible.</span><span class="sxs-lookup"><span data-stu-id="c3370-106">The **Allow negative inventory** option for the location profile is set to *No*, but the system still allows negative on-hand inventory.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c3370-107">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3370-107">Example scenario</span></span>

<span data-ttu-id="c3370-108">Para las transacciones reguladas por el gobierno, el sistema debe poder registrar el inventario negativo para contabilizar las pérdidas.</span><span class="sxs-lookup"><span data-stu-id="c3370-108">For government-regulated transactions, the system must be able to record negative inventory to book losses.</span></span> <span data-ttu-id="c3370-109">Lo ideal es que un artículo pueda mostrar inventario negativo, pero solo en ubicaciones designadas, como tanques.</span><span class="sxs-lookup"><span data-stu-id="c3370-109">You want an item to be able to show negative inventory, but only in designated locations, such as tanks.</span></span> <span data-ttu-id="c3370-110">Sin embargo, si el grupo de modelos de artículos permite el inventario negativo, verá que no importa si la ubicación está configurada para permitir el inventario negativo.</span><span class="sxs-lookup"><span data-stu-id="c3370-110">However, if the item model group allows negative inventory, you find that it doesn't matter whether the location is set to allow negative inventory.</span></span> <span data-ttu-id="c3370-111">Si el artículo está configurado de modo que no se permita el inventario negativo, no importa cómo esté configurado el perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="c3370-111">If the item is set up so that negative inventory isn't allowed, it doesn't matter how the location profile is set up.</span></span>

## <a name="resolution"></a><span data-ttu-id="c3370-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="c3370-112">Resolution</span></span>

<span data-ttu-id="c3370-113">El ajuste **Permitir inventario negativo** del perfil de ubicación se aplica solo a los procesos de almacén, como el de selección.</span><span class="sxs-lookup"><span data-stu-id="c3370-113">The **Allow negative inventory** setting from the location profile applies only to warehouse processes, such as picking.</span></span> <span data-ttu-id="c3370-114">Sin embargo, los grupos de modelos de artículos que están configurados para permitir el inventario negativo afectan a todos los procesos de los módulos de gestión de inventarios y gestión de almacén. El perfil de ubicación no invalidará la configuración.</span><span class="sxs-lookup"><span data-stu-id="c3370-114">However, item model groups that are set to allow negative inventory affect all processes from the Inventory management and Warehouse management modules, and the location profile won't override the setting.</span></span>

<span data-ttu-id="c3370-115">Puede controlar si un almacén puede tener inventario negativo.</span><span class="sxs-lookup"><span data-stu-id="c3370-115">You can control whether a warehouse is allowed to carry negative inventory.</span></span> <span data-ttu-id="c3370-116">Configure sus grupos de modelos de artículos para no permitir el inventario negativo físico y configure solo el almacén relevante para permitir el inventario negativo.</span><span class="sxs-lookup"><span data-stu-id="c3370-116">Set your item model groups to disallow negative physical inventory, and set only the relevant warehouse to allow negative inventory.</span></span>
