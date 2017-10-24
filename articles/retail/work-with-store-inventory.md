---
title: Administrar inventario en tienda
description: "En este artículo se describen los tipos de documentos que puede usar para gestionar el inventario."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1fd37bcd7155c61492f5f4990685203ea97bca36
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="manage-store-inventory"></a>Administrar inventario en tienda

[!include[banner](includes/banner.md)]


En este artículo se describen los tipos de documentos que puede usar para gestionar el inventario.

Puede utilizar los siguientes tipos de documentos para gestionar el inventario de la organización.

## <a name="purchase-orders"></a>Pedidos de compra
Los pedidos de compra se crean en la oficina central. Si se incluye un almacén comercial en el encabezado del pedido de compra, el pedido se puede recibir en la tienda mediante Modern POS (MPOS) o Cloud POS en Microsoft Dynamics 365 for Retail. Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones. Otra opción es que las cantidades se comprometan y se envíen a la oficina central. En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Retail, en el campo **Recibir ahora** del pedido de compra.

## <a name="transfer-orders"></a>Transferir pedidos
Un pedido de transferencia puede especificar que una tienda concreta es una ubicación desde la que se pueden enviar artículos. En este caso, el pedido de transferencia aparece en la tienda como una solicitud de selección en MPOS o PDV en la nube. Después de seleccionar las cantidades solicitadas, se comprometen y se envían a la oficina central. En la oficina central, las cantidades que se han seleccionado en la tienda se muestran en Dynamics 365 for Retail, en el campo **Enviar ahora** del pedido de transferencia. Un pedido de transferencia puede especificar que una tienda concreta es una ubicación a la que se pueden enviar artículos. En este caso, el pedido de transferencia aparece en la tienda como una solicitud de recepción en MPOS o PDV en la nube. Después de especificar las cantidades que se reciben en la tienda, se pueden guardar de manera local para realizar otras modificaciones. Otra opción es que las cantidades se comprometan y se envíen a la oficina central. En la oficina central, las cantidades que se han recibido en la tienda se muestran en Dynamics 365 for Retail, en el campo **Recibir ahora** del pedido de transferencia.

## <a name="stock-counts"></a>Recuentos de existencias
Los recuentos de existencias se pueden programar o no. Los recuentos de existencias programados se inician en la oficina central, que especifica los artículos que se deben contar. La oficina central crea un documento que se puede recibir en la tienda, donde se especifican las cantidades de existencias disponibles reales en MPOS o PDV en la nube. Los recuentos de existencias no programados se inician en una tienda y las cantidades de existencias disponibles se actualizan en MPOS o PDV en la nube. A diferencia de los recuentos programados de existencias, los recuentos no programados de existencias no tienen una lista predefinida de artículos. Cuando finaliza un recuento de existencias de cualquier tipo, se compromete y se envía a la oficina central. En la oficina central, se valida y se registra el recuento.

## <a name="inventory-lookup"></a>Búsqueda de inventario
La cantidad de producto disponible actualmente para múltiples tiendas y almacenes se puede ver en la página de consulta de inventario. Además de la cantidad disponible actual, las cantidades futuras de neto no comprometido (NNC) se pueden visualizar para cada tienda. Para ello, seleccione la tienda para la que desea ver el NNC y después para haga clic en **Mostrar disponibilidad en tienda**.





