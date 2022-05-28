---
title: Espacio de trabajo de administración de prestaciones
description: En este tema se describe el espacio de trabajo de gestión de beneficios de Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39e7f606ae3c5c0a66764cc3235837380725241f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690038"
---
# <a name="benefits-management-workspace"></a>Espacio de trabajo de administración de prestaciones


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

En este tema se describe el espacio de trabajo de **Gestión de beneficios** de Dynamics 365 Human Resources.

> [!NOTE]
> Para ver el espacio de trabajo **Gestión de beneficios**, primero debe habilitar la función **Espacio de trabajo de gestión de beneficios (vista previa)** en la gestión de funciones. Para obtener más información sobre la habilitación de características en vista previa, consulte [Administrar características](hr-admin-manage-features.md).<br><br>![Habilitar el espacio de trabajo de administración de prestaciones.](./media/hr-benefits-management-workspace-enable.png)

El espacio de trabajo **Gestión de beneficios** le brinda una vista rápida de los elementos de beneficios que requieren su atención. En esta página, puede ver lo siguiente:

- Totales de artículos en espera de acción
- Trabajadores con selecciones no confirmadas
- Trabajadores que se inscribieron recientemente en los beneficios
- Trabajadores con eventos de la vida futura
- Nuevas contrataciones que no están inscritas
- Trabajadores con eventos de la vida activos
- Trabajadores con matrículas abiertas que no han optado por ningún plan

