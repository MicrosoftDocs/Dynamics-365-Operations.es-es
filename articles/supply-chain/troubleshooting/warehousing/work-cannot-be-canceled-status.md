---
title: El trabajo no se puede cancelar debido a su estado
description: El trabajo no se puede cancelar debido a su estado
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
ms.openlocfilehash: f983501b490c5516525b4d5904603ed62e8799f9e6124e5672b36a12804ecb0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755987"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a>El trabajo no se puede cancelar debido a su estado

Código de error: WAX2190

## <a name="symptoms"></a>Síntomas

El sistema muestra el siguiente mensaje de error:

> No se puede cancelar el trabajo %1 porque su estado es %2.

## <a name="cause"></a>Causa

El trabajo no se puede cancelar en su estado actual.

El encabezado del trabajo o las líneas del trabajo no tienen el valor de **Estado del trabajo** esperado. El campo **Estado del trabajo** del encabezado del trabajo no está configurado como *Abierto* ni como *En curso*.

## <a name="resolution"></a>Resolución

Para cancelar el trabajo, siga estos pasos.

1. Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.
1. En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.
1. Seleccione **Aceptar**.
1. Seleccione **Sí** para confirmar que desea cancelar el trabajo.

Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).
