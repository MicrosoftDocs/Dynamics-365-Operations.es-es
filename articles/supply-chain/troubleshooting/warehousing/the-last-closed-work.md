---
title: La última línea de trabajo cerrada debe ser una colocación
description: La última línea de trabajo cerrada debe ser una colocación
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
ms.openlocfilehash: bbc5797df2b7465b36ec5ea546a67441626daeb1c72f82dfca4eb7db3503b713
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760283"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>La última línea de trabajo cerrada debe ser una colocación

Código de error: WAX1285

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> La última línea de trabajo cerrada debe ser una colocación.

## <a name="cause"></a>Causa

El trabajo no se puede cancelar en su estado actual.

En la última línea de trabajo, el campo **Estado de trabajo** está configurado en *Cerrado*, pero el campo **Tipo de trabajo** no está configurado en *Colocar*.

## <a name="resolution"></a>Resolución

Para cancelar el trabajo, siga estos pasos.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.

Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).
