---
title: No se puede seleccionar el cambio de Estado de inventario como Tipo de trabajo
description: No puede crear una línea de plantilla de trabajo para el cambio de estado de Inventario porque el tipo de trabajo solo lo utilizan los procesos del sistema. Seleccione un tipo de trabajo diferente.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ad7f26f3235d15779583f9cdadeb4e6dca16242a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477558"
---
# <a name="cant-select-inventory-status-change-in-the-work-type-column"></a>No se puede seleccionar el cambio de Estado de inventario en la columna Tipo de trabajo

## <a name="symptoms"></a>Síntomas

Al configurar Microsoft Dynamics 365 Supply Chain Management, puede recibir el siguiente mensaje de error:

> No puede crear una línea de plantilla de trabajo para el cambio de estado de Inventario porque el tipo de trabajo no es válido. Seleccione un tipo de trabajo diferente.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. El tipo de trabajo *Cambio de estado de inventario* solo lo utilizan los procesos del sistema. No se puede configurar. Debido a que la lista de tipos de trabajo se fija como una enumeración, las entradas adicionales no se pueden filtrar del menú desplegable **Tipo de trabajo**.
