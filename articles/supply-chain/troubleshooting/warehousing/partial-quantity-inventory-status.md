---
title: Hacer un cambio de estado de inventario para trabajo de cantidad parcial
description: Esta página explica cómo crear un elemento de menú con la configuración adecuada para permitir que los trabajadores realicen un cambio de estado de inventario para una cantidad parcial de un lote.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477474"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Habilitar un cambio de estado de inventario para trabajo de cantidad parcial

## <a name="symptoms"></a>Síntomas

Necesita realizar un cambio de estado de inventario para una cantidad parcial de un lote.

## <a name="resolution"></a>Resolución

Para permitir que los trabajadores realicen este cambio, puede crear un elemento de menú para la aplicación móvil Warehouse Management. En la página **Elementos de menú del dispositivo móvil**, cree (o edite) un elemento de menú con la siguiente configuración:

- **Modo:** *Trabajo*
- **Usar trabajo existente:** *No*
- **Proceso de creación de trabajo:** *Movimiento*
- **Mostrar estado de inventario**: *Sí*

Puede configurar otros campos en la página según sus necesidades.
