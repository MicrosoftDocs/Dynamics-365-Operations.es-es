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
ms.openlocfilehash: 8182f2f83f6a3e4cf54fe6fa64b25a2f461ff541
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026873"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>No puede importar un artículo utilizando la entidad Productos lanzados V2

Número de KB: 4611825

## <a name="symptoms"></a>Síntomas

Cuando intente importar un elemento utilizando la entidad *Productos lanzados V2*, recibirá un mensaje de error similar al siguiente ejemplo:

> No se puede crear un registro en Artículos: grupos de dimensiones de seguimiento (EcoResTrackingDimensionGroupItem). Número del artículo: 2040663, lote. El registro ya existe.

## <a name="resolution"></a>Resolución

Para importar nuevos productos lanzados, debe utilizar la entidad *Creación de productos lanzados V2* en lugar de la entidad *Productos lanzados V2*.
