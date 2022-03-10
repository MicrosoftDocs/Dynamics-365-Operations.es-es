---
title: El artículo no puede tener una lista de materiales ni una fórmula
description: Cuando intenta confirmar un pedido, recibe un mensaje de error durante la validación del artículo. Establece que el artículo no puede tener una lista de materiales (BOM) o una fórmula.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1e946adc3a04db60bf15ac7bb44163085e1c19802872964877d3929b1f79bf7d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730115"
---
# <a name="item-cant-have-a-bom-or-formula"></a>El artículo no puede tener una lista de materiales ni una fórmula

Código de error: PRO2614

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un pedido, recibe el siguiente mensaje de error durante la validación del artículo:

> El artículo no puede tener una L. MAT o fórmula.

## <a name="resolution"></a>Resolución

Los artículos que tienen una lista de materiales (BOM) o una fórmula deben ser de tipo *Elemento de planificación*, *BOM* o *fórmula*. Para cambiar el tipo de un elemento, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abrir el producto relevante.
1. En la ficha desplegable **Ingeniero**, establezca el campo **Tipo de producción** en *Elemento de planificación*, *L. MAT* o *fórmula*.
