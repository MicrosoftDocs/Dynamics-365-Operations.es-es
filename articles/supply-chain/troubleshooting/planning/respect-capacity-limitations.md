---
title: La planificación maestra es programar más que la capacidad disponible
description: La planificación maestra no parece respetar las limitaciones de capacidad y está programando más que la capacidad disponible
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 48b3d179bb923ff6f6cc5b6be291408b3eb34d98
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477538"
---
# <a name="master-planning-is-scheduling-more-than-the-available-capacity"></a>La planificación maestra es programar más que la capacidad disponible

## <a name="symptoms"></a>Síntomas

La planificación maestra no parece respetar las limitaciones de capacidad y está programando más que la capacidad disponible.

Cuando usa la programación de operaciones donde hay una capacidad finita, y donde la ruta especifica una combinación de requisitos para un grupo de recursos y recursos individuales, existe una pequeña posibilidad de overbooking debido a la forma en que el algoritmo valida los conflictos de capacidad. Esta sobreventa puede ocurrir cuando utiliza ayudantes para ejecutar la planificación maestra. Es más probable que ocurra si hay muchos trabajos que tienen un tiempo de ejecución relativamente corto.

## <a name="resolution"></a>Resolución

Si es esencial que no se produzca una sobreventa para la programación de operaciones, puede hacer que la programación sea parte de la planificación maestra de un solo subproceso activando la opción **Capacidad finita precisa para la programación de operaciones** en la página **Parámetros de planificación maestra**. Esta opción no está disponible de forma predeterminada. Debe agregarlo manualmente a la página mediante funciones de personalización. Cuando usa esta opción, la programación se ejecutará más lentamente debido a la falta de procesamiento paralelo.
