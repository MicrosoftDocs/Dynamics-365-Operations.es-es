---
title: Placa de matrícula no válida o error de ubicación en la aplicación móvil
description: Cuando escanea la identificación o ubicación de una placa de matrícula, recibe un mensaje de error de que no es válida. Asegúrese de que la identificación de la matrícula no esté reservada por otra persona.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f9f10dbade0d13b8fc4b0fc92981d84e6e28e83e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477575"
---
# <a name="invalid-license-plate-or-location-error-when-scanning-in-the-mobile-app"></a>Placa de matrícula no válida o error de ubicación al escanear en la aplicación móvil

## <a name="symptoms"></a>Síntomas

Cuando escanea la identificación o ubicación de una placa de matrícula, recibe el siguiente mensaje de error:

> La matrícula de entidad de almacén o ubicación no son válidas.

## <a name="resolution"></a>Resolución

Asegúrese de que la identificación de la matrícula no esté reservada por otra persona. Este problema solía ocurrir cuando el valor que un usuario escaneaba en la aplicación móvil Warehouse Management era tanto una ubicación válida como una identificación de matrícula válida. Sin embargo, este problema se resolvió en la versión 10.0.11.
