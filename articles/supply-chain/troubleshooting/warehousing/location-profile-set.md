---
title: El perfil de ubicación no permite el inventario negativo, pero se permite el inventario negativo disponible
description: La opción Permitir inventario negativo para el perfil de ubicación está establecida en No, pero el sistema aún permite el inventario negativo disponible.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 2a7345281301ee70a512dfadcd553cb4eb33003904d0dddf6967659b693f60d7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742617"
---
# <a name="location-profile-disallows-negative-inventory-but-negative-on-hand-inventory-is-permitted"></a>El perfil de ubicación no permite el inventario negativo, pero se permite el inventario negativo disponible

Número de KB: 4613622

## <a name="symptoms"></a>Síntomas

La opción **Permitir inventario negativo** para el perfil de ubicación está establecida en *No*, pero el sistema aún permite el inventario negativo disponible.

## <a name="example-scenario"></a>Supuesto de ejemplo

Para las transacciones reguladas por el gobierno, el sistema debe poder registrar el inventario negativo para contabilizar las pérdidas. Lo ideal es que un artículo pueda mostrar inventario negativo, pero solo en ubicaciones designadas, como tanques. Sin embargo, si el grupo de modelos de artículos permite el inventario negativo, verá que no importa si la ubicación está configurada para permitir el inventario negativo. Si el artículo está configurado de modo que no se permita el inventario negativo, no importa cómo esté configurado el perfil de ubicación.

## <a name="resolution"></a>Resolución

El ajuste **Permitir inventario negativo** del perfil de ubicación se aplica solo a los procesos de almacén, como el de selección. Sin embargo, los grupos de modelos de artículos que están configurados para permitir el inventario negativo afectan a todos los procesos de los módulos de gestión de inventarios y gestión de almacén. El perfil de ubicación no invalidará la configuración.

Puede controlar si un almacén puede tener inventario negativo. Configure sus grupos de modelos de artículos para no permitir el inventario negativo físico y configure solo el almacén relevante para permitir el inventario negativo.
