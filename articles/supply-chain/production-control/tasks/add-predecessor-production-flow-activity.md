---
title: Agregar un predecesor a una actividad de flujo de producción
description: En una versión de flujo de producción, todas las actividades deben estar secuenciadas.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9b761e61bf6a810da9258870e9a994da4ced125
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981440"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Agregar un predecesor a una actividad de flujo de producción

[!include [banner](../../includes/banner.md)]

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

