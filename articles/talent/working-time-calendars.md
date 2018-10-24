---
title: Calendarios de horarios de trabajo
description: "Este tema describe los calendarios de horario de trabajo de Dynamics 365 for Talent - Core HR, además de cómo configurar los calendarios."
author: jcart1106
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2018-07-01
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1bf37d65cd8ce6a98fc2d2fb11ae9587cf6958a3
ms.openlocfilehash: 2465065d7db18a5468d7c979e0d6cb9c7e76f969
ms.contentlocale: es-es
ms.lasthandoff: 09/27/2018

---

# <a name="working-time-calendars"></a>Calendarios de horarios de trabajo

[!include [banner](includes/banner.md)]

El calendario de horario de trabajo permite crear un calendario con las horas y los días que los empleados trabajan en su organización. Los calendarios ayudan a agilizar el proceso de solicitud de licencia de forma predeterminada en horas o días. Si un empleado envía una solicitud de licencia, no tiene que preocuparse de días libres ni de cierres, ya que el calendario de horario de trabajo lo gestiona en su lugar.

## <a name="setting-up-a-working-time-calendar"></a>Configuración de un calendario de horas de trabajo

Los calendarios incluyen detalles de la generación, los días y las horas que desea incluir, los días del calendario, los horarios de trabajo de esos días junto con los empleados inscritos. 

Para configurar un calendario, siga estos pasos:

1. En la página **Administración de la organización**, haga clic en **Calendarios**.

2. En el panel de acciones, seleccione **Nuevo** y especifique un nombre y una descripción.

3. Elija los días laborables de la organización y escriba el tiempo de trabajo.

4. Agregue los días libres y los cierres mediante el botón **Agregar**.

5. Especifique el nombre y la descripción de los días festivos y los cierres temporales, como festivos de Estados Unidos o puentes. Escriba las fechas de los festivos y los cierres temporales. Guarde la lista de días libres y cierres temporales y cierre la página.

6. Seleccione la lista de días libres y cierres temporales en el menú desplegable.

7. Si sus empleados tienen tiempo de fuera del trabajo, como almuerzos o descansos, agregue también ese tiempo. Seleccione **Tiempo fuera de trabajo** y especifique el nombre y el intervalo temporal. Cierre la página. 

8. Haga clic en **Agregar** para agregar el tiempo fuera del trabajo en el calendario.

9. En la pestaña **Días**, seleccione **Generar** para generar los días en el calendario. Escriba el intervalo del calendario. Los días y las horas laborables se generan en función de los días laborables y las horas definidos en las opciones de generación junto con las fechas seleccionadas.

10. Para asignar un calendario a los empleados, seleccione **Asignar a los empleados** en el panel de acciones. Seleccione a qué desearían asignar los empleados este calendario y, a continuación, haga clic en **Asignar**.

No se requiere que los empleados tengan calendarios asignados. Si hay un calendario de horario de trabajo definido, los días libres se excluyen automáticamente de la solicitud. La cantidad, en horas o días, toma como valor predeterminado los horarios de trabajo definidos en el calendario. Si un empleado no tiene un calendario asignado, todos los días están disponibles para tiempo libre y la cantidad de tiempo libre no es el valor predeterminado de la solicitud. 

