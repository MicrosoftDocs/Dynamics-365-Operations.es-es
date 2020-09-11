---
title: Acumular planes de bajas y ausencias
description: Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 43c16c5d0de91bf1f433f4fde36e7d13775f44a0
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712182"
---
# <a name="accrue-leave-and-absence-plans"></a>Acumular planes de bajas y ausencias

Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Acumular permisos y ausencias para varios empleados

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. Debajo de **Administrar bajas**, seleccione **Acumular planes de permisos y ausencias**.

3. Apare el cuadro de diálogo **Acumular planes de permiso y ausencia**. En **A partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.

4. Si desea ejecutar acumulaciones para todas las empresas, seleccione **Todas las empresas**. Si desea procesar acumulaciones para un solo plan de vacaciones, seleccione **No** para **Todos los planes** y luego seleccione un **Plan de vacaciones**. Si elige todas las empresas, no puede seleccionar planes de baja individuales. 

5. Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para el proceso de acumulación.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

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

## <a name="see-also"></a>Consulte también

[Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)</br>
[Crear un plan de permisos y ausencias](hr-leave-and-absence-plans.md)
