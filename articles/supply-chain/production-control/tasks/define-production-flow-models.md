---
title: Definir modelos de flujo de producción
description: Los modelos de flujo de producción describen cómo se calcula y mantienen la capacidad de celdas de trabajo de lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 511c466d6019cb182c9ada0b02172b8eeb3725e6
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975833"
---
# <a name="define-production-flow-models"></a>Definir modelos de flujo de producción

[!include [banner](../../includes/banner.md)]

Los modelos de flujo de producción describen cómo se calcula y mantienen la capacidad de celdas de trabajo de lean manufacturing. Por tanto, la definición de un modelo de flujo de producción es un requisito previo de la definición de las celdas de trabajo. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="define-a-production-flow-model"></a>Defina un modelo de flujo de producción. 
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Modelos de flujo de producción.
2. Haga clic en Nuevo.
3. En el campo Modelo de flujo de producción, especifique un id. para el modelo de flujo de producción.
4. En el campo Tipo de modelo, seleccione una opción.
    * Hay dos tipos de modelo: tipo de Capacidad de proceso y tipo Horas. Para el tipo de Capacidad de proceso, la capacidad de celdas de trabajo que usan este modelo de flujo de producción se expresará y calculará en cantidades de producto. Para el tipo de Horas, la capacidad de celdas de trabajo que usa este modelo de flujo de producción se expresará y calculará en horas. Tenga en cuenta que esta propiedad no se puede modificar para un modelo de flujo de producción existente. Cuando una celda de trabajo tenga reservas de capacidad, el tipo de modelo de flujo de producción no se podrá modificar.  
5. Especificar el número de días en el ciclo de EPE.
    * El intervalo describe el período en que se producirá cada parte producida por un flujo de producción o una celda de trabajo al menos una vez. Cuanto menor sea el ciclo de EPE, más flexible será el proceso de producción. Si el ciclo de EPE = 0, toda la demanda se podrá producir el mismo día. El ciclo de EPE se usa para programar los trabajos de procesos lean. Al programar un trabajo en una celda de trabajo con el ciclo de EPE = 5, el proceso de programación buscará capacidad de la celda de trabajo en la fecha de vencimiento - ciclo de EPE (5 días antes de la fecha de vencimiento) para garantizar que el producto se puede producir en dicho período. El plazo de inventario de un producto suele ser igual o mayor que el ciclo de EPE del proceso de producción relacionado.  
6. En el campo Tipo de período de planificación, seleccione una opción.
    * Cuando una celda de trabajo tenga reservas de capacidad, no se podrá cambiar el tipo del período de planificación. Solo puede seleccionar los modelos de flujo de producción con el mismo tipo de período para esta celda de trabajo especificada.  
7. En el campo Límite de tiempo de planificación, escriba un número.
    * El límite de tiempo de planificación describe el número de días en el que las reservas de capacidades se pueden realizar para las celdas de trabajo relacionadas. En el Límite de tiempo de planificación, escriba el número de días.   Los trabajos de proceso kanban que se encuentran fuera de este período no se planifican con la planificación automática. El límite de tiempo de planificación suele ser normalmente el doble del plazo medio de inventario de los productos producidos en un flujo de producción o una celda de trabajo. El ciclo de EPE no debe ser superior a la mitad del límite de tiempo de planificación.     
8. En el campo Reacción por escasez de capacidad, seleccione una opción.
    * Se incluyen las siguientes opciones: Posponer: posponer la demanda completa del evento de programación al día siguiente de producción disponible, con capacidad de proceso disponible. Cancelar: complete la planificación automática para el evento de programación y deje los trabajos relacionados no planificados.   Agregar al día solicitado: planifique los trabajos solicitados para el período pedido. Esto sobrecarga a la celda para este día y requiere que el planificador lo revise e interactúe manualmente.   Distribuya a períodos disponibles - distribuya los diferentes trabajos del evento a todos los días disponibles de la producción, empezando por primer día disponible. La cantidad de distribución mínima es la cantidad de trabajo kanban. La distribución asigna la cantidad de planificación mínima (cantidad kanban) a cada día con suficiente capacidad de proceso disponible.  

