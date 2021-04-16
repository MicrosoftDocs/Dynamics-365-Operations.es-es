---
title: Iniciar un pedido de producción
description: Este procedimiento muestra cómo iniciar un pedido de producción en la planta.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be1c389bc4193ef080dbeb1639b69acf466ef0de
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831875"
---
# <a name="start-a-production-order"></a>Iniciar un pedido de producción

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo iniciar un pedido de producción en la planta. En este proceso se informa del consumo de tiempo y materiales. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este es el quinto procedimiento de siete que explica el ciclo de vida del pedido de producción.


## <a name="start-a-production-order"></a>Iniciar un pedido de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
    * Seleccione un pedido de producción con estado Liberado.  
2. En el panel de acciones, haga clic en Pedido de producción.
3. Haga clic en Inicio.
    * En esta página, puede confirmar el inicio del pedido de producción.  
4. Haga clic en la pestaña General.
5. En el campo Desde N. º oper., especifique "10".
6. En el campo Consumo de ruta automático, seleccione Siempre.
7. Haga clic en la casilla Registrar ahora la tarjeta de ruta.
8. En el campo Consumo automático de L. MAT, seleccione Siempre.
9. Haga clic en la casilla Registrar ahora la lista de selección.
10. Haga clic en la casilla Imprimir lista de selección.
11. Haga clic en Aceptar
    * Esta es la lista de selección impresa que muestra los materiales usados para el pedido de producción.  
12. Cierre la página.

## <a name="validate-the-picking-list"></a>Validación de la lista de selección
1. En el panel de acciones, haga clic en Ver.
2. Haga clic en Lista de selección.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en Editar.
6. En el campo Consumo, especifique un número.
7. Haga clic en Registrar.
8. Haga clic en Aceptar
    * En el diario de lista de selección se registran los materiales consumidos por el pedido de producción. Antes de registrar el diario, puede realizar ajustes si existe diferencia entre la cantidad estimada y la cantidad consumida real.  
9. Haga clic en la pestaña del panel de cuadrícula.
10. Cierre la página.

## <a name="verify-the-route-card-journal"></a>Verificación del diario de tarjeta de ruta
1. En el panel de acciones, haga clic en Ver.
2. Haga clic en tarjeta de ruta.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en Editar.
6. En el campo Horas, especifique un número.
7. Haga clic en Registrar.
8. Haga clic en Aceptar
    * En el diario de tarjeta de ruta se registra el tiempo empleado en las operaciones individuales. También se puede informar de la cantidad de errores y aciertos.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]