---
title: Sincronizar la capacidad de recursos
description: Este tema proporciona información sobre cómo sincronizar la capacidad de un recurso en calendarios y proyectos.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760652"
---
# <a name="synchronize-resource-capacity"></a>Sincronizar la capacidad de recursos

[!include [banner](../includes/banner.md)]

Los procesos para la sincronización de recursos ayudan a garantizar que la información del calendario y del calendario de base se integren lentamente en la programación de recursos del proyecto. Si se modifica el calendario, los procesos realizan las actualizaciones necesarias a la programación de recursos del proyecto. Igualmente, los procesos también le permitirán mejorar el rendimiento, ya que la información de recursos del calendario se sincroniza previamente. Por lo tanto, verá con más frecuencia actualizaciones de información con la programación de recursos. Se recomienda la programación de los procesos como lote en lugar de uno cada vez. De no ser así, existe el riesgo de que alguien olvidará las fechas inclusivas en las que la información se sincronizó por última vez. Si no se usan fechas inclusivas, pueden producir huecos durante la sincronización de fecha.

![Sincronización de calendario](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Sincronizar acumulaciones de capacidad de recursos

El proceso de sincronización está diseñado para sincronizar toda la información del calendario de recursos. Esta información incluye la información del calendario base sobre los cambios realizados en la tabla de la capacidad del calendario de recursos del proyecto. Si se agregan nuevos recursos en el proyecto, la sincronización ayuda a garantizar que la información actualizada del calendario está disponible. Esta sincronización se puede realizar en cualquier momento.

Recomendamos que use un lote. Las opciones están disponibles durante la sincronización de reservas de capacidades.

1. Seleccione **Administración de proyectos y contabilidad** &gt; **Periódico** &gt; **Sincronización de capacidad** &gt; **Sincronizar acumulaciones de capacidad de recursos**.
2. Configure las opciones de la siguiente tabla.

    | Opción      | Descripción |
    |-------------|-------------|
    | Código del período | De forma opcional, puede seleccionar el código del intervalo de fechas del libro de contabilidad general para establecer las fechas inicial y final del proceso de sincronización de la acumulación de capacidad de recursos. |
    | Fecha de inicio  | Especifique la fecha inicial del proceso de sincronización de acumulación de capacidad de recursos. |
    | Fecha de finalización    | Especifique la fecha final del proceso de sincronización de acumulación de capacidad de recursos. |

[![Proceso de sincronización](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
