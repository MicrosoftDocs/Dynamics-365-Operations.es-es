---
title: No puede importar un artículo utilizando la entidad Productos lanzados V2
description: No puede importar un artículo utilizando la entidad Productos lanzados V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: bf6eb0eb755de3f2842c235946bfd7ccad04ccf7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474733"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>No puede importar un artículo utilizando la entidad Productos lanzados V2

Número de KB: 4611825

## <a name="symptoms"></a>Síntomas

Cuando intente importar un elemento utilizando la entidad *Productos lanzados V2*, recibirá un mensaje de error similar al siguiente ejemplo:

> No se puede crear un registro en Artículos: grupos de dimensiones de seguimiento (EcoResTrackingDimensionGroupItem). Número del artículo: 2040663, lote. El registro ya existe.

## <a name="resolution"></a>Resolución

Para importar nuevos productos lanzados, debe utilizar la entidad *Creación de productos lanzados V2* en lugar de la entidad *Productos lanzados V2*.
