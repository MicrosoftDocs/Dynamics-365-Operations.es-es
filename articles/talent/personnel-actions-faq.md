---
title: Acciones del personal [Preguntas frecuentes]
description: "Este tema contiene respuestas a preguntas que puede que tenga si su organización usa acciones de personal. Las acciones de personal son pasos adicionales que debe completar cuando realice ciertas tareas relacionadas con el personal."
author: ShielaSogge
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 93004f45189d16e991a3962ef16b4a102caf07bd
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="personnel-actions-faq"></a>Acciones del personal [Preguntas frecuentes]

[!include[banner](includes/banner.md)]

Este tema contiene respuestas a preguntas que puede que tenga si su organización usa acciones de personal. Las acciones de personal son pasos adicionales que debe completar cuando realice ciertas tareas relacionadas con el personal. Son ejemplos de tareas que requerirán acciones de personal crear nuevos puestos, modificar los valores de puestos existentes, contratar a trabajadores nuevos, transferir trabajadores, cambiar la compensación del trabajador, cambiar las asignaciones del puesto o despedir a trabajadores.

**Nota:** las acciones de personal solo están disponibles si los campos **Activar acciones del personal** y **Activar acciones de puestos** se han establecido en **Sí** en la pestaña **Acciones de personal** de la página **Parámetros compartidos de Recursos Humanos**. 

## <a name="how-can-i-tell-if-my-organization-requires-personnel-actions"></a>¿Cómo puedo saber si mi organización requiere acciones de personal?
La organización requiere acciones de personal si se le solicita que seleccione una acción de personal al crear nuevos puestos, cambie puestos existentes, contrate a nuevos trabajadores, transfiera a trabajadores, cambie la compensación del trabajador, cambie asignaciones del puesto, despida a trabajadores o especifique las bajas de los trabajadores. 

## <a name="what-is-the-difference-between-a-position-action-and-a-worker-action"></a>¿Cuál es la diferencia entre una acción de puesto y una acción de trabajador?
Existen dos tipos de acciones de personal:

- Acción de puesto: una acción de puesto se realiza en puestos existentes o puestos nuevos. Por ejemplo, una acción de puesto puede ser necesaria si cambia un valor en un puesto existente o si crea un nuevo puesto temporal. Para obtener información detallada sobre cómo usar acciones del puesto, consulte las tareas clave: puestos o tareas claves existentes del trabajador: nuevos puestos del trabajador.

- Acción de trabajador: una acción de trabajador se realiza en empleados existentes o empleados nuevos. Por ejemplo, una acción de trabajador puede ser necesaria al contratar a un empleado nuevo o ascender a un empleado existente. Para obtener información detallada sobre cómo usar acciones del trabajador, consulte el apartado Asignar acciones del personal a los trabajadores.

## <a name="what-do-the-statuses-of-the-personnel-actions-mean"></a>¿Qué implican los estados de las acciones de personal?
Las acciones de personal pueden tener los siguientes estados:

- **Borrador**: si se usa el flujo de trabajo, la acción no se ha enviado. Si el flujo de trabajo no se usa, la acción no ha finalizado.
- **En revisión**: la acción de personal se ha enviado al flujo de trabajo, pero el flujo de trabajo no se ha completado.
- **En espera de aprobación**: el flujo de trabajo se ha completado, pero los cambios aún se están procesando. Cancelada: se ha cancelado el flujo de trabajo o se ha recuperado la acción de personal. Rechazada: el aprobador ha rechazado la solicitud de acción.
- **Acción de procesamiento**: se ha aprobado la solicitud de acción y se están procesando los cambios.
- **Flujo de trabajo completo**: el flujo de trabajo se ha completado y se están procesando los cambios. Fallido: el flujo de trabajo ha fallado dado que la información es anticuada. Haga clic en Reactivar para mostrar la información más reciente y continuar.
- **Completado**: el puesto se ha creado o modificado correctamente o bien se ha contratado, transferido o despedido correctamente al empleado, o se ha cambiado su compensación. Error: se ha producido un problema distinto de la información anticuada. Abra el Registro del mensaje de acciones de personal para determinar la causa del error.
- **Denegada**: el aprobador ha denegado la solicitud de acción.

