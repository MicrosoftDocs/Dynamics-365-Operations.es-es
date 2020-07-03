---
title: Aplicar configuración de inventario
description: Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7fc81c190806a0bdb50569f526589cfa1808ce0c
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417447"
---
# <a name="apply-inventory-settings"></a>Aplicar configuración de inventario

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La configuración de inventario especifica si se debe verificar el inventario antes de agregar productos al carro. También definen mensajes de comercialización relacionados con el inventario, como "En stock" y "Solo quedan unos pocos". Esta configuración garantiza que no se pueda comprar un producto si está agotado.

Dynamics 365 Commerce proporciona estimaciones de disponibilidad lista para productos. Para obtener información sobre cómo se calcula la disponibilidad lista estimada, consulte [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).

En el creador de sitios de Commerce, se pueden definir umbrales y rangos de inventario para un producto o una categoría. Determinan si el inventario se puede clasificar como en existencias, bajas existencias o agotado. Para más detalles, ver [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).

## <a name="inventory-settings"></a>Configuración de inventario

En Comercio, la configuración del inventario se define en **Configuraciones del sitio \> Extensiones \> Gestión del inventario** en el creador de sitios. Hay cuatro configuraciones de inventario, una de las cuales está obsoleta (en desuso):

- **Habilitar comprobación de inventario en la aplicación**: esta configuración activa una comprobación de inventario del producto. La cesta, el carro y la recogida en los módulos de la tienda verificarán el inventario del producto y permitirán agregar un producto al carro solo si el inventario está disponible.
- **Nivel de inventario basado en**: esta configuración define cómo se calculan los niveles de inventario. Los valores disponibles son **Total disponible**, **Físicamente disponible** y **Umbral de agotado**. En Commerce, se pueden definir umbrales y rangos de inventario para cada producto y categoría. Las API de inventario devuelven información de inventario de producto para las propiedades **Total disponible** y **Físicamente disponible**. El minorista decide si el valor **Total disponible** o **Físicamente disponible** debe utilizarse para determinar el recuento de inventario y los rangos correspondientes para los estados en existencia y agotado.

    El valor de **Umbral de agotado** de la opción **Nivel de inventario basado en** es un valor antiguo (heredado) y obsoleto. Cuando se selecciona, el recuento de inventario se determina a partir de los resultados del valor **Total disponible**, pero el umbral está definido por la opción numérica **Umbral de agotado** que se describe más adelante. Esta configuración de umbral se aplica a todos los productos en un sitio de comercio electrónico. Si el inventario está por debajo del número de umbral, un producto se considera agotado. De lo contrario, se considera en existencias. Las capacidades del valor **Umbral de agotado** son limitadas y no recomendamos que lo use en la versión 10.0.12 y posteriores.

- **Rangos de inventario**: esta configuración define los rangos de inventario para los que se muestran los mensajes para los módulos del sitio. Solo es aplicable si el valor **Total disponible** o el valor **Físicamente disponible** se selecciona para la opción **Nivel de inventario basado en**. Los valores disponibles son **Todos**, **Bajo y agotado** y **Agotado**.

    - Cuando se selecciona **Todos** se mostrarán los mensajes para todos los rangos de inventario, desde en stock (mensaje "Disponible") hasta agotado (mensaje "Agotado").
    - Cuando se selecciona **Bajo y agotado**, se mostrarán los mensajes para todos los rangos de inventario, excepto en existencias (mensaje "Disponible").
    - Cuando se selecciona **Agotado**, solo se mostrará el mensaje "Agotado".

- **Umbral de agotado**: esta configuración numérica antigua solo tendrá efecto si se selecciona el valor **Umbral de agotado** para la opción **Nivel de inventario basado en**.

## <a name="modules-that-use-inventory-settings"></a>Módulos que usan configuraciones de inventario

Cuadro de compra, lista de deseos, carro y los módulos de icono de carro usan configuraciones de inventario para mostrar los rangos de inventario y los mensajes.

La siguiente imagen muestra un ejemplo de una página de detalles del producto (PDP) que muestra un mensaje de en existencias ("Disponible").

![Ejemplo de un módulo PDP que tiene un mensaje de en existencias](./media/pdp-InStock.png)

La siguiente imagen muestra un ejemplo de un PDP que muestra un mensaje ("Agotado").

![Ejemplo de un módulo PDP que tiene un mensaje de agotado](./media/pdp-outofstock.png)

La siguiente imagen muestra un ejemplo de un carro que muestra un mensaje en existencias ("Disponible").

![Ejemplo de un módulo de carro que tiene un mensaje de en existencias](./media/cart-instock.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md)

[Módulo de carro](add-cart-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulos y páginas de gestión de cuentas](account-management.md)

[Módulo de selector de tienda](store-selector.md)
