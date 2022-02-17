---
title: Espacio de trabajo de administración de personal
description: Este tema describe los elementos conceptuales del espacio de trabajo de Gestión de personal.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7a83dea308e3e2eec1edebd5d619f9455e1a2268
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066584"
---
# <a name="personnel-management-workspace"></a>Espacio de trabajo de administración de personal


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

El espacio de trabajo **Gestión de personal** incluye una gran cantidad de contenido. Contiene movimientos de personal, rastrea cambios de empleados, posiciones abiertas, cambios de dirección, registros que vencen y análisis, y proporciona enlaces a información específica. Este tema proporciona información detallada acerca de cada parte del espacio de trabajo.

## <a name="activity-tab"></a>Pestaña de actividad

La pestaña **Actividad** contiene secciones que agrupan a los trabajadores según su etapa en el proceso de empleo:

- **Candidatos pendientes de contratación**
- **Comienza pronto**
- **Contrataciones recientes**
- **Fin del empleo**
- **Desvinculados**

Cuando un trabajador se encuentra en una de estas etapas, las acciones específicas están disponibles como un botón en la tarjeta o en el menú que aparece al seleccionar los puntos suspensivos (**...**) en la esquina superior derecha. Las siguientes subsecciones describen las secciones de la pestaña **Actividad** y enumeran las acciones que están disponibles.

### <a name="candidates-to-hire"></a>Candidatos pendientes de contratación

La sección **Candidatos a contratar** del espacio de trabajo se completa a partir de varias fuentes:

- Una entidad de protocolo de datos abiertos (OData)
- Integración de LinkedIn
- Datos que se ingresan manualmente en el producto

Cuando los candidatos aparecen en la sección **Candidatos a contratar**, puede realizar las siguientes acciones seleccionando los puntos suspensivos en la tarjeta de candidato:

- **Descartar candidato**
- **No contratar**
- **Contratación**

> [!NOTE]
> Si la lista de candidatos se completa desde Microsoft Dataverse, se mostrarán los mismos candidatos en todas las entidades jurídicas porque no se ha asociado ninguna entidad jurídica al candidato.

### <a name="starting-soon"></a>Comienza pronto

La sección **Comenzando pronto** enumera los trabajadores que tienen una fecha de inicio en el futuro. La lista se ordena por fecha de inicio. La fecha de inicio más cercana a los datos de hoy aparece en primer lugar.

Si el gerente no aparece en la tarjeta, no se ha asignado un puesto para el trabajador.

> [!NOTE] 
> Le recomendamos que asigne un puesto a un trabajador antes de aplicar una lista de verificación. A veces, las tareas de incorporación se asignan al gerente de un empleado recién contratado. Sin embargo, si no se asigna ningún puesto, no se puede determinar el gerente del nuevo empleado. En ese caso, las tareas de incorporación que están destinadas al gerente se asignarán al propietario de la lista de verificación.

Cuando los trabajadores aparecen en la sección **Comenzando pronto**, las siguientes acciones están disponibles para ellos:

- Asignar puesto
- Comprobar empleo
- Asignar compensación fija
- Asignar compensación variable
- Ver en jerarquía
- Aplicar lista de comprobación\*\*

\*\* Esta acción es la acción predeterminada. Aparece como un botón en la tarjeta.

### <a name="recent-hires"></a>Contrataciones recientes

La sección **Contrataciones recientes** enumera los trabajadores que tienen una fecha de inicio en el pasado reciente. La lista se ordena por fecha de inicio. La fecha de inicio más cercana a los datos de hoy aparece en primer lugar.

De forma predeterminada, la lista muestra a los trabajadores que fueron contratados en los últimos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, defina un marco de tiempo para **Contrataciones recientes**. Los datos en la sección **Contrataciones recientes** se pueden mostrar para un número específico de días, meses o años. Por ejemplo, para ver la lista de trabajadores que fueron contratados en los últimos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**.

> [!NOTE]
> La configuración de la página **Parámetros de recursos humanos** es específica de la empresa. Por lo tanto, el período de tiempo para el que ve las contrataciones recientes puede variar según la empresa. Por ejemplo, en la empresa USMF, es posible que desee ver todas las nuevas contrataciones de los últimos siete días. Sin embargo, en la empresa USSI, es posible que desee ver todas las nuevas contrataciones de los últimos 14 días. En este caso, abra la página **Parámetros de recursos humanos** en cada empresa y configure los parámetros según sea necesario.

Si el gerente no aparece en la tarjeta, no se ha asignado un puesto para el trabajador.

Cuando los trabajadores aparecen en la sección **Contrataciones recientes**, las siguientes acciones están disponibles para ellos:

- Asignar puesto
- Comprobar empleo
- Compensación fija
- Asignar compensación variable
- Ver en jerarquía
- Aplicar lista de comprobación\*\*

\*\* Esta acción es la acción predeterminada. Aparece como un botón en la tarjeta.

### <a name="exiting"></a>Fin del empleo

La sección **Con fin del empleo** enumera los trabajadores que tienen una fecha de terminación inicio en el futuro. La lista se ordena por fecha de terminación. La fecha de terminación más cercana a los datos de hoy aparece en primer lugar. 

De forma predeterminada, la lista muestra a los trabajadores que tienen una fecha de terminación en los próximos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, defina un marco de tiempo para **Vistas de los trabajadores que salen**. Los datos en la sección **Salientes** se pueden mostrar para un número específico de días, meses o años. Por ejemplo, para ver la lista de trabajadores que terminarán en los próximos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**.

Cuando los trabajadores aparecen en la sección **Salientes**, las siguientes acciones están disponibles para ellos:

- Aplicar lista de comprobación\*\*
- Comprobar empleo
- Ver en jerarquía

