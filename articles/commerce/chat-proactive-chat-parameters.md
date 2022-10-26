---
title: Parámetros de chat proactivos del módulo Chat de Commerce
description: Este artículo describe los parámetros de chat proactivos de los módulos de chat de Commerce en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: f3cff89a25ff84414e7fdd32cbb26404c2080187
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691078"
---
# <a name="commerce-chat-module-proactive-chat-parameters"></a>Parámetros de chat proactivos del módulo Chat de Commerce

[!include [banner](includes/banner.md)]

Este artículo describe los parámetros de chat proactivos de Commerce Chat con omnicanal para servicio al cliente y Commerce Chat con Power Virtual Agents módulos de chat en Microsoft Dynamics 365 Commerce.

## <a name="proactive-chat-properties"></a>Propiedades de chat proactivas

Las propiedades proactivas del chat se encuentran en el panel de propiedades de Commerce Chat con omnicanal para servicio al cliente y Commerce Chat con módulos de Power Virtual Agents en el creador de sitios de Commerce.

> [!NOTE]
> De forma predeterminada, todas las propiedades de chat proactivas que se enumeran aquí están en blanco. Le recomendamos que obtenga más información sobre estas propiedades y las configure solo cuando sean necesarias. Este enfoque ayudará a reducir la activación de chats proactivos erróneos.

### <a name="proactive-chat"></a>Chat proactivo

| Nombre descriptivo | Description | Valor predeterminado |
|---------------|-------------|---------------|
| Habilitada | Involucrar a los clientes de manera proactiva, en función de diferentes factores desencadenantes. | Deshabilitado |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. | En blanco |

### <a name="wait-time-proactive-chat"></a>Tiempo de espera (chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Tiempo de espera (s) | El tiempo (en segundos) que los usuarios del sitio pasan en una página del sitio antes de que se active un chat proactivo. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="number-of-page-visits-proactive-chat"></a>Número de visitas a la página (chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Número de visitas a la página | El número de visitas a la página antes de que se active un chat proactivo. Los usuarios del sitio primero deben aceptar el aviso en el banner de consentimiento de cookies. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="specific-pages-proactive-chat"></a>Páginas específicas (Chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Página(s) | Una lista de las páginas que activarán un chat proactivo cuando sean visitadas. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="from-specific-pages-proactive-chat"></a>Desde páginas específicas (Chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Página(s) | Una lista de las páginas que activarán un chat proactivo cuando los usuarios naveguen desde ellas. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="specific-countryregion-proactive-chat"></a>País/región específicos (chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Código de país | Los usuarios que visiten desde países o regiones específicos activarán un chat proactivo. Los códigos de país/región deben tener dos letras mayúsculas (por ejemplo: **US**). |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="date-range-proactive-chat"></a>Intervalo de fechas (chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Fecha de inicio (dd/mm/aaaa) | La fecha en o después de la cual se activará un chat proactivo. |
| Fecha de finalización (dd/mm/aaaa) | La fecha en o antes de la cual se activará un chat proactivo. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="total-amount-in-cart-proactive-chat"></a>Importe total en el carrito (chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Mínimo | El importe monetario mínimo (incluido) en el carrito de compras que activará un chat proactivo cuando los usuarios visiten la página del carrito. |
| Máximo | El importe monetario máximo (incluido) en el carrito de compras que activará un chat proactivo cuando los usuarios visiten la página del carrito. |
|Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="total-number-of-items-in-cart-proactive-chat"></a>Número total de artículos en el carrito (chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Mínimo | El número mínimo de artículos (incluido) en el carrito de compras que activará un chat proactivo cuando los usuarios visiten la página del carrito. |
| Máximo | El número máximo de artículos (incluido) en el carrito de compras que activará un chat proactivo cuando los usuarios visiten la página del carrito. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

### <a name="specific-products-in-cart-proactive-chat"></a>Productos específicos en el carrito (Chat proactivo)

| Nombre descriptivo | Description |
|---------------|-------------|
| Id./SKU de producto(s) | Una lista de los ID de productos/números de unidades de mantenimiento de existencias (SKU) que activarán un chat proactivo cuando los usuarios visiten la página del carrito. |
| Saludo de chat | El mensaje de saludo que se usa cuando se activa un chat proactivo. |

## <a name="additional-resources"></a>Recursos adicionales

[Información general de las características de chat de Commerce](commerce-chat-overview.md)

[Módulo Chat de Commerce con omnicanal para Customer Service](commerce-chat-module.md)

[Módulo Chat de Commerce con Power Virtual Agents](chat-module-pva.md)
