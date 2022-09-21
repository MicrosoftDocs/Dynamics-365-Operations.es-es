---
title: Control de encabezado de trabajador
description: Este artículo proporciona información sobre el control de encabezado personalizable en el autoservicio de empleados, en el centro de personas y en la página del trabajador en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2867a952df79161aaee657dbc3df1f3298294dd5
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445954"
---
# <a name="worker-header-control"></a>Control de encabezado de trabajador

Microsoft Dynamics 365 Human Resources proporciona un control de encabezado personalizable en el **Autoservicio de empleados**, en el centro de **Personas** y en la página **Trabajador**. El encabezado contiene información clave sobre el trabajador y también acciones de un solo clic, como enviar correos electrónicos, llamar o enviar mensajes. El encabezado se puede modificar eliminando campos o agregando campos, incluidos campos personalizados, para mostrar información adicional. Para usar el nuevo control de encabezado, vaya a **Administración de características** y habilite característica **Control de encabezado de trabajador**.

## <a name="personalization"></a>Personalización

Uno de los beneficios clave del control del encabezado del trabajador es la capacidad de personalizar la información que aparece en el encabezado.

En la parte superior derecha del encabezado hay un grupo de tres campos que muestran diferentes datos, según el estado del empleado. Este grupo de campos se conoce como la parte destacada del encabezado. Puede personalizar la parte destacada del encabezado eliminando los campos actuales o agregando campos. Los campos que se pueden agregar a la parte de Spotlight en el control de encabezado difieren para **Autoservicio para los empleados**, centro **Personas**, y la página **Trabajador**.

## <a name="employee-self-service"></a>Autoservicio para empleados

El encabezado del trabajador en la página **Autoservicio para los empleados** contiene la siguiente información:

- Nombre del trabajador
- Número de personal
- Título de cargo
- Departamentos
- Tipo de trabajador
- Entidad jurídica del empleo
- Años de servicio
- Informa a (administrador)
- Tipo de puesto

El encabezado también contiene una acción de un solo clic para editar la información personal de la persona. Seleccione **Editar detalles personales** para abrir la página **Información personal** en **Autoservicio para los empleados**.

## <a name="people-hub"></a>Centro de personas

El encabezado del trabajador en el centro **Personas** (la página **Espacio de trabajo de personas**) contiene la siguiente información:

- Nombre del trabajador
- Número de personal
- Título de cargo
- Departamentos
- Tipo de trabajador
- Entidad jurídica del empleo
- Años de servicio
- Informa a (administrador)
- Tipo de puesto

El encabezado también contiene acciones de un solo clic, como enviar correos electrónicos, llamar o enviar mensajes. Si un usuario está viendo su propia información en la página **Espacio de trabajo de personas**, la sección de acción de un solo clic incluye el botón **Editar detalles personales**. El usuario puede seleccionar este botón para abrir la página **Información personal** en **Autoservicio para los empleados**.

## <a name="streamlined-worker-page"></a>Página de trabajador optimizada

El encabezado del trabajador en la página simplificada **Trabajador** contiene la siguiente información:

- Nombre del trabajador
- Número de personal
- Título de cargo
- Departamentos
- Tipo de trabajador
- Entidad jurídica del empleo

Según el estado del empleado, los datos del encabezado pueden cambiar. Por ejemplo, si el empleado ha salido de la empresa, el control de encabezado contiene una credencial **Salido**, la fecha de terminación del empleo y el motivo de la terminación.

La siguiente tabla muestra los datos que aparecen en el encabezado para diferentes estados de empleados.

| Estado del empleado | Datos que se muestran | Nota |
|-----------------|--------------------|------|
| Pendiente | <ul><li>Name</li><li>Número de personal</li><li>Título de cargo</li><li>Departamento</li><li>Tipo de trabajador</li><li>Entidad jurídica</li><li>Insignia pendiente</li><li>Fecha inicial</li><li>Notifica a</li><li>Tipo de puesto</li></ul> | |
| Contratación reciente | <ul><li>Name</li><li>Número de personal</li><li>Título de cargo</li><li>Departamento</li><li>Tipo de trabajador</li><li>Entidad jurídica</li><li>Insignia de contratación reciente</li><li>Años de servicio</li><li>Notifica a</li><li>Tipo de puesto</li></ul> | Por defecto, la insignia **Contratación reciente** se muestra para los empleados que han sido contratados en los últimos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, en el campo **Intervalo de fechas de Contrataciones recientes**, introduzca un plazo de tiempo. Por ejemplo, para ver la lista de empleados con la insignia **Contratación reciente** que fueron contratados en los últimos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**. |
| Empleado activo | <ul><li>Name</li><li>Número de personal</li><li>Título de cargo</li><li>Departamento</li><li>Tipo de trabajador</li><li>Entidad jurídica</li><li>Fecha inicial</li><li>Notifica a</li><li>Tipo de puesto</li></ul> | |
| Fin del empleo | <ul><li>Name</li><li>Número de personal</li><li>Título de cargo</li><li>Departamento</li><li>Tipo de trabajador</li><li>Entidad jurídica</li><li>Insignia de salida</li><li>Años de servicio</li><li>Notifica a</li><li>Tipo de puesto</li></ul> | Por defecto, la insignia **Saliendo** se muestra para los empleados que se irán en los próximos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, en el campo **Intervalo de fechas de trabajador saliente**, introduzca un plazo de tiempo. Por ejemplo, para ver la lista de empleados con la insignia **Saliendo** que van a salir en los próximos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**. |
| Desvinculado | <ul><li>Insignia de salida</li><li>Número de personal</li><li>Fecha final del empleo</li><li>Código de motivo</li></ul> | Por defecto, la insignia **Salido** se muestra para los empleados que se han ido en los últimos siete días. Para cambiar esta configuración, en la página **Parámetros de recursos humanos**, en la pestaña **General**, en el campo **Intervalo de fechas de trabajadores que han salido**, introduzca un plazo de tiempo. Por ejemplo, para ver la lista de empleados con la insignia **Salido** que han salido en los últimos 14 días, configure el campo **Período** como **14** y el campo **Unidad** como **Días**. |
