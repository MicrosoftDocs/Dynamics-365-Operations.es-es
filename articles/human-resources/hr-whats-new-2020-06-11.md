---
title: Novedades o cambios en Dynamics 365 Human Resources (11 de junio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 11 de junio de 2020.
author: andreabichsel
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6b0bb1c6d00cdd816534caddd83a71f2f0a3cc3
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054317"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Novedades o cambios en Dynamics 365 Human Resources (11 de junio de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3316. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>El formulario de empleados optimizado a veces hace que los botones de cierre de formulario secundario (X) dejen de funcionar (442369)

Cuando el nuevo formulario **Trabajador** fue habilitado, el botón de cierre (**X**) en ocasiones no funcionaba en formularios secundarios. Este problema era intermitente. Puede cerrar el formulario después de salir y volver a él. Por ejemplo, puede seleccionar un elemento del menú a la izquierda y volver al formulario **Trabajador** y luego ciérrelo. El lanzamiento de esta semana corrige este problema. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>La entidad de Persona de contacto personal del trabajador no exporta contactos personales con un tipo de relación principal

Con este lanzamiento, la entidad **Persona de contacto personal del trabajador** exporta todos los tipos de relación.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity debería formar parte del paquete de integración de nómina de Ceridian de forma predeterminada (448506)

Con este cambio, **HcmPositionWorkerAssignmentV2Entity** está incluido en el paquete de integración de nómina de Ceridian.

## <a name="in-preview"></a>En vista previa

## <a name="database-logging"></a>Registro de base de datos

La característica de registro de la base de datos le permite determinar qué tablas y campos se supervisan. También le permite determinar los eventos que deberían activar el seguimiento de cambios. Utiliza las capacidades de registro de bases de datos para ver estos cambios a lo largo del tiempo. Para más información, vea [Configurar y administrar el registro de bases de datos](hr-admin-database-logging.md).

## <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para más información, consulte [Aplicación de recursos humanos en Teams](./hr-admin-teams-leave-app.md). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades del marco de gestión de datos (DMF) para la gestión de ventajas
 
Las entidades de gestión de ventajas se están lanzando. Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas. Una plantilla de gestión de ventajas estará disponible para mover datos. La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.

## <a name="buy-and-sell-leave"></a>Comprar y vender bajas 

Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja. Este proceso a menudo se gestiona manualmente. Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos. Agiliza el proceso de gestión de bajas y ayuda a eliminar errores. Para obtener más información, consulte:

- [Gestionar directivas de compra y venta de bajas](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar y vender bajas](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Acumulación de bajas para una sola compañía o plan único

Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de licencia y ausencias. Esta capacidad proporciona transparencia en el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas. Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Agregar archivos adjuntos a las solicitudes de tiempo libre

La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19. Los empleados ahora pueden agregar estos archivos adjuntos. También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja. Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Agregar código de razón a las suspensiones acumuladas 

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="carry-forward-rules"></a>Transferir reglas 

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender la acumulación de bajas para los tipos de baja especificados

Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidad DMF disponible para suspensiones acumuladas 

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="coming-soon"></a>Próximamente

## <a name="new-platform-capabilities"></a>Nuevas capacidades de plataforma 

Podrá hacer que los campos sean obligatorios mediante la personalización. Esta función requerirá que habilite **Vistas guardadas**.

## <a name="configure-the-name-of-employee-self-service"></a>Configurar el nombre de Autoservicio para empleados

Una nueva opción estará disponible en los parámetros de Recursos humanos para actualizar el nombre del espacio de trabajo de autoservicio del empleado a Autoservicio. 

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]