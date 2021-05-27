---
title: Ajustes de campo faltantes cuando los grupos de modelo del artículo se copian a otra entidad jurídica
description: Faltan ajustes de campo cuando los grupos de modelo del artículo se copian a otra entidad jurídica.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026876"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="83087-103">Ajustes de campo faltantes cuando los grupos de modelo del artículo se copian a otra entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="83087-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="83087-104">Número de KB: 4612800</span><span class="sxs-lookup"><span data-stu-id="83087-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="83087-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="83087-105">Symptoms</span></span>

<span data-ttu-id="83087-106">Cuando copia grupos de modelos de artículos a otra entidad jurídica (empresa) mediante la entidad *Políticas de inventario de grupos de modelos de artículos*, faltan algunas configuraciones de campo (por ejemplo, el modelo de inventario y la descripción) en el nuevo grupo de modelos en la entidad jurídica de destino.</span><span class="sxs-lookup"><span data-stu-id="83087-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="83087-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="83087-107">Resolution</span></span>

<span data-ttu-id="83087-108">Para crear una copia completa de un grupo de modelos de artículos en otra entidad jurídica, también debe seleccionar las políticas de inventario del grupo de modelos de artículos (`InventInventoryPolicyEntity`) y las políticas de suposición de flujo de costes (`InventCostFlowAssumptionPolicyEntity`) que están asociadas con el grupo de modelos de artículos.</span><span class="sxs-lookup"><span data-stu-id="83087-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
