---
title: El pedido de producción planificado se debe programar para poder ser firmado
description: Cuando intenta reafirmar un pedido planificado, recibe un mensaje de error que indica que el pedido debe programarse antes de que pueda reafirmarse.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a360cb3cbd26e1bc1ebb1baf1a6a4d8282c28c5c
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294177"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>El pedido de producción planificado se debe programar para poder ser firmado

Código de error: SYS309802

## <a name="symptoms"></a>Síntomas

Cuando intenta confirmar un pedido planificado, recibe el siguiente mensaje de error:

> El pedido de producción planificado se debe programar para poder ser firmado.

## <a name="cause"></a>Causa

Las fechas de inicio y finalización programadas no pueden estar en blanco.

## <a name="resolution"></a>Resolución

Para especificar las fechas de inicio y finalización de la orden planificada, siga estos pasos.

1. Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**.
1. Abra el pedido planificado pertinente.
1. Sobre la ficha desplegable **General**, en la sección **Programado**, especifique las fechas en los campos **Fecha de inicio** y **Fecha final**.
