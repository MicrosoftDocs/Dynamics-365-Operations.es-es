---
title: Novedades y cambios en Dynamics 365 Human Resources (7 de febrero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 7 de febrero de 2020.
author: andreabichsel
ms.date: 02/07/2020
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
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 70acaaf2218c8b5c0239b968a29a927ac23080f0
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060848"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (7 de febrero de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.2835. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>El análisis de aprendizaje no muestra el curso si el aula está en blanco (388289)

La página de análisis de aprendizaje ahora muestra el curso si el aula está vacía.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>La búsqueda de posición no tiene en cuenta la zona horaria (405344)

La búsqueda de posiciones abiertas ahora tiene en cuenta la zona horaria al validar si una posición está abierta.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>La vista de análisis de saldo actual no se actualiza con el saldo correcto de licencias actual tras las solicitudes de permisos (409756)

El saldo actual ahora incluye las solicitudes de permisos enviadas.

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