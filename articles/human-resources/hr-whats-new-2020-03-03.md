---
title: Novedades y cambios en Dynamics 365 Human Resources (3 de marzo de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 3 de marzo de 2020.
author: andreabichsel
ms.date: 03/03/2020
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e2c6b54638a6541e4d3c802accb1440a754edd94b4a23336d799c4e6f4e61e09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722592"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (3 de marzo de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.2955. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>La solución Dataverse ahora está disponible con los siguientes cambios:

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

3.  Encuentre el entorno que desea actualizar. El entorno debería corresponder a **Nombre del entorno** en la sección **Información de Common Data Service** en el formulario **Acerca de** en Human Resources.

4.  Seleccione el entorno para ver los detalles del entorno.

5.  En la barra de acciones de la parte superior, seleccione **Administrar soluciones**. Se abrirá una nueva ventana del navegador y navegará al **Centro de administración de Dynamics 365** en el contexto de su entorno.

6.  En la lista **Solución**, seleccione **Delimitar Dynamics 365 Human Resources**.

7.  Seleccione **Actualizar** para aplicar la última solución.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>Problemas de importación con la entidad de datos de inscripción de licencia (406082)

Ahora puede inscribir a un empleado en un nuevo plan de vacaciones del mismo tipo, siempre que la nueva fecha de inscripción sea posterior a la fecha de inscripción vencida del plan anterior.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>Problema con las tasas de contribución a la exportación en la entidad 401k payrollWorkerEnrolledBenefitDetail en DMF (420700)

Este cambio corrige la funcionalidad de exportación para la entidad **payrollWorkerEnrolledBenefitDetail** para reflejar los valores actuales de la contribución del empleador.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>La búsqueda en el formulario de trabajador optimizado provoca un mensaje que dice que se debe completar el campo Persona (402525)

Cuando busque un empleado, ya no recibirá un mensaje que indique que debe completar el campo **Persona**.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>El valor del campo de nota no se muestra en el formulario Agregar más habilidades (380134)

Este cambio corrige un problema cuando personaliza el formulario **Agregar más habilidades** en Autoservicio para empleados.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>Los planes de compensación fija múltiple no caducan cuando se transfieren empleados (389466)

Con este cambio, todos los registros activos de compensación fija para la posición anterior caducarán en la fecha de transición.

## <a name="in-preview"></a>En vista previa

Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:

- **Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]