---
title: Enviar pedidos como entregas directas
description: En este tema se demuestra cómo crear una entrega directa para un pedido de ventas.
author: omulvad
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart, PurchEditLines, PurchTable, PurchTableReferences, MCRDropShipWorkbench, SalesShippingLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a8f214a56c6a5013cab8233d5b2e0126deb9220
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966114"
---
# <a name="ship-orders-as-direct-deliveries"></a>Enviar pedidos como entregas directas

[!include [banner](../../includes/banner.md)]

En este tema se demuestra cómo crear una entrega directa para un pedido de ventas. La entrega directa se usa si desea enviar mercancías al cliente directamente desde el proveedor, en lugar de enviarlas a su propio almacén primero. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Para finalizar correctamente la segunda subtarea "Crear entregas directas desde el área de trabajo", asegúrese de que el artículo que elige en el pedido de ventas tiene un proveedor predeterminado especificado en la ficha desplegable Compra del productos maestro emitido.

## <a name="set-an-individual-order-for-direct-delivery"></a>Definir un pedido individual para entrega directa
1. Vaya a **panel de navegación > Módulos > Clientes > Pedidos > Todos los pedidos de vents**.
2. Seleccione **Nuevo**.
3. Introduzca o seleccione un valor en el campo **Cuenta de clietne** y seleccione **Aceptar**.
4. Escriba o seleccione los valores de **Número de artículo** y **Sitio** y después seleccione **Guardar**.
5. En el panel de acciones, seleccione **Pedido de ventas** y **Entrega directa**. La página Crear entrega muestra todas las líneas de pedidos de ventas abiertas según se copian del pedido de ventas. Puede revisar los detalles del pedido y, si es necesario, modificar los detalles como condiciones de precios y cantidad de compra antes de crear la entrega directa.  
6. Seleccione **Sí** en el campo **Incluir todos**.
    - Si desea generar una entrega directa solo para un subconjunto de las líneas de pedidos de ventas, selecciónelas de manera individual.  
    - El campo **Cuenta de proveedor** puede o no rellenarse con un número de proveedor. Si el proveedor predeterminado está configurado para el producto (en la cobertura de artículo asociada), este proveedor se copiará en la línea. De lo contrario, debe especificar un proveedor manualmente. En este ejemplo, seleccionaremos un nuevo proveedor en el siguiente paso, incluso si ya hay uno rellenado.   
7. Introduzca o seleccione un valor en el campo **Cuenta de proveedor** y seleccione **Aceptar**. El mensaje informa de que se ha creado el pedido de compra.   
8. Expanda la sección **Detalles de línea.**
9. Seleccione la pestaña **Entrega** y compruebe que el campo **Entrega directa** está establecido **Sí**.
10. En el panel de acciones, seleccione **Gneral**.
11. Seleccione **Pedidos relacionados**.
12. Seleccione el vínculo en el campo **Pedido de compra**.
13. Expanda la sección **Detalles de línea** y seleccione la pestaña **Dirección** .
    - La dirección de entrega para esta línea de pedido de compra es la dirección de entrega del cliente y la no la dirección de su empresa.  
    - Si se modifica la dirección de entrega en la línea del pedido de ventas o la línea de pedido de ventas de origen, se actualizará automáticamente la dirección en la línea del pedido correspondiente.  
14. Seleccione la ficha **Entrega**.
    - Como la línea de pedido de ventas, el tipo asociado de la línea de pedido de compra asociado también se establece en Entrega directa.  
    - La Fecha de entrega y la Fecha de entrega confirmada de la línea del pedido de compra se establecen en la Fecha de recepción solicitada y la Fecha de recepción confirmada de la línea de pedido de ventas de origen respectivamente.   
    - Si actualiza cualquiera de estas fechas en la línea de compra o la línea de ventas, las fechas del pedido correspondiente se actualizarán automáticamente.     
    - El pedido de compra que se establece para entregar mercancías directamente al cliente está vinculado al pedido de ventas de origen mediante una asociación especial. Esta asociación impone la regla de que la actualización del albarán del pedido de ventas no se puede realizar desde el propio pedido de ventas y se debe realizar mediante el pedido de compra. Sin embargo, la facturación del cliente se debe llevar a cabo desde el pedido de ventas.  
15. En el panel de acciones, selecione **Compra.**
16. Seleccione **Confirmación**.
17. Seleccione **Aceptar**.
18. En el panel de acciones, seleccione **Recibir**.
19. Seleccione **Recepción de producto**.
20. En el campo **Recepción de producto**, escriba un valor.
21. Seleccione **Aceptar**.
22. En el panel de acciones, seleccione **Gneral**.
23. Seleccione **Pedidos relacionados** y resalte el registro deseado.
    - Después de que el pedido de compra se haya actualizado como recibido, es decir, después de que el proveedor haya enviado las mercancías a la dirección del cliente, el estado del pedido de ventas de origen se actualiza automáticamente a Entregado.  
    - El pedido de ventas se puede facturar ahora.    
24. Seleccione **Aceptar**.
25. Cierre la página.
26. Seleccione **Aceptar**. Cierre las páginas y vuelva a la página principal.

## <a name="create-direct-deliveries-from-the-workbench"></a>Crear entregas directas desde el área de trabajo
1. Vaya a **Navegación > Módulos > Clientes > Pedidos > Todos los pedidos de vents**.
2. Seleccione **Nuevo**.
3. Introduzca o seleccione un valor en el campo **Cuenta de clietne** y seleccione **Aceptar**.
4. Introduzca o seleccione un valor en los campos **Número de artículo** y **Sitio**.
5. Expanda la sección **Detalles de línea** y seleccione la ficha **Entrega**. En lugar de crear una entrega directa como parte del procesamiento de pedidos de ventas en el procedimiento anterior, puede elegir entregar esta tarea a un profesional de compras. Para incluir la línea de pedido de ventas en el proceso de control de entregas directas, debe marcar la línea para entrega directa.  
6. Seleccione **Sí** en el campo **Entrega directa**.
    - Si el artículo ya se ha configurado para entrega directa de forma predeterminada, el campo se establecerá automáticamente a Sí en la entrada de la línea de pedido. Puede configurar un artículo para entrega directa en el maestro del Producto emitido estableciendo la opción Entrega directa en Sí y seleccionando un almacén de entrega directa predeterminado.  
    - Dado que el pedido de compra no se ha creado todavía, el estado de la entrega directa se establece en "Realizar entrega directa".   
7. Seleccione **Guardar**.
8. Cierre las páginas hasta que vuelva a la página principal.
9. Escriba `Direct delivery` en la barra de búsqueda
    - La página Entrega directa actúa como área de trabajo que proporciona al agente de compras una visión general de todas las líneas de pedidos de ventas que se procesarán por entrega directa y le permite crear los pedidos de compra respectivos. Además, puede ver los pedidos abiertos de entrega directa y los pedidos confirmados en las fichas Confirmación y Entrega.  
    - Después de crear un pedido de entrega directa, se desplazó automáticamente a la ficha de confirmación. Puede elegir confirmar el pedido directamente desde esta página. Cuando se confirme la compra, se moverá automáticamente a la ficha Entrega, desde la que puede registrar su recepción.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]