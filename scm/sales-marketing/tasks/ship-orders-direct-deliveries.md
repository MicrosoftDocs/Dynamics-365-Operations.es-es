--- 
title: Enviar pedidos como entregas directas
description: "En este procedimiento se demuestra cómo crear una entrega directa para un pedido de ventas."
author: omulvad
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d98e288a157183fbf4d7c032d86bb4a65166e297
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="ship-orders-as-direct-deliveries"></a>Enviar pedidos como entregas directas

[!include[task guide banner](../../includes/task-guide-banner.md)]

En este procedimiento se demuestra cómo crear una entrega directa para un pedido de ventas. La entrega directa se usa si desea enviar mercancías al cliente directamente desde el proveedor, en lugar de enviarlas a su propio almacén primero. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Para finalizar correctamente la segunda subtarea "Crear entregas directas desde el área de trabajo", asegúrese de que el artículo que elige en el pedido de ventas tiene un proveedor predeterminado especificado en la ficha desplegable Compra del productos maestro emitido.


## <a name="set-an-individual-order-for-direct-delivery"></a>Definir un pedido individual para entrega directa
1. Vaya a Todos los pedidos de ventas.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar la cuenta US-001.  
4. Haga clic en Aceptar
5. En el campo Número de artículo, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar el artículo T0020.  
6. Haga clic en Guardar.
7. En el panel de acciones, haga clic en Pedido de ventas.
8. Haga clic en Entrega directa.
    * La página Crear entrega muestra todas las líneas de pedidos de ventas abiertas según se copian del pedido de ventas. Puede revisar los detalles del pedido y, si es necesario, modificar los detalles como condiciones de precios y cantidad de compra antes de crear la entrega directa.  
9. Seleccione Sí en el campo Incluir todos.
    * Si desea generar una entrega directa solo para un subconjunto de las líneas de pedidos de ventas, selecciónelas de manera individual.  
    * El campo Cuenta de proveedor puede o no rellenarse con un número de proveedor. Si el proveedor predeterminado está configurado para el producto (en la cobertura de artículo asociada), este proveedor se copiará en la línea. De lo contrario, debe especificar un proveedor manualmente. En este ejemplo, seleccionaremos un nuevo proveedor en el siguiente paso, incluso si ya hay uno rellenado.   
10. En el campo Cuenta de proveedor, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar la cuenta 1001.  
11. Haga clic en Aceptar
    * El mensaje informa de que se ha creado el pedido de compra.   
12. Expanda la sección Detalles de línea.
13. Haga clic en la pestaña Entrega.
    * El campo Entrega directa está establecido ahora en Sí.  
    * El estado Entrega directa muestra el pedido de compra creado.   
14. En el panel de acciones, haga clic en General.
15. Haga clic en Pedidos relacionados.
16. Haga clic para seguir el vínculo en el campo Pedido de compra.
17. Expanda la sección Detalles de línea.
18. Haga clic en la ficha Dirección.
    * Tenga en cuenta que la dirección de entrega para esta línea de pedido de compra es la dirección de entrega del cliente y la no la dirección de su empresa.  
    * Si se modifica la dirección de entrega en la línea del pedido de ventas o la línea de pedido de ventas de origen, se actualizará automáticamente la dirección en la línea del pedido correspondiente.  
19. Haga clic en la pestaña Entrega.
    * Como la línea de pedido de ventas, el tipo asociado de la línea de pedido de compra asociado también se establece en Entrega directa.  
    * La Fecha de entrega y la Fecha de entrega confirmada de la línea del pedido de compra se establecen en la Fecha de recepción solicitada y la Fecha de recepción confirmada de la línea de pedido de ventas de origen respectivamente.   
    * Si actualiza cualquiera de estas fechas en la línea de compra o la línea de ventas, las fechas del pedido correspondiente se actualizarán automáticamente.     
    * El pedido de compra que se establece para entregar mercancías directamente al cliente está vinculado al pedido de ventas de origen mediante una asociación especial. Esta asociación impone la regla de que la actualización del albarán del pedido de ventas no se puede realizar desde el propio pedido de ventas y se debe realizar mediante el pedido de compra. Sin embargo, la facturación del cliente se debe llevar a cabo desde el pedido de ventas.  
20. En el panel de acciones, haga clic en Compra.
21. Haga clic en Confirmación.
22. Haga clic en Aceptar
23. En el panel de acciones, haga clic en Recibir.
24. Haga clic en Recepción de producto.
25. En el campo Recepción de producto, escriba un valor.
26. Haga clic en Aceptar
27. En el panel de acciones, haga clic en General.
28. Haga clic en Pedidos relacionados.
29. En la lista, marque la fila seleccionada.
    * Después de que el pedido de compra se haya actualizado como recibido, es decir, después de que el proveedor haya enviado las mercancías a la dirección del cliente, el estado del pedido de ventas de origen se actualiza automáticamente a Entregado.  
    * El pedido de ventas se puede facturar ahora.    
30. Haga clic en Aceptar
31. Cierre la página.
32. Haga clic en Aceptar

## <a name="create-direct-deliveries-from-the-workbench"></a>Crear entregas directas desde el área de trabajo
1. Cierre la página.
2. Cierre la página.
3. Vaya a Todos los pedidos de ventas.
4. Haga clic en Nuevo.
5. En el campo Cuenta de cliente, especifique o seleccione un valor.
6. Haga clic en Aceptar
7. En el campo Número de artículo, especifique o seleccione un valor.
8. Expanda la sección Detalles de línea.
9. Haga clic en la pestaña Entrega.
    * En lugar de crear una entrega directa como parte del procesamiento de pedidos de ventas en el procedimiento anterior, puede elegir entregar esta tarea a un profesional de compras. Para incluir la línea de pedido de ventas en el proceso de control de entregas directas, debe marcar la línea para entrega directa.  
10. Seleccione Sí en el campo Entrega directa.
    *   Si el artículo ya se ha configurado para entrega directa de forma predeterminada, el campo se establecerá automáticamente a Sí en la entrada de la línea de pedido. Puede configurar un artículo para entrega directa en el maestro del Producto emitido estableciendo la opción Entrega directa en Sí y seleccionando un almacén de entrega directa predeterminado.  
    * Dado que el pedido de compra no se ha creado todavía, el estado de la entrega directa se establece en Realizar entrega directa.   
11. Cierre la página.
12. Cierre la página.
13. Vaya a Entrega directa.
    * La página Entrega directa actúa como área de trabajo que proporciona al agente de compras una visión general de todas las líneas de pedidos de ventas que se procesarán por entrega directa y le permite crear los pedidos de compra respectivos. Además, puede ver los pedidos abiertos de entrega directa y los pedidos confirmados en las fichas Confirmación y Entrega.   
14. Haga clic en Crear entrega directa.
15. Haga clic en la ficha Confirmación.
    * Una vez que haya creado un pedido de entrega directa, se mueve automáticamente a la ficha Confirmación. Puede elegir confirmar el pedido directamente desde esta página. Cuando se confirme la compra, se moverá automáticamente a la ficha Entrega, desde la que puede registrar su recepción.  


