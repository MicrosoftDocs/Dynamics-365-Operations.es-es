---
title: No se encontró suficiente trabajo para el clúster después de configurar el perfil
description: Si configura un perfil de clúster, puede recibir un mensaje de error que dice que no se puede encontrar suficiente trabajo. Edite el perfil y establezca Activar posiciones en No.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477490"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>No se encontró suficiente trabajo para el clúster cuando se usa la selección de clústeres dirigida por el sistema

## <a name="symptoms"></a>Síntomas

Cuando usa el proceso *Selección de grupos dirigida por el sistema*, si configura un perfil de clúster donde, por ejemplo, se pueden seleccionar 10 posiciones, el proceso funciona según lo planificado cuando hay suficiente trabajo para seleccionar 10 posiciones. Sin embargo, si solo hay ocho posiciones para elegir, recibirá el siguiente mensaje de error:

> No se encuentra suficiente trabajo para el clúster.

## <a name="resolution"></a>Resolución

Para solucionar este problema, edite el perfil del clúster y configure la opción **Activar posiciones** como *No*.
