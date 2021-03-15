---
title: Aplicar configuración de inventario
description: Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 77a3bde12fd047e15d7730903416cdb5263a8cd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972818"
---
# <a name="apply-inventory-settings"></a>Aplicar configuración de inventario

[!include [banner](includes/banner.md)]

Este tema cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La configuración de inventario especifica si se debe verificar el inventario antes de agregar productos al carro. También definen mensajes de comercialización relacionados con el inventario, como "En stock" y "Solo quedan unos pocos". Esta configuración garantiza que no se pueda comprar un producto si está agotado.

Dynamics 365 Commerce proporciona estimaciones de disponibilidad lista para productos. Para obtener información sobre cómo se calcula la disponibilidad lista estimada, consulte [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).

En el creador de sitios de Commerce, se pueden definir umbrales y rangos de inventario para un producto o una categoría. Determinan si el inventario se puede clasificar como en existencias, bajas existencias o agotado. Para más detalles, ver [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).

> [!NOTE]
> La versión Dynamics 365 Commerce 10.0.12 incluye compatibilidad con intervalos y umbrales de inventario.

## <a name="inventory-settings"></a>Configuración de inventario

En Comercio, la configuración del inventario se define en **Configuraciones del sitio \> Extensiones \> Gestión del inventario** en el creador de sitios. Hay cuatro configuraciones de inventario, una de las cuales está obsoleta (en desuso):

- **Habilitar comprobación de existencias en la aplicación**: esta configuración activa una comprobación de inventario del producto. La cesta, el carro y la recogida en los módulos de la tienda verificarán el inventario del producto y permitirán agregar un producto al carro solo si el inventario está disponible.
- **Nivel de inventario basado en**: esta configuración define cómo se calculan los niveles de inventario. Los valores disponibles son **Total disponible**, **Físicamente disponible** y **Umbral de agotado**. En Commerce, se pueden definir umbrales y rangos de inventario para cada producto y categoría. Las API de inventario devuelven información de inventario de producto para las propiedades **Total disponible** y **Físicamente disponible**. El minorista decide si el valor **Total disponible** o **Físicamente disponible** debe utilizarse para determinar el recuento de inventario y los rangos correspondientes para los estados en existencia y agotado.

    El valor de **Umbral de agotado** de la opción **Nivel de inventario basado en** es un valor antiguo (heredado) y obsoleto. Cuando se selecciona, el recuento de inventario se determina a partir de los resultados del valor **Total disponible**, pero el umbral está definido por la opción numérica **Umbral de agotado** que se describe más adelante. Esta configuración de umbral se aplica a todos los productos en un sitio de comercio electrónico. Si el inventario está por debajo del número de umbral, un producto se considera agotado. De lo contrario, se considera en existencias. Las capacidades del valor **Umbral de agotado** son limitadas y no recomendamos que lo use en la versión 10.0.12 y posteriores.

- **Rangos de inventario**: esta configuración define los rangos de inventario para los que se muestran los mensajes para los módulos del sitio. Solo es aplicable si el valor **Total disponible** o el valor **Físicamente disponible** se selecciona para la opción **Nivel de inventario basado en**. Los valores disponibles son **Todos**, **Bajo y agotado** y **Agotado**.

    - Cuando se selecciona **Todos** se mostrarán los mensajes para todos los rangos de inventario, desde en stock (mensaje "Disponible") hasta agotado (mensaje "Agotado").
    - Cuando se selecciona **Bajo y agotado**, se mostrarán los mensajes para todos los rangos de inventario, excepto en existencias (mensaje "Disponible").
    - Cuando se selecciona **Agotado**, solo se mostrará el mensaje "Agotado".

- **Umbral de agotado**: esta configuración numérica antigua solo tendrá efecto si se selecciona el valor **Umbral de agotado** para la opción **Nivel de inventario basado en**.

> [!IMPORTANT] 
> Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.12. Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Módulos que usan configuraciones de inventario

Cuadro de compra, lista de deseos, carro y los módulos de icono de carro usan configuraciones de inventario para mostrar los rangos de inventario y los mensajes.

La siguiente imagen muestra un ejemplo de una página de detalles del producto (PDP) que muestra un mensaje de en existencias ("Disponible").

![Ejemplo de un módulo PDP que tiene un mensaje de en existencias](./media/pdp-InStock.png)

La siguiente imagen muestra un ejemplo de un PDP que muestra un mensaje ("Agotado").

![Ejemplo de un módulo PDP que tiene un mensaje de agotado](./media/pdp-outofstock.png)

La siguiente imagen muestra un ejemplo de un carro que muestra un mensaje en existencias ("Disponible").

![Ejemplo de un módulo de carro que tiene un mensaje de en existencias](./media/cart-instock.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md)

[Módulo de carro](add-cart-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulos y páginas de gestión de cuentas](account-management.md)

[Módulo de selector de tienda](store-selector.md)

[Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]