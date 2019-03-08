---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (11 de enero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6e7edf52db663c7ad28f316c324d68e57bf6699a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "306131"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-11-2019"></a>Novedades y cambios en Dynamics 365 for Talent Core HR (11 de enero de 2019)

[!include [banner](includes/banner.md)]

**Compilación 8.1.2100**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.

## <a name="changes"></a>Cambios

### <a name="validate-leave-requests-by-forecasting-available-balance"></a>Valide solicitudes de licencia pronosticando el saldo disponible
Los cambios realizados en esta versión permiten a los empleados pedir un tiempo futuro de licencia sin restarlo de los saldos actuales. Los flujos de trabajo estándar se usarán para cualquier solicitud futura realizada. Para obtener más información, consulte [Acumulación de licencias basada en las horas trabajadas](leave-accrue-hours-worked.md).

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a>Ver saldo de licencia previsto en ESS y personas
Esta función permite visualizar saldos para períodos futuros de licencia, por Recursos Humanos, administradores, y empleados. Los empleados pueden ver los saldos futuros en el área de trabajo **Autoservicio para empleados** y Recursos Humanos tiene acceso a la misma información mediante el espacio de trabajo **Personas**.

### <a name="notifications-for-changing-leave-balances"></a>Notificaciones para modificar los saldos de licencia
Los saldos de licencia mostrarán el saldo actual de los empleados. Los saldos futuros están disponibles en las áreas de trabajo **Autoservicio para empleados** y **Personas** especificando “a partir de la fecha” para calcular el saldo previsto.

La exploración se ha agregado para ver los saldos previstos en las siguientes áreas:
  - Tarjeta de**Licencias** en el área de trabajo **Autoservicio para empleados**.
  - Tarjeta de**Baja y ausencia** en el área de trabajo **Autoservicio para directores**.
  - Página**Baja y ausencia** en el espacio de trabajo **Personas**.

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a>Permite decimales para planes de compensación variable (planes de efectivo)
Las primas en efectivo y los planes variables tienen ahora la flexibilidad adicional para los importes y las anulaciones para valores con importes decimales.

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a>No se pueden cambiar las fechas en inscripciones comp de variables después de que se guarde el plan
Este cambio permite que la fecha final del plan sea actualizada (extendida o caducada) después de que se haya guardado el plan. Puede activar o desactivar planes sean cuales sean las fechas de inicio o finales.

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a>Información de nómina disponible cuando se tiene asignado el rol de seguridad Administración de nóminas
El rol de administrador de nóminas se ha actualizado para tener acceso a la información de nómina durante el proceso de solicitud.

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Autogestión del empleado | La exploración de jerarquía de posiciones desde el icono no puede obtener el nodo principal
Los cambios se han realizado para eliminar un error que aparecía al agregar la jerarquía de puestos a las nuevas áreas de trabajo y desplazarse dentro de la estructura organizativa.

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a>Nuevo mensaje de validación cuando la secuencia del número de personal está en uso
Un cambio se ha efectuado para aclarar cuál es el problema cuando contrata a un empleado y el número de personal siguiente está en uso.

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a>Área de trabajo de autoservicio del empleado seleccionada como página de inicio
Cuando se selecciona el área de trabajo **Autoservicio de empleado** como la página de inicio para un usuario y dicho usuario no tiene asignado el rol de empleado, el sistema redirigirá al panel predeterminado.

### <a name="termination-reason-code-updates-position-assignment-record"></a>El código de motivo de finalización actualiza el registro de asignación de puesto
El código de motivo de baja ahora actualizará la asignación de puesto al cesar a un empleado y dar por terminado el puesto. 
