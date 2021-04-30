---
title: Usar flujos de trabajo de aprobación de arrendamiento
description: Este tema explica cómo utilizar los flujos de trabajo para aprobar arrendamientos de activos y cómo realizar un seguimiento del estado y el historial de los flujos de trabajo.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b4926ee45841c9fdd5a3cf7d12452e1f06d868c6
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880723"
---
# <a name="use-lease-approval-workflows"></a>Usar flujos de trabajo de aprobación de arrendamiento

[!include [banner](../includes/banner.md)]

Este tema explica cómo utilizar los flujos de trabajo para aprobar arrendamientos de activos y cómo realizar un seguimiento del estado y el historial de los flujos de trabajo. Los flujos de trabajo ayudan a dar coherencia a la gestión de las aprobaciones de arrendamientos al proporcionar un conjunto estándar de pasos de aprobación y asignar usuarios específicos que aprueban cada paso del proceso. Un aprobador puede aprobar un arrendamiento, rechazarlo, solicitar un cambio o asignarlo a otro usuario para su aprobación. Los flujos de trabajo también pueden brindar más visibilidad al proceso de aprobación al permitirle rastrear su estado e historial. Además, puede ver una lista de trabajo centralizada que enumera las tareas y aprobaciones asignadas a aprobadores específicos.

Antes de utilizar este procedimiento, asegúrese de que se haya creado al menos un flujo de trabajo de aprobación de arrendamiento. Si no existe ningún flujo de trabajo, cree uno. Para obtener información sobre cómo configurar un flujo de trabajo, consulte [Configurar flujos de trabajo de aprobación de arrendamiento](set-up-lease-wrkflw.md).

1. Envíe un arrendamiento para su aprobación. En la página **Detalles del libro** del arrendamiento, seleccione **Flujo de trabajo** y luego seleccione **Enviar**.
2. En el cuadro de diálogo que aparece, puede agregar un comentario. El aprobador designado verá este comentario junto con el arrendamiento. Cuando haya terminado de introducir el comentario, seleccione **Enviar**. El arrendamiento se envía al sistema de flujo de trabajo y el aprobador lo recibe para su aprobación.
3. Para ver los arrendamientos que están designados para aprobación, vaya a **Módulos \> Común \> Elementos de trabajo \> Elementos de trabajo asignados a mí**.
4. En la página **Elementos de trabajo asignados a mí**, seleccione el vínculo **Id. de arrendamiento** para el arrendamiento que desea ver. La página que aparece depende de los libros de arrendamiento y los detalles de arrendamiento a los que tiene acceso.
5. Cuando haya terminado de ver el arrendamiento, seleccione **Flujo de trabajo** y decida qué acción se debe tomar. Las opciones incluyen **Aprobar**, **Rechazado**, **Solicitar cambio**, **Delegar** y **Cancelado**. También puede seleccionar **Ver historial** para ver el historial de aprobaciones del arrendamiento seleccionado.
6. Después de haber seleccionado una acción, introduzca un comentario para describir la acción. Cuando haya terminado de introducir el comentario, seleccione la acción **Aprobado** en la lista.
7. Para ver las acciones de aprobación, vuelva a la paágina **Detalles del arrendamiento** de la página **Resumen de arrendamiento** y luego seleccione **Flujo de trabajo \> Ver historial**.

    Puede ver las actividades del flujo de trabajo en la página **Historial de flujo de trabajo**. Esta página muestra los pasos del flujo de trabajo que se han realizado en el arrendamiento específico. También puede utilizar el campo **Elementos de trabajo** para ver el estado de los elementos de trabajo asignados.

8. Para detener un flujo de trabajo, en la página **Historial de flujo de trabajo**, seleccione **Recuperar**. En el cuadro de diálogo que aparece, introduzca un comentario y luego seleccione **Aceptar**.
9. Para desactivar un flujo de trabajo o para activar un flujo de trabajo creado previamente, vaya a **Arrendamiento de activos \> Configurar \> Flujo de trabajo de arrendamiento**. Entonces, en la página **Flujo de trabajo de arrendamiento**, seleccione **Flujo de trabajo \> Versiones**. Para dejar inactivo un flujo de trabajo actual, seleccione el arrendamiento activo en el cuadro de diálogo de versión de arrendamiento y, a continuación, seleccione **Dejar inactivo**. Para activar un flujo de trabajo existente, seleccione el flujo de trabajo y luego seleccione **Activar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
