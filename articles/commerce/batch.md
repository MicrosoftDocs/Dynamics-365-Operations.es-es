---
title: Control administrado de artículos con seguimiento por lotes
description: En este artículo se describe el control mejorado de los artículos con seguimiento por lotes durante el proceso de registro de extracto en Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 736ab8dd21f04d7119cca6d53bfeb5e408b8cbd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881889"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Control administrado de artículos con seguimiento por lotes

[!include [banner](includes/banner.md)]

En este artículo se describe el control mejorado de los artículos con seguimiento por lotes durante el proceso de registro de extracto en Microsoft Dynamics 365 Commerce.

En el punto de venta (PDV) de Dynamics 365 Commerce, los números de lotes no se pueden obtener para los artículos con seguimiento por lotes en el momento de la venta. Sin embargo, para las configuraciones específicas cuando se registran las ventas en las sedes centrales de Commerce a través del registro de extractos o pedidos de clientes, Commerce espera que existan números de lotes válidos para artículos con seguimiento por lotes y se usarán durante el proceso de facturación.

Si hay números de lotes válidos disponibles para los productos, tanto el proceso de facturación de pedidos de clientes como el proceso de facturación de pedidos de ventas del registro de extractos los usan. Si los números de lote válidos no están disponibles para los productos, no se puede registrar el proceso de facturación de pedidos de clientes y el usuario de PDV recibe un mensaje de error. A continuación, el registro de extractos entra en un estado de error, incluso si se ha activado el inventario negativo para los productos.

Las mejoras que se han realizado en Commerce ayudan a garantizar que, cuando se activa inventario negativo para artículos con seguimiento por lotes, no se bloquean la facturación de pedidos de clientes ni la facturación de pedidos de ventas a través del registro de extractos para esos artículos si el inventario es 0 (cero) o un número de lote no está disponible. La funcionalidad mejorada usa un id. de lote predeterminado para las líneas de ventas cuando los números de lotes no están disponibles.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Defina el id. de lote predeterminado que se utiliza para los pedidos de clientes.

Para definir el id. de lote predeterminado que se utiliza para los pedidos de clientes, siga estos pasos.

1. En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de Commerce**.
1. En la pestaña **Pedidos de cliente**, en la ficha desplegable **Pedido**, introduzca un valor en el campo **Id. de lote predeterminado**.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Defina el id. de lote predeterminado que se utiliza para la facturación de pedidos de ventas mediante el registro de extractos.

Para definir el id. de lote predeterminado que se utiliza para la facturación de pedidos de ventas mediante el registro de extractos, siga estos pasos.

1. En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de Commerce**.
1. En la pestaña **Registro**, en la ficha desplegable **Actualización del inventario**, introduzca un valor en el campo **Id. de lote predeterminado**.

> [!NOTE]
> - La funcionalidad de id. de lote predeterminado solo está disponible cuando el almacenamiento avanzado está habilitado para los artículos y el almacén de la tienda específicos. En una versión futura, la funcionalidad de id. de lote predeterminado también se habilitará para escenarios donde no se use la gestión avanzada de almacenes.
> - La compatibilidad para el control mejorado de los artículos con seguimiento por lotes durante el registro de extractos para los escenarios no avanzados de gestión de almacenes se introdujo en Commerce versión 10.0.5.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
