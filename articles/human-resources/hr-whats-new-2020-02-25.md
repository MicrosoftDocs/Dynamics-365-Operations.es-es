---
title: Novedades y cambios en Dynamics 365 Human Resources (25 de febrero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 25 de febrero de 2020.
author: andreabichsel
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dc79c464f74961fd431f1d42583e4dcd67c30fb9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790413"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (25 de febrero de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.2927. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Habilitar la navegación de Administración de caso y el marco de administración de datos (DMF) de la entidad (414754)

Esta característica de vista previa permite una navegación adicional a casos de administración de casos. Puede habilitar esta característica de vista previa en el espacio de trabajo **Gestión de funciones**. Estos elementos de menú aparecen en el espacio de trabajo **Conformidad** de Dynamics 365 Human Resources. Con este cambio, Human Resources puede acceder a:

- Todos los casos
- Mis casos
- Mis casos abiertos
- Mis casos vencidos
- Casos asignados a mí mediante el flujo de trabajo

Junto con estas nuevas vistas de casos, también está disponible la entidad DMF **Detalle del caso**.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Habilitar definiciones de relación en la libreta de direcciones global (414762)

Las relaciones ahora están habilitadas en la libreta de direcciones global. Antes del lanzamiento de esta semana, el cuadro de información **Relación** de hechos mostraba las relaciones definidas por el sistema. Ahora puede definir esas relaciones dentro de la página de la libreta de direcciones global.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>Se puede eliminar una posición cuando existen registros de compensación activos para la posición (414568)

Con este cambio, aparece una advertencia cuando intenta eliminar un puesto y un trabajador tiene un registro de compensación activo para ese mismo puesto. Cuando esto sucede, debe actualizar el registro de compensación fija del empleado antes de eliminar el puesto.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>El flujo de trabajo de revisión de rendimiento ocasionalmente agrega aprobaciones de personas que no forman parte del proceso (414171)

Este cambio corrige un problema en el que se agregan participantes adicionales a la revisión del desempeño.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>Asignación de puesto de trabajo no creada en Dataverse cuando se selecciona en el cuadro de diálogo Nuevo trabajador (413479)

Este cambio corrige un problema cuando se contrata a un nuevo trabajador y se asigna al nuevo empleado a un puesto a través del diálogo **Nuevo trabajador**. Ahora la asignación de posición se refleja en Dataverse.

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

Durante las próximas semanas, estos cambios de entidad estarán disponibles en todos los entornos. Para instalar manualmente la última solución de Dataverse para Human Resources:

1.  Vaya al [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2.  Seleccione **entornos**.

3.  Encuentre el entorno que desea actualizar. Esto debería corresponder a **Nombre del entorno** en la sección **Información de Common Data Service** en el formulario **Acerca de** en Human Resources.

4.  Seleccione el entorno para ver los detalles del entorno.

5.  En la barra de acciones de la parte superior, seleccione **Administrar soluciones**. Se abrirá una nueva ventana del navegador y navegará al **Centro de administración de Dynamics 365** en el contexto de su entorno.

6.  En la lista **Solución**, seleccione **Delimitar Dynamics 365 Human Resources**.

7.  Seleccione **Actualizar** para aplicar la última solución.

## <a name="in-preview"></a>En vista previa

Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:

- **Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]