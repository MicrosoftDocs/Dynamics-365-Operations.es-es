---
title: Información general
description: En Dynamics 365 Human Resources el espacio de trabajo **Permisos y ausencias** proporciona un marco flexible para crear nuevos planes de baja, flujos de trabajo para administrar solicitudes y una página intuitiva de autoservicio para que los empleados soliciten tiempo libre.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 493bc3abe82103541125914896252b2eae596b38
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091757"
---
# <a name="overview"></a>Información general

Dynamics 365 Human Resources le ayuda a proporcionar excelentes prestaciones de baja a sus trabajadores. El espacio de trabajo **Permisos y ausencias** proporciona un marco flexible para crear nuevos planes de baja, flujos de trabajo para administrar solicitudes y una página intuitiva de autoservicio para que los empleados soliciten tiempo libre. Los análisis ayudan a su organización a medir y supervisar los saldos de bajas y el uso de sus planes de bajas.

## <a name="set-up-leave-and-absence"></a>Configurar permisos y ausencias

Para poder crear planes de bajas para sus empleados, necesita realizar algunos pasos de configuración:

- [Configurar parámetros de bajas y ausencias](hr-leave-and-absence-parameters.md)
- [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md)
- [Crear una solicitud de baja de flujo de trabajo](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Crear y administrar planes de bajas

Antes de crear planes de bajas para sus trabajadores, debe crear tipos de permisos y ausencias. Después de crear un plan de bajas, puede inscribir trabajadores en el plan. También puede ejecutar el proceso de acumulación, crear alertas y ver análisis para sus planes.

- [Configurar tipos de permisos y ausencias](hr-leave-and-absence-types.md)
- [Crear un plan de permisos y ausencias](hr-leave-and-absence-plans.md)
- [Asignar trabajadores a un plan de ausencias](hr-leave-and-absence-enroll.md)
- [Acumular planes de permisos y ausencias](hr-leave-and-absence-accrue.md)
- [Ver análisis de permisos y ausencias](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Solicitar tiempo libre y administrar solicitudes

Sus empleados pueden enviar solicitudes de tiempo libre y usted puede administrarlas en el espacio de trabajo **Autoservicio para empleados**.

- [Solicitar licencia](hr-employee-self-service-request-time-off.md)
- [Administrar solicitudes de bajas y ausencias](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Características de vista previa para permisos y ausencias

Puede probar nuevas características de vista previa de Permisos y ausencias en un entorno de **espacio aislado**. Para obtener información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md). Entre las características de vista previa se incluyen:

- **Calendario de bajas y ausencias**: los parámetros de bajas y ausencias se moverán de **Parámetros de recursos humanos** a una nueva pantalla llamada **Parámetros de bajas y ausencias**. La nueva pantalla incluye una nueva pestaña **Calendario**. Esta vista previa solo habilita un subconjunto de los parámetros. Puede acceder a la nueva pantalla desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**. Los calendarios incluyen:
  - **Calendario de la empresa**: muestra todas las solicitudes de tiempo libre de los empleados. Las personas con el rol **Recursos humanos** pueden acceder a este calendario desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**.
  - **Calendario del equipo gerente**: muestra todas las solicitudes de tiempo libre de informes directos. Los gerentes pueden acceder al calendario desde la pestaña **Mi equipo** en Autoservicio de empleados, en **Bajas y ausencias**. 

- **Calendarios de bajas y ausencias por vacaciones** : los tipos de baja incluyen una nueva opción **vacaciones**, utilizada junto con el calendario laboral. Los días definidos por vacaciones y cierres ahora se designan como **Vacaciones** cuando se generan días hábiles. Cuando se procesan las acumulaciones, se realizan ajustes a los empleados asignados al calendario para contabilizar los días festivos que caen en un día hábil.

- **Auditoría de acumulación de bajas**: una nueva pantalla le permite revisar cuándo se han procesado y eliminado las acumulaciones, tanto por parte de todos los empleados como de los empleados individuales. Puede acceder a esta nueva pantalla desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**.

- **Eliminación de bajas acumuladas**: ahora puede eliminar registros de acumulación para planes de bajas específicos. Puede acceder a esta nueva opción desde la pestaña **Vínculos** del espacio de trabajo **Bajas y ausencias**. Para empleados individuales, esta opción aparece en la agrupación **Bajas y ausencias** en el perfil del empleado. 

- **Redondeo de acumulación de bajas**: las nuevas opciones de **tipo de baja** definen qué tipo de redondeo debe usar la acumulación, más la precisión decimal del redondeo durante el proceso de acumulación. Cuando se procesan las acumulaciones, el redondeo y la precisión se aplican a los registros de acumulación. 

- **Configurar múltiples tipos de bajas en un solo plan de bajas**: una nueva columna en el programa de acumulación de bajas para los tipos de vacaciones le permite definir varios tipos de bajas en un plan de bajas y ausencias con diferentes programaciones de acumulación. El anterior campo **Tipo de baja** se ha eliminado. En la inscripción de empleados, los saldos para los tipos de licencia ahora se muestran en una tabla en lugar de en la parte superior de la pantalla.

  > [!IMPORTANT]
  > Después de habilitar esta función, no puede desactivarla.

- **Usar la equivalencia de tiempo completo (FTE) de un empleado para la acumulación**: una nueva columna en el programa de acumulación de bajas permite utilizar FTE para la acumulación. Cuando se procesan las acumulaciones, la aplicación utiliza la posición principal del empleado y el FTE definido para determinar el monto acumulado prorrateado.

  > [!NOTE]
  > Esta función solo está disponible si habilita **Configurar múltiples tipos de bajas por plan de baja**. 
