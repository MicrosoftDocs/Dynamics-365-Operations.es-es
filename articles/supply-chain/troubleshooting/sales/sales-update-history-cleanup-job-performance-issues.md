---
title: El trabajo de limpieza del historial de actualización de ventas falla o tiene problemas de rendimiento
description: El trabajo por lotes de limpieza del historial de ventas puede fallar o tardar mucho si hay una gran cantidad de datos de actualización de ventas.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 4f04dc204c705b40ed25fadc75118feaef4d6b6e
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641481"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>El trabajo de limpieza del historial de actualización de ventas falla o tiene problemas de rendimiento

## <a name="symptoms"></a>Síntomas

El trabajo por lotes de **Limpieza del historial de actualización de ventas** falla o tiene problemas de rendimiento.  

## <a name="cause"></a>Causa

Esto puede ocurrir cuando su sistema incluye una gran cantidad de actualizaciones de ventas, lo que puede resultar en una gran cantidad de datos de actualización de ventas. El trabajo de limpieza intenta limpiar todos estos datos en una transacción. Como resultado, el trabajo puede tardar mucho en ejecutarse o incluso fallar.

## <a name="resolution"></a>Resolución

Una nueva versión del trabajo por lotes **Limpieza del historial de actualizaciones de ventas** está disponible para Supply Chain Management, versión 10.0.19 y superior. Esta característica no está habilidata de forma predeterminada. Para obtener detalles sobre cómo funciona y cómo habilitarla en la administración de características, consulte [Mejoras en el rendimiento de la limpieza del historial de ventas](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

