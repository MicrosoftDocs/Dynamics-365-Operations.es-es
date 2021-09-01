---
title: Crear un pedido de compra para un proveedor plantilla
description: Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla.
author: kamaybac
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e6c8283290564d930418c1832bbd285532445ff0e69db8f78d13542c8232e97
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720309"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Crear un pedido de compra para un proveedor plantilla

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un pedido de compra para un distribuidor plantilla. El proveedor se crea automáticamente con el pedido de compra, en lugar de tener que crear la cuenta de proveedor manualmente. Los pedidos de compra normalmente se crean por un agente de compras. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF. Es un requisito previo que se haya configurado una cuenta de proveedor plantilla en la página Parámetros de proveedores.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Crear un pedido de compra para un proveedor plantilla
1. Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. Seleccione Sí en el campo Proveedor de una sola vez.
    * Una cuenta de proveedor se crea automáticamente y se asigna al pedido de compra. La cuenta de proveedor se crea basándose en la plantilla que se especifica en la pestaña General de la página Parámetros de proveedores.  
4. En el campo Nombre, escriba un nombre único para el proveedor.
5. Haga clic en Aceptar
    * El pedido de compra se puede completar ahora y procesarse como cualquier otro pedido. No hay características especiales relacionadas con cómo se hace esto. La factura considerará una transacción vencida en la cuenta del proveedor que se creó con el pedido y el pago se procesará entonces.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]