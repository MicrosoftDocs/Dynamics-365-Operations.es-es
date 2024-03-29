---
title: Habilitar la gestión del modo de entrega coherente en los canales de comercio electrónico
description: Este artículo describe cómo habilitar el manejo del modo de entrega coherente para abordar posibles problemas relacionados con los flujos de cargos en los canales de comercio electrónico de Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 43450c9d380bd57c234bb1c9acfbe296ab115f14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279660"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Habilitar la gestión del modo de entrega coherente en los canales de comercio electrónico 

[!include [banner](includes/banner.md)]

Este artículo describe cómo habilitar el manejo del modo de entrega coherente para abordar posibles problemas relacionados con los flujos de cargos en los canales de comercio electrónico de Microsoft Dynamics 365 Commerce.

En Dynamics 365 Commerce, los cargos de nivel de encabezado no prorrateados no se aplican de forma predeterminada en los canales de comercio electrónico. Este comportamiento podría causar uno o ambos de los siguientes problemas en los canales de comercio electrónico:

- No aparecen los cargos de nivel de encabezado no prorrateados.
- Los cargos por los modos de entrega no son coherentes entre la selección del modo de entrega y el resumen de pedido de finalización de compra.

Para solucionar estos problemas, debe activar la característica **Habilitar modo de entrega coherente en el canal**. Esta característica garantiza que los cargos de nivel de encabezado no prorrateados aparezcan en los canales de comercio electrónico y que la información de entrega de pedidos de ventas se maneje de manera coherente mediante el mismo flujo de trabajo de solicitud.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Activar la característica Habilitar modo de entrega coherente en el canal

Para habilitar la característica **Habilitar modo de entrega coherente en el canal** en la sede de Commerce, siga estos pasos.

1. Abre el espacio de trabajo **Administración de características** (**Administración del sistema \> Espacios de trabajo \> Administración de características**).
1. En la lista de características disponibles, busque y seleccione **Habilitar modo de entrega coherente en el canal**.
1. En el panel derecho, seleccione **Habilitar ahora**.
