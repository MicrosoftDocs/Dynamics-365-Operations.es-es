---
title: Crear un proyecto nuevo
description: En este tema se proporciona información sobre cómo crear un proyecto nuevo.
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
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760653"
---
# <a name="create-a-new-project"></a>Crear un proyecto nuevo

[!include [banner](../includes/banner.md)]

Complete los siguientes pasos para crear un proyecto nuevo.

1. En la página **Administración de proyectos**, seleccione **Nuevo proyecto** y especifique los valores siguientes:

    - **Tipo de proyecto:** Tiempo y material
    - **Nombre del proyecto:** Fase 2 de la actualización XYZ
    - **Grupo de proyectos:** TM\_WIP
    - **Id. de contrato de proyecto:** 00000002

2. Seleccione **Crear proyecto**.

## <a name="assign-a-resource-to-a-project"></a>Asignar un recurso a un proyecto

1. En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el registro del trabajador para el que ha configurado anteriormente las competencias y abra el registro de trabajador.
2. En el panel de acciones, en la pestaña **Proyecto**, en el grupo **Configuración**, seleccione **Asignar proyectos**.
3. En la página **Asignaciones de proyecto de validación de recursos**, en la pestaña **Proyectos** del campo **Agregar el proyecto a los proyectos seleccionados**, filtre el proyecto **Fase 2 de la actualización XYZ**.
4. En el panel **Proyectos restantes**, seleccione un proyecto y, a continuación, haga clic en el botón de la flecha para agregarlo al panel **Proyectos seleccionados**.

Si es necesario, también puede asignar categorías para un recurso. El tipo de categoría es **Coste** o **Ingresos**. La organización es la que se encarga de determinar el tipo de categoría. Si no hay categorías asignadas para el recurso, Finance buscará la categoría predeterminada en los precios de hora para costes e ingresos.

## <a name="set-up-project-resource-and-role-characteristics"></a>Configurar características de rol y recursos de proyectos

Un director de proyecto puede usar la funcionalidad de recursos de proyecto para crear los roles que se requieren para el proyecto. Los roles se pueden usar cuando los recursos confirmados son aún desconocidos cuando estos se reservan. Los roles se pueden reservar temporalmente como recursos planeados, de manera que pueda continuar las etapas de planificación de proyectos.

[![Ejemplo de rol](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Escenario:** Se contrató a Contoso para completar un proyecto de tiempo y material que tiene una acta de constitución de proyecto aprobada. El director de proyecto junior aún está completando el ámbito del proyecto. El responsable de recursos está identificando actualmente recursos específicos que se reservarán para trabajar en el nuevo proyecto. Debido a la naturaleza fundamental de proyecto, uno de los roles que el patrocinador de proyecto solicitó, es el de director de proyecto principal. El director de recursos debe adquirir el nuevo recurso y definir el rol en el sistema, en el caso de que el director de proyecto junior requiera la información del recurso durante la planificación del proyecto.

Los siguientes pasos muestran cómo el director de recursos puede configurar el rol de director de proyecto principal y asociarle características de recursos. Más adelante, el rol se puede usar para buscar los recursos disponibles que coinciden con las competencias de recursos necesarias.

1. En la página **Configurar roles**, seleccione **Nuevo** y especifique los valores siguientes:

    - **Id. de rol:** Director de proyecto principal
    - **Descripción:** Director de proyecto principal

2. Seleccione **Crear**.
3. Seleccione el rol **Director de proyecto principal** y, a continuación, haga clic en **Configurar características**.
4. En el campo **Tipo de características**, seleccione **Aptitud**.
5. En el campo **Características disponibles**, especifique el tipo de aptitud que desea buscar.
6. En el campo **Tipo de característica**, seleccione **Certificado**.
7. En el campo **Características disponibles**, especifique el tipo de certificado que desea buscar.

## <a name="assign-a-project-resource-to-a-project"></a>Asignar un recurso de proyecto a un proyecto

1. En la página **Todos los proyectos**, seleccione el proyecto **Fase 2 de la actualización XYZ**.
2. En la pestaña **Equipo del proyecto y programación**, haga clic en **Agregar**.
3. En el campo **Rol** seleccione **Miembro del equipo**.
4. Seleccione **Reservar desde calendario**.
5. En la página **Disponibilidad de recursos**, haga clic en **Ver configuración**.
6. En la página **Ajustar parámetros de visualización**, especifique los valores siguientes:

    - **Formato de la vista de intervalo de fechas:** Día
    - **Mostrar descripciones de disponibilidad:** Sí
    - **Mostrar capacidad restante:** Sí

7. En la lista de recursos, seleccione un recurso.
8. Seleccione **Reserva en firme** y **Capacidad total**.

## <a name="assign-a-resource-to-a-default-role"></a>Asignar un recurso a un rol predeterminado

Para ayudar a los directores de proyecto o de recursos, puede explorar en profundidad en los recursos que se pueden reservar para un proyecto. Puede asociar un rol predeterminado a un recurso existente o un recurso recién adquirido. Por ejemplo, cuando se contrató a Daniel, este tenía la experiencia y aptitudes para ejercer la función de la analista de negocios. El administrador de recursos asignó este rol como rol predeterminado de Daniel. Por lo tanto, la directora de recursos agregó a Daniel a un conjunto de analistas de negocios disponibles para trabajar en proyectos.

Durante la reserva de recursos, los directores de proyecto pueden filtrar los recursos de rol que están disponibles para trabajar en proyectos. Pueden usar esta información como criterio cuando realicen análisis de decisiones de varios criterios durante el cumplimiento de recursos. También pueden agregar otras características de recursos al filtro para buscar recursos que tienen aptitudes, formación y experiencia específicas para un proyecto determinado.

**Escenario:** Se ha iniciado un proyecto aprobado y el rol de director de proyecto principal se reservó como recurso planeado durante la fase de planificación de proyectos. El responsable de recursos ha adquirido ahora a un recurso para cumplir el rol de director de proyecto principal.

1. En la página **Lista de recursos**, seleccione **Daniel Goldschmidt**.
2. En la página **Rol del recurso**, seleccione **Nuevo** y especifique los valores siguientes:

    - **Vigente:** escriba la fecha actual.
    - **Vencimiento:** seleccione **Nunca**.
    - **Rol:** escriba **Director de proyecto principal**.

3. Haga clic en **Guardar** y, a continuación, cierre la página.
4. En la pestaña **Competencias**, agregue la aptitud **ProjectMgmt** y el certificado **PMP**.
