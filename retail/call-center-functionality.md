---
title: Funcionalidad del centro de llamadas
description: "Este artículo proporciona una visión general de la funcionalidad de ventas del centro de llamadas en Microsoft Dynamics 365 for Operations."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf93b1f91679cdb520ead2a12a5e52108a83fbb2
ms.lasthandoff: 03/31/2017


---

# <a name="call-center-functionality"></a>Funcionalidad del centro de llamadas

[!include[banner](includes/banner.md)]


Este artículo proporciona una visión general de la funcionalidad de ventas del centro de llamadas en Microsoft Dynamics 365 for Operations.

La venta minorista y el comercio en Microsoft Dynamics AX admite centros de llamadas como un tipo de canal de venta minorista. En un centro de llamadas, los trabajadores realizan pedidos de clientes por teléfono y crean pedidos de ventas. La funcionalidad del centro de llamadas incluye características que diseñadas para facilitar la realización de pedidos por teléfono y la gestión del servicio al cliente en el proceso del pedido. Por ejemplo, los trabajadores de los centros de llamadas pueden especificar la información de pago directamente en el pedido de ventas y pueden ver un resumen detallado de gastos y de pagos antes de enviar el pedido. Los trabajadores tienen opciones para controlar precios, y pueden acceder a distintos datos sobre los clientes, productos y precios desde la página **Pedido de ventas**. Los centros de llamadas también tienen la funcionalidad mejorada para el seguimiento del historial y el estado del pedido de cliente. Cada centro de llamadas puede tener sus propios usuarios, métodos de pago, grupos de precios, dimensiones financieras y modos de entrega. Puede configurar estas opciones cuando crea el centro de llamadas. Además, puede usar la página **Centro de llamadas** para habilitar o deshabilitar los siguientes grupos de funcionalidades que son únicas a los centros de llamadas:

-   **Finalización del pedido:** este grupo incluye características relacionadas con los pagos y la finalización del pedido en la página **Pedido de ventas**.
-   **Venta dirigida:** este grupo incluye características relacionadas con los códigos fuente, las secuencias de comandos las y solicitudes del catálogo.

Cuando se activan estas funciones de la configuración del centro de llamadas, están disponibles en la página **Pedido de ventas** para los usuarios que estén asociados con el centro de llamadas. La mayoría de ellas requieren configuración adicional antes de que se puedan usar. Para que los usuarios puedan crear pedidos del centro de llamadas, debe agregar a dichos usuarios al centro de llamadas como usuarios del centro de llamadas. Este paso permite la configuración y la funcionalidad específicas al canal de centro de llamadas. A continuación se muestran algunos ejemplos de la funcionalidad que está disponible:

-   La venta dirigida proporciona opciones de configuración para que los scripts y las imágenes de los productos de venta por teléfono ayuden y dirijan a los vendedores mientras que toman pedidos.
-   Los pedidos no se pueden completar hasta que los vendedores hayan capturado al menos un método de pago.
-   Se pueden configurar reglas de sobreventa y venta cruzada para que los vendedores promocionen productos concretos para el cliente.
-   Los vendedores pueden capturar el código fuente para el catálogo del cual un cliente está realizando el pedido.
-   Los vendedores pueden agregar los vales de un minorista al pedido.
-   Los vendedores pueden vender programas de continuidad.
-   Los pedidos se pueden poner en espera manual o automáticamente, para indicar que es necesaria una investigación adicional antes de que el pedido pueda ser procesado.





