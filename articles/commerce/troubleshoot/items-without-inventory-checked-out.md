---
title: Los artículos agotados se pueden comprar
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los clientes pueden agregar artículos agotados a su carrito y proceder al pago.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6df9c77248c7f4e16765b98327fe5838f0fce7e4
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585517"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Los artículos agotados se pueden comprar

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los clientes pueden agregar artículos agotados a su carrito y proceder al pago.

## <a name="description"></a>Descripción

Los usuarios pueden agregar un artículo a su carrito, aunque no haya inventario disponible en la tienda, y luego pasar a la página de pago.

## <a name="resolution"></a>Resolución

### <a name="enable-the-show-out-of-stock-errors-property-in-commerce-site-builder"></a>Habilite la propiedad Mostrar errores de falta de existencias en el creador de sitios de Commerce

Para habilitar la propiedad **Mostrar errores de falta de existencias** en el creador de sitios de Commerce, siga estos pasos.

1. Seleccione el sitio en el que está trabajando.
1. En el panel de navegación izquierdo, seleccione **Páginas**.
1. Seleccione **CartPage** para abrirlo.
1. Seleccione la parte del **Carrito 1**, seleccione **Editar** y luego, en el panel de propiedades, seleccione la casilla **Mostrar errores de falta de existencias**.
1. Guarde y publique la página.

## <a name="additional-resources"></a>Recursos adicionales

[Aplicar configuración de inventario](../inventory-settings.md)

[Calcular la disponibilidad de inventario para canales comerciales](../calculated-inventory-retail-channels.md)

[Configurar búferes de inventario y niveles de inventario](../inventory-buffers-levels.md)
