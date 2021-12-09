---
title: Mejoras de rendimiento de limpieza del historial de ventas
description: Este tema describe la característica de mejoras de rendimiento de limpieza del historial de ventas y cómo habilitarla.
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
ms.openlocfilehash: 3dc36c8562f39a076bd4871524e2d132d1883d28
ms.sourcegitcommit: 8c17717b800c2649af573851ab640368af299981
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2021
ms.locfileid: "7860726"
---
# <a name="saleshistorycleanupperformanceimprovements"></a>Mejoras de rendimiento de limpieza del historial de ventas

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)] 
<!-- KFM: Preview until GA with 10.0.24 -->

El trabajo por lotes periódico **Limpieza del historial de ventas** puede llevar mucho tiempo si se ejecuta con poca frecuencia en entornos con un gran volumen de actualizaciones de ventas. En estas situaciones, la característica *Mejoras en el rendimiento de la limpieza del historial de ventas* puede ayudar a reducir la duración de la ejecución y mejorar la fiabilidad.

La característica mejora el trabajo de limpieza existente de las siguientes formas:

- Divide la limpieza en lotes (puede cambiar el tamaño del lote mediante personalizaciones).
- Se ejecutará durante un máximo de 2 horas (puede cambiar la duración mediante personalizaciones).
- Siempre que sea posible, aprovechará las capacidades de la base de datos para minimizar el bloqueo y evitar unir tablas transaccionales durante la limpieza.

Después de habilitar la característica, el trabajo por lotes **Limpieza del historial de actualizaciones de ventas** (**Ventas y marketing \> Tareas periódicas \> Limpiar \> Limpieza del historial de actualizaciones de ventas**) funcionará como antes, pero con un mejor rendimiento y durante un máximo de 2 horas. Esto significa que es posible que deba ejecutarse varias veces para limpiar todos los datos durante un periodo de tiempo de retención específico.

## <a name="turn-on-the-saleshistorycleanupperformanceimprovements-feature"></a>Activar la característica de mejoras en el rendimiento de la limpieza del historial de ventas

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Ventas y marketing*
- **Nombre de la característica:** *Mejoras en el rendimiento de la limpieza del historial de ventas*
