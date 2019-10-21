---
title: Crear evaluaciones del rendimiento
description: Este tema explica cómo crear una revisión de rendimiento y describe el propósito de cada sección de la revisión.
author: andreabichsel
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3583f974d1768e0efefb80f0ad8aa011669c1301
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179888"
---
# <a name="create-performance-reviews"></a>Crear evaluaciones del rendimiento

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tema explica cómo crear una revisión de rendimiento y describe el propósito de cada sección de la revisión. Este procedimiento se creó con los datos de demostración de la empresa USMF.

1. En la página principal, seleccione el espacio de trabajo **Autoservicio para empleados**.
2. Seleccione **Nueva revisión** para crear una revisión nueva.
3. En el campo **Tipo de revisión**, especifique o seleccione un valor.
4. En el campo **Período de rendimiento**, especifique o seleccione un valor.
5. En el campo **Fecha final**, especifique una fecha.
6. Seleccione **Aceptar**. También podrá crear una revisión a partir de una plantilla. Esta es la mejor manera de crear una revisión porque cada sección contendrá la información necesaria para iniciar una revisión.  
7. Puede mostrar u ocultar las fichas como la ficha de los datos adjuntos:

    1. En el panel de acciones, seleccione **Mostrar secciones** para abrir el diálogo desplegable.
    1. Seleccione **Sí** o **No** en el campo **Mostrar datos adjuntos** para mostrar u ocultar la ficha de datos adjuntos.
    1. Seleccione **Guardar**.

8. Seleccione **Agregar objetivo a la revisión** para agregar un objetivo. Cuando haya terminado, seleccione **Aceptar**.
9. Seleccione **Agregar competencia** para abrir el cuadro desplegable.
10. En el campo **Título**, escriba un valor.
11. En el campo **Descripción**, escriba `Increase customer skills by working with the support team`.
12. Seleccione **Aceptar**.
13. Seleccione **Contraer todo**.
14. Seleccione **Expandir todo**.
15. Seleccione **Agregar comentario**.
16. Seleccione **Registrar**.
17. Seleccione la pestaña **Medidas**.
18. Seleccione **Agregar medida** para abrir el cuadro desplegable.
19. En el campo **Medida**, especifique o seleccione un valor.
26. En el campo **Importe objetivo**, especifique un número.
20. Seleccione **Aceptar**.
21. Seleccione la pestaña **Actividades**.
22. Seleccione **Agregar**.
23. En el campo **Título**, escriba un valor.
24. En el campo **Descripción**, escriba un valor.
25. En el campo **Fecha inicial**, especifique una fecha.
26. En el campo **Fecha de finalización**, escriba una fecha.
27. Seleccione **Sí** en el campo **Plan de desarrollo**.
28. En el campo **Palabras clave**, escriba un valor.
29. Seleccione **Guardar**.
30. Seleccionar la pestaña **Calificaciones**.  

    - La ficha desplegable de **detalles de la valoración** permite a los empleados autoevaluarse y que el responsable evalúe al empleado. Si se utilizan ponderaciones, el valor ponderado de las puntuaciones se calculará automáticamente.  
    - Para ver esta sección, habilite la configuración de parámetros para mostrar valoraciones del empleado.  

31. Seleccione la ficha **Aprobaciones**. Si la revisión utiliza flujos de trabajo, entonces las aprobaciones aparecerán después de completar el flujo de trabajo. Si no se usa ningún flujo de trabajo, aquí aparecerán el trabajador y el responsable. La casilla necesaria se selecciona en función de los valores del tipo de revisión.  
32. Seleccione la ficha **General**.

    - El período de rendimiento crea las fechas inicial y final predeterminadas. Estas fechas se pueden editar.  
    - Los estados controlan el acceso a la revisión. El estado **No iniciada** permite a todo el mundo editar la revisión. El estado **En curso** solo permite que el empleado vea y edite la revisión. Listo para revisión permite que sólo el responsable vea y edite la revisión. El estado Revisión final permite que el empleado y el responsable vean la revisión y también la editen si se configura en el tipo de revisión. Los estados **Completada**, **Rechazada** y **Cancelada** convierten la revisión en de sólo lectura.  

33. En el campo **Visión general**, escriba un valor.
34. Seleccione la ficha **Revisión**. A medida que la revisión pasa por los estados, el empleado y el responsable pueden agregar comentarios para cada objetivo o competencia.  
35. Seleccione la pestaña **Aprobaciones** . El trabajador y el administrador podrán aprobar la revisión. Una vez efectuadas todas las aprobaciones necesarias, el estado cambiará a **Completada** y no podrán hacerse más cambios.  

