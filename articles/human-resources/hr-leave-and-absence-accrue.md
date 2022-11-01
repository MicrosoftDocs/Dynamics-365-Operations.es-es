---
title: Acumular planes de bajas y ausencias
description: Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.
author: twheeloc
ms.date: 09/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aac35177ca120b1ae1b4759b98278fafadc3e033
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702139"
---
# <a name="accrue-leave-and-absence-plans"></a>Acumular planes de bajas y ausencias

>[!Important]
>La funcionalidad mencionada en este artículo está disponible actualmente para los clientes de Dynamics 365 Human Resources independiente. Algunas o todas las funciones estarán disponibles como parte de una versión futura de la infraestructura de Finance después de la versión 10.0.26 de Finance.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Acumular permisos y ausencias para varios empleados

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. Debajo de **Administrar bajas**, seleccione **Acumular planes de permisos y ausencias**.

3. Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**. En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.

4. Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**. Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**. Si elige todas las empresas, no puede seleccionar planes de baja individuales.

5. Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

    1. Escriba información para el proceso de acumulación.
    2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y después seleccione **Aceptar**.
    3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.
    4. Seleccione **Aceptar**. El proceso de acumulación se ejecutará con los parámetros que establezca. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>Acumular permisos y ausencias para un empleado

1. En el registro del empleado, seleccione **Baja**.

2. Seleccione **Acumular planes de permisos y ausencias**.

3. Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**. En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.

4. Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**. Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**. Si elige todas las empresas, no puede seleccionar planes de baja individuales.

5. Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para el proceso de acumulación.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso de acumulación se ejecutará con los parámetros que establezca.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Eliminar acumulaciones de permisos y ausencias para varios empleados

Eliminar registros de acumulación para un plan e intervalo de fechas específico. Las fechas de acumulación deben ser la de hoy o fechas en el futuro.

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. Debajo de **Administrar bajas**, seleccione **Eliminar acumulaciones de permisos y ausencias**.

3. En el cuadro de diálogo **Eliminar acumulaciones de planes de permiso y ausencia**, seleccione **Dejar plan**.

4. Si corresponde, elija **Eliminar ajustes de saldo**.

5. introduzca o seleccione una **Fecha de abandono de acumulación**. Esta fecha tiene que ser hoy o en el futuro.

6. Seleccione **Aceptar**. El proceso de acumulación eliminará acumulaciones con los parámetros que establezca.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Eliminar acumulaciones de permisos y ausencias para un empleado

1. En el registro del empleado, seleccione **Baja**.

2. Seleccione **Eliminar acumulaciones de planes de permisos y ausencias**.

3. En el cuadro de diálogo **Eliminar acumulaciones de planes de permiso y ausencia**, seleccione **Dejar plan**.

4. Si corresponde, elija **Eliminar ajustes de saldo**.

5. introduzca o seleccione una **Fecha de abandono de acumulación**. Esta fecha tiene que ser hoy o en el futuro.

6. Seleccione **Aceptar**. El proceso de acumulación eliminará acumulaciones con los parámetros que establezca.

## <a name="review-leave-accrual-and-deletion-processes"></a>Revisar los procesos de acumulación y eliminación de permisos

**Auditoría de acumulación de permisos** se muestra cada vez que ejecuta o elimina una acumulación para uno o todos los empleados. También se muestra la fecha y la persona que realizó la acción.

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.
2. Debajo de **Administrar bajas**, seleccione **Eliminar auditoría de acumulaciones de permisos**.

## <a name="leave-accrual-rounding"></a>Redondeo de acumulación de bajas
Cuando un empleado está inscrito o no inscrito, el redondeo de la acumulación de licencias se prorrateará. Anteriormente, el redondeo solo se permitía cuando un plan de licencia se configuraba para prorratear y un empleado se inscribía o cancelaba durante la mitad del período. Las acumulaciones de licencias ahora se redondearán independientemente de la inscripción/cancelación de la inscripción a la mitad del período o al comienzo de un período.

## <a name="leave-accrual-transaction-auditing"></a>Auditoría de transacciones de acumulación de bajas

Esta función ayuda a los administradores de bajas y ausencias a comprender las transacciones de acumulación de bajas y ausencias relacionadas con los saldos de tiempo libre de un empleado para un tipo de baja específico.

Para ver los detalles de la transacción:

1. En el registro del empleado, seleccione **Baja**.

2. Seleccione **Ver tiempo libre** y luego seleccione la pestaña **Saldos**.

Para ver las transacciones de acumulación relacionadas con un tipo de licencia específico, seleccione el valor numérico en la columna **Saldo actual**.

Para ver los detalles de la transacción para un monto de acumulación específico, seleccione una fila de acumulación, abra el panel **Información relacionada** de la derecha y, a continuación, abra la sección **Detalles de la transacción**. Se muestra la sección Detalles de la transacción:

- Cambios en el saldo del tipo de baja del empleado
- Detalles de empleo para ese período de acumulación especificado
- Detalles sobre el período de acumulación y las tarifas
- Cualquier cambio realizado para dejar las configuraciones del plan

![Mostrar auditoría de transacciones de acumulación de bajas.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>Consulte también

[Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)</br>
[Crear un plan de bajas y ausencias](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
