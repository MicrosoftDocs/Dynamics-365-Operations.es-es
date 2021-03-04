---
title: Crear calendarios y generar horarios de trabajo
description: Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones. En este artículo se explica cómo definir un calendario laboral basado en una plantilla de horario de trabajo.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkCalendarTable, WorkCalendarDate, HcmPersonnelManagementWorkspace, WrkCtrGroupDateCalendar, WrkCtrDateCalendar
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f5c630297a8962d1bb383110881b2acdc872b9cd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420341"
---
# <a name="create-calendars-and-generate-working-times"></a>Crear calendarios y generar horarios de trabajo



Los calendarios describen la capacidad y los horarios de trabajo de los recursos de operaciones. En este artículo se explica cómo definir un calendario laboral basado en una plantilla de horario de trabajo. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.

1. En la página principal, seleccione **Administración del ciclo de vida de los recursos**.
2. Seleccione **Calendarios**.
3. Seleccione **Nuevo**.
4. En el campo **Calendario**, clasifique el calendario. Este es el id. del calendario, que se usa como referencia al asignar calendarios, por ejemplo a un recurso de operaciones o un grupo de recursos.  
5. En el campo **Nombre**, asigne un nombre al calendario.
6. En el campo **Días laborables estándar en horas**, especifique un número.
7. Asegúrese de que la fila esté seleccionada y, a continuación, seleccione **Horarios de trabajo** en el panel de acciones.
8. Seleccione **Crear horarios de trabajo**. Genere horas laborables para cada día del período en el que desee poder programar el trabajo. A medida que pasa el tiempo, puede generar horarios de trabajo para períodos adicionales.  
9. En el campo **Fecha inicial**, escriba una fecha. Este es el primer día en que este calendario debe estar abierto.  
10. En el campo **Fecha final**, especifique una fecha. Este es el último día en que este calendario está abierto.  
11. En el campo **Plantilla de horario de trabajo**, especifique o seleccione un valor. La plantilla de horario de trabajo define las horas laborables para cada día de la semana.  
12. Seleccione **Aceptar**.
13. Cierre la página.



[!INCLUDE[footer-include](../includes/footer-banner.md)]