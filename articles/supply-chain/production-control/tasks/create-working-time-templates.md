---
title: Crear plantillas de horarios de trabajo
description: Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920938"
---
# <a name="create-working-time-templates"></a>Crear plantillas de horarios de trabajo

[!include [banner](../../includes/banner.md)]

Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo. Este procedimiento le muestra cómo definir una plantilla de horario de trabajo mediante las propiedades de programación de horario de trabajo para clasificar los intervalos de horario de trabajo. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.

1. Vaya a **Espacios de trabajo > Administración del ciclo de vida de los recursos**.
1. Seleccione **Plantillas de horarios de trabajo**.

## <a name="create-working-time-template"></a>Crear plantilla de horario de trabajo

1. Seleccione **Nuevo**.
1. En el campo **Plantilla de horario de trabajo**, escriba un valor.
1. En el campo **Nombre**, escriba un valor.
1. Expanda la sección **Lunes**.
1. Seleccione **Agregar**.
1. En el campo **Desde**, especifique una hora.
    * Especifique la hora en que el trabajo comienza por la mañana.  
1. En el campo **Hasta**, especifique una hora.
    * Especifique la hora del descanso para el almuerzo de los trabajadores.  
1. Seleccione **Agregar**.
1. En el campo **Desde**, especifique una hora.
    * Especifique la hora en que se reanuda el trabajo tras el almuerzo.  
1. En el campo **Hasta**, especifique una hora.
    * Especifique el final del día laborable.  

## <a name="replicate-working-times-to-all-week-days"></a>Replicar horarios de trabajo en todos los días de la semana

1. Seleccione **Copiar día**.
    * Copiar las definiciones de los horarios de trabajo de lunes a martes.  
1. Seleccione **Aceptar**.
1. Seleccione **Copiar día**.
    * Copiar las definiciones de los horarios de trabajo de lunes a miércoles.  
1. En el campo **Hasta día laboral**, seleccione una opción.
1. Seleccione **Aceptar**.
1. Seleccione **Copiar día**.
    * Copiar las definiciones de los horarios de trabajo de lunes a jueves.  
1. En el campo **Hasta día laboral**, seleccione una opción.
1. Seleccione **Aceptar**.
1. Seleccione **Copiar día**.
    * Copiar las definiciones de los horarios de trabajo de lunes a viernes.  
1. En el campo **Hasta día laboral**, seleccione una opción.
1. Seleccione **Aceptar**.

## <a name="define-time-slots-for-special-operations"></a>Definir franjas temporales para operaciones especiales

1. Expanda la sección **Viernes**.
1. En la lista, busque y seleccione el registro deseado.
1. En el campo **Propiedad**, especifique o seleccione un valor.
1. En la lista, busque y seleccione el registro deseado.
1. En el campo **Propiedad**, especifique o seleccione un valor.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Marcar días de fin de semana como cerrados para recogida

1. Expanda la sección **Sábado**.
1. Seleccione *Sí* en el campo **Cerrado para recogida**.
1. Expanda la sección **Domingo**.
1. Seleccione *Sí* en el campo **Cerrado para recogida**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]