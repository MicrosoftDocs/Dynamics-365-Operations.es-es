---
title: Novedades o cambios en Dynamics 365 Human Resources 12 de julio de 2021
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 12 de julio de 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d2851c36594384dd62f4bb95263cfd4407aec104
ms.sourcegitcommit: 71952e97774547230285026c6a3a6caea2512920
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "6614842"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Novedades o cambios en Dynamics 365 Human Resources 12 de julio de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4353.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
|  Alternar visualización de años de servicio | |Esta función ofrece la opción de usar diferentes fechas para calcular los años de servicio que se muestran en la página **Entrada de empleados simplificada** y en la página **Personas**.  Estará disponible en los [parámetros de Recursos Humanos](/dynamics365/human-resources/hr-setup-parameters). |


### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Problema |  Descripción |
| --- | --- | --- |
| 595871 | El panel Acerca de en Recursos humanos tiene terminología Dataverse incorrecta | Con el cambio de marca de Common Data Service a Dataverse, la terminología se ha actualizado en el panel de información de Microsoft Dynamics 365 Human Resources (**Ayuda y soporte > Acerca de**). |
| 598676 | El formulario de entrada de empleados simplificado anula la tarea puede crear un error cuando se usa con Vista guardada| En la página **Trabajador** página, si la función 'Entrada simplificada de empleados' está activada, la aplicación puede fallar si **Siempre abierto para editar** se establece en la vista guardada. |
| 592344 |La sección de compensación de trabajadores sobre el puesto debe leerse solo cuando la administración de beneficios está habilitada | La información de compensación de trabajadores se crea utilizando la funcionalidad de beneficios heredados.  Cuando la gestión de prestaciones está habilitada, los campos serán de solo lectura. Cuando la gestión de prestaciones está activada y **Ocultar formularios de prestaciones heredados** se establece en **Sí** en los parámetros compartidos de recursos humanos, la pestaña **Compensación de trabajadores** se ocultará. |
| 598617 | **HcmDiscusión** La pestaña de activación de formularios provoca un bucle infinito cuando se aplican personalizaciones | Cuando tanto la vista de cuadrícula como de detalles **Siempre abierto para editar** están activados, el código que activa la pestaña en el método de tarea anulado entra en conflicto con la personalización sobre qué control debería tener el foco y crea un bucle infinito. |
| 593553 | El campo de fecha del diario en el diario de rendimiento se muestra en UTC | El campo **Fecha del diario** de los diarios de rendimiento se muestra en la zona horaria UTC en lugar de en la zona horaria definida en la configuración de la fecha del sistema, lo que hace que la fecha sea incorrecta para algunas zonas horarias. |
| 586930 | Abrir actividades para objetivos de desempeño abre un registro completamente diferente | Cuando la función 'Vista de informes extendidos de Diarios de rendimiento' está habilitada en Gestión de funciones, la selección de los objetivos de rendimiento para los informes ampliados en la pestaña **Mi equipo** en **Autoservicio para los empleados** abre los objetivos para un empleado en lugar del empleado seleccionado. |
| 569959 |  La entidad HcmPositionWorkerAssignmentV2 no asigna un trabajador a un puesto | Los usuarios recibieron un error al agregar un registro de asignación de puesto a través de la entidad y la publicación falló. |
| 582259 | El informe VETS 4212 utiliza el formulario de 2017 en lugar del formulario de 2020 | Actualizado al formato 2020.  Para cargar el nuevo formato, vaya a **Configuraciones de informes** y elimine el informe VETS-4212 en la columna de la izquierda. Ir a **Informes electrónicos - Repositorios - Recursos de recursos humanos** y seleccione **Abrir**.  Seleccione **Impresión PDF VETS-4212** y luego seleccione **Importar**.|


## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|
|  Habilitar a un administrador de ausencias para administrar la licencia | [Habilitar a un administrador de ausencias para administrar la licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [Configurar el rol de administrador de ausencias](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  Configurar los requisitos de archivos adjuntos por tipo de licencia | [Configurar los requisitos de archivos adjuntos por tipo de licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurar unidades de baja por tipo de baja | [Configurar unidades de baja por tipo de baja](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permitir que los empleados se marquen como listos para recibir el pago | [Permitir que los empleados se marquen como listos para recibir el pago](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Listo para pagar](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Actualización de la plataforma 10.0.20 (44) | La actualización de la plataforma 10.0.20 está programada para comenzar a implementarse con la próxima versión de servicio el 26 de julio de 2021. Para obtener más información, consulte [Platform updates para la versión 10.0.20 de aplicaciones de Finance and Operations (agosto de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20). |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
