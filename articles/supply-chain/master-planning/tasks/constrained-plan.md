--- 
title: Generar un plan con restricciones
description: "Este procedimiento muestra cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="generate-a-constrained-plan"></a>Generar un plan con restricciones

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad. El plan garantiza que la fabricación no comience antes de que los materiales estén disponibles y que no se reserven recursos en exceso. 

La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento se va a utilizar para el planificador de producción.


## <a name="set-up-a-constrained-plan"></a>Configurar un plan restringido
1. Haga clic en Planificación maestra.
2. Haga clic en Planes maestros.
3. En la lista, busque y seleccione el registro deseado.
    * Ejemplo: StaticPlan  
4. Seleccione Sí en el campo Capacidad limitada.
5. En el campo Límite de tiempo de capacidad finita, indique "30".
6. Expanda la sección Límites de tiempo en días.
7. Seleccione Sí en el campo Capacidad.
8. En el campo Límite de tiempo de programación de capacidad (días), escriba un número.
    * Ejemplo: 60  
9. Seleccione Sí en el campo Retrasos calculados.
10. En el campo Calcular límite de tiempo de retrasos (días), escriba un número.
    * Ejemplo: 60  
11. Expanda la sección Retrasos calculados.
12. Seleccione Sí en el campo Agregar el retraso calculado a la fecha de requisito.
13. Seleccione Sí en el campo Agregar el retraso calculado a la fecha de requisito.
14. Seleccione Sí en el campo Agregar el retraso calculado a la fecha de requisito.
15. Cierre la página.

## <a name="create-a-constrained-plan"></a>Crear un plan restringido
1. Haga clic en Ejecutar.
2. En el campo Plan maestro, especifique o seleccione un valor.
    * Seleccione el plan para el que ha configurado las restricciones.  
3. Haga clic en Aceptar
    * Esto puede tardar unos minutos.  
4. Haga clic en Pedidos planificados.


