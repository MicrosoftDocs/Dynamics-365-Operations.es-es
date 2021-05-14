---
title: El trabajo permanece bloqueado
description: El trabajo permanece bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924139"
---
# <a name="work-remains-blocked"></a>El trabajo permanece bloqueado

Código de error: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> El trabajo %1 permanece bloqueado porque el lanzamiento relacionado %2 tiene el estado %3.

## <a name="cause"></a>Causa

El trabajo se está procesando actualmente en un lanzamiento y no puede desbloquearse, como lo indica una de las siguientes condiciones:

- En la pestaña **Motivos de bloqueo** el campo **Motivo de bloqueo del trabajo** para una o más líneas está establecido en *Lanzamiento de procesamiento*.
- Cuando selecciona **Lanzamiento** en el grupo **Información relacionada** de la pestaña **Información relacionada** del panel de acciones, el campo **Estado de lanzamiento** se establece en *Procesamiento*.

## <a name="resolution"></a>Resolución

En el panel de acciones, en la ficha **Información relacionada** del grupo **Información relacionada**, seleccione **Lanzamiento**. Luego, en la página **Lanzamientos**, en el panel de acciones, en la pestaña **Lanzamiento**, en el grupo **Lanzamiento**, seleccione **Limpiar datos de lanzamiento**.

## <a name="workaround"></a>Solución alternativa

Si los pasos anteriores no solucionaron el problema, puede cancelar el trabajo siguiendo estos pasos.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar, y que actualmente tiene un valor de **Estado del trabajo** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.

Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).
