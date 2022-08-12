---
title: Novedades y cambios en Dynamics 365 Human Resources (18 de febrero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 18 de febrero de 2020.
author: andreabichsel
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec7d8dbc73dce57d3968c4d239a51d27673a2493
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066295"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (18 de febrero de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.2903. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="platform-update-32"></a>Actualización 32 de la plataforma 

La Platform update 32 ya está disponible. Para obtener más información, consulte [Novedades o cambios en Platform update 32 para finanzas y operaciones (febrero de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>Los valores de búsqueda se recuerdan al cambiar las opciones de vista en forma de empleado optimizada (383833)

El nuevo formulario **Trabajador** ahora recuerda los valores de búsqueda cuando cambia las opciones de vista y aplica los cambios.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>Los mosaicos de resumen de administración de compensación en la característica de vista previa redirigen a un formulario incorrecto (401861)

Los mosaicos de administración de compensación fija y variable ahora muestran los registros correctos en el nuevo formulario **Trabajador**. Se aplica solo a la función optimizada de vista previa del formulario de empleado. Puede habilitar esta característica de vista previa en **Gestión de funciones**. Para obtener más información, vea [Administrar funciones](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a>Campo de estado vacío para algunos registros de solicitud de licencia en Dataverse (414915)

Este cambio corrige un problema en Dataverse cuando el campo **Estado** en una solicitud de baja se establece en **Revisión**. Dataverse ahora refleja el estado.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>El análisis de lagunas de habilidades solo es posible para el trabajo asignado (411390)

Ahora puede hacer un análisis de lagunas de habilidades en cualquier trabajo definido en Recursos Humanos.

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a>La divisa del sistema no se sincroniza desde Dataverse a Recursos humanos en nuevos entornos (418011)

La divisa del sistema en Dataverse ahora se puede sincronizar con Recursos humanos.

## <a name="in-preview"></a>En vista previa

- [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Característica de vista previa: administración de prestaciones](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Próximamente

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
