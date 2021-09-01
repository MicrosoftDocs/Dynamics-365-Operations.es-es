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
ms.openlocfilehash: 424ad46281612f6a3e8cb4c90478a39f757d5416c3ce1d77ed6ff6dba7b20dcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723464"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Cuando se divide una cantidad con peso capturado, se utiliza la cantidad mínima en lugar de la cantidad nominal

Número de KB: 4612073

## <a name="symptoms"></a>Síntomas

Cuando una cantidad con peso capturado se divide en lotes, el campo **Cant. picking** utiliza la cantidad mínima establecida para el artículo, no la cantidad nominal.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado. El sistema utiliza la configuración de cantidad mínima de cada artículo para la selección.
