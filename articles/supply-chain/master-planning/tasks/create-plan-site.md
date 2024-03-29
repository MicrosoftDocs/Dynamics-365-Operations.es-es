---
title: Crear un plan para un sitio
description: El planificador de producción calcula los requisitos de materiales y capacidad para la producción de un artículo específico.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c8330fc15074eb59762dac73d0b176bd7faadc
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469516"
---
# <a name="create-a-plan-for-a-site"></a>Crear un plan para un sitio

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]