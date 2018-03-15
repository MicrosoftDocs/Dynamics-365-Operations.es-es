---
title: Enviar un pedido de otra tienda
description: "Este tema describe la característica de envío Cargo."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 797058bdbbdb63a08eb35034ffe3c913307f38df
ms.openlocfilehash: 41434614b01f9a00f2b8a56765ecb90ee07e3d90
ms.contentlocale: es-es
ms.lasthandoff: 03/06/2018

---

# <a name="ship-an-order-from-a-different-store"></a>Enviar un pedido de otra tienda

[!include[banner](includes/banner.md)]

Con la característica de envío Cargo de Dynamics 365 for Retail, los pedidos del cliente se pueden realizar en una tienda y enviar desde otra tienda. Los pedidos de clientes en el cliente de punto de venta (PDV) admiten varias opciones de cumplimiento. Algunos ejemplos de opciones de cumplimiento:
-   Recogida en la misma tienda en otra fecha.
-   Recogida en la misma tienda en la misma o en otra fecha.
-   Envío del almacén de envío predeterminado que está asignado a la tienda, y entrega en una fecha específica.

La característica de envío Cargo utiliza las siguientes operaciones de PDV: Envío de todos los productos y Envío de productos seleccionados. Esto permite que el empleado de la tienda seleccione el “envío desde" la ubicación desde la que se puede cumplir el pedido o la línea de pedido. De forma predeterminada, la ubicación de “envío desde" es el almacén de envío asociado al almacén. Sin embargo, el empleado de la tienda puede cambiar esta ubicación y seleccionar cualquier tienda que esté definida en el grupo de localizadores de tiendas asignado a la tienda. 

La capacidad para seleccionar direcciones de “envío a” se mantiene sin cambio. 

Los métodos de envío que se pueden usar para cumplir la línea de pedido se basan en la configuración de modos válidos de entrega de productos y direcciones. Dado que las reglas sobre modos válidos de entrega sólo se mantienen en Central Retail, el cliente de PDV realiza una llamada en tiempo real para capturar los modos de entrega válidos para una línea de envío. 


