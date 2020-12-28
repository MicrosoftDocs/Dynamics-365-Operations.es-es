---
title: Programaciones de entrega
description: Las programaciones de entrega le permiten realizar el seguimiento de cantidad de la línea de pedido cuando está usando entregas para un pedido de ventas único, un presupuesto de ventas o un pedido de compra.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc25ff113291b2a8a0a7ba15637e4d094feb9aae
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437016"
---
# <a name="delivery-schedules"></a>Programaciones de entrega

[!include [banner](../includes/banner.md)]

Las programaciones de entrega le permiten realizar el seguimiento de cantidad de la línea de pedido cuando está usando entregas para un pedido de ventas único, un presupuesto de ventas o un pedido de compra.

Use una programación de entrega cuando la cantidad total de una línea de pedido o presupuesto debe entregarse en varios envíos. Los envíos individuales se representan por medio las líneas de entrega. Dos o más líneas de entrega constituyen una programación de entrega. Las líneas de entrega pueden tener diferentes fechas de entrega, cantidades, modos de entrega y dimensiones de almacenamiento, como sitio y almacén.  

**Ejemplo de una programación de entrega**

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| Pedido total (línea de pedido original) | 600 sillas                               |
| Programación de entrega solicitada       | 100 sillas por mes                     |
| Plazo de entrega solicitado | 6 meses, el primer día de cada mes |

En este escenario, el cliente solicita una entrega de 600 sillas en lotes de 100 sillas durante un período de seis meses. Para realizar un seguimiento de los requisitos de entrega, se crea una programación de entrega. En la página de programación de entrega, cree seis líneas de entrega distintas. Cada línea de entrega contiene 100 sillas e indica la fecha de entrega de esas 100 sillas. En este caso, cada línea se compensará el primer día del mes durante seis meses consecutivos.  

Una vez que haya creado la programación de entrega, el tipo de la línea de pedido original se convierte automáticamente en **Línea de pedido con varias entregas**. Una línea de este tipo se denomina línea comercial y está marcada mediante un icono. La línea de entrega está marcada con otro icono. Si cambia una cantidad en una línea de entrega, la línea comercial se actualiza a la cantidad total de la programación de entrega. Si un acuerdo comercial ha definido un descuento total para el pedido, la programación de entrega garantiza que se pueda aplicar al pedido el descuento de pedido total, incluso cuando el pedido se divide en entregas distintas.  

Los pedidos que tengan una programación de entrega se procesan con las líneas de entrega. El proceso incluye el registro de albaranes, recepciones de producto y facturación.  

Las impresiones de documentos de pedidos y de presupuestos con una programación de entrega solo muestran las líneas de entrega. No muestran las líneas originales (líneas comerciales). **Nota:** Además, solo se muestran las líneas de entrega cuando realiza estas acciones:

-   Registrar
-   Copiar páginas
-   Examinar informes y páginas de lista

Cuando confirma los presupuestos de ventas, los pedidos de ventas resultantes muestran la programación de entrega completa, incluso las líneas de pedido con múltiples entregas. Además, la programación de entrega completa se muestra en todas las páginas principales, como pedidos de ventas, presupuestos de ventas y pedidos de compra.



