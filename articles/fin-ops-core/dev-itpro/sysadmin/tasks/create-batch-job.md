---
title: Crear un trabajo por lotes
description: Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático.
author: maertenm
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76c6c68f7effad0c40282b22ea2a6bf991862cf5
ms.sourcegitcommit: d7d997ad84623ad952672411c0eb6740972ae0b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "7864182"
---
# <a name="create-a-batch-job"></a>Crear un trabajo por lotes

[!include [banner](../../includes/banner.md)]

Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático. Los trabajos por lotes se ejecutan mediante las credenciales de seguridad del usuario que creó el trabajo. Realice el procedimiento siguiente para crear un trabajo por lotes. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-the-batch-job"></a>Crear el trabajo por lotes
1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Consultas > Trabajos por lotes**.
2. Seleccione **Nuevo**.
3. En el campo **Descripción del trabajo**, especifique una descripción para el trabajo por lotes.
4. En el campo **Fecha/hora de inicio programadas**, ingrese la fecha y hora en que se debe ejecutar el trabajo por lotes.
5. Seleccione **Guardar**.

## <a name="create-a-recurrence"></a>Crear una periodicidad
1. En el panel de acciones, seleccione **Trabajo por lotes**.
2. Seleccione **Periodicidad**. Utilice estas opciones para especificar un intervalo y un patrón para la periodicidad.  
3. Seleccione **Aceptar**.

## <a name="add-alerts"></a>Agregar alertas
1. En el panel de acciones, seleccione **Trabajo por lotes**.
2. Seleccione **Alertas**. Indique si desea que se envíen mensajes de alerta cuando finalice el trabajo por lotes, tenga un error o se cancele. A continuación, especifique si desea que las alertas se muestren como mensajes emergentes.   
3. Seleccione **Aceptar**.

## <a name="add-a-task-to-a-batch-job"></a>Agregar una tarea a un trabajo por lotes
1.  En la página **Trabajo por lotes**, seleccione **Ver tareas**.
2.  Seleccione **Ctrl+N** para crear una tarea.
3.  Escriba una descripción para la tarea por lotes.
4.  En el campo **Cuentas de empresa**, seleccione la base de datos de la empresa en la que debe ejecutarse la tarea.
5.  En el campo **Nombre de clase**, seleccione el proceso en el que desea que se ejecute la tarea. 
6.  Si es necesario, seleccione un grupo de lotes para la tarea.

    Las tareas de cliente deben asignarse a un grupo de lotes. Se asignan automáticamente al grupo de lotes predeterminado (también conocido como grupo de lotes vacíos).

7.  Seleccione **Ctrl+S** para guardar la tarea.
8.  Para hacer que la tarea seleccionada dependa de otra tarea en el trabajo, seleccione la cuadrícula **Tiene condiciones** y luego siga estos pasos para cada condición que desee definir:

    1. Seleccione **Ctrl+N** para crear una condición.
    2. Seleccione el Id. de tarea de la tarea principal.
    3. Seleccione el estado que debe tener la tarea principal para que pueda ejecutarse la tarea dependiente.
    4. Seleccione **Ctrl+S** para guardar la condición.

    Si define más de una condición y deben cumplirse *todas* las condiciones para que pueda ejecutarse la tarea dependiente, seleccione el tipo de condición **Todo**. Si la tarea dependiente puede ejecutarse después de que se cumpla *cualquiera* de las condiciones, seleccione el tipo de condición **Cualquiera**.

9.  Seleccione cómo se deben manejar los errores de tareas. Para ignorar el fallo de una tarea específica, en la ficha **General**, seleccione la opción **Ignorar error de tarea** para esa tarea. Si se ha seleccionado esta opción, el fallo de tarea no provocará el fallo del trabajo. También puede utilizar el campo **Reintentos máximos** para especificar el número máximo de reintentos de una tarea para que se considere que se ha producido un fallo de tarea. Como práctica recomendada, le recomendamos que no configure el campo **Reintentos máximo** con un valor superior a **5**.

    Para obtener más información sobre reintentos de lotes, vea [Habilitar reintentos de lotes](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Ajustar estado del trabajo por lotes
1. Vaya **Administración del sistema > Consultas > Trabajos por lotes**.
2. Seleccione el trabajo por lotes adecuado.
3. En el panel de acciones, seleccione **Trabajo por lotes > Funciones > Cambiar estado**.
4. Seleccione el estado adecuado:
    - **Retenido**: establezca el trabajo por lotes como **retenido** para que se retenga del programador de trabajos por lotes. Equivalente a *detenido*.
    - **En espera**: establezca el trabajo por lotes como **en espera** para que quede a la espera de ser recogido por el programador de trabajos por lotes. Equivalente a *en marcha*.
5. Seleccione **Aceptar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
