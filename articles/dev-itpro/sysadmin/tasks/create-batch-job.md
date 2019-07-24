---
title: Crear un trabajo por lotes
description: Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
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
ms.openlocfilehash: d211dcd7cb47df135d395d2a993429746aa35a85
ms.sourcegitcommit: 6ba4006fb6a67ddd4b1e54e3d62b9d1239b5e5a3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "1700850"
---
# <a name="create-a-batch-job"></a>Crear un trabajo por lotes

[!include [task guide banner](../../includes/task-guide-banner.md)]

Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático. Los trabajos por lotes se ejecutan mediante las credenciales de seguridad del usuario que creó el trabajo. Realice el procedimiento siguiente para crear un trabajo por lotes. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-the-batch-job"></a>Crear el trabajo por lotes
1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Consultas > Trabajos por lotes**.
2. Haga clic en **Nuevo**.
3. En el campo **Descripción del trabajo**, escriba un valor.
4. En el campo **Fecha/hora de inicio programada**, especifique una fecha y una hora.
5. Haga clic en **Guardar**.

## <a name="create-a-recurrence"></a>Crear una periodicidad
1. En el panel de acciones, haga clic en **Trabajo por lotes**.
2. Haga clic en **Periodicidad**. Utilice estas opciones para especificar un intervalo y un patrón para la periodicidad.  
3. Haga clic en **Aceptar**.

## <a name="add-alerts"></a>Agregar alertas
1. En el panel de acciones, haga clic en **Trabajo por lotes**.
2. Haga clic en **Alertas**. Indique si desea que se envíen mensajes de alerta cuando finalice el trabajo por lotes, tenga un error o se cancele. A continuación, especifique si desea que las alertas se muestren como mensajes emergentes.   
3. Haga clic en **Aceptar**.

## <a name="adjust-batch-job-status"></a>Ajustar estado del trabajo por lotes
1. Vaya **Administración del sistema > Consultas > Trabajos por lotes**.
2. Seleccione el trabajo por lotes adecuado.
3. En el panel de acciones, haga clic en **Trabajo por lotes > Funciones > Cambiar estado**.
4. Seleccione el estado adecuado:
    - **Retenido**: establezca el trabajo por lotes como **retenido** para que se retenga del programador de trabajos por lotes. Equivalente a *detenido*.
    - **En espera**: establezca el trabajo por lotes como **en espera** para que quede a la espera de ser recogido por el programador de trabajos por lotes. Equivalente a *en marcha*.
5. Haga clic en **Aceptar**.
