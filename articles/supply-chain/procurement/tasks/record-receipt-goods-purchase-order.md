---
title: Registrar la recepción de mercancías en el pedido de compra
description: Este artículo explica cómo registrar la recepción de mercancías directamente en un pedido de compra.
author: GalynaFedorova
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22baf6d0f6db04b3c6ce3c09ee8cb286e9a1e590
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882471"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a>Registrar la recepción de mercancías en el pedido de compra

[!include [banner](../../includes/banner.md)]

Este artículo explica cómo registrar la recepción de mercancías directamente en un pedido de compra. También es posible registrar la recepción de productos en el almacén y, a continuación, registrarla después en el pedido de compra. Esta tarea se realiza normalmente por un agente de compras o un coordinador de Proveedores. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF. El ejemplo incluye pasos para crear un pedido de compra sencillo para que pueda reproducir el procedimiento como guía de tareas. Si estuviera utilizando el procedimiento en sus propios datos, empezaría en la subtarea **Registrar recepción de mercancías**.


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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]