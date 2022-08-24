---
title: Los artículos agotados se pueden comprar
description: Este artículo proporciona una guía para la resolución de problemas que puede ayudar cuando los clientes pueden agregar artículos agotados a su carrito y proceder al pago.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 3bc924e44077886b942e19b25a84f0f1d4298c13
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282744"
---
# <a name="items-without-inventory-can-be-checked-out"></a>Los artículos agotados se pueden comprar

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía para la resolución de problemas que puede ayudar cuando los clientes pueden agregar artículos agotados a su carrito y proceder al pago.

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
