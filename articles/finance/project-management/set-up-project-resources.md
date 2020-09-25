---
title: Configurar recursos del proyecto
description: Este tema proporciona información sobre cómo configurar o solicitar recursos del proyecto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760658"
---
# <a name="set-up-project-resources"></a>Configurar recursos del proyecto

[!include [banner](../includes/banner.md)]

Debe configurar un calendario y asociarlo a un empleado o un trabajador. El calendario se usa para programar el proyecto y el horario de trabajo de los recursos reservados para el proyecto. Durante la configuración del calendario, los directores de proyecto pueden realizar la nivelación de recursos como parte de la optimización de recursos. En función de la programación del calendario, se pueden aplicar restricciones en los recursos. Puede configurar un calendario en la página **Calendarios**.

Al configurar un trabajador como recurso de proyecto, puede seleccionar aquellos trabajadores que estén trabajando en la compañía para la que esté configurando recursos. Asimismo, puede seleccionar los trabajadores de otras empresas que formen parte de su organización. Estos trabajadores se conocen como recursos de empresas vinculadas.

Los procedimientos siguientes explican cómo configurar un trabajador como recurso del proyecto en la empresa y cómo configurar un recurso de proyecto de empresas vinculadas.

## <a name="set-up-a-worker-as-a-project-resource"></a>Configurar un trabajador como recurso de proyecto

1. En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el trabajador que va a agregar como recurso del proyecto y abra el registro de trabajador.
2. En el Panel de acciones, seleccione **Proyecto** &gt; **Configuración** &gt; **Configuración del proyecto**.
3. Seleccione un calendario y luego cierre la página.

También puede especificar los proyectos predeterminados para un recurso como un tipo de asignación previa. Las asignaciones previas se pueden utilizar cuando el director de recursos o el director de proyecto sabe en qué proyectos trabajará el recurso por adelantado. Las asignaciones previas también se pueden basar en la solicitud de un cliente o patrocinador de proyecto. Para asignar previamente un proyecto, en la página **Asignar proyectos**, en la ficha **Proyectos**, en la lista **Proyectos restantes**, seleccione el proyecto adecuado.

## <a name="set-up-an-intercompany-resource"></a>Configurar un recurso de empresas vinculadas

Al configurar un trabajador como recurso de empresas vinculadas, debe completar la configuración de la empresa de préstamo y la empresa que recibe el préstamo.

### <a name="in-the-lending-company"></a>En la empresa de préstamo

1. En Finance, compruebe que la empresa de préstamo esté seleccionada y, a continuación realice el procedimiento que se detalló en la sección anterior, “Configurar un trabajador como recurso de proyecto”.
2. En la página **Contabilidad de empresas vinculadas**, seleccione **Nuevo**.
3. En el campo **Id. de entidad jurídica**, seleccione la empresa de préstamo. Rellene los campos restantes según sea necesario y, a continuación seleccione **Guardar**.
4. En la página **Precio de transferencia**, seleccione **Nuevo**.
5. En el campo **Entidad jurídica a la que se presta el trabajador**, seleccione la empresa adecuada.
6. Si solo desea prestar a la empresa de solicitud del préstamo el recurso que ha creado al principio de esta sección, en el campo **Recurso**, seleccione el nombre de recurso que haya creado. Si desea que todos los recursos de la empresa estén a disposición de la empresa que solicita el préstamo, deje el campo **Recurso** en blanco.
7. Vaya a la página **Parámetros de administración de proyectos y contabilidad** en la pestaña **Empresas vinculadas** y establezca la opción **Activar la programación de recursos y las hojas de horas de empresas vinculadas** en **Sí**.

### <a name="in-the-borrowing-company"></a>En la empresa que solicita el préstamo

- En la página **Lista de recursos**, en el filtro de la búsqueda, escriba el nombre de recurso que creó para la empresa de préstamo y compruebe que el nombre está incluido en la lista de recursos de la empresa que solicita el préstamo.

## <a name="request-project-resources"></a>Solicitar recursos de proyecto
La funcionalidad de programación de recursos del proyecto solo admite a administradores de recursos para distribuir recursos de personal en compromisos o proyectos. Para habilitar esta funcionalidad, realice las tareas siguientes o compruebe que se hayan realizado:

- Configurar secuencias numéricas.
- Configuración de flujos de trabajo de Gestión de proyectos y contabilidad.
- Habilitar los flujos de trabajo de las solicitudes de recursos

Una vez que haya completado las tareas anteriores, puede completar las tareas siguientes según sea necesario:

- Cree una solicitud de recurso de un recurso con personal de reserva provisional.
- Supervise las solicitudes de recursos.
- Rellene las solicitudes de recursos.
- Solicite un recurso de personal de WBS.
- Reserve recursos para un proyecto sin tener un pedido de recurso de personal.
