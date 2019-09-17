---
title: Novedades y cambios en Dynamics 365 for Talent (14 de marzo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/14/2019
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
ms.search.validFrom: 2019-03-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ee8e076174acba8e706991f3086d6299a10945ec
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742502"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-14-2019"></a>Novedades y cambios en Dynamics 365 for Talent (14 de marzo de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
En esta versión se incluyen correcciones de errores menores.

## <a name="changes-in-onboarding"></a>Cambios en Onboarding
En esta versión se incluyen correcciones de errores menores.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
**Compilación 8.1.2186**

### <a name="performance-management-not-working-in-all-scenarios-when-using-duplicate-security-roles"></a>La gestión del rendimiento no funciona en todas las situaciones al utilizar roles de seguridad duplicados
Los cambios realizados en esta versión habilitan escenarios de gestión del rendimiento al utilizar el listo para usar o roles duplicados.

### <a name="mass-assign-checklists-to-workers"></a>Asignar listas de comprobación en masa a los trabajadores
Con este cambio, ahora puede seleccionar varios empleados y asignar en masa una o varias listas de comprobación a dichos empleados. 

### <a name="platform-update-24"></a>Actualización 24 de la plataforma
Para obtener detalles adicionales sobre la actualización 24 de la plataforma, consulte [Novedades o cambios en la actualización 24 de la plataforma Finance and Operations (marzo de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24) Cambios relevantes incluidos en la plataforma 24: 

- Las alertas se habilitan en Talent.
- La barra de navegación actualizada ahora se alínea con el encabezado de Oficina.

### <a name="office-location-update-switches-the-context-to-the-top-of-the-worker-list"></a>La actualización de la ubicación de Oficina cambia el contexto a la parte superior de la lista del trabajador
Con la versión actual, cambiar la ubicación de la oficina no va a intercambiar más el contexto del trabajador que está viendo cuando le asigne una ubicación de la oficina.

### <a name="position-assignment-end-date-doesnt-display-correctly-on-worker-hire-and-transfer-actions"></a>La fecha final de la asignación de puesto no se muestra correctamente en las acciones de contratación y transferencia del trabajador
Las fechas finales de la asignación de puesto ahora se muestran correctamente según la zona horaria preferida usuario al utilizar acciones.

### <a name="common-data-service-job-entity-doesnt-allow-job-type-and-job-function-fields-to-update"></a>La entidad de trabajo Common Data Service no permite la actualización de los campos tipo de trabajo y función de trabajo
Las entidades Common Data Service ahora se sincronizan correctamente cuando se actualizan mediante Common Data Service.

## <a name="coming-soon"></a>Próximamente

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Seguridad de compensación avanzada (fija y variable)
En muchas organizaciones, los administradores de compensación y prestaciones solo pueden tener acceso a ciertos registros de compensación. Estos puede ser para ejecutivos o empleados regionales. Con este cambio, Recursos Humanos puede administrar y mantener los planes de compensación para distintos grupos de empleados en la organización. Puede asignar roles de seguridad a los planes fijos y variables, lo que determinará el acceso a los planes y los datos del empleado relacionados con los planes, como el salario y los registros de bonificaciones. Solo los roles con acceso concedido pueden procesar la compensación para estos empleados.

###  <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos
Con Platform update 24, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento.

### <a name="duplicate-employee-check-interface-changes"></a>Comprobación de empleado duplicado: cambios en la interfaz
Con este cambio, se detectan los duplicados a medida que se especifican los campos de nombre, y un estado muestra cuántos se han encontrado. Puede seleccionar el vínculo proporcionado para abrir una nueva página para evaluar si utilizar la coincidencia detectada. Para evitar interrumpir la entrada de datos, el formulario de los duplicados no se abre automáticamente.
