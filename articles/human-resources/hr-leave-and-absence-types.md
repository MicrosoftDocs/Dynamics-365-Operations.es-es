---
title: Configurar tipos de permisos y ausencias
description: Configure los tipos de baja que los empleados pueden tomar en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39e4c4b9c83ca648c21ac20bd20b739af8a6b9ed
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271136"
---
# <a name="configure-leave-and-absence-types"></a>Configurar tipos de permisos y ausencias

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Los tipos de permisos en Dynamics 365 Human Resources definen los distintos tipos de ausencias que los empleados puedan notificar. Puede adaptar los tipos de baja en función de las necesidades de su organización. Entre los tipos de baja se incluyen:

- Tiempo libre remunerado (PTO)
- Ausencia no retribuida
- Vacaciones pagadas
- Baja por enfermedad
- Baja médica
- Licencia familiar
- Incapacidad de corta duración
- Licencia por duelo

## <a name="add-a-leave-type"></a>Agregar un tipo de licencia

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Tipos de permisos y ausencias**.

3. Seleccione **Nuevo**.

4. Escriba un nombre para el tipo de baja debajo de **Tipo**, seleccione un flujo de trabajo en **Id. de flujo de trabajo** e introduzca una descripción debajo de **Descripción**.

5. En **General**, seleccione **Ninguno**, **Programado** o **No programado** en el menú desplegable **Categoría**.

6. Seleccione un código de ganancia en el menú desplegable **Código de ganancias**.

7. Debajo de **Código de motivo requerido**, elija si desea requerir un código de motivo. Si desea requerir códigos de motivo, es posible que deba agregarlos. Debajo de **Códigos de motivo**, seleccione **Agregar**, seleccione un código de motivo y luego seleccione la casilla **Habilitado** que se encuentra al lado.

8. Debajo de **Restringir el acceso a los roles seleccionados**, elija si desea restringir el acceso. Luego seleccione los roles de seguridad en **Roles de seguridad para este tipo de permiso**. Los roles de seguridad se definen en el flujo de trabajo que ha seleccionado en **Id. de flujo de trabajo** anteriormente en este procedimiento.

9. Debajo de **Color del calendario**, elija qué color mostrar en los calendarios de permisos y ausencias para este tipo de permisos. 

10. En **Relaciones de suspensión**, elija si desea que este tipo de licencia suspenda otro tipo de licencia o sea suspendido por otro tipo de licencia. Cuando se envía una solicitud de baja para el tipo de licencia que suspende, se creará automáticamente una suspensión de licencia para el tipo de licencia suspendida. 

10. Seleccione **Guardar**.

## <a name="configure-leave-type-rules"></a>Configurar reglas de tipo de permiso

1. Establezca opciones de redondeo para el tipo de baja. Las opciones incluyen **Ninguno**, **Arriba**, **Abajo** y **Aproximación**. También puede establecer la precisión de redondeo para el tipo de baja.

2. Establezca **Corrección de día festivo** para el tipo de baja. Cuando selecciona esta opción, Human Resources usa el número de días festivos que caen en un día laboral para determinar cómo acumular tiempo libre para el tipo de baja. Por ejemplo, si el día de Navidad cae en lunes, Human Resources restará un día del tipo de baja al procesar las acumulaciones.

   Puede establecer días festivos en el calendario de tiempo laborable. Para obtener más información, consulte [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md).
   
 3. Establezca **Tipo de baja de transferencia** para el tipo de baja. Cuando selecciona esta opción, los saldos de arrastre se transferirán al tipo de baja especificado. El tipo de baja de transferencia también debe incluirse en el plan de baja y ausencia. 
 
4. Defina las **Reglas de vencimiento** para el tipo de licencia. Cuando configura esta opción, puede elegir la unidad de días o meses y establecer la duración hasta el vencimiento. La fecha de vigencia de la regla de expiración se usa para determinar cuándo comenzar a ejecutar el trabajo por lotes que procesa el vencimiento de la licencia o la fecha en que la regla entra en vigencia. El vencimiento en sí siempre ocurrirá en la fecha de inicio del período de acumulación. Por ejemplo, si la fecha de inicio del período de acumulación es el 3 de agosto de 2021 y la regla de vencimiento se estableció en 6 meses, la regla se procesará en función de la compensación de vencimiento de la fecha de inicio del período de acumulación, por lo que se ejecutará el 3 de febrero de 2022. Cualquier saldo de baja que exista al momento del vencimiento se restará del tipo de baja y se reflejará en el saldo de bajas.
 
## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Crear un plan de bajas y ausencias](hr-leave-and-absence-plans.md)
- [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md)
- [Suspender baja](hr-leave-and-absence-suspend-leave.md)
- [Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
