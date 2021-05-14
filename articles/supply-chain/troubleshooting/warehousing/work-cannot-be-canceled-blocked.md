---
title: El trabajo no se puede cancelar porque está bloqueado
description: El trabajo no se puede cancelar porque está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924288"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a>El trabajo no se puede cancelar porque está bloqueado

Código de error: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> El trabajo %1 no se puede cancelar porque está bloqueado por el tipo de motivo %2. El trabajo debe desbloquearse para poderlo cancelar.

## <a name="cause"></a>Causa

El trabajo está bloqueado y no se puede cancelar.

En la página **Trabajo**, en la pestaña **General**, la opción **Bloqueado** está configurada en *Sí*. Esta configuración indica que el trabajo está bloqueado. La pestaña **Motivos de bloqueo** muestra por qué se bloqueó el trabajo.

## <a name="resolution"></a>Resolución

Para desbloquear el trabajo, seleccione la pestaña **Motivos de bloqueo**, y luego siga uno de estos pasos:

- Si el campo **Motivo de bloqueo del trabajo** está configurado en *Razón indefinida*: en el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Desbloquear trabajo**.
- Si el campo **Motivo de bloqueo del trabajo** está establecido en *Procesamiento de lanzamiento*: en el panel de acciones, en la pestaña **Información relacionada**, en el grupo **Información relacionada**, seleccione **Lanzamiento**. Luego, en la página **Lanzamientos**, en el panel de acciones, en la pestaña **Lanzamiento**, en el grupo **Lanzamiento**, seleccione **Limpiar datos de lanzamiento**.

## <a name="workaround"></a>Solución alternativa

Si los pasos anteriores no solucionaron el problema, puede cancelar el trabajo siguiendo estos pasos.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar, y que actualmente tiene un valor de **Estado del trabajo** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.

Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).
