---
title: Configurar tipos de permisos y ausencias
description: Configure los tipos de baja que los empleados pueden tomar en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
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
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198059"
---
# <a name="configure-leave-and-absence-types"></a>Configurar tipos de permisos y ausencias

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

5. En **General**, seleccione **Ninguno**, **Programado**o **No programado** en el menú desplegable **Categoría**.

6. Seleccione un código de ganancia en el menú desplegable **Código de ganancias**.

7. Debajo de **Código de motivo requerido**, elija si desea requerir un código de motivo. Si desea requerir códigos de motivo, es posible que deba agregarlos. Debajo de **Códigos de motivo**, seleccione **Agregar**, seleccione un código de motivo y luego seleccione la casilla **Habilitado** que se encuentra al lado.

8. Debajo de **Restringir el acceso a los roles seleccionados**, elija si desea restringir el acceso. Luego seleccione los roles de seguridad en **Roles de seguridad para este tipo de permiso**. Los roles de seguridad se definen en el flujo de trabajo que ha seleccionado en **Id. de flujo de trabajo** anteriormente en este procedimiento.

9. Seleccione **Guardar**.

## <a name="configure-leave-type-rules"></a>Configurar reglas de tipo de permiso

1. Establezca opciones de redondeo para el tipo de baja. Las opciones incluyen **Ninguno**, **Arriba**, **Abajo** y **Aproximación**. También puede establecer la precisión de redondeo para el tipo de baja.

2. Establezca **Corrección de día festivo** para el tipo de baja. Cuando selecciona esta opción, Human Resources usa el número de días festivos que caen en un día laboral para determinar cómo acumular tiempo libre para el tipo de baja. Por ejemplo, si el día de Navidad cae en lunes, Human Resources restará un día del tipo de baja al procesar las acumulaciones.

   Puede establecer días festivos en el calendario de tiempo laborable. Para obtener más información, consulte [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md).
   
## <a name="configure-preview-features"></a>Configurar características de vista previa

Si ha habilitado las características de vista previa para Permisos y ausencias, también debe configurarlas.

[!include [banner](includes/preview-feature-leave-absence.md)]

1. Elija el tipo de permiso para transferir saldos a transferir. También puede crear un nuevo tipo de permiso para transferir. 

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Crear un plan de permisos y ausencias](hr-leave-and-absence-plans.md)
- [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md)
