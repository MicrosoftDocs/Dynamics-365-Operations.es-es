---
title: Solo se imprime una etiqueta para varios encabezados de trabajo en una sola recepción
description: Solo se imprime una etiqueta para varios encabezados de trabajo en una sola recepción.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026880"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Solo se imprime una etiqueta para varios encabezados de trabajo en una sola recepción

Número de KB: 4614667

## <a name="symptoms"></a>Síntomas

Se crean varios encabezados de trabajo para la misma matrícula de destino como parte de un evento de recepción de una sola aplicación de almacén. Sin embargo, solo se imprime una etiqueta de matrícula cuando se recibe el producto.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado.

En el diseño actual, siempre se genera una sola etiqueta de matrícula, independientemente del número de combinaciones de encabezado de trabajo y línea de trabajo que existan. La etiqueta generada incluye la información de una sola combinación.

Para solucionar este problema, asegúrese de que la creación del encabezado de trabajo siempre esté asignada a una sola matrícula de destino.
