---
title: Novedades o cambios en Dynamics 365 Human Resources 22 de junio de 2021
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 22 de junio de 2021.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61c457abf87ce2da554ddb1472512416159c4dca
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068436"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Novedades o cambios en Dynamics 365 Human Resources 22 de junio de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe las características que son nuevas, que se han cambiado o que vendrán próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4258.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Informar a los usuarios de los trabajadores sin la función de empleo: cuando el acceso avanzado está activado y la función **Ver todos los trabajadores sin empleo** está desactivada en la gestión de funciones, se mostrará un banner en el formulario de trabajadores sin empleos. El banner indicará al usuario que encienda la función **Ver todos los trabajadores sin empleo**. | No aplicable| [Trabajadores sin empleo](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Soporte de campos personalizados para las reglas de idoneidad de gestión de prestaciones | [Soporte de campo personalizado para el procesamiento de idoneidad](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configurar reglas de elegibilidad](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Auditoría de transacciones de acumulación de bajas | No aplicable | [Auditoría de transacciones de acumulación de bajas](hr-leave-and-absence-accrue.md)|
| Mejoras en la experiencia del flujo de trabajo de bajas y ausencias | [Mejoras en la experiencia del flujo de trabajo de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar permiso](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este artículo para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del artículo.

| Número del problema | Problema |  Description |
| --- | --- | --- |
| 583052 | El usuario que recibe comentarios puede editar los comentarios recibidos | Cuando un empleado que recibe comentarios en un diario de desempeño selecciona **Agregar enlace externo**, el formulario se vuelve editable, lo que permite al empleado editar los comentarios de desempeño que ha recibido. |
| 522281 | Seleccionar el número de empleados en los mosaicos de estructura de compensación en la Gestión de compensación genera resultados incorrectos| Al profundizar en los planes de compensación desde el espacio de trabajo de compensación, ahora se muestra el número correcto de empleados. |
| 580683 | Los usuarios asignados a los roles de Empleado y Gerente no pueden adjuntar notas o actualizar un diario de desempeño | Los usuarios asignados a los roles de Empleado y Gerente no pueden adjuntar notas o actualizar un diario de desempeño. El usuario recibe el error "No se puede crear un registro en la entrada del diario de rendimiento (HcmPerfJournal). Permiso de directiva de seguridad denegado". |
| 583077 | La fecha de nacimiento de un empleado en el calendario de licencias y ausencias de la empresa muestra una fecha incorrecta | Los usuarios podrán ver la fecha de nacimiento correcta de los empleados en el calendario de licencias y ausencias de la empresa. |
| 586996 | La función de visualización de permisos entre empresas hace que los saldos estén vacíos cuando el acceso está restringido a una sola empresa | Los usuarios pueden ver correctamente los saldos de licencias futuras de los empleados cuando la vista de licencias entre empresas está habilitada. |
| 581014 | Habilitar la vista de licencias y absentismos entre empresas provoca un error al visualizar saldos futuros | Los errores se han corregido cuando los usuarios veían los saldos de licencias futuras con la vista de licencias entre empresas habilitada. |
| 509404 | El análisis de la plantilla de departamento no tiene en cuenta el movimiento de empleados entre departamentos. | Cuando un empleado migra de un departamento a otro, los datos de la plantilla del departamento no reflejan el departamento antiguo desde el que se cambió el empleado si el detalle del puesto venció en el año actual. |
| 584851 | La regla de prorrateo del crédito de beneficios "Ninguno" nunca proporciona crédito |La regla de prorrateo de crédito flexible "Ninguno" dio como resultado que los empleados recibieran cero créditos durante el período de beneficios, independientemente de cuándo fueron contratados. Esto se ha corregido para que un empleado reciba créditos flexibles completos si es contratado antes de que comience el período de beneficios, y ninguno si es contratado después de que comience el período. |
| 584897 | Duplicar el deber 'Usar funcionalidad externa básica' da como resultado un error | Al intentar duplicar el deber 'Usar funcionalidad externa básica', el usuario recibió el error "No se pudo encontrar el objeto con el identificador UserDefinedAppHostDialogView". |
| 575692 | La licencia acumulada y la ausencia no están disponibles para los trabajadores pendientes | La acumulación de licencias y ausencias se puede ejecutar en futuras contrataciones cuando **Entrada de empleados simplificada** está habilitado. |
| 580110 | Agregar una empresa a la integración de nómina restablece la integración para usar todas las entidades incluso si la opción está configurada para no actualizar el proyecto | Si un cliente ha eliminado entidades o cambiado el proyecto de datos para la integración de nómina y tiene la opción configurada para evitar una actualización automática del proyecto, agregar una nueva empresa a la integración ignora la configuración y actualiza el proyecto.  |
| 584518 |Problema de rendimiento de procesamiento de beneficios de inscripción | Este error solucionó problemas de rendimiento en el proceso de inscripción de beneficios heredados. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Actualización de la plataforma 10.0.19 (43) | La actualización de la plataforma 10.0.19 está programada para comenzar a implementarse con la próxima versión de servicio el 28 de junio de 2021. Para obtener más información, consulte [Actualizaciones de plataforma para la versión 10.0.19 de aplicaciones de finanzas y operaciones (junio de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  Alternar visualización de años de servicio | Esta función ofrece la opción de usar diferentes fechas para calcular los años de servicio que se muestran en el formulario **Entrada de empleados simplificada** y en el formulario **Personas**.  Estará disponible en los parámetros de Recursos Humanos. |
|  Habilitar a un administrador de ausencias para administrar la licencia | [Habilitar a un administrador de ausencias para administrar la licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Adjuntos de mandato para tipos de licencia específicos | Esta característica permite a los administradores exigir que se agreguen archivos adjuntos al enviar solicitudes de baja para tipos de baja específicos. |
|  Configurar unidades de baja por tipo de baja | Esta función permite a los administradores configurar unidades de licencia (horas o días) para cada tipo de licencia.  |
| Permitir que los empleados se marquen como listos para recibir el pago | [Permitir que los empleados se marquen como listos para recibir el pago](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

