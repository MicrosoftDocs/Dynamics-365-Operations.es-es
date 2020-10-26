---
title: Generar y procesar devoluciones de cliente
description: Este procedimiento muestra cómo procesar devoluciones de cliente desde que se genera la reclamación hasta pasarlas como acumulaciones a Clientes.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsRebateAgreement, SalesTableListPage, SalesCreateOrder, SalesTable, MCRPriceHistory, SalesEditLines,  PdsRebateTableListPage, MCRBrokerWriteOffReason, MRCHierarchyAddCust, PdsItemRebateGroup, PdsRebate, PdsRebateProgramTMATable, PdsRebateTable, PdsRebateTableListPagePreviewPane, PdsRebateTrans, PdsRebateType_CustLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a8ebc281036842bdc8965e062990438e1fb466ff
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986873"
---
# <a name="generate-and-process-customer-rebates"></a>Generar y procesar devoluciones de cliente

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo procesar devoluciones de cliente desde que se genera la reclamación hasta pasarlas como acumulaciones a Clientes. Se le guiará por un ejemplo específico para explicar cómo afectan las distintas condiciones en las líneas de devolución a los importes finales que se abonarán al cliente. Deberá usar la empresa de demostración USMF y realizar las tareas siguientes antes de comenzar el procedimiento: (1) Vaya a la página Parámetros de clientes, expanda la ficha Precios y, luego, en la ficha Detalles de precio, confirme que la opción Habilitar detalles de precio esté establecida en Sí. (2) Vaya a la página Acuerdos de devoluciones y seleccione el acuerdo de devolución de cliente: USMF-000001. Si el campo Estado de aprobación de flujo de trabajo no está establecido en Aprobado, debe hacer clic en Validación en el panel Acciones para aprobarlo.


## <a name="review-a-customer-rebate-agreement"></a>Revisión de un acuerdo de devoluciones de cliente
1. Vaya al **Panel de navegación > Módulos > Ventas y marketing >Devoluciones de cliente > Acuerdos de devoluciones**.
    - Los siguientes pasos examinan las condiciones del acuerdo USMF-000001. Esto hace más fácil comprender cómo se calculan los valores de crédito del cliente más adelante en el procedimiento.  
    - El acuerdo es para un cliente individual, en este ejemplo, el cliente US-009.  
    - Las devoluciones se dan al cliente una vez compra un producto específico. En este caso, el producto tiene número de artículo T0020.   
    - El rendimiento de ventas de cliente, según el cual se estiman los importes de la devolución, debe ser calculado por semana.  
    - El valor del "Origen del precio" es Bruto, lo que significa que el importe de ventas para la línea sobre cuya base se estima la reclamación no se reduce según el descuento de línea.  
    - El campo Tipo de salto de línea de devolución muestra el método para calcular devoluciones. En este caso, el objetivo de ventas según el cual estimar las devoluciones está establecido en Cantidad.   
    - Las líneas del acuerdo especifican el tipo de importe de la devolución, el valor real de la devolución y los umbrales. En este ejemplo, el cliente optará a una devolución de 20 USD por unidad vendida, si sus compras semanales corresponden a entre 1 y 50 unidades; y una devolución de 40 USD por unidad vendida si la compra es superior a 50 unidades.  
2. Cierre la página.

