---
title: Diagrama de árbol lean de pedidos de ventas
description: Este procedimiento se centra en validar el diagrama de árbol de una línea de ventas donde el artículo se produce con kanbans.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff57169ea58a90d1113bb7ef0a581f900e62a9b2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828571"
---
# <a name="lean-pegging-from-sales-orders"></a>Diagrama de árbol lean de pedidos de ventas

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en validar el diagrama de árbol de una línea de ventas donde el artículo se produce con kanbans. Después de validar el diagrama de árbol, se planifican todos los trabajos kanban. Esto resulta útil para escenarios de pedidos donde el creador del pedido necesita asegurarse de que la producción puede comenzar inmediatamente. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el creador del pedido avanzado que trabaja en una empresa lean.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Crear un pedido de ventas para un artículo controlado por kanban
1. Vaya a Todos los pedidos de ventas.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
    * Use US-001.  
4. Haga clic en Aceptar
5. En el campo Código de artículo, escriba 'L0001'.
6. Establezca el valor de cantidad en '30'.
    * Es importante que la cantidad sea mayor de 24 para activar la regla kanban de evento.  

## <a name="open-a-pegging-tree"></a>Abrir un árbol de diagrama de árbol 
1. Haga clic en Producto y suministro.
2. Haga clic en Ver diagrama de árbol.
    * Tenga en cuenta que el diagrama de árbol muestra todos los niveles del diagrama de árbol necesario para la línea de pedido de ventas. En este caso, hay dos niveles de kanbans y todos los componentes necesarios.  

## <a name="plan-the-pegging-tree"></a>Planificar el diagrama de árbol
1. En el árbol, seleccione "Línea de ventas 000832\Kanban 000558".
2. Expanda la sección Trabajos kanban.
    * Observe que el estado de trabajo del trabajo es Sin planificar.  
3. Haga clic en Planificar todo el diagrama de árbol.
    * Esto planeará todos los trabajos kanban en el diagrama de árbol, cambiando el estado del trabajo de Sin planificar a Planificado.  
4. Actualice la página.
    * Observe que el estado del trabajo kanban cambió de Sin planificar a Planificado.  
5. En el árbol, seleccione "Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559".
    * El trabajo para el segundo kanban también se planifica, ya que se planifica el diagrama de árbol completo. Observe que el estado del trabajo kanban se cambia de Sin planificar a Planificado.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]