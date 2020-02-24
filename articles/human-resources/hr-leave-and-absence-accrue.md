---
title: Acumular planes de permisos y ausencias
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 28b7d843d9dd652e45c24af09d0414530c06c4ac
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010451"
---
# <a name="accrue-leave-and-absence-plans"></a>Acumular planes de permisos y ausencias

Puede acumular permisos y ausencias en Dynamics 365 Human Resources para varios empleados o para un individuo.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Acumular permisos y ausencias para varios empleados

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. Debajo de **Administrar bajas**, seleccione **Acumular planes de permisos y ausencias**.

3. En el cuadro de diálogo **Acumular planes de permisos y ausencias**, en **Acumular a partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.

4. Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para el proceso de acumulación.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso de acumulación se ejecutará con los parámetros que establezca.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Acumular permisos y ausencias para un empleado

1. En el registro del empleado, seleccione **Baja**.

2. Seleccione **Acumular planes de permisos y ausencias**.

3. En el cuadro de diálogo **Acumular planes de permisos y ausencias**, en **Acumular a partir de**, seleccione **Fecha de hoy** o seleccione **Fecha personalizada** e introduzca una fecha personalizada.

4. Si desea ejecutar el proceso de acumulación en segundo plano, seleccione **Ejecutar en segundo plano** y realice las siguientes tareas:

   1. Escriba información para el proceso de acumulación.

   2. Para configurar un trabajo periódico, seleccione **Periodicidad**, introduzca la información de periodicidad y seleccione **Aceptar**.

   3. Para configurar una alerta de trabajo, seleccione **Alertas**, seleccione las alertas que quiera recibir y luego seleccione **Aceptar**.

   4. Seleccione **Aceptar**. El proceso de acumulación se ejecutará con los parámetros que establezca.

## <a name="preview-features-for-leave-and-absence"></a>Características de vista previa para permisos y ausencias

[!include [banner](includes/preview-feature-leave-absence.md)]

Puede habilitar las siguientes características de vista previa para permisos y ausencias:

- **Eliminar acumulaciones de permisos y ausencias**. Eliminar registros de acumulación para un plan e intervalo de fechas específico. Las fechas de acumulación deben ser la de hoy o fechas en el futuro.

- **Auditoría de acumulación de bajas**. Se muestra cada vez que alguien ejecuta o elimina una acumulación para uno o todos los empleados, junto con la fecha y quién realizó la acción.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Crear un plan de permisos y ausencias](hr-leave-and-absence-plans.md)