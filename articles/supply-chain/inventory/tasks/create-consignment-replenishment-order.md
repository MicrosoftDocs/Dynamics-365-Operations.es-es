---
title: Crear un pedido de reabastecimiento de entrega
description: Este tema explica cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega.
author: mkirknel
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e993190150e2d82088390d8db4b7c5ada2b0161
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437259"
---
# <a name="create-a-consignment-replenishment-order"></a>Crear un pedido de reabastecimiento de entrega

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega. También muestra cómo registrar una recepción de productos para registrar el inventario de entrega como inventario disponible propiedad del proveedor. Este procedimiento normalmente lo haría un profesional de compras. Puede usar esta guía en la empresa de datos de demostración USMF. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

## <a name="create-a-consignment-replenishment-order"></a>Crear un pedido de reabastecimiento de entrega
1. En el panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Entrega > Pedidos de reabastecimiento de entrega**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de proveedor**, seleccione el proveedor **US-104** (es preciso seleccionar un proveedor que esté registrado como propietario en la página **propietarios de inventario**). 
4. Seleccione **Aceptar**.
5. Seleccione **Agregar línea**.
6. En el campo **Código de artículo**, escriba `M9211CI` (debe seleccionar un artículo que se haya configurado como inventario de envío).
7. En el campo **Cantidad**, especifique un número.
8. En el campo **Fecha de entrega solicitada**, especifique una fecha. El motor MRP usa las fechas solicitada y confirmada para la llegada esperada de las mercancías.  
9. En el campo **Fecha de entrega confirmada**, especifique una fecha.
10. Expanda la sección **Detalles de línea.**
11. Seleccionar la pestaña **Dimensiones del inventario**
12. Para mostrar el propietario en el campo **Propietario de las dimensiones de inventario**, actualice la página. Ahora el proveedor US-104 aparece como propietario.  

## <a name="check-the-inventory-transaction-status"></a>Compruebe el estado de la transacción de inventario
1. Seleccione **Inventario**.
2. Seleccione **Transacciones**.
3. En la fila que desee, tenga en cuenta que el campo **Recepción** está establecido en **Pedido**.  
4. Cierre la página.

## <a name="receive-items"></a>Recibir artículos
1. Seleccione **Recepción de producto**.
2. En el campo **Recepción de producto externa**, escriba un valor.
3. En el campo **Cantidad**, escriba un número que sea inferior al número que se muestra aquí. 
4. Seleccione **Aceptar**.

## <a name="check-the-on-hand-inventory"></a>Compruebe el inventario disponible
1. Seleccione **Inventario**.
2. Seleccione **Disponibles**.
3. Seleccione **Visión general**. Los artículos que se han recibido como inventario de entrega propiedad del proveedor están disponibles. La cantidad restante en el pedido de reabastecimiento de entrega se muestra en el campo **Pedido en total**.  
4. Cierre la página.

