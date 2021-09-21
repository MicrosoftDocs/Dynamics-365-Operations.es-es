---
title: Error de ruta de certificación al actualizar o migrar a WMS
description: Si la aplicación muestra el error "No se encontró el ancla de confianza para la ruta de certificación" al actualizar o migrar a WMS, esta página brinda información sobre cómo solucionar el problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2cff41455268c43bdd99e285b9675f0c69be7de7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477498"
---
 # <a name="trust-anchor-for-certification-path-not-found-when-updating-and-migrating-to-wms"></a>No se encontró el ancla de confianza para la ruta de certificación al configurar y migrar a WMS

## <a name="symptoms"></a>Síntomas

Al actualizar y migrar a Warehouse Management avanzado (WMS), la aplicación Warehouse Management puede mostrarle el siguiente mensaje de error:

> java.security.cert.certPathValidatorException: no se encuentra el ancla de confianza para la ruta de certificación.

## <a name="cause"></a>Causa

Esto ocurre porque no se confía en los certificados autofirmados en Android 8+ en entornos locales.

## <a name="resolution"></a>Resolución

Utilice una autoridad de certificación (CA) externa (pública). Hay una solución para este problema disponible en la versión 1.9.0.0 de la aplicación Warehouse Management. Para obtener más información sobre este problema y cómo solucionarlo, consulte [No se encontró el ancla de confianza para la ruta de certificación al configurar la conexión de la aplicación](certification-path-app-connection-error.md).
