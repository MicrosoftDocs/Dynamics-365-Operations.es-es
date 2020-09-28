---
title: Crear un equipo de proyecto
description: En este tema se proporciona información sobre cómo y administrar equipos de proyecto.
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
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760654"
---
# <a name="create-a-project-team"></a>Crear un equipo de proyecto

[!include [banner](../includes/banner.md)]

Para usar los roles que se configuraron anteriormente en un proyecto, un director de proyecto debe asociar los roles al proyecto. Se pueden asignar varios roles en un proyecto. Para evitar confusiones, estos roles se etiquetan automáticamente durante la reserva. Por ejemplo, si el director de proyecto necesita tres ingenieros de software, se generan automáticamente tres roles de ingenieros de software que tienen las etiquetas **ingeniero de software 1**, **ingeniero de software 2** e **ingeniero de software 3**. Si se establecieron anteriormente características de rol para el rol, se aplican como filtro durante búsquedas para un recurso. Se pueden agregar características adicionales según sea necesario para restringir más la búsqueda.

La configuración de la vista también se pueden personalizar para ofrecer una mejor vista de la disponibilidad de recursos. Hay opciones para mostrar la disponibilidad por hora, diaria, semanal, mensual, trimestral y anual. También hay una opción para mostrar la capacidad disponible y restante en los recursos. Esta opción es útil para la gestión del tiempo cuando se calcula el tiempo disponible para las actividades o la disponibilidad de recursos.

El director de proyecto puede seleccionar un rol en la página y, a continuación, si hay un recurso disponible que se adapta al requisito, seleccionarlo para reservar un recurso para ese rol. Tenga en cuenta que no es necesario que los recursos estén reservados durante la fase de planificación. Al crear un WBS, puede reemplazar roles por los recursos de personal para el proyecto. Si los roles se reemplazan con los recursos de personal en la WBS, la configuración de recursos actualiza automáticamente la programación y la lista del equipo del proyecto.

[![Lista del equipo del proyecto que incluye tanto roles como recursos reales](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

El director de proyecto tiene varias opciones para reservar un recurso para un proyecto como **Capacidad restante**, **Capacidad total**, **Porcentaje de capacidad**, y **Especificar horas**. Estas opciones de reserva se pueden cancelar en cualquier momento si cambian las asignaciones de recursos. Se admiten dos tipos de reserva:

- **Reserva en firme**: Se ha aprobado y confirmado la reserva de recursos para trabajar en el compromiso para la duración especificada.
- **Reserva provisional**: Las reservas de recursos se establecieron provisionalmente para trabajar en el compromiso para la duración especificada.

El siguiente procedimiento explica cómo crear un equipo de proyecto.

## <a name="create-a-project-team"></a>Crear un equipo de proyecto

1. En la página de lista **Todos los proyectos**, seleccione un proyecto y, a continuación, haga clic en **Editar**.
2. En la pestaña **Equipo del proyecto y programación**, en el campo **Programar fecha final**, especifique la fecha inicial de la programación más un mes. Por ejemplo, si la fecha inicial de la programación es el 24 de junio de 2017 (24/06/2017), escriba **24/07/2017**.
3. Seleccione **Agregar**.
4. En el panel **Agregar roles al proyecto**, en el campo **Rol**, seleccione **Director de proyecto principal**.
5. Seleccione **Competencias requeridas**.
6. En la página **Elegir características**, las características que estableció anteriormente para el rol de director de proyecto principal se seleccionan de forma predeterminada. Seleccionar **Aceptar**.
7. En la página **Agregue roles al proyecto**, en el campo **Número de recursos**, escriba **1**.
8. En el campo **Recurso**, las búsquedas muestran todos los recursos con las competencias necesarias. Seleccione **Daniel Goldschmidt** y, a continuación, haga clic en **Crear**.
9. En la página **Proyecto** y haga clic en **Agregar**.
10. En el panel **Agregar roles al proyecto**, en el campo **Rol**, seleccione **Miembro del equipo**. En el campo **Número de recursos**, escriba **5**.
11. Seleccione **Crear**.
12. En la página **Proyectos**, seleccione **Cumplir con recurso**.

## <a name="monitor-project-teams"></a>Supervisar los equipos de proyecto
1. En la página **Todos los proyectos**, seleccione el vínculo **Id. de proyecto** del proyecto **Fase 2 de la actualización de XYZ**.
2. En la ficha desplegable **Equipo del proyecto y programación**, compruebe que los recursos de proyectos mostrados son correctos.
