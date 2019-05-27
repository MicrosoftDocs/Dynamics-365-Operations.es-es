---
title: Novedades y cambios en Dynamics 365 for Talent (6 de mayo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4830c5d626e5e10972c81c3445eb54e4b6b00e6c
ms.sourcegitcommit: 0400bfd66e98af50e64444a1c102575099a9312f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "1539414"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-6-2019"></a>Novedades y cambios en Dynamics 365 for Talent (6 de mayo de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="select-optional-documents-upon-offer-creation"></a>Seleccione documentos al crear la oferta

Al seleccionar una plantilla de paquete de la propuesta, ahora Attract le solicita para seleccionar los documentos opcionales, aplicables de esa plantilla de paquete. Puede agregar otros documentos opcionales mientras prepara la propuesta.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Onboard

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2282. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-26"></a>Actualización 26 de la plataforma

Para obtener más información acerca de la Platform update 26, consulte [Características de vista previa en Dynamics 365 for Finance and Operations platform update 26 (mayo de 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-26). 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Soporte de la entidad de Common Data Service para los campos personalizados

En la versión de esta semana, las entidades siguientes ahora admiten campos personalizados: Cálculo de frecuencia de prestación, Cálculo de tasa de prestación, Tipo de Prestación, calendario laboral, calendario festivo laboral, Ciclo de pago y tipos de identificación del trabajador.

### <a name="leave-mass-enrollment-changing-the-tier-basis-to-seniority-date-doesnt-refresh-the-initial-accrual-rate-318526"></a>Dejar inscripción masiva, cambiar la función del nivel “Fecha de antigüedad” no actualiza la tasa de inicio de la acumulación (318526)

Al inscribir en masa a empleados y cambiar la función del nivel, la acumulación inicial ahora refleja la base del nivel seleccionado.

### <a name="workflow-showing-duplicate-place-holders-313636"></a>El flujo de trabajo muestra marcadores de posición duplicados (313636)

Los cambios en esta versión eliminan la duplicación de marcadores de duplicación cuando se envían las notificaciones de flujo de trabajo.

### <a name="dimension-fields-arent-updated-when-using-open-in-excel-176261"></a>Los campos de dimensiones no se actualizan al utilizar “Abrir en Excel” (176261)

Con esta versión, ahora puede actualizar la dimensión financiera usando **Abrir en Excel** de la página **Trabajador** . 

### <a name="worker-address-created-in-common-data-service-isnt-synced-to-talent-317555"></a>La dirección del trabajador creada en Common Data Service no se sincroniza con Talent (317555)

Con este cambio, las direcciones creadas en Common Data Service se actualizan en Talent Core HR.


## <a name="in-preview"></a>En vista previa

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nueva página para validar datos de la jerarquía de puestos

Los recursos humanos (HR) y los administradores ahora pueden validar la jerarquía directiva para cualquier referencia circular que podría haber sido importada de forma inadvertida. Puede obtener acceso a esta nueva página desde **Administración de organización > Vínculos > Puestos > Validación de la jerarquía de puestos**.

### <a name="specify-reason-codes-on-leave-types"></a>Especificar códigos de motivo en tipos de baja

Las organizaciones pueden requerir información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para tipos de baja específicos y solicitudes de indisponibilidad

Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados envíen solicitudes de indisponibilidad. Este requisito podría existir debido a la directiva de la empresa o normas legales. Ahora puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Proporcionar una lista de baja y la transacción de ausencia para recursos humanos

La capacidad de seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos (RR.HH) a contestar las preguntas del empleado, también ayuda a garantizar proporcionar el tiempo de indisponibilidad preciso a los empleados. Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para que el personal de RR.HH. pueda ver las razones detrás de los saldos.

## <a name="coming-soon"></a>Próximamente

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indicar el tipo de instancia al aprovisionar Talent

Al aprovisionar una nueva instancia de Talent, podrá indicar si el tipo de instancia es **Producción** o **Espacio aislado**, permitiendo la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de la producción. Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.
