---
title: Gestionar directivas de compra y venta de bajas
description: Puede permitir que los empleados compren y vendan bajas Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1fe7ce7eafdec175e3395a6ac37b33cb2bb8dbda
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066684"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Gestionar directivas de compra y venta de bajas


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede permitir que los empleados compren y vendan bajas creando una directiva de compra y venta de bajas. Puede configurar estas políticas para utilizar el flujo de trabajo para las aprobaciones, establecer cantidades y tarifas máximas, y establecer tarifas de compra y venta. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Permitir que los empleados compren y vendan bajas

1. En la página **Parámetros de permisos y ausencias**, seleccione **Sí** para **Permitir que los empleados compren bajas** y **Permitir que los empleados vendan bajas**.

## <a name="create-a-buy-and-sell-leave-policy"></a>Crear directivas de compra y venta de bajas

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**. 

2. Seleccione **Política de compra y venta de bajas**.

3. Seleccione **Nuevo**.

4. Introduzca un **Nombre** y una **Descripción** para la directiva en **Directiva de compra y venta de bajas**. 

5. Seleccione un **Tipo de directiva**. 

   Los tipos de directivas disponibles son **Importte** y **Horas por semana**. Seleccione **Importe** para introducir un **Importe fijo** por los importes máximos que los empleados pueden comprar y vender. Si seleccionas **Horas por semana**, el tiempo de trabajo definido en el calendario de tiempo de trabajo asignado del empleado se utiliza para determinar el importe máximo de la directiva. 

6. Seleccione una **Fecha inicial** y una **Fecha final** para la directiva. Las solicitudes para comprar o vender bajas solo estarán disponibles para su envío durante este período de tiempo. 

7. Seleccione un **Id. de flujo de trabajo** para la directiva. Cualquier solicitud de compra y venta utilizará este flujo de trabajo para su revisión y aprobación. 

8. En **Política de compra**, Seleccione **Equivalencia a tiempo completo** (FTE) para prorratear el importe máximo según el FTE definido en la posición del empleado. Si el tipo de política es **Importe**, introduzca un **Importe fijo máximo**. 

9. Seleccione **Añadir** para agregar los tipos de baja para que los empleados compren bajas. Puede agregar varios tipos de bajas a la directiva. 

10. Introduzca los **Meses de servicio** para el tipo de baja, para permitir diferentes meses de servicio para determinar el importe máximo que un empleado puede comprar. 

11. Introduzca el **Importe máximo** para el tipo de baja. 

12. Introduzca la **Tarifa** con la que el empleado comprará la baja. 

13. Opcionalmente, introduzca el **Código de ingresos** a usar para comprar la baja. 

14. Opcionalmente, establezca si usar FTE para determinar el importe máximo para el tipo de baja. 

15. Para crear una directiva de venta, siga los pasos 8 a 14 de **Directiva de ventas**. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Agregue la directiva de compra y venta de bajas a un plan de baja y ausencia

1. En la página **Baja y ausencia**, seleccione un plan de baja y ausencia.

2. En **Reglas**, seleccione **Política de compra y venta de bajas**.

## <a name="see-also"></a>Consulte también

[Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)</br>
[Configurar tipos de permisos y ausencias](hr-leave-and-absence-types.md)</br>
[Acumular planes de bajas y ausencias](hr-leave-and-absence-accrue.md)</br>
[Comprar y vender bajas](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
