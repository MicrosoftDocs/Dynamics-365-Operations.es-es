---
title: No se pudo encontrar el perfil del clúster
description: Al trabajar con operaciones de almacén de entrada, es posible que reciba un error que indique que no se puede encontrar el perfil del clúster. Asegúrese de que los perfiles de clúster estén configurados correctamente.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bbf9c5bc70c8f3ba1fa26db425249e65e82c0518
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477568"
---
# <a name="cluster-profile-cant-be-found"></a>No se puede encontrar el perfil del clúster

## <a name="symptoms"></a>Síntomas

Al trabajar con operaciones de almacén de entrada, es posible que reciba el siguiente mensaje de error:

> "Se ha generado pedido de calidad %1. No se pudo encontrar el perfil del clúster. Compruebe su configuración".

Este mensaje de error está relacionado con un proceso de recepción donde la gestión de la calidad (QMS) está activada. Según las configuraciones de su entorno, los detalles adicionales sobre la transacción que genera el mensaje de error pueden ayudar a solucionar el problema.

## <a name="resolution"></a>Resolución

Primero, revise la configuración de la selección de clúster y asegúrese de que los perfiles de clúster estén configurados correctamente. No puede utilizar un elemento del menú de un dispositivo móvil para la selección de grupos a menos que se configuren perfiles de grupos. Dependiendo de su entorno, es posible que también deba revisar otras configuraciones relacionadas.
