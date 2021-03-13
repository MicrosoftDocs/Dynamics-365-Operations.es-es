---
title: Novedades y cambios en Dynamics 365 Human Resources (3 de abril de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 3 de abril de 2020.
author: andreabichsel
manager: tfehr
ms.date: 04/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b00ef61cdd7ceac6c6f57187a0e6c98e94c8cb71
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127930"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-3-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (3 de abril de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3111. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte para referencia de Lifecycle Services (LCS).

## <a name="features-that-are-generally-available-the-week-of-april-6"></a>Funciones que generalmente están disponibles la semana del 6 de abril

- **Características de bajas y ausencias** - Para obtener más información, consulte [Vista general de bajas y de ausencias](hr-leave-and-absence-overview.md).

- **Características de gestión de beneficios** - Para obtener más, consulte [Visión general de los beneficios](hr-benefits-management-overview.md).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Los límites del entorno de Human Resources ahora se basan en licencias actualizadas (394595)

El límite en la cantidad de entornos por proyecto en LCS ha cambiado. El límite anterior era dos entornos. El límite en la cantidad de entornos de producción y espacio aislado que puede crear para Human Resources en LCS ahora se basa en licencias actualizadas. Ahora puede crear tantos entornos como sea necesario por proyecto LCS, dependiendo de la cantidad de licencias compradas. La nueva licencia, actualizada el 1 de febrero de 2020, permite a los clientes comprar entornos adicionales. Para obtener más información sobre los requisitos de licencia para entornos adicionales, consulte [Guía de licencias de Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).
 
## <a name="error-when-trying-to-delete-a-questionnaire-428603"></a>Error al intentar eliminar un cuestionario (428603)

La actualización de esta semana corrige un problema en el que se muestra el siguiente error al intentar eliminar un cuestionario:

Se ha detectado un par X ++ TTSBEGIN / TTSCOMMIT desequilibrado.

## <a name="performance-journal-and-professional-certificates-security-issue-428499"></a>Diario de rendimiento y problema de seguridad de certificados profesionales (428499)

Este cambio limita la visibilidad de las revistas de rendimiento y los certificados profesionales en función de las empresas a las que tienen acceso. 

## <a name="the-abbreviation-for-quebec-and-manitoba-387510"></a>La abreviatura de Quebec y Manitoba (387510)

Los datos iniciales se han actualizado para reflejar la abreviatura correcta para Manitoba y Quebec.

## <a name="new-entities-available-in-data-management-framework"></a>Nuevas entidades disponibles en el marco de gestión de datos

Ahora están disponibles las siguientes entidades. Si no ve estas entidades en la lista de entidades, use la opción **Actualizar entidades** en **Parámetros del marco> Configuración de la entidad> Actualizar lista de entidades**.

 - Transacción bancaria de bajas y ausencias V2
 - Inscripción en bajas y ausencias V2
 - Nivel de plan de bajas y ausencias V2
 - Plan de bajas y ausencias V2

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
| Nueva entidad **Cargo** | <ul><li>**Cargo** agregado</li></ul>La nueva entidad **Cargo** está incluida en Dataverse pero no se hace referencia desde las entidades **Puesto de trabajo** o **Trabajo** en este momento. |

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

## <a name="leave-suspension"></a>Dejar suspensión

Puede suspender la baja y la ausencia en Human Resources para un empleado. La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados. Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la baja creará un ajuste prorrateado al saldo de baja del empleado. Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Transferir reglas

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="coming-soon"></a>Próximamente

## <a name="new-production-release-cadence"></a>Nueva cadencia de lanzamiento de producción

A partir de abril, la cadencia de lanzamiento de Human Resources cambiará de una actualización semanal a una actualización quincenal. Para garantizar la alineación con prácticas de implementación seguras y mantener altos estándares de estabilidad y fiabilidad en el servicio, el proceso de implementación de actualizaciones del servicio en todas las regiones será una implementación de dos semanas. Pruebas y supervisiones adicionales verificarán la implementación exitosa en cada etapa del proceso. Para obtener más información sobre la cadencia de lanzamiento, vea [Proceso de actualización](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Problemas conocidos

## <a name="employment-detail-entity"></a>Entidad Detalle de empleo

La entidad **Detalle de empleo** ha sido actualizada con los siguientes campos: **Frecuencia de pago**, **Id. de categoría de empleo**, **Tipo de empleo**, **Id. de tipo de empleo** y **Estado de prestación de empleo**. Los datos de configuración para estos campos dependen de que la gestión de prestaciones esté habilitada en la Gestión de características. Estos campos no deberían rellenarse o actualizarse en la entidad **Detalle de empleo**, porque provocará errores durante la importación.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>La vista previa SharePoint no funciona en algunos entornos

Si la vista previa del documento para documentos almacenados en SharePoint no funciona, intente el siguiente procedimiento:

1. Verifique que la cuenta de usuario administrador tenga un correo electrónico asociado con el registro de usuario. Puede ver esta información en la página **Usuario**. Si el correo electrónico no está configurado, debe agregar el correo electrónico y el proveedor con el complemento OData Excel. Por defecto, la dirección de correo electrónico no está presente en el diseño de Excel. Deberá editar el diseño de Excel, agregar todos los campos, aplicar y actualizar. Una vez que haya completado esos pasos, puede actualizar la cuenta de administrador.

2. Una vez que la cuenta de administrador tenga una cuenta de correo electrónico asociada, inicie sesión en Human Resources con credenciales de administrador.

3. Acceda a un archivo adjunto en SharePoint para comenzar la vista previa del documento.

4. Inicie sesión con otra cuenta de usuario que tenga acceso a los archivos adjuntos y verifique que la vista previa funcione como se esperaba.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)