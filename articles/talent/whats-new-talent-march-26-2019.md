---
title: Novedades y cambios en Dynamics 365 for Talent (26 de marzo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
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
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 24070d1efa3299c378d7a4a328531817a598d272
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741576"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-26-2019"></a>Novedades y cambios en Dynamics 365 for Talent (26 de marzo de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="enhancements-to-interview-scheduling"></a>Mejoras en la programación de la entrevista
Las siguientes mejoras están disponibles en la programación de la entrevista.

- Los reclutadores o el administrador de contratación ahora pueden elegir también activar un recordatorio manual para que un entrevistador envíe comentarios. La plantilla de correo electrónico asociada del aviso también se puede configurar.
- A medida que comparte el resumen de la entrevista con el candidato, el programador de la entrevista puede elegir ocultar los nombres de los entrevistadores y también ocultar filas de la vista resumen de la entrevista.

## <a name="changes-in-onboard"></a>Cambios en Onboard

### <a name="embedded-images-in-activities"></a>Imágenes incrustadas en actividades
Ahora puede insertar imágenes directamente en actividades. Además de poder copiar y pegar imágenes de la Web, puede cargar imágenes del sistema de archivos local. El tamaño de la actividad está limitado a 1 MB. Si la imagen es demasiado grande, cambie el tamaño e intente para cargarla de nuevo.

[![Distribución](./media/embedimages.png)](./media/embedimages.png)

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Onboard

## <a name="changes-in-core-hr"></a>Cambios en Core HR
**Compilación 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Compatibilidad con campo personalizado disponible para entidades selectas en Common Data Service 

Las siguientes entidades de Common Data Service ahora son compatibles con los campos de cliente creados en Dynamics 365 for Talent:

- Trabajador
- Origen étnico
- Estado de excombatiente
- Código de idioma
- Puesto
- Tipo de trabajo
- Función de trabajo
- Posición
- Tipo de puesto
 
### <a name="employment-history-not-displayed-chronologically"></a>Historial de empleo no presentado cronológicamente
Con este cambio, la página historial de empleo ahora muestra los registros de empleo cronológicamente, independientemente de la empresa. También puede usar opciones de ordenación para clasificar por empresa.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>Los planes de compensación fija no aparecen al limitar el usuario de la empresa en seguridad.
En este lanzamiento, los planes de compensación fija aparecen al limitar usuarios por empresa en seguridad. Todas las configuraciones de seguridad se cumplirán y los planes fijos aparecerán para las empresas a las que el usuario tiene permisos para acceder. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>No puede eliminar los registros de trabajos mediante Abrir de la opción de Excel en Talent
Con esta versión, ahora puede quitar los registros de trabajos mediante la opción **Abrir en Excel** en Dynamics 365 for Talent.

### <a name="upgrade-to-common-data-service"></a>Actualice a Common Data Service
Las fechas límites para actualizarse a Common Data Service se acercan rápidamente. Inicie sesión en el centro de gestión de PowerApps para determinar si su base de datos debe actualizarse. Para obtener más información acerca de las fechas límites y de los pasos necesarios para realizar la actualización, consulte [Actualizar a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>En vista previa

Para obtener información sobre cómo habilitar características de vista previa, consulte [Acceso a las funciones de vista preliminar en Talent](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir a los códigos de motivo ser especificados en los tipos de baja
Las organizaciones pueden necesitar información adicional relacionada con las solicitudes de indisponibilidad. Para obtener esta información, los empleados deben incluir un código de motivo en sus solicitudes de indisponibilidad. Con esta versión, ahora puede especificar códigos de motivo asociados a un tipo concreto de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Configurar códigos de motivo para que se requiera registrar indisponibilidad para ciertos de tipos de baja
Las organizaciones pueden requerir que se especifiquen los códigos de motivo ser establecido en tipos específicos de baja cuando los empleados registran indisponibilidad. Esto puede requerirse por una norma legal de su país/región o una directiva de la empresa. Esta versión proporciona la capacidad para que Recursos Humanos especifique qué tipos de baja requieren un código de motivo. Esto se aplica cuando los empleados registran solicitudes de indisponibilidad en los que la baja requiere un código de motivo.

## <a name="coming-soon"></a>Próximamente

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Seguridad de compensación avanzada (fija y variable)
En muchas organizaciones, los administradores de compensación y prestaciones solo pueden tener acceso a ciertos registros de compensación. Estos puede ser para ejecutivos o empleados regionales. Con este cambio, Recursos Humanos puede administrar y mantener los planes de compensación para distintos grupos de empleados en la organización. Puede asignar roles de seguridad a los planes fijos y variables, lo que determinará el acceso a los planes y los datos del empleado relacionados con los planes, como el salario y los registros de bonificaciones. Solo los roles concedidos con acceso pueden procesar la compensación para estos empleados.

###  <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos
Con Platform update 25, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Comprobaciones duplicadas por empleado: cambios de la interfaz de usuario
Con este cambio, se detectan los duplicados a medida que se especifican los campos de nombre, y un estado muestra el número de duplicados encontrado. Puede seleccionar el vínculo proporcionado para abrir una nueva página para evaluar si utilizar la coincidencia detectada. Para evitar interrumpir la entrada de datos, el formulario de los duplicados no se abre automáticamente.
