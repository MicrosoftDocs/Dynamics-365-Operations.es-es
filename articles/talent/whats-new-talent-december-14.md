---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (14 de diciembre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 9887d22a513e820c35c51b6c702e2d9d34ab1214
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529765"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-december-14-2018"></a>Novedades y cambios en Dynamics 365 Talent - Core HR (14 de diciembre de 2018)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Compilación 8.1.2085**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="changes"></a>Cambios

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>EE. UU - Soporte de ACA (Ley de cuidados asequible) para los formularios 1095-B y 1095-C del ejercicio fiscal 2018

Cada año, los grandes empleadores aplicables (ALE) deben proporcionar a cada empleado a tiempo completo un 1095-C. Además, si el patrón proporciona cobertura de seguro debe proporcionar el 1095-C (si es ALE) y un 1095-B (si es un pequeño empresario) a todos los empleados, a jornada completa o a tiempo parcial, cubiertos en uno de sus planes de salud. Esta característica facilita formularios imprimibles para el 1095-C y 1095-B.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Durante la importación el campo SubmittedByPersonId de HcmPerfJournalEntity se omite

Al importar o exportar entradas del diario de rendimiento, el campo **Enviado por** se omite. Con este cambio, el valor **importado/exportado** reflejará el valor de la tabla durante la exportación, al importar el sistema se actualizará con el valor que se incluye en el archivo de importación.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>La ficha Análisis del área de trabajo de “licencia y ausencia" muestra el error de “OpenConnectionError” para las funciones de la gestión de fuera del sistema

Con esta actualización, no se emitirán errores al abrir la pestaña **Análisis** del espacio de trabajo **licencia y ausencia**.

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Autogestión del empleado, la exploración de jerarquía de posiciones desde el icono no puede obtener el nodo principal

Un cambio se ha realizado para corregir el error “Error al obtener el nodo principal" cuando la jerarquía de puestos se ha personalizado para que aparezca en un área de trabajo existente y un puesto se selecciona en la jerarquía.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>Debe ser Administrador del sistema para ver la ficha de la nómina en la página de puesto

Un cambio se ha efectuado para incluir los elementos de seguridad adecuados en el privilegio existente: “Mantener detalles de trabajador y puesto de nómina”. Con este cambio, de forma predeterminada, el administrador de nóminas tendrá acceso a los campos de nómina en la página de puesto.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Error al enviar la evaluación del rendimiento al administrador y el marcador de posición %Reviews.PerfPeriod% se usa en las instrucciones de envío

Se ha realizado un cambio que corrige el error “referencia nula” al utilizar el marcador de posición %Reviews.PerfPeriod% en las instrucciones del envío.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>El informe de Workforce Power BI muestra un error cuando la fecha antigüedad del trabajador cae en 29 de febrero

Con este cambio, ahora Power BI admite el 29 de febrero.

### <a name="integration-between-core-hr-and-attract"></a>La integración entre Core HR y Attract

Un cambio se ha efectuado para actualizar la integración entre Core HR y Attract en relación con los candidatos a contratar. Para que los candidatos a contratar estén visibles en el área de trabajo **Dirección de personal**, se usan las entidades Common Data Service siguientes:

Solicitud de trabajo
- El motivo del estado tiene que establecerse en propuesta aceptada
-   Proporciona el candidato y la vacante

Candidato
-   Proporciona información del candidato

Vacante
-   Proporciona el ID de vacante y los participantes en la vacante

Participantes en la vacante
-   Proporciona un director de contratación

Al agregar un candidato a la dirección del personal, ahora el candidato también puede ser despedido mediante una nueva opción disponible en la tarjeta del candidato.

## <a name="coming-soon"></a>Próximamente

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Baja y ausencia: Saldos futuros de licencia y de previsión de la licencia

Con los cambios creados para permitir que los empleados pronostiquen el tiempo libre y pidan futuras solicitudes de tiempo libre sin afectar a sus saldos actuales de tiempo libre, el modo en que el tiempo libre de los saldos se muestra también está cambiando. 

El saldo disponible presentado actualmente es la cantidad de tiempo libre disponible para solicitudes que incluyen acumulaciones hasta hoy y todas las solicitudes aprobadas de licencia hasta la finalización de tiempo. 

Cuando se lanza la capacidad de previsión, el saldo mostrado cambia para ser el saldo actual del tiempo libre incluidas las acumulaciones hasta hoy y las solicitudes hasta hoy. Los empleados y los administradores verán estos saldos actualizados en el autoservicio de empleado y director en la tarjeta **Licencias** y en la ventana **Saldos de licencias**. Los administradores de RR.HH. verán estos saldos actualizados en el espacio de trabajo **Personas** y en la ventana **Planes de licencia asignados** del empleado.

## <a name="known-issue"></a>Problema conocido

### <a name="mapping-errors-in-the-integration-with-finance"></a>Errores de asignación en la integración con Finance

Los siguientes problemas se han identificado en la plantilla actual para la integración de Talent con Dynamics 365 Finance. Una nueva plantilla se publicará pronto y se aplicará a todos los proyectos nuevos de integración que se creen. Para los proyectos existentes de integración, las equivalencias de tareas se pueden volver a calcular. Consulte la tabla siguiente para obtener las asignaciones actualizadas. 

>[!NOTE]
> La tarea de asignación de puestos de trabajo a la tarea principal de los puestos no integra los datos. Este es un problema que se está investigando actualmente. No hay solución en la asignación actual. 

La tarea Departamentos a la unidad operativa necesita actualizar las asignaciones siguientes.

| Campo de origen existente          | Nuevo campo de origen |
| -------------------------------|------------------|
| cdm_description (descripción)  | cdm_name (nombre)  |

También es necesario agregar una asignación adicional. Seleccione el último campo **Ninguno** para agregar la siguiente asignación.

| Campo de origen                   | Campo de destino    |
| -------------------------------|----------------------|
| cdm_description (descripción)  | NAMEALIAS (NAMEALIAS)|

Las asignaciones actualizadas deben tener la misma apariencia que la imagen siguiente.

![Tarea Departamentos a unidades operativas](./media/DepartmentMapping.png)


La tarea Trabajo a Detalle de trabajo necesita actualizar las asignaciones siguientes.

| Campo de origen existente          | Nuevo campo de origen                   |
| -------------------------------|------------------------------------|
| cdm_name (nombre)                | cdm_description (descripción)      |
| cdm_name (descripción)         | cdm_jobdescription (descripción del trabajo)|


Las asignaciones actualizadas deben tener la misma apariencia que la imagen siguiente.

![Tarea Trabajos a detalles del trabajo](./media/JobMapping.png)

La tarea Trabajadores a trabajo necesita actualizar las asignaciones siguientes.

| Campo de origen existente                 | Nuevo campo de origen                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (dirección de correo electrónico 1)   | cdm_primaryemailaddress (dirección de correo electrónico principal) |
| cdm_telephone1 (teléfono 1)          | cdm_primarytelephone (teléfono principal)       |

La transformación del campo Género también debe actualizarse. Seleccione el tipo de mapa **fn** (función) para el género y actualice las asignaciones de valores siguientes.

| Valor Common Data Service                   | Valor Finance and Operations                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Hombre                                             |
| 75440001                    | Mujer                                           |
| 75440002                    | None                                             | 
| 75440003                    | NonSpecific                                      |

Las asignaciones actualizadas deben tener la misma apariencia que las imágenes siguientes.

![Tarea Trabajadores a Trabajador](./media/WorkerMapping.png)

![Transformación de campo de género](./media/WorkerTransform.png)
