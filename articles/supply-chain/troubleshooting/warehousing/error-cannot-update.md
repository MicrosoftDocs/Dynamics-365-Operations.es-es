---
title: Se produce un error cuando se selecciona la ubicación durante el registro de la lista de selección
description: Se produce un error cuando se selecciona la ubicación durante el registro de la lista de selección.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: da5905fb7ed1e890c85e891843379aa07de3279bd8972d6fc57136aa703c9ea4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762803"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a>Se produce un error cuando se selecciona la ubicación durante el registro de la lista de selección

Número de KB: 4613106

## <a name="symptoms"></a>Síntomas

Este problema ocurre cuando su sistema está configurado para reservar automáticamente pedidos de ventas. Si intenta seleccionar la ubicación para una línea de registro de la lista de selección, recibirá el siguiente mensaje de error cuando utilice los procesos de reserva de gestión de almacenes (WMS):

> No se puede actualizar la cantidad con nuevas dimensiones

Este problema puede ocurrir porque no tiene suficiente inventario disponible en una ubicación específica.

## <a name="resolution"></a>Resolución

El sistema se está comportando según lo diseñado.

En situaciones en las que usa el proceso de reserva a nivel de almacén, si el inventario disponible no se reserva en todos los niveles de dimensión de inventario y no tiene suficiente inventario disponible en una ubicación específica, le recomendamos que utilice el proceso de reserva manual desde la línea de selección. A continuación, puede utilizar la función *Reservar lote* para distribuir las reservas más bajas, como la ubicación, para todas las cantidades disponibles.
