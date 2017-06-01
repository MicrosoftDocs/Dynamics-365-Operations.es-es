---
title: "Funciones de edición recién agregadas en Grabador de tareas"
description: "Si utiliza el Grabador de tareas para crear guías de tareas, puede editar los archivos de forma más eficaz mediante la funcionalidad descrita en este tema."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 272856c01074a352e3945f29e9cdf7655aaf22ba
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Funciones de edición recién agregadas en Grabador de tareas

[!include[banner](../includes/banner.md)]


Si utiliza el Grabador de tareas para crear guías de tareas, puede editar los archivos de forma más eficaz mediante la funcionalidad descrita en este tema.

Estas funciones están disponibles en el menú **Configuración &gt; Grabación de tareas &gt; Editar grabación**.

-   Insertar pasos sin volver a grabar el archivo completo.
-   Mover los pasos bajo una subtarea sin volver a grabar el archivo completo.
-   Contraer los campos Nombre y descripción de la grabación.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Insertar pasos sin volver a grabar el archivo completo.
Ahora puede agregar un paso en cualquier lugar de una guía de tareas sin reproducir o volver a grabar el archivo completo.

1.  Seleccione el paso después del cual desea que se inserte el nuevo paso. Asegúrese de que el paso está resaltado.

Para que el Grabador de tareas inserte un paso, debe tener abierta la página correcta. La página correcta es la página en la que se produce el nuevo paso. El Grabador de tareas tiene un mecanismo que determina cuál es la página activa y deshabilitará la funcionalidad si no está abierta la página correcta. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Cuando se encuentre en la página correcta, **Insertar paso** estará disponible.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Haga clic en **Insertar paso**.

Al hacer clic en **Insertar paso**, el Grabador de tareas cambia al modo de grabación. Cualquier acción realizada en la IU se grabará ahora y agregará de forma local como pasos.

3. Haga clic en **Detener**.

Puede repetir el proceso, agregando tantos pasos o moviendo tantas subtareas según sea necesario (vea más abajo para las subtareas).

4. Cuando haya acabado de editar la guía de tareas, haga clic en **Edición realizada** y, a continuación, elija una de las opciones para guardar o publicar la guía de tareas.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Mover los pasos bajo una subtarea sin volver a grabar el archivo completo.
Puede mover los pasos bajo una subtarea sin reproducir o volver a grabar el archivo completo. También puede mover el paso de la subtarea o el paso de la subtarea final si desea agrupar un bloque existente de pasos.

1.  Seleccione el paso o el paso de la subtarea que desea mover. Asegúrese de que el paso está resaltado.
2.  Haga clic en el botón de elipsis y luego haga clic en **Mover paso después de**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Seleccione el paso o el paso de la subtarea que desea para mover después el paso o el paso de la subtarea. El Grabador de tareas moverá el paso.

4. Para mover el paso de la subtarea final, selecciónela, haga clic en **Mover paso después de** y luego seleccione el paso tras el cual desea que esté el paso de la subtarea.

Si desea introducir el primer paso de la guía de tareas en una subtarea, cree un paso de subtarea como segunda subtarea y luego mueva el primer paso dentro de esta. Puede agregar o mover tantos pasos o subtareas como crea necesario.

5. Cuando haya acabado de editar la guía de tareas, haga clic en **Edición realizada** y, a continuación, elija una de las opciones para guardar o publicar la guía de tareas.

## <a name="collapse-recording-name-and-description"></a>Contraer Nombre y descripción de la grabación.
Puede expandir y contraer los campos **Nombre de la grabación** y **Descripción de la grabación**. Al contraer estos campos, aparecerán más pasos en el panel de edición del Grabador de tareas. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Consulte también
--------

[Crear documentación o formación con las grabaciones de tareas](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Referencia rápida del Grabador de tareas](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)




