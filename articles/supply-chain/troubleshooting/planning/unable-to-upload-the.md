---
title: No puede actualizar el coste unitario previsto cuando importa registros de previsión de la demanda
description: Cuando utiliza entidades de datos para importar registros de previsión de la demanda, el precio de coste de los registros existentes no se actualiza para que coincida con los datos importados.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: de471da861785f283eeaa78f97b5d1e1a6b023d71de6fff72ae39edd6bb124cc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765379"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>No puede actualizar el coste unitario previsto cuando importa registros de previsión de la demanda

Número de KB: 4614109

## <a name="symptoms"></a>Síntomas

Cuando utiliza entidades de datos para importar registros de previsión de la demanda, el valor **Coste unitario previsto** de los registros existentes no se actualiza para que coincida con los datos importados.

## <a name="cause"></a>Causa

**Coste unitario previsto** es un campo de solo lectura. El valor se basa en el coste unitario del producto y no se puede establecer directamente a través de la importación.

## <a name="resolution"></a>Resolución

Debido a que el campo es de solo lectura, no puede importar valores en él. El valor se calculará de acuerdo con la lógica empresarial existente.
