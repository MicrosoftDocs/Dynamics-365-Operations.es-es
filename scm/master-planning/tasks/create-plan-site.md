--- 
title: Crear un plan para un sitio
description: "El planificador de producción calcula los requisitos de materiales y capacidad para la producción de un artículo específico."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d89d34d4d429faf87c70943961f7141a6258d482
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-plan-for-a-site"></a>Crear un plan para un sitio

[!include[task guide banner](../../includes/task-guide-banner.md)]

El planificador de producción calcula los requisitos de materiales y capacidad para la producción de un artículo específico. Una vez creadas las sugerencias de abastecimiento, encuentra los pedidos en el sitio para el que está planificando y pone en firme los pedidos, empezando por los urgentes. Los pedidos más urgentes son los que se deben poner en firme en la fecha actual. Use la empresa de datos de demostración USMF para llevar a cabo estas tareas.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Crear un plan de capacidad y materiales para un artículo
1. Haga clic en Planificación maestra.
    * Necesita desplazarse al panel de información predeterminado.  
2. Haga clic en Ejecutar.
3. Expanda la sección Registros que incluir.
4. Haga clic en Filtro.
5. En la lista, marque la fila seleccionada.
6. En el campo Criterios, escriba un valor.
    * Ejemplo: D0001  
7. Haga clic en Aceptar
8. Haga clic en Aceptar
    * Esto puede tardar unos minutos.  
9. Actualice la página.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Identificar los pedidos planificados urgentes para el artículo
1. Abra el filtro de columna Número de artículo.
2. Aplique un filtro en el campo "Número de artículo" con un valor de "D0001", mediante el operador de filtro "empieza por".
3. Abra el filtro de columna Fecha del pedido.
4. Aplique un filtro en el campo "Fecha del pedido", con un valor de la fecha actual, usando el operador de filtro "es exactamente".

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Poner en firme todos los pedidos urgentes para el artículo
1. En la lista, active o desactive todas las filas.
2. Haga clic en En firme.
3. Haga clic en Aceptar


