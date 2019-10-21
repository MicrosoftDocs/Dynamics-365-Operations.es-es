---
title: Crear un pedido de compra desde un pedido de ventas
description: Este procedimiento muestra cómo crear un pedido de compra basado en un pedido de ventas.
author: omulvad
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b346731ec80d08afabe648e1b47b30b53b29e744
ms.sourcegitcommit: 62d66f98d4bbf916e19184506b90055bb68d219f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "1924419"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Crear un pedido de compra desde un pedido de ventas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un pedido de compra basado en un pedido de ventas. Las cantidades del producto del pedido de compra se designan a continuación para satisfacer la demanda del pedido de ventas de origen. La satisfacción de la demanda de ventas de esta manera es una alternativa a un método más completo y optimizado de la planificación de requisitos de distribución. Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Crear un pedido de compra desde un pedido de ventas
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta de cliente**, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro deseado.
5. Haga clic en **Aceptar**.
6. En el campo **Código de artículo**, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado. Si está usando USMF, podría seleccionar D0001.  
8. En el campo **Cantidad**, especifique un número.
9. Haga clic en **Agregar línea.**
10. En el campo **Código de artículo**, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, busque y seleccione el registro deseado. Si está usando USMF, podría seleccionar T0020.  
12. En la lista, haga clic en el vínculo de la fila seleccionada.
13. En el campo **Cantidad**, especifique un número.
14. Haga clic en **Guardar**.
15. En el **panel de acciones**, haga clic en **Pedido de ventas**.
16. Haga clic en **Pedido de compra**. La página **Crear pedido de compra** muestra todas las líneas de pedidos de ventas abiertas que se han copiado del pedido de ventas. Puede revisar los detalles del pedido y, si es necesario, modificar los detalles seleccionados como condiciones de precios y cantidad de compra antes de crear las compras. 
17. Seleccione la opción **Incluir todos**.
    - Si desea generar una pedidos de compra solo para un subconjunto de las líneas de pedidos de ventas, selecciónelas de manera individual.  
    - El campo **Cuenta de proveedor** puede o no rellenarse con un número de proveedor. Si el proveedor predeterminado está configurado para el producto (en la cobertura de artículo asociada), este proveedor se copiará en la línea. De lo contrario, debe especificar un proveedor manualmente.  En esta guía, independientemente de si el campo **Cuenta de proveedor** ya contiene un valor o no, los siguientes pasos le indican que seleccione un nuevo proveedor que sea diferente para cada línea.  
18. En el campo **Cuenta de proveedor**, haga clic en el botón desplegable para abrir la búsqueda.
19. En la lista, busque y seleccione el registro deseado.
20. En la lista, haga clic en el vínculo de la fila seleccionada.
21. Seleccione la segunda línea del pedido.
22. En el campo **Cuenta de proveedor**, haga clic en el botón desplegable para abrir la búsqueda.
23. En la lista, busque y seleccione el registro deseado.
24. En la lista, haga clic en el vínculo de la fila seleccionada.
25. Hacer clic en **Validar**.
26. Haga clic en **Aceptar**. El mensaje informa de que se han creado uno o varios pedidos de compra. El sistema genera un pedido de compra independiente para cada proveedor que ha especificado para las líneas de pedido de ventas. Esto significa que si el mismo proveedor va a proporcionar varias líneas de pedidos de ventas, se generará un único pedido de compra con varias líneas.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Revisar los pedidos de compra creados a partir de pedidos de ventas
1. En el **panel de acciones**, haga clic en **General**.
2. Haga clic en **Pedidos relacionados**. La página **Pedidos relacionados** muestra todos los pedidos que se crearon del pedido de ventas. En este ejemplo, hay dos pedidos de compra generados para dos proveedores diferentes respectivamente. 
3. Haga clic para seguir el vínculo en el campo **Pedido de compra**. Cada línea de pedido de compra se asocia con la línea de pedido de ventas que condujo a la compra. La relación con el pedido de ventas se indica en la ficha **Producto** de la ficha desplegable **Detalles de línea**, en los campos **Tipo de referencia**, **Número de referencia** y **Lote de referencia**.  
4. Expanda o contraiga la sección **Detalles de línea**.
5. Haga clic en la ficha **Producto**.
    - El **Lote de referencia** garantiza que los costes de la compra actual se carguen en el pedido de ventas vinculado.  
    - Par navegar hasta el pedido de ventas de origen, abra el vínculo del campo **Número de referencia**.  

