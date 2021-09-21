---
title: El peso de la carga solo puede contener números positivos
description: Al procesar el trabajo entre ubicaciones, es posible que reciba un error con respecto al peso de la carga y que se cancele la actualización. Siga estos pasos para arreglar el problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8ea1f6679a521e3e8683b8e5f18f509e98044414
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477512"
---
# <a name="load-weight-error-and-update-canceled-when-processing-work-between-locations"></a>Error de peso de carga y actualización cancelada al procesar trabajo entre ubicaciones

## <a name="symptoms"></a>Síntomas

Si hay trabajo abierto cuando procesa el trabajo desde las ubicaciones de embalaje a las ubicaciones de preparación, o desde las ubicaciones de preparación a las ubicaciones de muelle puede recibir este error:

> El campo "Peso de la carga" (=-%1) solo puede contener números positivos. Se ha cancelado la actualización.

## <a name="resolution"></a>Resolución

Para solucionar este problema, vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Verificación de consistencia** y ejecute el proceso para **Comprobación de la coherencia del peso de la carga del almacén**.