## <a name="can-i-delete-a-personnel-action"></a>¿Se puede eliminar una acción de personal?
Sí, puede eliminar las acciones de personal que tengan el estado de **Borrador**, **Error**, **Fallida** o **Cancelada**.

## <a name="what-is-the-fastest-way-to-check-the-status-of-a-personnel-action-request"></a>¿Cuál es la forma más rápida de comprobar el estado de una solicitud de acción de personal?
Abra cualquiera de las páginas de lista de la acción de personal y seleccione una acción de personal.

## <a name="what-should-i-do-if-a-personnel-action-request-fails"></a>¿Qué debo hacer si una solicitud de acción de personal falla?
Si una solicitud de acción de personal falla, siga estos pasos para solucionar el error y volver a enviar la solicitud:

> 1. En el **Panel de acciones**, haga clic en el botón **Texto de error** para ver el texto del mensaje que describe el problema.

> 2. En el **Panel de acciones**, haga clic en **Reactivar** para cargar la información más reciente y establecer el estado de la acción de personal de nuevo a **Borrador**.

> 3. Resuelva el error y haga clic en **Completo** o **Enviar**.

## <a name="what-happens-to-a-personnel-action-that-uses-workflow-when-the-final-approval-is-completed"></a>¿Qué sucede a una acción de personal que use el flujo de trabajo cuando se completa la aprobación final?
Si no hay errores, la acción de personal pasará a ser de solo lectura. (Puede ver el historial en la página de lista **Todas las acciones del trabajador**, pero no se puede modificar la acción del personal.) Cuando el estado de una acción del personal es **Completada**, el puesto o el registro de trabajador se ha actualizado su factura. Para ver los cambios realizados, abra la página de lista **Puestos** o **Trabajadores**.

## <a name="why-do-i-receive-the-following-error-when-i-enter-a-non-zero-value-in-the-pay-rate-field-the-value-is-out-of-its-valid-range--it-much-be-between-000-and-000"></a>¿Por qué recibo el siguiente mensaje de error cuando especifico un valor distinto de cero en el campo de índice salarial? “El valor se encuentra fuera del intervalo válido; debe estar entre 0,00 y 0,00“
Recibe este mensaje porque el campo Nivel del formulario Trabajo está en blanco para el trabajo asociado con el puesto seleccionado.

Para solucionar el error, siga estos pasos:

> 1. En el formulario de asignaciones de puesto a trabajadores, haga clic en el campo del puesto.  
> 2. Haga clic en el valor de campo Trabajo para abrir la página Trabajo.
> 3. En el panel de acciones, haga clic en Editar.
> 4. Haga clic en la ficha Compensación.
> 5. En el campo Nivel, seleccione un nivel.
> 6. Cierre la página Trabajo.
> 7. Cierre la página Puesto.
> 8. Vuelva a la ficha Compensación en la página Trabajador y seleccione la compensación fija.  Seleccione Nuevo y especifique el puesto del empleado en el campo Puesto.  Escriba un valor en el campo Plan y, después, introduzca la compensación del empleado en el campo del Índice salarial.

## <a name="why-cant-i-change-the-effective-date-in-the-header-of-the-worker-action-form"></a>¿Por qué no se puede cambiar la fecha de vigencia en el encabezado del formulario de la acción de trabajador?
No puede cambiar la fecha de vigencia dado que el campo se rellena con la fecha más lógica para el tipo de acción.

Por ejemplo:

- La fecha de vigencia en el encabezado de una acción **Dar de baja a un trabajador** es la fecha especificada en el campo **Fecha de finalización**.
- La fecha de vigencia de una acción **Contratar a un trabajador** es la fecha especificada en el campo **Fecha inicial del empleo**.
- La fecha de vigencia de una acción **Transferir a un trabajador** es la fecha especificada en el campo **Fecha inicial de la asignación** del trabajador.


