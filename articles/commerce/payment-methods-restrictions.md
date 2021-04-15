---
title: Restringir métodos de pago para devoluciones sin un recibo
description: Este tema describe cómo determinados tipos de pago se pueden limitar para la devolución si las devoluciones se crean sin un recibo.
author: rapraj
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: dd07c9c95639c8e69e1013fd7da283cf51b60ed0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804536"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restringir métodos de pago para devoluciones sin un recibo


[!include [banner](includes/banner.md)]

Al configurar el sistema, se deben configurar todos los tipos de pago que acepte un minorista. Este tema describe cómo determinados tipos de pago se pueden limitar para la devolución si las devoluciones se crean sin un recibo.

## <a name="set-up-payment-methods"></a>Configurar métodos de pago

Para configurar los métodos de pago, debe completar las tareas siguientes.
1. Cree métodos de pago aceptados en toda la organización.
2. Creación de tipos y números de tarjeta de la organización. Si desea aceptar tarjetas de crédito o de débito, debe crear un método de pago para tarjetas y, a continuación, los tipos y números de tarjeta de la organización.
3. Configurar métodos de pago en tienda. Asocie métodos de pago a cada tienda e indique la configuración específica de la tienda para cada método de pago.
4. Configurar tipos de pago con tarjeta para tiendas. Complete la configuración de tarjeta para todos los métodos de pago con tarjeta que acepte la tienda.

![Configuración de tienda](media/NoReceiptReturns1.png "Configuración de tienda") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restringir métodos de pago para devoluciones sin un recibo

Para cada método de pago de tienda, en la página **Administración de tienda**, en **Devoluciones sin recibo**, establezca **Limitar las devoluciones sin recibo** en **Sí**. 

El valor predeterminado es **No**, que garantiza que el método de pago se tiene en cuenta para devoluciones. 

Cuando **Limitar devoluciones sin recibo** se establece en **Sí**, el método de pago seleccionado no se permitirá para las devoluciones. 

![Método de pago de la tienda](media/NoReceiptReturns3.png "Método de pago de tienda") 

> [!NOTE]
> Si un cajero selecciona un método de pago limitado para la devolución sin un recibo, aparece un mensaje para comprobar los métodos de los pagos aceptables.

![Métodos de pago aceptables](media/NoReceiptReturns4.png "Métodos de pago aceptables") 

Si una transacción tiene una devolución con recibo como sin él, las condiciones de la restricción no se aplicarán porque la transacción será un flujo de trabajo de devolución con un recibo. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]