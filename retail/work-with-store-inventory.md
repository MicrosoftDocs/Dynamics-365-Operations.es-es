---
title: Administrar inventario en tienda
description: "En este artículo se describen los tipos de documentos que puede usar para gestionar el inventario."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fbe9945799f1e65ed6ad624a3df270fa4eb72b88
ms.lasthandoff: 03/31/2017


---

# <a name="manage-store-inventory"></a>Administrar inventario en tienda

[!include[banner](includes/banner.md)]


En este artículo se describen los tipos de documentos que puede usar para gestionar el inventario.

Puede utilizar los siguientes tipos de documentos para gestionar el inventario de la organización.

## <a name="purchase-orders"></a>Pedidos de compra
Los pedidos de compra se crean en la oficina central. Si se incluye almacén comercial en el encabezado del pedido de compra, el pedido se puede recibir en la tienda mediante PDV PDV moderno (MPOS) o PDV en la nube en Microsoft Dynamics 365 for Operations - Retail. Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones. Otra opción es que las cantidades se comprometan y se envíen a la oficina central. En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Operations, en el campo **Recibir ahora** del pedido de compra.

## <a name="transfer-orders"></a>Transferir pedidos
Un pedido de transferencia puede especificar que una tienda concreta es una ubicación desde la que se pueden enviar artículos. En este caso, el pedido de transferencia aparece en la tienda como una solicitud de selección en MPOS o PDV en la nube. Después de seleccionar las cantidades solicitadas, se comprometen y se envían a la oficina central. En la oficina central, las cantidades que se han seleccionado en la tienda se muestran en Dynamics 365 for Operations, en el campo **Enviar ahora** del pedido de transferencia. Un pedido de transferencia puede especificar que una tienda concreta es una ubicación a la que se pueden enviar artículos. En este caso, el pedido de transferencia aparece en la tienda como una solicitud de recepción en MPOS o PDV en la nube. Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones. Otra opción es que las cantidades se comprometan y se envíen a la oficina central. En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Operations, en el campo **Recibir ahora** del pedido de transferencia.

## <a name="stock-counts"></a>Recuentos de existencias
Los recuentos de existencias se pueden programar o no. Los recuentos de existencias programados se inician en la oficina central, que especifica los artículos que se deben contar. La oficina central crea un documento que se puede recibir en la tienda, donde se especifican las cantidades de existencias disponibles reales en MPOS o PDV en la nube. Los recuentos de existencias no programados se inician en una tienda y las cantidades de existencias disponibles se actualizan en MPOS o PDV en la nube. A diferencia de los recuentos programados de existencias, los recuentos no programados de existencias no tienen una lista predefinida de artículos. Cuando finaliza un recuento de existencias de cualquier tipo, se compromete y se envía a la oficina central. En la oficina central, se valida y se registra el recuento.






