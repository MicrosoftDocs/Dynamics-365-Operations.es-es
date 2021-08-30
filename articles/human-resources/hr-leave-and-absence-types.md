---
title: Configurar tipos de permisos y ausencias
description: Configure los tipos de baja que los empleados pueden tomar en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 07/16/2021
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
ms.openlocfilehash: 0ca474fe12867ae767db936ad0b2995c4437bdf0ee94831450fda825b9e075dc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730427"
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
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Configurar los requisitos de archivos adjuntos por tipo de licencia

> [!NOTE]
> Para usar el campo **Se requiere adjunto**, primero debe activar la función **(Vista previa) Configurar el archivo adjunto requerido para las solicitudes de licencia** en la gestión de funciones. Para obtener más información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md).

1. En la página **Baja y ausencia**, en la pestaña **Enlaces**, en **Configuración**, seleccione **Tipos de bajas y ausencias**.

2. Seleccione un tipo de baja y ausencia en la lista. Entonces, en la sección **General**, use el campo **Se requiere adjunto** para especificar si se debe cargar un archivo adjunto cuando un empleado envía una nueva solicitud de licencia para el tipo de licencia seleccionado. 

Se requerirá que los empleados carguen un archivo adjunto cuando envíen una nueva solicitud de baja que tenga un tipo de baja donde el campo **Se requiere adjunto** está habilitado. Para ver el archivo adjunto que se cargó como parte de una solicitud de baja, los aprobadores de solicitudes de baja pueden usar la opción **Archivos adjuntos** para los elementos de trabajo que se les asignan. Si se accede a una solicitud de licencia mediante la aplicación de Human Resources en Microsoft Teams, la opción **Ver detalles** para la solicitud de licencia se puede utilizar para ver sus detalles y cualquier archivo adjunto.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Configurar unidades (horas/días) de baja por tipo de baja

> [!NOTE]
> Para usar la función de unidades de licencia por tipo de licencia, primero debe encender el **(Vista previa) Configurar unidades de licencia por tipo de baja** en la gestión de funciones. Para obtener más información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md).

> [!IMPORTANT]
> De forma predeterminada, los tipos de permisos de una entidad jurídica utilizan las unidades de permisos de la configuración de los parámetros de permisos a nivel de entidad jurídica.
> 
> La unidad de baja de un tipo de baja y ausencia se puede modificar solo si no hay transacciones de licencia para ese tipo de licencia.
> 
> Una vez activada la función, no se puede desactivar.

1. En la página **Baja y ausencia**, en la pestaña **Enlaces**, en **Configuración**, seleccione **Tipos de bajas y ausencias**.

2. Seleccione un tipo de baja y ausencia en la lista. Entonces, en la sección **General**, en el campo **Unidad**, seleccione la unidad de salida. Puede elegir **Horas** o **Días**.

3. Opcional: si seleccionó **Horas** en el campo **Unidad**, puede utilizar el campo **Habilitar la definición de medio día** para especificar si los empleados pueden seleccionar el primer medio día o el segundo medio día libre si solicitan medio día de baja.

Los empleados que envían una nueva solicitud de licencia pueden seleccionar diferentes tipos de licencia para construir su solicitud de licencia. Sin embargo, todos los tipos de licencia que se seleccionan como parte de una única solicitud de licencia deben tener la misma unidad de licencia. Los empleados pueden ver la unidad de licencia para cada tipo de licencia formulario **Solicitar tiempo libre**.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Crear un plan de bajas y ausencias](hr-leave-and-absence-plans.md)
- [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md)
- [Suspender baja](hr-leave-and-absence-suspend-leave.md)
- [Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
