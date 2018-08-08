--- 
title: "Agregar un predecesor a una actividad de flujo de producción"
description: "En una versión de flujo de producción, todas las actividades deben estar secuenciadas."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d19fb20e8cc941daeaa506e4bf1cb0c7031cf2ee
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Agregar un predecesor a una actividad de flujo de producción

[!include [task guide banner](../../includes/task-guide-banner.md)]

En una versión de flujo de producción, todas las actividades deben estar secuenciadas. Una actividad puede tener uno o múltiples predecesores o sucesores. 

Este procedimiento muestra cómo asociar un predecesor a una actividad. 

Para realizar esta tarea, se necesita un flujo de producción que tenga la versión Borrador con al menos dos actividades que se puedan conectar. 

Para obtener más información, lea el documento “Los flujos de producción y las actividades en lean manufacturing”.


## <a name="find-the-production-flow-and-version"></a>Encuentre el flujo de producción y la versión.
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En la lista, busque y seleccione el registro deseado.
5. Haga clic en Actividades.

## <a name="select-an-activity-and-add-a-predecessor"></a>Seleccione una actividad y agregue un predecesor
1. En la lista, busque y seleccione el registro deseado.
2. Haga clic en Agregar un predecesor.
3. En el campo Actividad, especifique o seleccione un valor.
4. En campo Coeficiente de tiempo de ciclo, escriba un número.
    * La proporción de tiempo de ciclo predeterminado de una relación de actividad es 1. Esto supone que las actividades se ejecutan en el mismo paso o el ritmo de producción. Si el predecesor se ejecuta a un ritmo más alto (un ritmo de producción inferior), la proporción debe ser inferior a 1, si el predecesor se ejecuta a un ritmo más lento (un ritmo de producción más alto), el tiempo de ciclo es mayor que 1.  
5. Haga clic en Aceptar


