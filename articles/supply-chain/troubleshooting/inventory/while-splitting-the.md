---
title: Cuando se divide una cantidad con peso capturado, se utiliza la cantidad mínima en lugar de la cantidad nominal
description: Cuando una cantidad con peso capturado se divide en lotes, el campo Cant. picking utiliza la cantidad mínima establecida para el artículo, no la cantidad nominal.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026890"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Cuando se divide una cantidad con peso capturado, se utiliza la cantidad mínima en lugar de la cantidad nominal

Número de KB: 4612073

## <a name="symptoms"></a>Síntomas

Cuando una cantidad con peso capturado se divide en lotes, el campo **Cant. picking** utiliza la cantidad mínima establecida para el artículo, no la cantidad nominal.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. El sistema utiliza la configuración de cantidad mínima de cada artículo para la selección.
