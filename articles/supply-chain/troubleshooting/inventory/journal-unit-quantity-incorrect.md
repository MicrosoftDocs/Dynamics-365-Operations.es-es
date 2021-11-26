---
title: La unidad y la cantidad de unidades no funcionan correctamente en el diario de inventario
description: La unidad y la cantidad de unidades no funcionan correctamente en el diario de inventario
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 074be71d7b6ec1acab6307a79e397c2a2a045c39
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778434"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>La unidad y la cantidad de unidades no funcionan correctamente en el diario de inventario

## <a name="symptoms"></a>Síntomas

Puede encontrar uno o ambos de los siguientes problemas cuando trabaja con unidades y cantidades en un diario de inventario:

- No ve unidades o cantidades de unidades en el diario de inventario mientras se configura una unidad de conversión para el producto liberado y no puede cambiar la unidad en el diario de inventario.
- Ve los campos **Cantidad** y **Unidad** en el diario de inventario, pero no ve el campo **Cantidad de unidades**. Si cambia la unidad, introduce una cantidad y registra el diario, el diario sigue mostrando la unidad de medida original para esa cantidad.

## <a name="resolution"></a>Resolución

Para arreglar este problema, siga estos pasos.

1. En el espacio de trabajo **Administración de características**, asegúrese de que la característica *Uso de unidad de medida y cantidad de unidad en diarios de inventario* está activada. Esta característica agrega los campos **Unidad** y **Cantidad de unidades** al diario. (A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada).
1. Una vez activada la característica, use los campos **Cantidad**, **Cantidad de unidades** y **Unidad** de la siguiente manera:

    - **Cantidad**: especifique la cantidad utilizando la unidad predeterminada que se define para el producto liberado. Sin embargo, la unidad predeterminada en sí no se muestra aquí. Si se configura una conversión entre la unidad predeterminada y la unidad seleccionada en el campo **Unidad**, el campo **Cantidad** se actualiza automáticamente, según las selecciones de los campos **Cantidad de unidades** y **Unidad**.
    - **Cantidad de unidades**: especifique la cantidad empleando la unidad de medida seleccionada en el campo **Unidad**.
    - **Unidad**: seleccione la unidad para aplicar al valor en el campo **Cantidad de unidades**.
