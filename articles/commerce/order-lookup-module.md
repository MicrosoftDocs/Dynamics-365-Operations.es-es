---
title: Módulo de búsqueda de pedidos
description: En este artículo se trata el modulo de búsqueda de pedidos y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: c83463d9a0ece9605b0d22bee2a1c76057c8ed05
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869439"
---
# <a name="order-lookup-module"></a>Módulo de búsqueda de pedidos

[!include [banner](includes/banner.md)]

En este artículo se trata el modulo de búsqueda de pedidos y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.

El módulo de búsqueda de pedidos proporciona un formulario que los clientes pueden utilizar para buscar los pedidos que realizaron en un sitio de comercio electrónico. Se utiliza como parte de la función [Habilitar la búsqueda de pedidos para los pagos de invitados](order-lookup-guest.md). El módulo de búsqueda de pedidos se puede utilizar para buscar pedidos que se enviaron a través de un sitio de comercio electrónico, el punto de venta minorista (POS) o un centro de llamadas. El formulario puede recuperar pedidos enviados tanto por usuarios invitados como por usuarios registrados.

La siguiente ilustración muestra un ejemplo del formulario que representa el módulo de búsqueda de pedidos. Cuando los clientes completen el formulario y seleccionen **Encuentra tu pedido**, se les redirige a la página de detalles del pedido.

![Formulario para el módulo de búsqueda de pedidos en una página.](./media/OrderLookup_module.PNG)

## <a name="order-lookup-module-properties"></a>Propiedades del módulo de búsqueda de pedidos

| Nombre de la propiedad     | Valor     | Descripción |
|-------------------|-----------|-------------|
| Cabecera           | Texto      | El encabezado que aparece en la parte superior del formulario (por ejemplo, "Encuentra tu pedido"). |
| Texto enriquecido         | Texto enriquecido | Texto explicativo opcional que aparece debajo del encabezado. |
| Tipo de estado del pedido | Enum      | <p>Seleccione el tipo de información que el formulario solicitará al cliente además del ID de confirmación del pedido. Actualmente se admiten los siguientes valores:</p><ul><li><b>Correo electrónico</b> - El formulario incluirá un campo donde los clientes pueden ingresar la dirección de correo electrónico que utilizaron cuando realizaron el pedido.</li><li><b>Ninguno</b> - El formulario no solicitará más información que el ID de confirmación del pedido.</li></ul> |

## <a name="add-an-order-lookup-module-to-a-page"></a>Agregar un módulo de búsqueda de pedidos a una página

El módulo de búsqueda de pedidos se puede agregar al cuerpo de cualquier página de su sitio de comercio electrónico. Si desea utilizar el módulo de búsqueda de pedidos para habilitar la búsqueda de pedidos para los pagos de invitados, asegúrese de agregarlo a una página que no requiera que el usuario haya iniciado sesión. Para encontrar la configuración **¿Requiere iniciar sesión?** de una página en la vista de árbol del creador de sitios de Commerce, seleccione la ranura **Página predeterminada (requerida)** y observe la parte inferior del panel derecho.

## <a name="additional-resources"></a>Recursos adicionales

[Habilitar la búsqueda de pedidos para los pagos de invitados](order-lookup-guest.md)

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
