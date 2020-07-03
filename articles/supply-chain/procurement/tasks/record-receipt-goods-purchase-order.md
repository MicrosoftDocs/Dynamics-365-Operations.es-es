---
title: Registrar la recepción de mercancías en el pedido de compra
description: Este tema explica cómo registrar la recepción de mercancías directamente en un pedido de compra.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1aa4043aca2e53eae32256a98d556c25b4ec1957
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454796"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrar la recepción de mercancías en el pedido de compra

[!include [banner](../../includes/banner.md)]

Este tema explica cómo registrar la recepción de mercancías directamente en un pedido de compra. También es posible registrar la recepción de productos en el almacén y, a continuación, registrarla después en el pedido de compra. Esta tarea se realiza normalmente por un agente de compras o un coordinador de Proveedores. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF. El ejemplo incluye pasos para crear un pedido de compra sencillo para que pueda reproducir el procedimiento como guía de tareas. Si estuviera utilizando el procedimiento en sus propios datos, empezaría en la subtarea **Registrar recepción de mercancías**.


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a>Preparar un nuevo pedido de compra para la recepción de mercancías
1. Vaya a **Panel de exploración, Módulos > Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de proveedor**, escriba `US-101`.
4. Seleccione **Aceptar**.
5. En el campo **Número de artículo**, especifique `M0001`.
6. En el campo **Cantidad**, especifique `5`.
7. En el panel de acciones, selecione **Compra.**
8. Seleccione **Confirmar**.

## <a name="record-receipt-of-goods"></a>Registrar recepción de mercancías
1. En el panel de acciones, seleccione **Recibir**.
2. Seleccione **Recepción de producto**. El campo **Cantidad** le permite seleccionar diferentes opciones para la cantidad que desea recibir. Por ejemplo, si se ha registrado una cantidad anteriormente en el almacén, puede seleccionar **Cantidad registrada**. Para este ejemplo, utilice el valor **Cantidad pedida**.
3. Expanda la sección **Información general**.
4. En el campo **Recepción de producto**, escriba cualquier valor. Este campo se utiliza para especificar una referencia que se usará como asiento para el diario de recepción de productos.  
5. Expanda la sección **Líneas**.
6. Establezca el valor de **Cantidad** en '4'. Aquí puede especificar manualmente la cantidad que se está recibiendo para cada línea del pedido.  
7. Seleccione **Aceptar**. Las mercancías se han registrado ahora como recibidas en el pedido de compra y se ha creado un diario de recepción de producto como documento para reflejar esto. Puede utilizar la acción Recepción de producto para revisar los diarios creados con el pedido de compra y ver qué se ha recibido y cuándo.  

