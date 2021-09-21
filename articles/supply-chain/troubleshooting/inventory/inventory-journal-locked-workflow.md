---
title: Su diario de inventario está bloqueado y el trabajo por lotes del flujo de trabajo no funciona
description: Uno de sus diarios de inventario está bloqueado por alguna operación y no se libera
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
ms.openlocfilehash: 8b21ec2e2b3b8546dcb138422c5540053392c179
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477497"
---
# <a name="your-inventory-journal-is-locked-and-the-workflow-batch-job-doesnt-work"></a>Su diario de inventario está bloqueado y el trabajo por lotes del flujo de trabajo no funciona

## <a name="symptoms"></a>Síntomas

Uno de sus diarios de inventario está bloqueado por alguna operación y no se libera. Por ejemplo, si se produce un error desconocido durante la publicación (que es una operación de bloqueo del sistema), el diario puede permanecer en estado de bloqueado por el sistema. En este caso, el controlador de elementos de trabajo de flujo de trabajo generará un error mientras bloquea la validación.

## <a name="resolution"></a>Resolución

Inicie sesión en la instancia de SQL Server para Supply Chain Management y compruebe si **InventJournalTable.SystemBlocked** se establece en *1*. Si es así, asegúrese de que el diario no esté en estado bloqueado y luego restablezca **InventJournalTable.SystemBlocked** en *0*.
