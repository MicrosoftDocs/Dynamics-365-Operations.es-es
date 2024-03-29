---
title: Crear relación de actividad - Sucesor
description: El flujo de actividades en un flujo de producción lean se documenta a través de relaciones de actividad.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8cee0c75de1fee24cfb6df018de62ece102c96cc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579217"
---
# <a name="create-activity-relation---successor"></a>Crear relación de actividad - Sucesor

[!include [banner](../../includes/banner.md)]

El flujo de actividades en un flujo de producción lean se documenta a través de relaciones de actividad. Esta grabación muestra cómo crear una relación de actividad.

Requisitos previos:

- Un flujo de producción y una versión en modo de borrador. 

- Se crean dos actividades que van una detrás de otra en el flujo de producción pero no se relacionan.


## <a name="find-the-production-flow-version"></a>Buscar la versión del flujo de producción 
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En la lista, marque la fila seleccionada.
5. En la lista, seleccione una versión de borrador.
    * Las relaciones de actividad se pueden agregar tanto al borrador como a las versiones activas de un flujo de producción.  

## <a name="open-the-activity-overview"></a>Abrir la visión general de la actividad
1. Haga clic en Actividades.
    * Tenga en cuenta que el formulario muestra todas las actividades del flujo de producción que se asignan a la versión de los flujo de producción en los que está trabajando.  

## <a name="add-a-successor"></a>Agregar un sucesor
1. Haga clic en Añadir sucesor.
2. En el campo Actividad, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Active la casilla Restricción.
6. En el campo Valor de restricción, escriba un número.
    * La hora de restricción es la hora que se programará entre el final programado del predecesor (hora y fecha de vencimiento) y el inicio programado del sucesor.  
7. En el campo Unidades, escriba un valor.
8. En campo Coeficiente de tiempo de ciclo, escriba un número.
    * Si ambas actividades se ejecutan en el mismo takt, el tiempo de ciclo debe ser 1. Si la predecesora se ejecuta al doble de velocidad que la sucesora, la proporción debe ser 2.   Los coeficientes de tiempo de ciclo se usan para calcular los tiempos de ciclo individuales de las actividades del flujo de producción.  
9. Haga clic en Aceptar
10. Cierre la página.
11. Haga clic en la pestaña del panel de cuadrícula.
12. Cierre la página.
13. Actualice la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]