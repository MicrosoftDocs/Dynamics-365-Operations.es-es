---
title: Convertir clientes de modo asincrónico y en clientes de modo sincrónico
description: Este artículo explica cómo convertir clientes asíncronos en clientes síncronos en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b442bfc0685706359771e4d9e2729565d3652a60
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278202"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Convertir clientes de modo asincrónico y en clientes de modo sincrónico

[!include [banner](includes/banner.md)]

Este artículo explica cómo convertir clientes asíncronos en clientes síncronos en Microsoft Dynamics 365 Commerce.

Para convertir clientes asíncronos en clientes síncronos, siga estos pasos.

1. En la sede de Commerce, ejecute el **trabajo P** para enviar los clientes asíncronos a la sede de Commerce.
1. Ejecute el trabajo **Sincronizar clientes y socios comerciales desde el modo asíncrono** para crear las id. de cuenta de cliente. (Este trabajo se llamaba anteriormente **Sincronizar clientes y socios comerciales desde el modo asíncrono**.)
1. Ejecute el trabajo **1010** para sincronizar los nuevos id. de cuenta de cliente con los canales.

Si un pedido hace referencia a un cliente asincrónico o una dirección que aún no se ha sincronizado con la sede de Commerce, el cliente o la dirección se sincronizarán como parte del trabajo por lotes **Sincronización de pedidos**. Si una transacción de pago y envío hace referencia a un cliente o una dirección asincrónicos, el cliente o la dirección se sincronizarán antes del registro al final del día (EOD).

## <a name="additional-resources"></a>Recursos adicionales

[Gestión de clientes en tiendas](customer-mgmt-stores.md)

[Modo de creación de clientes asincrónico](async-customer-mode.md)

[Atributos de cliente](dev-itpro/customer-attributes.md)

[Exclusión de datos sin conexión](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
