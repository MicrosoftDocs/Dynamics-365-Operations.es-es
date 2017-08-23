--- 
title: "Definir grupos de programación lean"
description: "Los grupos de programación lean se definen para agrupar y distinguir productos en la programación kanban."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 75d8b6614fd3b36d87bcb95b0b753b611a101f62
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="define-lean-schedule-groups"></a>Definir grupos de programación lean

[!include[task guide banner](../../includes/task-guide-banner.md)]

Los grupos de programación lean se definen para agrupar y distinguir productos en la programación kanban. La agrupación se puede realizar como asociación genérica por empresa o de manera específica para una celda de trabajo. Cada grupo tiene un código de color asignado para indicación visual en la ListPage de programación kanban. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="define-lean-scheduling-group"></a>Definir grupo de programación lean
1. Vaya a Gestión de información de productos > Lean manufacturing > Grupos de programación lean.
2. Haga clic en Nuevo.
3. En el campo Grupo de programación, escriba un valor.
    * Un grupo de programación se puede definir como grupo global o específico de una celda de trabajo. En este ejemplo sencillo, definimos un grupo global y la celda de trabajo se mantiene vacía. La configuración de este grupo se aplica a todas las celdas de trabajo que no tienen grupos de programación específicos.  
4. Seleccione un color en la selección del color.
    * Los colores se usan para resaltar los trabajos de la página de lista de programación kanban o el tablero de proceso kanban.  
5. En la lista, marque la fila seleccionada.
6. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="associate-product"></a>Asociar producto
1. Asociar un producto específico
    * Hay dos formas de asociar productos a grupos de programación lean, como producto específico (Tipo de relación de artículos = artículo) o como parte de una clave de asignación de artículos (tipo de relación de artículo = grupo).    
2. En el campo Tipo de relación de artículos, seleccione Artículo.
3. En el campo Código de artículo, escriba un valor.
4. En el campo Índice de capacidad de proceso, especifique un número.
    * El índice de capacidad de proceso predeterminado es 1, lo que significa que los productos relacionados consumen exactamente la capacidad especificada en las actividades de proceso de los flujos de producción. El índice de capacidad de proceso > 1 define un consumo superior de recursos, el índice de capacidad de proceso < 1 define un consumo menor de recursos. El índice se usa en el cálculo de costes y en el cálculo del consumo de trabajos kanban.  

## <a name="associate-item-allocation-key"></a>Asociar clave de asignación de artículos
1. Asociar una clave de asignación de artículos
    * Agregue una asociación a una clave de asignación de artículos mediante el grupo Tipo de relación de artículos.   Tenga en cuenta que para este proceso necesita una clave de asignación de artículos de previsión definida en sus datos.  
2. En el campo Tipo de relación de artículos, seleccione Grupo.
3. En el campo Clave de asignación de artículos, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, haga clic en el vínculo de la fila seleccionada.

