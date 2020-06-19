---
title: Información general
description: En Dynamics 365 Human Resources el espacio de trabajo Permisos y ausencias proporciona un marco flexible para crear nuevos planes de baja, flujos de trabajo para administrar solicitudes y una página intuitiva de autoservicio para que los empleados soliciten tiempo libre.
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
ms.openlocfilehash: ec72d2d741f7f8428a7daa97bb982e9fc00b8c3f
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428976"
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

- [Solicitar permiso](hr-employee-self-service-request-time-off.md)
- [Administrar solicitudes de permisos y ausencias](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-known-issues"></a>Ausencia y problemas conocidos de ausencia

### <a name="rounding-precision"></a>Precisión del redondeo

No puede configurar **Precisión de redondeo** cuando establece **Tipo de redondeo**. Solo puede configurar **Precisión de redondeo** mediante el uso de la entidad **Tipo de permiso y ausencia**. 

1. En **Tipos de permiso y ausencia**, seleccione **Abrir en Excel** para abrir la entidad **Tipo de permiso y ausencia**.

2. Después de que el archivo se abra y esté habilitado, seleccione **Diseñar**.

3. En la tabla **Tipo de permiso y ausencia**, seleccione la opción de lápiz para editar.

4. Seleccione **RoundingPrecision** y **RoundingType** y luego seleccione **Agregar** para agregar a la lista de campos.

5. Seleccione **Actualizar** y, a continuación, seleccione **Hecho**.

6. Introduzca o seleccione el **Tipo de redondeo** para cada tipo de permiso si aún no se han configurado. 

7. Introducir la **Precisión de redondeo** para los tipos apropiados.

8. Seleccione **Publicar** para llevar los cambios a Human Resources.

## <a name="leave-and-absence-preview-features"></a>Características de vista previa para permisos y ausencias

Puede probar nuevas características de vista previa de Permisos y ausencias en un entorno de **espacio aislado**. Para obtener información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md). 

[!include [banner](includes/preview-feature.md)]

Entre las características de vista previa se incluyen:

- **Acumulación de bajas por empresa o plan**: puede ejecutar el proceso de acumulación para todas las empresas o para una sola empresa. También puede ejecutar el proceso de acumulación para un plan específico de baja de una empresa específica. 

- **Comprar baja**: puede habilitar y crear directivas de compra de bajas para que los empleados envíen solicitudes de compra. Los empleados pueden enviar solicitudes de compra y tener saldos actualizados automáticamente para reflejar la solicitud.  

- **Agregar archivos adjuntos a las solicitudes de baja aprobadas**: puede agregar un archivo adjunto a una solicitud de baja que ya se ha aprobado. 

