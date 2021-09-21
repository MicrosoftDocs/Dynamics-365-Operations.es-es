---
title: Se debe especificar una matrícula de entidad de almacén para esta ubicación
description: Si recibe este error después de crear una orden de transferencia para un almacén habilitado para WMS, la ubicación de recepción predeterminada está en blanco para un almacén de tránsito.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477491"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Error de especificación de la placa de matrícula al confirmar el envío para una orden de transferencia

## <a name="symptoms"></a>Síntomas

Si crea una orden de transferencia utilizando un almacén que está habilitado para la administración avanzada de almacenes (WMS) y luego confirma el envío cuando el trabajo esté completado, puede recibir el siguiente mensaje de error:

> Se debe especificar una matrícula de entidad de almacén para esta ubicación.

## <a name="cause"></a>Causa

Esto sucede porque el campo **Ubicación de recibo predeterminada** está en blanco para un almacén de tránsito del almacén "desde".

## <a name="resolution"></a>Resolución

Para solucionar este problema, especifique una ubicación de recepción predeterminada en el almacén de tránsito. Asegúrese de que esta ubicación esté controlada por matrículas.
