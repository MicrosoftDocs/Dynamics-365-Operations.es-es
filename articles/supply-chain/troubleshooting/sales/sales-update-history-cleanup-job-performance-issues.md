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
ms.openlocfilehash: 124fb90ecafd4f4cccbd8a8bb443694c95365732
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570354"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>El trabajo de limpieza del historial de actualización de ventas falla o tiene problemas de rendimiento

## <a name="symptoms"></a>Síntomas

El trabajo por lotes de **Limpieza del historial de actualización de ventas** falla o tiene problemas de rendimiento.  

## <a name="cause"></a>Causa

Esto puede ocurrir cuando su sistema incluye una gran cantidad de actualizaciones de ventas, lo que puede resultar en una gran cantidad de datos de actualización de ventas. El trabajo de limpieza intenta limpiar todos estos datos en una transacción. Como resultado, el trabajo puede tardar mucho en ejecutarse o incluso fallar.

## <a name="resolution"></a>Resolución

Una nueva versión del trabajo por lotes **Limpieza del historial de actualizaciones de ventas** está disponible para Supply Chain Management, versión 10.0.19 y superior. Esta característica no está activada de forma predeterminada. Para obtener detalles sobre cómo funciona y cómo habilitarla en la administración de características, consulte [Programar la limpieza de datos del historial de ventas](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

