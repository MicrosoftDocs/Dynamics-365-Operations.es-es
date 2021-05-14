---
title: El trabajo no está bloqueado
description: El trabajo no está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924213"
---
# <a name="work-isnt-blocked"></a>El trabajo no está bloqueado

Código de error: WHSUnblockNotBlockedWorkErrorMessage

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> El trabajo con id. %1 no está bloqueado.

## <a name="cause"></a>Causa

La opción **Lanzamiento bloqueado** del lanzamiento está configurada en *No*. El trabajo no se puede desbloquear porque no está bloqueado actualmente.

## <a name="resolution"></a>Resolución

 Trabaje solo cuando la opción **Lanzamiento bloqueado** está configurada en *Sí* y se puede desbloquear.
