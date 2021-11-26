---
title: Mantener la información de lesiones y enfermedades del empleado
description: Esta tarea describe cómo crear un caso de lesión o enfermedad.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7c351919616c8ab5cf15d14c6cc79a5097e248fc
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771264"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Mantener la información de lesiones y enfermedades del empleado

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Se recomienda completar primero la guía de tareas "Configuración de lesión o enfermedad", puesto que aquí se usa parte de la información de configuración. 



Esta grabación de tareas cubre los pasos básicos para crear un caso de lesión o enfermedad. Además de los detalles de la lesión o enfermedad, se realiza un seguimiento del estado de un caso. De forma predeterminada, los casos tienen un estado de **Abierto**. Puede administrar el estado usando el elemento de menú **Estado del caso** en la parte superior de la página.

1. Vaya a **Recursos humanos \> Trabajadores \> Lesiones y enfermedades \> Incidentes de lesiones o enfermedad**.
2. Seleccione **Nuevo**.
3. En el campo **Descripción del caso**, indique un valor (por ejemplo, **Lesión de muñeca**).
4. En el campo **Trabajador**, escriba o seleccione un valor (por ejemplo, **Ana Bowman**).
5. En el campo **Fecha y hora del incidente**, ingrese una fecha y hora (por ejemplo, 20 de enero de 2016, a las 10:00 a. m.).
6. En el campo **Tipo de lesión o enfermedad**, especifique o seleccione un valor (por ejemplo, **Fractura**).
7. En el campo **Parte del cuerpo**, especifique o seleccione un valor (por ejemplo, **Muñeca**).
8. En el campo **Tipo de resultado**, especifique o seleccione un valor (por ejemplo, **Terapia**).
9. En el campo **Fecha y hora informadas**, especifique una fecha y una hora.

    La fecha y hora notificadas deben ser posteriores a la fecha y hora del incidente.

10. En el campo **Persona que informó del caso**, escriba o seleccione un valor (por ejemplo, **Ana Bowman**).

    La persona especificada podría ser el empleado u otro testigo del incidente.

11. En la sección **Incidente**, en el campo **Donde ocurrió el incidente**, ingrese un valor (por ejemplo, **Depósito**).
12. En el campo **En el sitio de trabajo**, seleccione **Sí** si el incidente ocurrió en el local de trabajo.
13. En el campo **Fecha y hora de inicio laboral**, ingrese la fecha y hora en que la persona afectada comenzó a trabajar antes de que ocurriera el incidente.
14. En el campo **Trabajo o tarea del empleado**, ingrese el trabajo o tarea que el trabajador estaba realizando cuando ocurrió el incidente (por ejemplo, **Cargando cajas**). 
15. En el campo **Causa del incidente**, ingrese la causa del incidente (por ejemplo, **Resbaló en el piso mojado**).
16. En el campo **Nivel de gravedad**, especifique o seleccione un valor.
17. En el campo **Acción que debe realizarse**, ingrese un valor (por ejemplo, **Limpiar pronto vertidos**).
18. En el campo **Días previstos de ausencia laboral**, ingrese el número de días que se espera que la persona esté fuera del trabajo.

    Una vez que el individuo vuelva al trabajo, actualice el campo **Días de ausencia laboral** con el número real de días que ha estado ausente.

19. En la sección **Costes por lesión o enfermedad**, seleccione **Agregar**.
20. En el campo **Fecha**, escriba una fecha.
21. En el campo **Tipo de coste**, especifique o seleccione un valor (por ejemplo, **Terapia**).

    También puede especificar un importe y adjuntar cualquier documentación justificativa al coste (por ejemplo, facturas o notas del médico).

22. Seleccione **Agregar**.
23. En el campo **Fecha**, escriba una fecha.
24. En el campo **Tipo de coste**, especifique o seleccione un valor (por ejemplo, **Médico**).
25. En la sección **Tratamiento de lesiones o enfermedades**, seleccione **Agregar**.
26. En el campo **Fecha de tratamiento**, especifique una fecha y una hora.
27. En el campo **Tipo de tratamiento**, especifique o seleccione un valor (por ejemplo, **Tablilla**).
28. Opcional: establezca la sección **Traslado a unidad de emergencias** en **Sí**.
29. En el campo **Comentarios del tratamiento**, especifique un valor (por ejemplo, **Tablilla durante 2 semanas**).
30. En el campo **Nombre del médico**, escriba un valor (por ejemplo, **Dr. Anderson**).
31. En el campo **Centro de salud en el que se realiza el tratamiento y ubicación**, ingrese un valor (por ejemplo, **Elm St. Emergency**).
32. En el campo **Detalles del tratamiento**, ingrese un valor (por ejemplo, **La radiografía confirma fractura, use tablilla**).
33. Seleccione **Guardar**.

El estado del caso se puede actualizar en cualquier momento. Si el procesamiento de la lesión o enfermedad está en curso, establezca el estado como **En curso**. Una vez cierre el incidente, solo podrá agregar o quitar costes, tratamientos o archivos relacionados con el incidente. Para cambiar otra información, debe reabrir el caso.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