\*\* Esta acción es la acción predeterminada. Aparece como un botón en la tarjeta.

### <a name="exited"></a>Desvinculados

La sección **Con salida** enumera los trabajadores que tienen una fecha de terminación en el pasado reciente. La lista se ordena por fecha de terminación. La fecha de terminación más cercana a los datos de hoy aparece en primer lugar.

De forma predeterminada, la lista muestra a los trabajadores que tienen una fecha de terminación en los últimos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, defina un marco de tiempo para **Vistas de los trabajadores que se han ido**. Los datos en la sección **Con salida** se pueden mostrar para un número específico de días, meses o años. Por ejemplo, para ver la lista de trabajadores que fueron despedidos en los últimos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**.

Cuando un trabajador aparece en la sección **Con salida**, las siguientes acciones están disponibles para ellos:

- Aplicar lista de comprobación\*\*
- Comprobar empleo
- Ver en jerarquía

\*\* Esta acción es la acción predeterminada. Aparece como un botón en la tarjeta.

## <a name="employee-changes-tab"></a>Pestaña de cambios de empleados

La pestaña **Cambios de empleados** proporciona una lista de todas las acciones del personal de los trabajadores. Esta lista no está disponible de forma predeterminada. Para habilitar la funcionalidad, en la página **Parámetros compartidos de recursos humanos**, en la pestaña **Acciones de personal**, establezca la opción **Habilitar acciones de los trabajadores** como **Sí**.

## <a name="position-changes-tab"></a>Pestaña de cambios de posición

La pestaña **Cambios de puesto** proporciona una lista de todas las acciones del personal de los puestos. Esta lista no está disponible de forma predeterminada. Para habilitar la funcionalidad, en la página **Parámetros compartidos de recursos humanos**, en la pestaña **Acciones de personal**, establezca la opción **Habilitar acciones de puestos** como **Sí**.

## <a name="open-positions-tab"></a>Pestaña Vacantes

La pestaña **Puestos abiertos** enumera todas las posiciones abiertas. Para aparecer en la lista, los puestos deben tener una fecha de activación de hoy o anterior, y no deben tener una asignación de trabajador actual.

> [!NOTE]
> La lista considera la asignación de trabajadores a partir de hoy. Cualquier puesto que tenga una asignación de trabajador con fecha futura seguirá apareciendo en la lista. Sin embargo, una vez alcanzada la fecha de vigencia de la asignación de trabajador, el puesto se eliminará de la lista.

## <a name="expiring-records-tab"></a>Pestaña de registros vencidos

La pestaña **Registros que caducan** enumera todos los elementos que han caducado o caducarán para los trabajadores de la empresa en la que el usuario inició sesión. Las siguientes elementos aparecen en la lista:

- **Certificados**
- **Identificación**
- **Períodos de prueba**
- **Filtrados**
- **Pruebas**

Para especificar si la lista muestra registros vencidos o registros vencidos, en la página **Parámetros de recursos humanos**, en la pestaña **General**, defina un marco de tiempo para **Expedientes que caducan** o **Registros caducados**. Los datos en la pestaña **Expedientes que caducan** se pueden mostrar durante un número específico de días. Por ejemplo, para ver la lista de registros que vencerán en los próximos 14 días, configure el campo **Número de días** como **14**.

> [!NOTE] 
> Si establece el marco de tiempo para **Registros caducados** o **Expedientes que caducan** como **0** en la página **Parámetros de recursos humanos**, la lista no mostrará ninguno de esos registros.

## <a name="employees-tile"></a>Icono de empleados

El icono **Empleados** proporciona un recuento de todos los empleados que están empleados en la empresa en la que el usuario está conectado actualmente. Cuando selecciona el icono **Empleados**, una nueva página muestra los detalles de los empleados.

## <a name="contractors-tile"></a>Icono para contratistas

El icono **Contratistas** proporciona un recuento de todos los contratistas que están empleados en la empresa en la que el usuario está conectado actualmente. Cuando selecciona el icono **Contratistas**, una nueva página muestra los detalles de los contratistas.

## <a name="open-positions-tile"></a>Icono Vacantes

El icono **Vacantes** proporciona un recuento de todas las posiciones abiertas. Cuando selecciona el icono **Vacantes**, una nueva página muestra los detalles de las vacantes. Para incluirse en el recuento, los puestos deben tener una fecha de activación de hoy o anterior, y no deben tener una asignación de trabajador actual.

> [!NOTE]
> El icono considera la asignación de trabajadores a partir de hoy. Cualquier puesto que tenga una asignación de trabajador con fecha futura se seguirá incluyendo en el recuento. Sin embargo, una vez alcanzada la fecha de vigencia de la asignación de trabajador, el puesto se excluirá del recuento.

## <a name="approvals-tile"></a>Icono de aprobaciones

El icono **Aprobaciones** proporciona un recuento de todos los elementos del flujo de trabajo que están pendientes de la aprobación del usuario actual. Cuando selecciona el icono **Aprobaciones**, una nueva página muestra los detalles de los elementos del flujo de trabajo que requieren su aprobación.

## <a name="address-changes-tile"></a>Icono de cambios de dirección

El icono **Cambios de dirección** proporciona un recuento de todos los cambios de dirección que ocurrieron durante el número de días que se especifica en la página **Parámetros de recursos humanos**. Al seleccionar la ventana **Cambios de dirección**, se muestra una nueva página que muestra los detalles de cambios de dirección. En la esquina superior derecha de la página, puede seleccionar **Incluir futuros cambios de dirección** en la esquina superior derecha para mostrar los cambios de dirección con una fecha futura.

Para obtener más información sobre cómo ver y administrar los cambios de dirección, consulte [Ver y administrar cambios de dirección](hr-personnel-view-address-changes.md).
