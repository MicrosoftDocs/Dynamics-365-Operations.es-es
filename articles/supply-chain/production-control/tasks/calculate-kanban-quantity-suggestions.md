---
title: Cálculo de sugerencias de cantidades kanban
description: Este procedimiento se centra en la optimización del tamaño y las cantidades kanban para una regla kanban calculando la cantidad kanban.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18d2a8dd2a8c132873744ba890ca6b1eb1fd34b6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570139"
---
# <a name="calculate-kanban-quantity-suggestions"></a>Cálculo de sugerencias de cantidades kanban

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la optimización del tamaño y las cantidades kanban para una regla kanban calculando la cantidad kanban. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento va destinado al administrador del flujo de valor. Es indispensable haber completado el procedimiento Adición de una directiva de cálculo de cantidad kanban a una regla kanban.


## <a name="create-a-kanban-quantity-calculation"></a>Creación de un cálculo de cantidad kanban
1. Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Calcular cantidad kanban.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba "Speaker2016".
4. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione la directiva que ha creado en el procedimiento Adición de una directiva de cálculo de cantidad kanban a una regla kanban. Por ejemplo, Speaker2016.  
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Regla activa a partir de la fecha, defina la fecha y la hora en "2012-12-17T08:00:00".
    * Esta fecha se toma como base para determinar qué reglas kanban se incluyen en el cálculo de cantidad kanban.  
7. En el campo Fecha inicial del período de demanda satisfecha, defina la fecha y la hora en "2012-11-17T09:00:00".
    * La fecha a partir de la cual se incluyen las transacciones de demanda pasada para calcular la cantidad kanban.  
8. En el campo Fecha final del período de demanda satisfecha, defina la fecha y la hora en "2012-12-17T07:59:59".
    * La fecha hasta la cual se incluyen las transacciones de demanda pasada para calcular la cantidad kanban.  
9. En el campo Fecha inicial del período de demanda, defina la fecha y la hora en "2012-12-17T08:00:00".
    * La fecha a partir de la cual se incluyen las transacciones de demanda actual para calcular la cantidad kanban.  
10. En el campo Fecha final del período de demanda, defina la fecha y la hora en "2013-01-16T07:59:59".
    * La fecha hasta la cual se incluyen las transacciones de demanda actual para calcular la cantidad kanban.  

## <a name="generate-kanban-quantity-proposal"></a>Generación de la propuesta de cantidad kanban
1. Haga clic en Guardar.
2. Haga clic en Generar.
    * Esto genera una línea de propuesta de cantidad kanban para la regla kanban 000020.  

## <a name="run-kanban-quantity-calculation"></a>Ejecución del cálculo de cantidad kanban
1. Haga clic en Calcular.
    * Esto calcula la propuesta de cantidad kanban.  
2. Haga clic en Aceptar
3. En la lista, marque la fila seleccionada.
    * Observe cómo la cantidad de kanban sugerida es 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Cambio de la cantidad de producto y nuevo cálculo
1. Defina la cantidad del producto en "5".
2. Haga clic en Calcular.
3. Haga clic en Aceptar
    * Observe que con una cantidad kanban de 5, la sugerencia cambia a una cantidad kanban de 4.  
    * Esto es así por el hecho de que con una cantidad de producto inferior, se necesitan más kanbans para satisfacer la demanda.  

## <a name="update-kanban-rule"></a>Actualización de la regla kanban
1. En el campo Fecha de vigencia de regla, especifique una fecha y una hora.
    * Defina Regla activa a partir de la fecha en una fecha futura. Por ejemplo, hoy + un año.  
2. Haga clic en Actualizar.
3. Haga clic en Aceptar
4. Cierre la página.

## <a name="validate-change-on-kanban-rule"></a>Validación de cambios en reglas kanban
1. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione la regla kanban que se creó en la subtarea anterior. Esta debe ser la primera regla kanban en la lista ordenada por número.  
3. Expanda la sección Detalles.
    * Tenga en cuenta la fecha de vigencia, que significa que esta regla no estará activa hasta esta fecha.  
4. Expanda la sección Cantidades.
    * Observe que esta es la cantidad predeterminada especificada en el cálculo de la cantidad kanban.  
    * Observe que esta es la cantidad kanban fija de 4 proveniente del cálculo de cantidad kanban.  
5. Haga clic en la ficha del panel de lista.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]