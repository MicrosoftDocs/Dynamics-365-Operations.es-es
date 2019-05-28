---
title: Crear plantillas de horarios de trabajo
description: Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46c1e871133b51105386ac3b647432d0c36a6998
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551892"
---
# <a name="create-working-time-templates"></a>Crear plantillas de horarios de trabajo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo. Este procedimiento le muestra cómo definir una plantilla de horario de trabajo mediante las propiedades de programación de horario de trabajo para clasificar los intervalos de horario de trabajo. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.

1. Vaya a Todos los espacios de trabajo > Administración del ciclo de vida de los recursos.
2. Haga clic en Plantillas de horarios de trabajo.

## <a name="create-working-time-template"></a>Crear plantilla de horario de trabajo
1. Haga clic en Nuevo.
2. En el campo Plantilla de horario de trabajo, escriba un valor.
3. En el campo Nombre, escriba un valor.
4. Expanda la sección Lunes.
5. Haga clic en Agregar.
6. En el campo Desde, especifique una hora.
    * Especifique la hora en que el trabajo comienza por la mañana.  
7. En el campo Hasta, especifique una hora.
    * Especifique la hora del descanso para el almuerzo de los trabajadores.  
8. Haga clic en Agregar.
9. En el campo Desde, especifique una hora.
    * Especifique la hora en que se reanuda el trabajo tras el almuerzo.  
10. En el campo Hasta, especifique una hora.
    * Especifique el final del día laborable.  

## <a name="replicate-working-times-to-all-week-days"></a>Replicar horarios de trabajo en todos los días de la semana
1. Haga clic en Copiar día.
    * Copiar las definiciones de los horarios de trabajo de lunes a martes.  
2. Haga clic en Aceptar
3. Haga clic en Copiar día.
    * Copiar las definiciones de los horarios de trabajo de lunes a miércoles.  
4. En el campo Hasta día laboral, seleccione una opción.
5. Haga clic en Aceptar
6. Haga clic en Copiar día.
    * Copiar las definiciones de los horarios de trabajo de lunes a jueves.  
7. En el campo Hasta día laboral, seleccione una opción.
8. Haga clic en Aceptar
9. Haga clic en Copiar día.
    * Copiar las definiciones de los horarios de trabajo de lunes a viernes.  
10. En el campo Hasta día laboral, seleccione una opción.
11. Haga clic en Aceptar

## <a name="define-time-slots-for-special-operations"></a>Definir franjas temporales para operaciones especiales
1. Expanda la sección Viernes.
2. En la lista, busque y seleccione el registro deseado.
3. En el campo Propiedad, especifique o seleccione un valor.
4. En la lista, busque y seleccione el registro deseado.
5. En el campo Propiedad, especifique o seleccione un valor.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Marcar días de fin de semana como cerrados para recogida
1. Expanda la sección Sábado.
2. Seleccione Sí en el campo Cerrado para recogida.
3. Expanda la sección Domingo.
4. Seleccione Sí en el campo Cerrado para recogida.

