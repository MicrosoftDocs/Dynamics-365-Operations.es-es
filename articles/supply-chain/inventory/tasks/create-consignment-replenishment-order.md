---
title: Crear un pedido de reabastecimiento de entrega
description: "Este procedimiento muestra cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7f8005ec9e723c94d53e6ab81f04ee388c83faa
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-consignment-replenishment-order"></a>Crear un pedido de reabastecimiento de entrega

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega. También muestra cómo registrar una recepción de productos para registrar el inventario de entrega como inventario disponible propiedad del proveedor. Este procedimiento normalmente lo haría un profesional de compras. Puede usar esta guía en la empresa de datos de demostración USMF. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.




## <a name="create-a-consignment-replenishment-order"></a>Crear un pedido de reabastecimiento de entrega
1. Ir a Adquisición y abastecimiento > Envío > Pedidos de reabastecimiento de envío.
2. Haga clic en Nuevo.
3. En el campo Cuenta del proveedor, seleccione el proveedor US-104.
    * Debe seleccionar un proveedor registrado como propietario en la página Propietarios de inventario.  
4. Haga clic en Aceptar
5. Haga clic en Agregar línea.
6. En el campo Número de artículo, escriba "M9211CI".
    * Debe seleccionar un artículo que se ha configurado como inventario de entrega.  
7. En el campo Cantidad, especifique un número.
8. En el campo Fecha de entrega solicitada, especifique una fecha.
    * El motor MRP usa las fechas solicitada y confirmada para la llegada esperada de las mercancías.  
9. En el campo Fecha de entrega confirmada, especifique una fecha.
10. Expanda la sección Detalles de línea.
11. Haga clic en la ficha Dimensiones de inventario.
12. Para mostrar el propietario en el campo Propietario de las dimensiones de inventario, actualice la página.
    * Ahora el proveedor US-104 aparece como propietario.  

## <a name="check-the-inventory-transaction-status"></a>Compruebe el estado de la transacción de inventario
1. Haga clic en Inventario.
2. Haga clic en Transacciones.
3. En la lista, marque la fila seleccionada.
    * Tenga en cuenta que el campo Recepción está establecido en Pedido.  
4. Cierre la página.

## <a name="receive-items"></a>Recibir artículos
1. Haga clic en Recepción de producto.
2. En el campo Recepción de producto externa, escriba un valor.
3. En el campo Cantidad, escriba un número que sea inferior al número que se muestra aquí.
4. Haga clic en Aceptar

## <a name="check-the-on-hand-inventory"></a>Compruebe el inventario disponible
1. Haga clic en Inventario.
2. Haga clic en Disponible.
3. Haga clic en Visión general.
    * Los artículos que se han recibido como inventario de entrega propiedad del proveedor están disponibles. La cantidad restante en el pedido de reabastecimiento de entrega se muestra en el campo Pedido en total.  
4. Cierre la página.
5. Haga clic en Cerrar.

