---
title: Novedades y cambios en Dynamics 365 Human Resources (19 de marzo de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 19 de marzo de 2020.
author: Darinkramer
manager: AnnBe
ms.date: 03/19/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 902539a5abecba6ad99718afbb37613838450032
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526874"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (19 de marzo de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3014. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte para referencia de Lifecycle Services (LCS).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Los límites del entorno de Human Resources ahora se basan en licencias actualizadas (394595)

El límite en la cantidad de entornos por proyecto en Lifecycle Services (LCS) ha cambiado. El límite anterior era dos entornos. El límite en la cantidad de entornos de producción y espacio aislado que puede crear para Human Resources en LCS ahora se basa en licencias actualizadas. Ahora puede crear tantos entornos como sea necesario por proyecto LCS, dependiendo de la cantidad de licencias compradas. La nueva licencia, actualizada el 1 de febrero de 2020, permite a los clientes comprar entornos adicionales. Para obtener más información sobre los requisitos de licencia para entornos adicionales, consulte [Guía de licencias de Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>Proporcionar una visión cruzada de los datos de compensación de la compañía para empleados y gerentes (403904)

Active esta función en el el espacio de trabajo **Administración de características**. Para obtener más información sobre características de vista previa, consulte [Habilitar o deshabilitar características de vista previa](hr-admin-manage-features.md#enable-or-disable-preview-features).

Cuando habilita esta función, los gerentes pueden ver la compensación de informes directos y extendidos sin tener que iniciar sesión en la empresa de empleo. El historial de compensación completo está disponible desde cualquier empresa que haya iniciado sesión a la que pueda acceder el gerente. Para más información, consulte [Resumen de autoservicio para empleados y gerentes](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>Habilitar la funcionalidad de combinación de libreta de direcciones global (427189)

Ahora puede combinar entradas duplicadas de la libreta de direcciones seleccionando los registros duplicados y eligiendo **Unir** desde la página **Libreta de direcciones global**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>No se puede ajustar el saldo de vacaciones para un plan sin acumulación que se creó con la función Tipo de licencia múltiple activada (419635)

Ahora puede ajustar los saldos para los planes de vacaciones que se crearon con la característica de vista previa **Tipo de licencia múltiple** habilitada en la gestión de funciones.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>Campo de posición principal en WorkerPositionAssignmentEntity cuando un empleado es despedido (420774)

Para los empleados con un empleo terminado, la posición principal que estaba activa en el momento de la terminación se muestra en la entidad. Para las integraciones, ya no se creará un registro duplicado para la asignación del puesto de trabajo del empleado. 

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>La solución Common Data Service ahora está disponible con los siguientes cambios:

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
| Nueva entidad **Cargo** | <ul><li>**Cargo** agregado</li></ul>La nueva entidad **Cargo** está incluida en Common Data Service pero no se hace referencia desde las entidades **Puesto de trabajo** o **Trabajo** en este momento. |

> [!NOTE]
> Las dimensiones financieras tanto para los puestos como para el empleo proporcionan una integración en una dirección para actualizaciones desde Human Resources a Common Data Service. Actualmente las actualizaciones de dimensiones financieras no se sincronizan desde Common Data Service a Human Resources.

Durante las próximas semanas, estos cambios de entidad estarán disponibles en todos los entornos. Para instalar manualmente la última solución de Common Data Service para Human Resources:

1.  Vaya al [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2.  Seleccione **entornos**.

3.  Encuentre el entorno que desea actualizar. El entorno debería corresponder a **Nombre del entorno** en la sección **Información de Common Data Service** en el formulario **Acerca de** en Human Resources.

4.  Seleccione el entorno para ver los detalles del entorno.

5.  En la barra de acciones de la parte superior, seleccione **Administrar soluciones**. Se abrirá una nueva ventana del navegador y navegará al **Centro de administración de Dynamics 365** en el contexto de su entorno.

6.  En la lista **Solución**, seleccione **Delimitar Dynamics 365 Human Resources**.

7.  Seleccione **Actualizar** para aplicar la última solución.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>La vista previa SharePoint no funciona en algunos entornos

Si la vista previa del documento para documentos almacenados en SharePoint no funciona, intente el siguiente procedimiento:

1. Verifique que la cuenta de usuario administrador tenga un correo electrónico asociado con el registro de usuario. Puede ver esta información en la página **Usuario**. Si el correo electrónico no está configurado, debe agregar el correo electrónico y el proveedor con el complemento OData Excel. Por defecto, la dirección de correo electrónico no está presente en el diseño de Excel. Deberá editar el diseño de Excel, agregar todos los campos, aplicar y actualizar. Una vez que haya completado esos pasos, puede actualizar la cuenta de administrador.

2. Una vez que la cuenta de administrador tenga una cuenta de correo electrónico asociada, inicie sesión en Human Resources con credenciales de administrador.

3. Acceda a un archivo adjunto en SharePoint para comenzar la vista previa del documento.

4. Inicie sesión con otra cuenta de usuario que tenga acceso a los archivos adjuntos y verifique que la vista previa funcione como se esperaba.

## <a name="coming-soon"></a>Próximamente

### <a name="platform-update-33"></a>Platform update 33

- Aplicaciones de página completa (Vista previa): esta característica de vista previa, que requiere que habilite la función Vistas guardadas, permite a Power Apps y aplicaciones de terceros agregarse como experiencias de página completa a través del panel de control.

- Vistas guardadas (vista previa): esta característica de vista previa permite vistas guardadas, lo cual proporciona una mejora significativa para el subsistema de personalización. Esta característica permite a los usuarios tener múltiples conjuntos de personalizaciones con nombre por página. También puede publicar vistas en roles de seguridad.

- Optimizado "es una de" experiencia de filtrado: esta característica permite una experiencia de filtrado optimizada "es uno de" que facilita la entrada de múltiples valores de filtro, tiene un mecanismo más simple para eliminar valores de filtro individuales o todos, y tiene un diseño más compacto e intuitivo visualización de valores de filtro.

- Campos recomendados: los usuarios a menudo necesitan agregar campos a una cuadrícula o página. Esto puede ser difícil con tantos campos disponibles. En lugar de tener que buscar en una lista grande, esta función permite que el sistema muestre un conjunto de campos recomendados en función de lo que otros usuarios a menudo agregan en escenarios similares.

- Acciones predeterminadas fijas en cuadrículas: esta función garantiza que la acción predeterminada en una cuadrícula esté vinculada a una columna específica en una cuadrícula, independientemente de si esa columna se mueve u oculta.

## <a name="new-production-release-cadence"></a>Nueva cadencia de lanzamiento de producción

A partir de abril, la cadencia de lanzamiento de Human Resources cambiará de una actualización semanal a una actualización quincenal. Esto asegurará la alineación con prácticas de implementación seguras y mantendrá altos estándares de estabilidad y fiabilidad en el servicio. Estamos implementando pruebas y supervisiones adicionales para verificar la implementación exitosa en cada etapa del proceso. Para obtener más información sobre la cadencia de lanzamiento, vea [Proceso de actualización](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>En vista previa

Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:

- **Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)