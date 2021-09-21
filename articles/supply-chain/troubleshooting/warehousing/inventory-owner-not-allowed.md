---
title: Propietario de inventario no permitido al procesar movimientos
description: Es posible que reciba el error "El propietario del inventario %1 no se permite". Los procesos de gestión de almacenes solo admiten el inventario que es propiedad de la entidad jurídica.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477500"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>Propietario de inventario no permitido al procesar movimientos en la aplicación de almacén

## <a name="symptoms"></a>Síntomas

Al procesar movimientos en la aplicación móvil Warehouse Management, puede recibir este mensaje de error:

> El propietario del inventario %1 no está permitido en este proceso.

## <a name="cause"></a>Causa

Esto sucede porque la dimensión de seguimiento **Propietario** falta cuando se utiliza la aplicación móvil Warehouse Management para realizar movimientos. Un diario de transferencia de inventario regular del cliente de Supply Chain Management parece funcionar según lo previsto y solo se puede registrar si la dimensión **Propietario** se completa.

## <a name="resolution"></a>Resolución

Microsoft ha evaluado este problema y ha determinado que es una limitación de funciones. Actualmente, los procesos de gestión de almacenes solo admiten el inventario que es propiedad de la entidad jurídica.
