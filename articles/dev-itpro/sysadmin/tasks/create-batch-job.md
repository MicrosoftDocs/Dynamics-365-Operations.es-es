---
title: Crear un trabajo por lotes
description: Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbb844ebcf8d4b47b127132a5bf0ea45fa40f747
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "313368"
---
# <a name="create-a-batch-job"></a>Crear un trabajo por lotes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático. Los trabajos por lotes se ejecutan mediante las credenciales de seguridad del usuario que creó el trabajo. Realice el procedimiento siguiente para crear un trabajo por lotes. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-the-batch-job"></a>Crear el trabajo por lotes
1. Vaya Administración del sistema > Consultas > Trabajos por lotes.
2. Haga clic en Nuevo.
3. En el campo Descripción del trabajo, escriba un valor.
4. En el campo Fecha/hora de inicio programada, especifique una fecha y una hora.
5. Haga clic en Guardar.

## <a name="create-a-recurrence"></a>Crear una periodicidad
1. En el panel de acciones, haga clic en Trabajo por lotes.
2. Haga clic en Periodicidad.
    * Utilice estas opciones para especificar un intervalo y un patrón para la periodicidad.  
3. Haga clic en Aceptar

## <a name="add-alerts"></a>Agregar alertas
1. En el panel de acciones, haga clic en Trabajo por lotes.
2. Haga clic en Alertas.
    * Indique si desea que se envíen mensajes de alerta cuando finalice el trabajo por lotes, tenga un error o se cancele. A continuación, especifique si desea que las alertas se muestren como mensajes emergentes.   
3. Haga clic en Aceptar

