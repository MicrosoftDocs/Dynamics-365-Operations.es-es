---
title: Novedades y cambios en Dynamics 365 Human Resources (10 de marzo de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 10 de marzo de 2020.
author: andreabichsel
ms.date: 03/10/2020
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
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 296e11befb0dc916faab2eb0388188852bc3ceb6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051122"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (10 de marzo de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.2985. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>No se puede acceder al informe de análisis de lagunas de habilidades (394460)

Este informe no se admite en Dynamics 365 Human Resources. Se elimina el elemento del menú para imprimir el informe SSRS.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Mensaje incorrecto al acceder a la página de Inicio (417950)

Con este cambio, la seguridad oculta este elemento del menú si no tiene acceso al formulario.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Mantenimiento de tareas simplificado para empleados (380538)

El formulario de mantenimiento de tareas de los trabajadores enumera todas las tareas para un empleado a través de la incorporación, la exclusión, las transiciones y los procesos comerciales. Ahora puede eliminar, reasignar o actualizar el estado de las tareas.

Ejemplo: Benjamin Martin es un administrador de beneficios. Durante la incorporación de los empleados, se crean tareas para que Benjamin revise la selección de beneficios del nuevo empleado. Benjamin tiene tareas pasadas que ha completado y tareas futuras que debe completar. Benjamin decide abandonar la empresa, por lo que sus tareas deben reasignarse o eliminarse. El formulario de mantenimiento de tareas (en el Panel Acciones del **Trabajador**) permite que todas las tareas de Benjamin se reasignen a otro trabajador o se eliminen.  

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>La solución Dataverse ahora está disponible con los siguientes cambios:

| Descripción | Cambio |
| --- | --- |
| La entidad **Puesto de trabajo** cambia | <ul><li>Se ha agregado **Región de compensación**</li>|
| **Dimensión del puesto de trabajo** entidad agregada | <ul><li>Se ha agregado **Dimensiones financieras**</li>
| La entidad **Trabajador** cambia | <ul><li>Se ha agregado **Orden del nombre**</li><li>Se ha agregado **Trabaja desde casa**</li><li>Se ha agregado **Idioma**</li><li>Se ha agregado **Antigüedad**</li><li>Se ha agregado **Fecha de aniversario**</li><li>Se ha agregado **Fecha de contratación original**</li></ul> |
| La entidad **Empleo** cambia | <ul><li>Se ha agregado **Dimensiones financieras**</li><li>Se ha agregado **Razón de la finalización**</li><li>**Fecha de finalización** ha cambiado de nombre a **Fecha de transición**</li><li>Se ha agregado **Fechas del período de pruebas**</li></ul> |
| La entidad **Dirección del trabajador** cambia | <ul><li>Se ha agregado **Dirección postal**</li><li>**Línea de dirección 1**, **Línea de dirección 2** y **Línea de dirección 3** marcadas para eliminación</li></ul> |
| Nuevas entidades de configuración de compensación variable | <ul><li>**Tipo de plan de compensación variable**</li><li>**Plan de compensación variable**</li><li>**Reglas de atribución**</li><li>**Nivel de plan de compensación variable**</li></ul> |
| Nueva entidad **Empleo de calendario de trabajador** | <ul><li>Se ha agregado la entidad **Calendario de trabajo**</li></ul> |
| Nueva entidad **Detalle de puesto de nómina** | <ul><li>**Detalle de puesto de nómina** agregado</li></ul> |
| Nueva entidad **Cargo** | <ul><li>**Cargo** agregado</li></ul> La nueva entidad **Cargo** está incluida en Dataverse pero no se hace referencia desde las entidades **Puesto de trabajo** o **Trabajo** en este momento. |

> [!NOTE]
> Las dimensiones financieras tanto para los puestos como para el empleo proporcionan una integración en una dirección para actualizaciones desde Human Resources a Dataverse. Actualmente las actualizaciones de dimensiones financieras no se sincronizan desde Dataverse a Human Resources.

Durante las próximas semanas, estos cambios de entidad estarán disponibles en todos los entornos. Para instalar manualmente la última solución de Dataverse para Human Resources:

1.  Vaya al [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2.  Seleccione **entornos**.

3.  Encuentre el entorno que desea actualizar. El entorno debería corresponder a **Nombre del entorno** en la sección **Información de Dataverse** en el formulario **Acerca de** en Human Resources.

4.  Seleccione el entorno para ver los detalles del entorno.

5.  En la barra de acciones de la parte superior, seleccione **Administrar soluciones**. Se abrirá una nueva ventana del navegador y navegará al **Centro de administración de Dynamics 365** en el contexto de su entorno.

6.  En la lista **Solución**, seleccione **Delimitar Dynamics 365 Human Resources**.

7.  Seleccione **Actualizar** para aplicar la última solución.

## <a name="in-preview"></a>En vista previa

Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:

- **Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Próximamente

### <a name="platform-update-33"></a>Platform update 33

- Aplicaciones de página completa (Vista previa): esta característica de vista previa, que requiere que habilite la función Vistas guardadas, permite a Power Apps y aplicaciones de terceros agregarse como experiencias de página completa a través del panel de control.

- Vistas guardadas (vista previa): esta característica de vista previa permite vistas guardadas, lo cual es una mejora significativa para el subsistema de personalización. Esta característica permite a los usuarios tener múltiples conjuntos de personalizaciones con nombre por página. También puede publicar vistas en roles de seguridad.

- Optimizado "es una de" experiencia de filtrado: esta característica permite una experiencia de filtrado optimizada "es uno de" que facilita la entrada de múltiples valores de filtro, tiene un mecanismo más simple para eliminar valores de filtro individuales o todos, y tiene un diseño más compacto e intuitivo visualización de valores de filtro.

- Campos recomendados: los usuarios a menudo necesitan agregar campos a una cuadrícula o página. Esto puede ser difícil con tantos campos disponibles. En lugar de tener que buscar en una lista grande, esta función permite que el sistema muestre un conjunto de campos recomendados en función de lo que otros usuarios a menudo agregan en escenarios similares.

- Acciones predeterminadas fijas en cuadrículas: esta función garantiza que la acción predeterminada en una cuadrícula esté vinculada a una columna específica en una cuadrícula, independientemente de si esa columna se mueve u oculta.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]