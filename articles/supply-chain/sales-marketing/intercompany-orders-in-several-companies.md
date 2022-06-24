---
title: Creación de pedidos de ventas y compra de empresas vinculadas en varias empresas
description: Este artículo explica la creación de pedidos de ventas o de compras de empresas vinculadas en varias empresas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6dce419126d60199bc11d4bd3209185ad779e979
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873561"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Creación de pedidos de ventas y compra de empresas vinculadas en varias empresas

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management no está limitado únicamente a la gestión de una empresa de producción y varias empresas de ventas. Todas las empresas configuradas para empresas vinculadas pueden ser empresas comerciales y de producción.

Si hay más empresas que puedan entregar el mismo artículo, puede elegir libremente a quién comprar y las actualizaciones se procesan aun cuando un pedido de ventas se convierta en varios pedidos de compra.

De la misma forma que crea automáticamente un pedido de compra de empresas vinculadas, puede crear un pedido de ventas original en la empresa y hacer que varias empresas proveedoras de empresas vinculadas cumplan el pedido creando más de un pedido de empresas vinculadas. Microsoft Dynamics 365 Supply Chain Management automáticamente crea pedidos de empresas vinculadas en las empresas proveedoras.

Para ello, todas las empresas deben configurarse como relaciones comerciales. La empresas proveedoras se deben configurar en Microsoft Dynamics 365 Supply Chain Management como proveedores de empresas vinculadas y deben ser el proveedor principal del artículo relevante. En el pedido de ventas, en **Vista de encabezado**, debe seleccionar el campo **Crear automáticamente pedidos de empresas vinculadas** y el campo **Entrega directa** en la ficha desplegable **Configuración de empresas vinculadas** . Esta es la configuración predeterminada.

Se crean las líneas de ventas del modo habitual. Al dejar el registro, aparece un mensaje informando de que se han creado los pedidos de compra de empresas vinculadas y los pedidos de ventas de empresas vinculadas. El mensaje contiene vínculos a los nuevos pedidos. Para ver los pedidos de venta de empresas vinculadas en sus empresas proveedoras, abra el pedido de ventas original y, en la ficha **General**, en el grupo **Información relacionada**, seleccione **Referencias**.

Si abre los pedidos de compras de empresas vinculadas para los proveedores, verá que Microsoft Dynamics 365 Supply Chain Management rellena automáticamente el número de pedido de ventas original y el número de pedido de ventas de empresas vinculadas para cada proveedor.

De forma similar, si abre los pedidos de ventas de empresas vinculadas para los proveedores, verá que Microsoft Dynamics 365 Supply Chain Management rellena automáticamente el número de pedido de ventas original y el número de pedido de compras de empresas vinculadas para cada proveedor.

> [!NOTE]
> Si los artículos del pedido existe en una de las empresas proveedoras de empresas vinculadas pero no existe en la otra, Microsoft Dynamics 365 Supply Chain Management crea los pedidos de empresas vinculadas para la empresa proveedora en la que existen los artículos, pero detiene la creación de pedido para la otra empresa. Si esto sucede, aparece un mensaje de notificación.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
