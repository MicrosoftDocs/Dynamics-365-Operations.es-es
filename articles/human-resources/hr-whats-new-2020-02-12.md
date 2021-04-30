---
title: Novedades y cambios en Dynamics 365 Human Resources (12 de febrero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 12 de febrero de 2020.
author: andreabichsel
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0d5991f23723056d7ee766c00ed0f4ee16ff0f85
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890943"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (12 de febrero de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.2867. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>Las entidades existentes CompFixedEmpls y HcmPersonImage deben ser accesibles desde OData (414178)

Con el lanzamiento de esta semana, las entidades **CompFixedEmpls** y **HcmPersonImage** ahora son públicas y están disponibles a través de ODAta.

## <a name="delete-employment-from-dataverse-doesnt-work-when-employment-details-arent-active-403193"></a>Eliminar empleo de Dataverse no funciona cuando los detalles de empleo no están activos (403193)

Este cambio ahora permite eliminar el empleo a través de Dataverse cuando no existen detalles de empleo activo.

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>El flujo de trabajo de registro del curso cambia de estado a completo y errores después de la segunda aprobación (409749)

El flujo de trabajo de registro del curso se ha actualizado para permitir múltiples aprobadores.

## <a name="in-preview"></a>En vista previa

Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:

- **Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Próximamente

### <a name="platform-update-32"></a>Actualización 32 de la plataforma 

Platform update 32 estará disponible pronto. [Obtener más información sobre Platform update 32 aquí](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).

### <a name="updated-dataverse-solution"></a>Solución Dataverse actualizada

Una nueva solución Dataverse estará disponible pronto con los siguientes cambios:

| Descripción | Cambio |
| ----------------------------------------- | --- |
| La entidad **Puesto de trabajo** cambia | Se ha agregado **Región de compensación**</br>Se ha agregado **Dimensiones financieras** |
| La entidad **Trabajador** cambia | Se ha agregado **Orden del nombre**</br>Se ha agregado **Trabaja desde casa**</br>Se ha agregado **Idioma**</br>Se ha agregado **Antigüedad**</br>Se ha agregado **Fecha de aniversario**</br>Se ha agregado **Fecha de contratación original** |
| La entidad **Empleo** cambia | Se ha agregado **Dimensiones financieras**</br>Se ha agregado **Razón de la finalización**</br>**Fecha de finalización** ha cambiado de nombre a **Fecha de transición**</br>Se ha agregado **Fechas del período de pruebas** |
| La entidad **Dirección del trabajador** cambia | Se ha agregado **Dirección postal**</br>**Línea de dirección 1**, **Línea de dirección 2** y **Línea de dirección 3** marcadas para eliminación |
| Nuevas entidades de configuración de compensación variable | **Tipo de plan de compensación variable**</br>**Plan de compensación variable**</br>**Reglas de atribución**</br>**Nivel de plan de compensación variable** |
| Nueva entidad **Empleo de calendario de trabajador** | Se ha agregado la entidad **Calendario de trabajo** |
| Nueva entidad **Detalle de puesto de nómina** | **Detalle de puesto de nómina** agregado |
| Nueva entidad **Cargo** | **Cargo** agregado. La nueva entidad **Título** se incluirá en el proceso de sincronización entre Recursos Humanos y Dataverse. No será referenciado inicialmente desde las entidades **Puesto de trabajo** o **Trabajo**. |

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]