---
title: "Funciones de edición recién agregadas en Grabador de tareas"
description: "Si utiliza el Grabador de tareas para crear las guías de la tarea, puede editar los archivos de forma más eficaz mediante la funcionalidad descrita en este wiki."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Funciones de edición recién agregadas en Grabador de tareas

Si utiliza el Grabador de tareas para crear las guías de la tarea, puede editar los archivos de forma más eficaz mediante la funcionalidad descrita en este wiki.

Estas funciones están disponibles en ** registro &gt; de edición &gt; del Grabador de tareas desde los valores ** el menú.

-   Pasos de Insertar sin volver a registrar el archivo completo.
-   Mover los pasos bajo subtarea sin volver a registrar el archivo completo.
-   Contraer el nombre y los campos descripción del registro.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Inserte los pasos sin volver a registrar el archivo completo
Ahora puede agregar un paso en cualquier lugar de una guía de la tarea sin jugar posterior o volver a registrar el archivo completo.

1.  Permite seleccionar la etapa tras la cual desea que el paso nuevo que se insertará. Asegúrese de que el paso se resaltado.

Para que el Grabador de tareas inserte un paso, debe tener la página correcta abierto. La página es correcta la página en la que el nuevo aparece paso. El Grabador de tareas tiene un mecanismo que determine cuál es la página activa, y deshabilitar la funcionalidad si la página correcta no está abierto. 

![tg1 [] (. /media/tg1.png])(. /media/tg1.png) 


Cuando está en la página correcta, ** paso de Insertar ** disponible.

![tg2 [] (. /media/tg2-231x300.png])(. /media/tg2.png)

2. Haga clic en ** paso de Insertar **.

Al hacer clic en ** paso de Insertar **, cambiará Grabador de tareas el modo de registro. Cualquier acción permitida la interfaz de usuario ahora se registrará y agregó en contexto como pasos.

3. Haga clic en ** ** detención.

Es posible repetir el proceso, agregando tantos pasos o moviendo tantas subtareas según convenga (consulte abajo para las subtareas).

4. Al editar terminado la guía de la tarea, haga clic en ** edición de ** a continuación, elija una de las opciones de guardar o para publicar la guía de la tarea.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Mover los pasos bajo subtarea sin volver a registrar el archivo completo
Puede mover pasos en subtarea sin jugar posterior o volver a registrar el archivo completo. También puede mover el paso de la subtarea o el paso de la subtarea del final si desea agrupar un bloque existente de pasos.

1.  Permite seleccionar la etapa o el paso de la subtarea que desea mover. Asegúrese de que el paso se resaltado.
2.  Haga clic en el punto suspensivo, haga clic en ** mueva el paso después de **.

![tg3 [] (. /media/tg3.png])(. /media/tg3.png)

3. Permite seleccionar la etapa o el paso de la subtarea que desea mover el paso o el paso de la subtarea siguiente. El Grabador de tareas moverá el paso.

4. Para mover el paso de la subtarea del final, selecciónela, haga clic en el punto suspensivo clic **, mueva el paso después de **, y seleccione el paso tras la cual desea que el paso de la subtarea la finalización de ser.

Si desea que el primer paso en la guía de la tarea que se encuentra dentro de una subtarea, cree un paso de la como subtarea el segundo paso, y desplácelo el primer paso al. Puede agregar tantos o mover o subtareas pasos según sea necesario.

5. Al editar terminado la guía de la tarea, haga clic en ** edición de ** a continuación, elija una de las opciones de guardar o para publicar la guía de la tarea.

## <a name="collapse-recording-name-and-description"></a>Nombre y descripción del registro de hundimiento
Puede expandir y contraer ** nombre de registro y ** ** descripción del registro ** campos. Cuando estos campos están incurridos, más pasos serán visibles en el panel de edición del Grabador de tareas. 

![tg4 [] (. /media/tg4-300x252.png])(. /media/tg4.png)  

<a name="see-also"></a>Consulte también
--------

[Crear documentación o formación con las grabaciones de tareas](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[] Referencia rápida del Grabador de tareas (/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


