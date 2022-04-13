---
title: El flujo de trabajo del diario de inventario nunca se completa y el diario no se puede procesar
description: Después de enviar un flujo de trabajo de aprobación de diario, el procesamiento del flujo de trabajo deja de responder y no puede editar ni procesar sus diarios.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 5e8168a20a1fa4f52d28129eebb9931b31157ced
ms.sourcegitcommit: ab690bc897699ff8a4c489e749251fe0367050ca
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2022
ms.locfileid: "8488978"
---
# <a name="inventory-journal-workflow-never-completes-and-the-journal-cant-be-processed"></a>El flujo de trabajo del diario de inventario nunca se completa y el diario no se puede procesar

## <a name="symptoms"></a>Síntomas

Después de enviar un flujo de trabajo de aprobación de diario, el procesamiento del flujo de trabajo deja de responder y no puede editar ni procesar sus diarios.

## <a name="resolution"></a>Resolución

Hay varias razones por las que es posible que no se complete el procesamiento del flujo de trabajo. Compruebe los siguientes problemas:

- Vaya a **Gestión de inventarios &gt; Configuración &gt; Flujos de trabajo de gestión de inventario**, y revise la configuración del flujo de trabajo afectado. Para obtener más información, consulte [Flujos de trabajo de aprobación de diario de inventario](../../inventory/inventory-journal-workflow.md).
- Es posible que el flujo de trabajo encuentre una excepción o un error. Revise el historial de elementos de trabajo del flujo de trabajo afectado para ver si incluye un error de aplicación que finaliza el flujo de trabajo.
- El diario de inventario se puede actualizar o editar solo si está aprobado. Si la recuperación está activa, puede intentar recuperar el diario. La ejecución del trabajo por lotes del flujo de trabajo puede suspenderse por varios motivos. Algunas de estas razones pueden deberse al problema del marco del flujo de trabajo.