## <a name="generate-rebate-claims"></a>Generación de reclamaciones de devolución
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. Haga clic en **Nuevo**. Para imitar la manera en la que se generarán las reclamaciones de devolución, la siguiente tarea es crear un pedido de ventas donde el producto y la cantidad permitirán al cliente optar a una devolución.    
3. En el campo **Cuenta de cliente**, especifique o seleccione un valor.
4. Haga clic en **Aceptar**.
5. En el campo **Número de artículo**, especifique o seleccione un valor.
6. Establezca el valor de **Cantidad** en '40'.
7. En la sección **Líneas de pedido de ventas**, haga clic en **Línea de pedido de ventas**.
8. Haga clic en **Detalles de precio**. Si no ve esta opción, se debe a que no estableció la opción **Habilitar detalles de precio** en "Sí" antes de empezar el procedimiento.     
9. Expanda la sección **Devoluciones**. La ficha **Devoluciones** muestra todos los acuerdos de devoluciones aplicables a la línea de pedido actual y el importe estimado de devolución. Observe que los importes mostrados son solo indicaciones de lo que pueden ser las reclamaciones futuras de devolución. Los importes de devolución reales pueden variar en función de: el volumen total de ventas alcanzado por el cliente bajo un acuerdo periódico de devoluciones; si el cliente ha devuelto la cantidad total o parcialmente; y si el pedido de ventas aplicable se ha facturado.
10. Cierre la página.
11. Haga clic en **Agregar línea.**
12. En el campo **Número de artículo**, especifique o seleccione un valor.
13. Establezca el valor de **Cantidad** en '60'.
14. Haga clic en **Guardar**.
15. En el **Panel Acciones**, haga clic en **Factura**.
16. Haga clic en **Factura**.
17. Expanda la sección **Parámetros**.
18. En el campo **Cantidad**, seleccione "Todo".
19. Haga clic en **Aceptar**.
20. Haga clic en **Aceptar**.

## <a name="process-rebate-claims"></a>Procesar demandas de devolución
1. Vaya al **Panel de navegación > Módulos > Ventas y marketing >Devoluciones de cliente > Devoluciones**.
    - La página Devoluciones funciona como área de trabajo desde donde se pueden revisar, aprobar y procesar reclamaciones de devoluciones. Ahora procesará las reclamaciones creadas como resultado de facturar un pedido de ventas para el cliente US-009, el tema del acuerdo de devolución USMF-000001.   
    - La primera línea representa una reclamación de devolución de 800 USD, que se basa en las ventas de 40 unidades del producto T0020, calculado a 20 USD por unidad. Esto coincide con las condiciones del primer nivel de cantidad del acuerdo de devolución.  
    - La segunda reclamación es por 2.400 USD y se basa en la venta de 60 unidades del producto T0020, calculado a 40 USD por unidad, según el segunda nivel de cantidad del acuerdo.  
    - Ambas reclamaciones se encuentran en estado "Para calcularse". Esto significa que están asociadas con un contrato que sigue el rendimiento de ventas del cliente periódicamente y que tienen que volver a calcularse para representar el volumen total de ventas dentro del período correspondiente.   
2. Haga clic en **Acumular**.
3. En el campo **Cliente**, especifique o seleccione un valor.
4. En el campo **Fecha inicial**, seleccione la fecha en curso.
5. Haga clic en **Aceptar**. Como resultado de ejecutar la función **Acumular**, el importe de la reclamación estimado se ha ajustado para responder al hecho de que el volumen total de ventas del cliente en el período relevante es mayor que cuando se generó la primera devolución. Más concretamente, puesto que la cantidad comprada total ha alcanzado las 100 unidades, el cliente ahora puede optar a 40 USD por unidad (según el segundo nivel de cantidades del acuerdo), o a 400 USD de devolución total. La diferencia se registra como nuevo "ajuste" de reclamación por 800 USD adicionales. Ahora el estado de las reclamaciones de devolución incluidas en la actualización Acumular están definidas en Calculado. 
6. En la lista, marque todas las filas.
7. Haga clic en **Aprobar**.
8. Haga clic **Procesar**.
9. En el campo **Cliente**, especifique o seleccione un valor.
10. Haga clic en **Aceptar**. Un mensaje muestra que la devolución se ha procesado correctamente, y el estado de las reclamaciones ha cambiado a Marcar. Esto significa que como resultado de un diario de acumulación de devoluciones que se registran:
    - Las demandas se han transferido ahora al saldo del cliente temporal como deducciones.
    - La cuenta de acumulación de devoluciones se ha abonado para representar el pasivo de futuros del cliente.
    - La cuenta de gastos de la devolución se ha abonado, para reconocer el coste que se incurrió en relación con las ventas.   

