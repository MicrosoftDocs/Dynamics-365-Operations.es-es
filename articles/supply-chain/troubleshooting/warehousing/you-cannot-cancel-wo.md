---
title: No puede cancelar el trabajo de un usuario
description: No puede cancelar el trabajo de un usuario
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924410"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a>No puede cancelar el trabajo de un usuario

Código de error: WAX708

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> No se puede cancelar el trabajo asignado a un usuario.

## <a name="cause"></a>Causa

El trabajo está bloqueado por un usuario y no se puede cancelar. Para confirmar esto, abra el id. de trabajo y luego abra la pestaña **General**. Si el trabajo está bloqueado, el campo **Situación laboral** se establecerá en *En curso*, y el campo **Bloqueado por** se establecerá en un id. de usuario.

## <a name="resolution"></a>Resolución

Para cancelar el trabajo, siga estos pasos.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.

Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).
