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
ms.openlocfilehash: efd773313f89784d8fca6b37d867e204cb2d06ab29694a19cbec7eed107a8019
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764701"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>No puede importar un artículo utilizando la entidad Productos lanzados V2

Número de KB: 4611825

## <a name="symptoms"></a>Síntomas

Cuando intente importar un elemento utilizando la entidad *Productos lanzados V2*, recibirá un mensaje de error similar al siguiente ejemplo:

> No se puede crear un registro en Artículos: grupos de dimensiones de seguimiento (EcoResTrackingDimensionGroupItem). Número del artículo: 2040663, lote. El registro ya existe.

## <a name="resolution"></a>Resolución

Para importar nuevos productos lanzados, debe utilizar la entidad *Creación de productos lanzados V2* en lugar de la entidad *Productos lanzados V2*.
