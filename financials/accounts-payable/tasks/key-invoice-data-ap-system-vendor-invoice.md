--- 
title: Introducir datos de factura en el sistema de proveedores mediante una factura de proveedor
description: "Esta guía de tareas le ayudará a crear una factura de proveedor de un pedido de compra y a ver los resultados de conciliación del pedido de compra, la recepción y la factura (triple conciliación)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a365c52af49a66d6af5bb38f0053bd9c0fd34301
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a>Introducir datos de factura en el sistema de proveedores mediante una factura de proveedor

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tareas le ayudará a crear una factura de proveedor de un pedido de compra y a ver los resultados de conciliación del pedido de compra, la recepción y la factura (triple conciliación).


## <a name="create-a-purchase-order"></a>Crear un pedido de compra
1. Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. Busque un proveedor para seleccionarlo. Por ejemplo, desplácese hasta US-104.
5. Seleccione el proveedor US-104.
6. Haga clic en Aceptar
7. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
8. Seleccione un artículo de inventario. Para este ejemplo, seleccione el código de artículo 1000.
9. Expanda o contraiga la sección Detalles de línea.
10. Haga clic en la pestaña Configurar.
    * Puede anular la directiva de conciliación para no usar ninguna conciliación, doble conciliación o triple conciliación.  
11. Expanda o contraiga la sección Detalles de línea.
12. En el panel de acciones, haga clic en Compra.
13. Haga clic en Confirmar.

## <a name="receive-the-products"></a>Recibir los productos
1. En el panel de acciones, haga clic en Recibir.
2. Haga clic en Recepción de producto.
3. En el campo Recepción de producto, especifique el número de recepción de producto. Por ejemplo, escriba PR123.
4. Haga clic en Aceptar para registrar la recepción de producto.
5. Cierre la página.

## <a name="create-a-vendor-invoice"></a>Crear una factura de proveedor
1. Vaya a Clientes > Pedidos de compra > Pedidos de compra recibidos pero no facturados.
2. Seleccione el pedido de compra que ha creado.
3. En el panel de acciones, haga clic en Factura.
4. Haga clic en Factura.
5. En el campo Número, especifique el número de factura.
6. En el campo Descripción de factura, escriba un valor.
7. En el campo Fecha de la factura, especifique una fecha.
8. En el campo Precio unitario, escriba 1200.
9. Haga clic en Agregar línea.
10. En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, busque el número de artículo de cargo de la instalación. Por ejemplo, S0001
12. Seleccione el número de artículo de cargo de la instalación.
    * Tenga en cuenta que no se ha realizado ninguna conciliación desde que realizó los cambios.  
13. Haga clic en Actualizar estado de conciliación.
14. En el panel de acciones, haga clic en Revisar.
15. Haga clic en Detalles coincidentes.
    * La nueva línea con servicios no tiene que conciliarse, por lo que el estado sigue siendo “No se realizó”.  
16. Seleccione la recepción de producto para el artículo de inventario que ha recibido.
    * La línea con la recepción de producto se concilió, pero no existe coincidencia de cantidad o de precio, por lo que se ha producido algún error.  
17. En el campo Precio unitario, escriba un número.
    * Ahora que el precio unitario coincide, el estado se actualiza a Aprobado. Si la directiva permite las discrepancias o si la conciliación solo es una advertencia, podrá registrar la factura.  
18. Cierre la página.
19. Haga clic en Registrar.
20. Cierre el formulario.
    * Tenga en cuenta que el pedido de compra ya no aparece en la lista como recibido, sino como no facturado.  


