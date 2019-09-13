---
title: Generar un plan con restricciones
description: Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.
author: ShylaThompson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b5d37de41fe68845cec3f2285aed2484ac117aa
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867182"
---
# <a name="generate-a-constrained-plan"></a>Generar un plan con restricciones

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad. El plan garantiza que la fabricación no comience antes de que los materiales estén disponibles y que no se reserven recursos en exceso. 

La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento se va a utilizar para el planificador de producción.


## <a name="set-up-a-constrained-plan"></a>Configurar un plan restringido
1. En la página principal, seleccione el espacio trabajo **Planificación maestra**.
2. Seleccione **Planes maestros** en la lista de vínculos en el extremo derecho del área de trabajo.
3. En la lista, busque y seleccione el registro deseado. Ejemplo: **StaticPlan**  
4. Seleccione **Sí** en el campo **Capacidad limitada**.
5. En el campo **Límite de tiempo de capacidad finita**, indique `30`.
6. Expanda la sección **Límites de tiempo en días**.
7. Seleccione **Sí** en el campo **Capacidad**.
8. En el campo **Límite de tiempo de programación de capacidad (días)**, escriba un número. Ejemplo: `60`  
9. Seleccione **Sí** en el campo **Retrasos calculados**.
10. En el campo **Calcular límite de tiempo de retrasos (días)**, escriba un número. Ejemplo: `60` 
11. Expanda la sección **Retrasos calculados**.
12. Seleccione **Sí** en todos los campos **Agregar el retraso calculado a la fecha de requisito**.
13. Cierre la página.

## <a name="create-a-constrained-plan"></a>Crear un plan restringido
1. Seleccione **Ejecutar**.
2. En el campo **Plan maestro**, especifique o seleccione el plan para el que ha configurado restricciones.  
3. Seleccione **Aceptar**.
4. Seleccione **Pedidos planificados**.

