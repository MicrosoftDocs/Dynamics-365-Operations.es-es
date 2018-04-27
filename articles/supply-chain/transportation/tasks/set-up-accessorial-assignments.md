--- 
title: Configurar asignaciones de cargos adicionales
description: "Este procedimiento muestra cómo configurar una asignación de cargos adicionales."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 31787aa180639b934b837b98dc170070d33fd56f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-accessorial-assignments"></a>Configurar asignaciones de cargos adicionales

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar una asignación de cargos adicionales. Esto lo hace normalmente el coordinador de transporte. Antes de usar este procedimiento, debe ejecutar el procedimiento "Configuración de cargos adicionales del centro y cargos adicionales maestros".


## <a name="set-up-accessorial-assignment"></a>Configuración de asignaciones de cargos adicionales
1. Vaya a Administración de transporte > Configuración > Clasificación > Asignaciones de cargos adicionales.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. Expanda la sección Detalles.
5. En el campo Centro, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, seleccione el centro para el que creó cargos adicionales maestros al ejecutar el procedimiento "Configuración de cargos adicionales y maestros adicionales. 
7. En el campo Id. de cargos adicionales del centro, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Expanda la sección Criterios.
    * En la sección Criterios, puede elegir los criterios exactos para cuando se deba aplicar el cargo, en función de los distintos valores ofrecidos aquí.  
10. Establezca la opción Aplicar siempre en Sí.
11. En el campo Nivel de asignación de cargos adicionales, seleccione una opción.
12. Expanda la sección Cálculo.
13. En el campo Tipo de tasas de cargos adicionales, seleccione Fijo.
    * El tipo de tasa de cargos adicionales determina cómo se calcula el cargo real. En este ejemplo se trata de un cargo fijo.  
14. En el campo Tasa de cargos adicionales, escriba un número.
15. Haga clic en Guardar.


