---
title: El peso debe ser positivo.
description: El peso debe ser positivo.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 27ec37e0c0644ff10ece4626d5c136bca3c52ef12f1c6de947afd03003a5368a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776785"
---
# <a name="weight-must-be-positive"></a>El peso debe ser positivo.

Código de error: WeightMustBePositive

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> El peso debe ser positivo.

## <a name="cause"></a>Causa

El campo **Peso bruto** está configurado en *0* (cero) o un valor negativo.

## <a name="resolution"></a>Resolución

Para especificar un peso, siga uno de estos pasos.

- En el campo **Peso bruto**, establezca un valor. Luego seleccione una unidad en la lista desplegable.
- Seleccione **Obtener el peso del sistema** para calcular el valor **Peso bruto**.