![Espacio de trabajo de administración de prestaciones.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Ver elementos de acción

Puede ver sus elementos de acción seleccionando un mosaico o una pestaña. Si selecciona una pestaña, puede ver y seleccionar trabajadores desde la página del espacio de trabajo.

![Elementos de acción.](./media/hr-benefits-management-workspace-action-items.png)

Si selecciona un mosaico, va a la página de esa área. Por ejemplo, al seleccionar cualquiera de estos mosaicos se muestra la página **Planes de beneficios para trabajadores**, filtrada para los empleados en los que necesita tomar medidas:

- **Selecciones no confirmadas**
- **Abrir inscripciones con planes sin comprobar**
- **Inscrito en prestaciones**
- **Nueva contratación no inscrita**

![Planes de prestaciones de trabajador.](./media/hr-benefits-management-workspace-plans.png)

Seleccionando **Acontecimientos de la vida activa** o **Eventos de la vida futura** pasará a una lista de eventos de la vida activos o futuros.

![Eventos de vida.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>En procesamiento

Para procesar la elegibilidad de inscripción, eventos de la vida o actualizaciones de cambio de tarifas, seleccione el elemento apropiado en la barra de navegación.

![En procesamiento.](./media/hr-benefits-management-workspace-processing.png)

Para ver los resultados del proceso, seleccione **Resultados de proceso** en la página.

![Procesar resultados.](./media/hr-benefits-management-workspace-process-results.png)

Para obtener más información acerca del procesamiento de beneficios, vea .

- [Procesar idoneidad de inscripción](hr-benefits-process-enrollment-eligibility.md)
- [Procesar cambios de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Procesar idoneidad de eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Procesar eventos de vida](hr-benefits-process-life-events.md)
- [Procesar cambios de tipo](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Cambio de período

Para ver un período de beneficios diferente, selecciónelo en la lista desplegable **Período**.

![Cambio de período.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>Pestaña inscripción abierta

Puede ver elementos de acción seleccionando un mosaico o una pestaña. Si selecciona una pestaña, puede ver y seleccionar trabajadores desde la página del espacio de trabajo.
La pestaña **Inscripción abierta** proporciona métricas clave para el proceso de inscripción abierta. 

La información sobre la inscripción abierta se mostrará 30 días antes de la **Fecha de inicio de la inscripción**. Esto se define en la configuración **Periodos** en **Gestión de prestaciones** > **Enlaces** > **Periodos**, en el campo **Fecha de inicio de la inscripción**.  Para cambiar esta configuración, vaya a **Parámetros compartidos de recursos humanos** > **Gestión de prestaciones** > **Opciones de inscripción abierta** y actualice el campo **Número de**.  

La siguiente información está disponible en la pestaña **Inscripción abierta**:
 - Empleados que no han iniciado el proceso de inscripción abierta
 - Empleados que tienen elecciones en proceso
 - Empleados que han completado el proceso de elección
 - Selecciones no confirmadas

**Iconos de resumen**

- **No empezado**: el mosaico **No empezado** muestra un recuento de empleados que no han iniciado el proceso de inscripción. El mosaico **No empezado** es una lista filtrada que muestra solo aquellos empleados que no tienen ningún plan seleccionado, renunciado o retirado para el período del plan de inscripción abierta. Los planes obligatorios se ignoran y no se incluyen porque se seleccionan de forma predeterminada para el empleado.  Puede profundizar en este mosaico para ver una lista de empleados que no han iniciado el proceso de inscripción abierta en la página **Plan de prestaciones para trabajadores**.

  > [!NOTE]
  > Si no desea realizar un seguimiento del progreso de la inscripción abierta para un **Tipo de plan**, puede excluirlo yendo a **Gestión de prestaciones** > **Enlaces** > **Parámetros de autoservicio para empleados** > **Configuración de mosaicos de planes de prestaciones** y actualizando el campo **Seguimiento del progreso de la inscripción abierta**.  Por ejemplo, puede haber creado planes donde **Tipo de plan** = **Otro**. Estos planes pueden ser planes opcionales para los que no desea realizar un seguimiento del progreso de la inscripción. Si no selecciona este tipo de plan, los planes de estos tipos se ignorarán al realizar un seguimiento del progreso o finalización de la inscripción en la pestaña **Inscripción abierta**. Esta configuración se aplica al tipo de plan que se selecciona para todos los períodos y entidades legales.

- **En curso**: el mosaico **En curso** da un recuento de empleados que tienen elecciones en curso. El mosaico **En curso** es una lista filtrada que muestra solo los empleados que tienen al menos un plan que no se aplica o está seleccionado. Los planes obligatorios se ignoran y no se incluyen porque se seleccionan de forma predeterminada para el empleado. Puede profundizar en este mosaico para ver los planes seleccionados y condonados en la página **Actualización masiva de planes de prestaciones para trabajadores**.

- **Inscrito en prestaciones**: el mosaico **Inscrito en prestaciones** proporciona un recuento de empleados que están completamente inscritos en las prestaciones. El mosaico **Inscrito en prestaciones** es una lista filtrada que muestra a los empleados que han seleccionado o renunciado a todos los planes. La consulta excluirá los planes que no se están rastreando para la inscripción abierta en la página **Parámetros de autoservicio para empleados**. Puede profundizar en este mosaico para ver una lista de empleados en la página **Planes de prestaciones para trabajadores**.

- **Selecciones no confirmadas**: el mosaico **Selecciones no confirmadas** muestra un recuento de empleados que tienen planes que se seleccionaron o renunciaron y necesitan ser confirmados. Puede profundizar en este mosaico para mostrar la página **Actualización masiva de planes de prestaciones para trabajadores**.

**Actividad**

- **No empezado**: la pestaña **No empezado** muestra una lista de empleados que no han iniciado el proceso de inscripción. El mosaico **No empezado** es una lista filtrada que muestra empleados que no tienen ningún plan seleccionado, renunciado o retirado para el período del plan de inscripción abierta. Los planes obligatorios se ignoran y no se incluyen porque se seleccionan de forma predeterminada para el empleado. Puede desglosar el trabajador para mostrar la página **Detalle de planes de prestaciones para trabajadores**.

- **Elecciones en curso**: la pestaña **Elecciones en curso** muestra una lista de empleados que tienen elecciones en curso. **Elecciones en curso** es una lista filtrada que muestra los empleados que tienen al menos un plan que no se aplica o está seleccionado. Los planes obligatorios se ignoran y no se incluyen porque se seleccionan de forma predeterminada para el empleado. Puede desglosar el trabajador para mostrar la página **Detalle de planes de prestaciones para trabajadores**.

## <a name="view-more-options"></a>Ver más opciones

Para ver más información y las acciones adicionales, seleccione **Vínculos**.

![Vínculos.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Consulte también

[Información general de administración de prestaciones](hr-benefits-management-overview.md)
