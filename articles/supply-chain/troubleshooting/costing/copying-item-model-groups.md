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
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Ajustes de campo faltantes cuando los grupos de modelo del artículo se copian a otra entidad jurídica

Número de KB: 4612800

## <a name="symptoms"></a>Síntomas

Cuando copia grupos de modelos de artículos a otra entidad jurídica (empresa) mediante la entidad *Políticas de inventario de grupos de modelos de artículos*, faltan algunas configuraciones de campo (por ejemplo, el modelo de inventario y la descripción) en el nuevo grupo de modelos en la entidad jurídica de destino.

## <a name="resolution"></a>Resolución

Para crear una copia completa de un grupo de modelos de artículos en otra entidad jurídica, también debe seleccionar las políticas de inventario del grupo de modelos de artículos (`InventInventoryPolicyEntity`) y las políticas de suposición de flujo de costes (`InventCostFlowAssumptionPolicyEntity`) que están asociadas con el grupo de modelos de artículos.
