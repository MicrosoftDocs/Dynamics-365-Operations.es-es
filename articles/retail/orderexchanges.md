---
title: Configurar y procesar un cambio en un pedido de devolución
description: En este tema se explica cómo configurar un cambio en una devolución en Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5a0a6a060a1b4a4d5a80c797f61b212a828d2f04
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517164"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Configurar y procesar un cambio en un pedido de devolución

[!include [banner](includes/banner.md)]

En versiones anteriores de Microsoft Dynamics 365 for Retail, las devoluciones relacionadas con pedidos de cliente se procesaban con el documento de pedido de devolución en Retail Headquarters. Sin embargo, el documento de pedido de devolución se puede usar para procesar solo los productos devueltos. Los productos devueltos se indican con una cantidad negativa en las líneas de pedido de devolución. En cambio, las ventas se indican con una cantidad positiva. Sin embargo, el documento de pedido de devolución no admite cantidades positivas. Debido a esta limitación, las versiones anteriores de Retail no admitían situaciones en las que los cambios de producto se hacen con el documento de pedido de devolución.

Ahora se ha agregado funcionalidad para admitir situaciones en las que los cambios se realizan con pedidos de devolución. Retail usa el documento de pedido de ventas en lugar del documento de pedido de devolución para procesar transacciones de este tipo.

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a>Configurar Retail para admitir cambios en pedidos de devolución

Siga estos pasos para configurar el sistema de forma que admita cambios en pedidos de devolución.

1. Vaya a **Retail \> Configuración de sede central \> Parámetros \> Parámetros comerciales**. En la ficha desplegable **Pedidos de cliente**, establezca la opción **Procesar pedidos de devolución como pedidos de ventas** en **Sí**.
2. Ejecute el trabajo **Programación de distribución de configuración global** (**1110**).

## <a name="make-an-exchange"></a>Realizar un cambio

Una vez que el sistema se haya configurado de la manera descrita en la sección anterior, el usuario del punto de venta (PDV) seleccionará un pedido de ventas o una factura de ventas para procesar una devolución, como en las versiones anteriores de Retail. Sin embargo, después de agregar los artículos devueltos al carro, el usuario podrá agregar nuevas líneas de ventas al carro.

Para estas nuevas líneas de ventas, el usuario debe definir todos los atributos necesarios para procesar una línea de pedidos de cliente. Estos atributos incluyen el método de entrega y la ubicación de cumplimiento. El pago para la transacción será el valor neto de las líneas de pedido de devolución y las líneas de pedido de ventas. Si se realiza el pago para la transacción, el pedido de devolución se registrará como un documento de pedido de ventas en Retail Headquarters y el sistema facturará inmediatamente las líneas de devolución.

Para proporcionar mayor visibilidad de los distintos importes del carro, se han agregado al carro tres nuevos campos de importe. Puede usar el diseñador de pantalla para hacer que estos campos nuevos estén disponibles en la interfaz de usuario del punto de venta.

- **Depósito aplicado**: el importe del depósito que se aplica en una transacción cuando el usuario hace una recogida de pedido de cliente. Si no hay anulación de depósito y se configura un depósito del 10 por ciento, el importe de este campo es el 90 por ciento del importe total del pedido de cliente.
- **Importe de realización**: el importe total de las líneas en las que el modo de entrega se estableció en **Realizar** cuando el pedido de cliente se creó o editó, o durante un cambio de pedido de cliente. El importe de este campo incluye todos los impuestos y gastos.
- **Importe de devolución**: el importe total de las líneas que tienen cantidades negativas durante el cambio de pedido de cliente. El importe de este campo incluye todos los impuestos y gastos.
