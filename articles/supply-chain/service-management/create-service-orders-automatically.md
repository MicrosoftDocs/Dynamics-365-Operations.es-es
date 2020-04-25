---
title: Crear pedidos de servicio automáticamente
description: Es posible crear pedidos de servicio para un acuerdo de servicio o para varios.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4ba2cf115faacda14e25838a488fc54c53f48f3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202730"
---
# <a name="create-service-orders-automatically"></a>Crear pedidos de servicio automáticamente    

[!include [banner](../includes/banner.md)]


Es posible crear pedidos de servicio para un acuerdo de servicio o para varios. Cuando se creen, podrá verlos en el formulario **Pedidos de servicio**.

Los pedidos de servicio sólo se crean para el período válido del acuerdo de servicio. Si el intervalo que especifique en el formulario **Crear pedidos de servicio** empieza antes de la fecha de inicio o termina después de la fecha de finalización del acuerdo de servicio, sólo se crearán para la parte del intervalo que se encuentre dentro de las fechas del acuerdo de servicio.

Al crear pedidos de servicio de forma manual o automática desde la línea del acuerdo de servicio, el pedido de servicio debe estar dentro del intervalo de tiempo definido por las fechas inicial y final para la línea, a menos que no especifique una fecha final en la línea.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Crear pedidos de servicio automáticamente para un acuerdo de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.

2.  Seleccione un acuerdo de servicio.

3.  Haga clic en la ficha **Entregar** y, a continuación, haga clic en **Pedidos de servicio planificados**.

4.  Especifique las fechas en los campos **Desde fecha** y **Hasta fecha** para definir el período de servicio.

5.  Active la casilla de verificación **Mostrar el registro de información** para que aparezca una lista de los pedidos de servicio que se han creado.

6.  Seleccione tipos de transacción en el grupo de campos **Incluir los tipos de transacción** . Estos tipos de transacciones representan las líneas que se crean en el acuerdo de servicio y cada tipo de transacción que seleccione genera varios pedidos de servicio según el intervalo de servicio especificado en la línea del acuerdo de servicio.

7.  Para crear cualquier pedido de servicio que falta en una serie continua de pedidos de servicio, active la casilla de verificación **Continuo**.

8.  Haga clic en **Aceptar**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Crear pedidos de servicio automáticamente para varios acuerdos de servicio

1.  Haga clic en **Gestión de servicio** \> **Periódico** \> **Pedidos de servicio** \> **Crear pedidos de servicio**.

2.  Haga clic en **Seleccionar** para efectuar selecciones de adición o eliminación de los criterios que se van a utilizar para crear pedidos de servicio.

3.  Haga clic en **Aceptar**.

## <a name="see-also"></a>Consulte también

[Pedidos de servicio](service-orders.md)

[Crear pedidos de servicio automáticamente](auto-create-service-orders.md)

  


