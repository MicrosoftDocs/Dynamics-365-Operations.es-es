---
title: Novedades y cambios en Dynamics 365 for Talent (27 de febrero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/27/2019
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
ms.search.validFrom: 2019-02-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d8e6a02b43ad60e3a0c4382f98cb808066587da7
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519014"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-27-2019"></a>Novedades y cambios en Dynamics 365 for Talent (27 de febrero de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Onboard

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2163

### <a name="add-a-custom-fields-menu-item-to-system-administration"></a>Se ha agregado un elemento de menú de campos personalizados a Administración del sistema

Se ha agregado exploración al menú **Campos personalizados** al área de trabajo **Administración del sistema**.

### <a name="hide-the-import-and-create-options-for-new-mobile-applications"></a>Se han ocultado las opciones de importación y creación para las nuevas aplicaciones móviles

Actualmente, las nuevas aplicaciones móviles no se pueden crear en Talent. La opción de crear nuevas experiencias móviles se ha quitado del menú **Aplicación móvil**.

### <a name="variable-compensation-award-dmf-entity"></a>Prima de compensación variable (entidad DMF)

En esta versión, una entidad de del marco de gestión de datos (DMF) **Prima de compensación variable** está disponible ahora para la exportación.

### <a name="uk-addresses-appear-in-the-personnel-management-analytics-page-as-swiss-addresses"></a>Las direcciones del Reino Unido aparecen en la página de Analytics de administración del personal como direcciones suizas

En esta versión, las direcciones se muestran por ciudad. Esta versión corrige los problemas de visualizaciones que presentaban mal la ubicación de un empleado.

### <a name="the-workforce-power-bi-report-shows-an-error-when-a-workers-seniority-date-is-on-leap-day"></a>El informe de Workforce Power BI muestra un error cuando la fecha de antigüedad de un trabajador cae en 29 de febrero

Una corrección se ha creado en Microsoft Power BI para tener en cuenta las fechas de antigüedad que caen el 29 de febrero.

### <a name="employee-fixed-compensation-employee-variable-awards-employee-variable-plans-enrollments-allow-for-custom-fields"></a>La compensación fija del empleado, las primas variables del empleado, los planes variables del empleado (inscripciones) permiten campos personalizados

Ahora se pueden añadir campos personalizados para la compensación fija del empleado, las primas variables del empleado y los planes variables del empleado (inscripciones). Ahora puede realizar un seguimiento de más información sobre los planes de compensación del empleado fijos y variales, además de la información que está disponible de forma predeterminada. Los campos personalizados se pueden especificar y actualizar a través de la interfaz de usuario o a través de entidades que se le ofrecen.

### <a name="other-miscellaneous-bug-fixes"></a>Otras correcciones de errores diferentes

Este lanzamiento incluye otras correcciones de errores menores.

## <a name="coming-soon"></a>Próximamente

### <a name="advanced-compensation-security-fixed-and-variable"></a>Seguridad de compensación avanzada (corregida y variable)

En muchas organizaciones, los administradores de compensación y prestaciones pueden tener acceso solo a registros de compensación específicos. Estos registros pueden ser para ejecutivos o empleados regionales. Este cambio dejará que los recursos humanos (HR) administren y mantengan los planes de compensación para diferentes grupos de empleados en la organización. Los roles de seguridad que se pueden asignar a los planes fijos y variables determinarán el acceso a dichos planes y los datos de los empleados relacionados con ellos (por ejemplo, información de sueldo y registros de bonificaciones). Solo los roles que tienen el acceso especificado podrán procesar la compensación para dichos empleados.

### <a name="platform-update-24"></a>Actualización 24 de la plataforma

Para obtener más información acerca de la actualización 24 de la plataforma Microsoft Dynamics 365 for Finance and Operations, consulte [Características de vista previa en la actualización 24 de la plataforma Finance and Operations (marzo de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).

### <a name="make-employee-fixed-compensation-available-for-future-position-assignments"></a>Haga que la compensación fija del empleado esté disponible para las asignaciones de puesto futuras

Es típico que los empleados que entran en una organización tengan una fecha de inicio futura. Este cambio dejará que la compensación fija se defina para los empleados que tienen asignaciones de puesto futuras.

## <a name="known-issues"></a>Problemas conocidos

### <a name="changes-to-the-core-hr-integration-template-talent-common-data-service-to-finance-and-operations"></a>Cambios en la plantilla de integración de Core HR (Talent Common Data Service a Finance and Operations)
La plantilla de Core HR se ha actualizado a una "plantilla avanzada de consulta”. Por lo tanto, de forma predeterminada, la consulta avanzada estará disponible para proyectos creados con esta plantilla. Además, cualquier función de asignación predeterminada sólo se mostrará en el editor de consultas avanzado. (Las funciones de asignación predeterminadas aparecen como “FN” en las asignaciones.)

Para obtener más información sobre los errores de asignación, consulte [Novedades o cambios en Dynamics 365 for Talent Core HR (14 de diciembre de 2018)](https://docs.microsoft.com/dynamics365/unified-operations/talent/whats-new-talent-december-14).

Para usar la plantilla nueva, cree un nuevo proyecto, y seleccione la nueva plantilla de integración de Talent.

Para actualizar la plantilla existente, siga estos pasos.

1. Actualice las asignaciones siguientes:

    - **Puestos de trabajo a puestos:** Elimine esta asignación.
    - **Asignación de puestos de trabajo a la tarea principal de puestos:** Elimine esta asignación.
    - **Puestos de trabajo a puesto base:** Agregue una nueva asignación desde la entidad de Common Data Service **Puestos de trabajo** a la entidad **Puesto base** de Finance and Operations. Muévala al puesto 7 en la secuencia.

        [![Asignación de puestos de trabajo a puesto base](./media/CDS-Mapping1.png)](./media/CDS-Mapping1.png)

    - **Detalles de puestos de trabajo a puesto:** Agregue una nueva asignación desde la entidad de Common Data Service **Puestos de trabajo** a la entidad **Detalles de puesto** de Finance and Operations. Muévala al puesto 8 en la secuencia.

        [![Asignación de detalles de puestos de trabajo a puesto](./media/CDS-Mapping2.png)](./media/CDS-Mapping2.png)

    - **Duraciones de puestos de trabajo a puesto:** Agregue una nueva asignación desde la entidad de Common Data Service **Puestos de trabajo** a la entidad **Duraciones de puesto** de Finance and Operations.

        [![Asignación de duraciones de puestos de trabajo a puesto](./media/CDS-Mapping3.png)](./media/CDS-Mapping3.png)

    - **Jerarquías de puestos de trabajo a puesto:** Agregue una nueva asignación desde la entidad de Common Data Service **Puestos de trabajo** a la entidad **Jerarquías de puesto** de Finance and Operations. Seleccione **Consulta avanzada** para que su consulta avanzada esté disponible para el proyecto.

       [![Botón de consulta avanzada](./media/CDS-Advanced-Query.png)](./media/CDS-Advanced-Query.png)

2. Agregue las asignaciones siguientes.
    
    [![Distribución](./media/CDS-Mapping4.png)](./media/CDS-Mapping4.png)

    1. cdm_jobpositionnumber cdm_jobspositionnumb... = POSITIONID cdm_parentjobpositionid.cdm-jobpositionnumb... = PARENTPOSITIONID cdm_validfrom cdm_validfrom = VALIDFROM cdm_validto cdm_validto = VALIDTO
       
    2. Seleccione el vínculo **Consulta y filtrado avanzados** junto del campo **Buscar**.  

    3. Encuentre la columna **cdm_parentjobpositionid.cdm_jobpositionnumber**, y seleccione el botón de flecha hacia abajo en su lado derecho.

    4. En el cuadro de diálogo que aparece, seleccione **Quitar vacío**.

    5. Seleccione **Agregar columna \> Agregar columna condicional** para agregar una transformación del valor predeterminado para HIERARCHYTYPENAME.

        [![Agregar comando de columna condicional](./media/Add-column.png)](./media/Add-column.png).

    6. En el cuadro de diálogo **Agregar columna condicional**, especifique **HIERARCHYTYPENAME** como nombre de la nueva columna.
    7. En la parte **Si** de la condición, seleccione cualquier campo, use **igual a** como relación, y especifique cualquier valor. En las partes ***Entonces** y **Si no** de la condición, especifique lo que debe ser el valor predeterminado. En este caso, especifique **Línea** en ambas partes.

        [![Cuadro de diálogo Agregar columna condicional](./media/Add-conditional-column.png)](./media/Add-conditional-column.png)

    8. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Consulta y filtrado avanzados**.
    9. En la página **Asignar tarea**, seleccione la nueva columna como el origen para crear otra asignación para HIERARCHYTYPENAME.

        [![Distribución](./media/CDS-Mapping5.png)](./media/CDS-Mapping5.png)
