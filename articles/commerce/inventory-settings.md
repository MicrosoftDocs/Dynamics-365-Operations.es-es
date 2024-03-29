---
title: Aplicar configuración de inventario
description: Este artículo cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 49310a44f8b9c636734e04d4eed9445384b55791
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405330"
---
# <a name="apply-inventory-settings"></a>Aplicar configuración de inventario

[!include [banner](includes/banner.md)]

Este artículo cubre las configuraciones de inventario y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.

La configuración de inventario especifica si se debe verificar el inventario antes de agregar productos al carro. También definen mensajes de comercialización relacionados con el inventario, como "En existencias" y "Solo quedan unos pocos". Esta configuración garantiza que no se pueda comprar un producto si está agotado.

Dynamics 365 Commerce proporciona estimaciones de disponibilidad lista para productos. Para obtener información sobre cómo se calcula la disponibilidad lista estimada, consulte [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).

En el creador de sitios de Commerce, se pueden definir umbrales y rangos de inventario para un producto o una categoría. Determinan si el inventario se puede clasificar como en existencias, bajas existencias o agotado. Para más detalles, ver [Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md).

> [!NOTE]
> La versión Dynamics 365 Commerce 10.0.12 incluye compatibilidad con intervalos y umbrales de inventario.

## <a name="inventory-settings"></a>Configuración de inventario

En Comercio, la configuración del inventario se define en **Configuraciones del sitio \> Extensiones \> Gestión del inventario** en el creador de sitios. Hay seis configuraciones de inventario, una de las cuales está obsoleta (en desuso):

- **Habilitar comprobación de existencias en la aplicación**: esta configuración activa una comprobación de inventario del producto. La cesta, el carro y la recogida en los módulos de la tienda verificarán el inventario del producto y permitirán agregar un producto al carro solo si el inventario está disponible.
- **Nivel de inventario basado en**: esta configuración define cómo se calculan los niveles de inventario. Los valores disponibles son **Total disponible**, **Físicamente disponible** y **Umbral de agotado**. En Commerce, se pueden definir umbrales y rangos de inventario para cada producto y categoría. Las API de inventario devuelven información de inventario de producto para las propiedades **Total disponible** y **Físicamente disponible**. El minorista decide si el valor **Total disponible** o **Físicamente disponible** debe utilizarse para determinar el recuento de inventario y los rangos correspondientes para los estados en existencia y agotado.

    El valor de **Umbral de agotado** de la opción **Nivel de inventario basado en** es un valor antiguo (heredado) y obsoleto. Cuando se selecciona, el recuento de inventario se determina a partir de los resultados del valor **Total disponible**, pero el umbral está definido por la opción numérica **Umbral de agotado** que se describe más adelante. Esta configuración de umbral se aplica a todos los productos en un sitio de comercio electrónico. Si el inventario está por debajo del número de umbral, un producto se considera agotado. De lo contrario, se considera en existencias. Las capacidades del valor **Umbral de agotado** son limitadas y no recomendamos que lo use en la versión 10.0.12 y posteriores.

- **Nivel de inventario para varios almacenes**: esta configuración permite que el nivel de inventario se calcule con el almacén predeterminado o con varios almacenes. La opción **Basado en almacén individual** calculará los niveles de inventario según el almacén predeterminado. Alternativamente, un sitio de comercio electrónico puede apuntar a varios almacenes para facilitar la cumplimentación. En ese caso, la opción **Basado en el agregado de los almacenes de envío y recogida** se utiliza para indicar la disponibilidad de existencias. Por ejemplo, cuando un cliente compra un artículo y selecciona "envío" como modo de entrega, el artículo puede enviarse desde cualquier almacén del grupo de cumplimiento que tenga inventario disponible. La página de detalles del producto (PDP) mostrará un mensaje "En existencias" para el envío si algún almacén de envío disponible en el grupo de cumplimentación tiene inventario. 

    > [!IMPORTANT] 
    > La opción **Nivel de inventario para varios almacenes** está disponible a partir de la versión 10.0.19 de Commerce. Si está actualizando desde una versión anterior de Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones, consulte [Actualizaciones del SDK y la biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Configuración de inventario para páginas de lista de productos** - Esta configuración define cómo se muestran los productos agotados en las listas de productos que se representan mediante la colección de productos y los módulos de resultados de búsqueda. Los valores disponibles son **Mostrar en orden con otros productos**, **Ocultar productos agotados de la lista** y **Mostrar los productos agotados al final de la lista**. Para utilizar esta configuración, primero debe configurar algunos requisitos previos en la sede de Commerce. Para obtener más información, consulte [Lista de productos con reconocimiento de inventario](inventory-aware-product-listing.md).

    > [!IMPORTANT] 
    > La configuración **Ajustes de inventario para páginas de lista de productos** está disponible a partir de la versión 10.0.20 de Commerce. Si está actualizando desde una versión anterior de Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones, consulte [Actualizaciones del SDK y la biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Rangos de inventario**: esta configuración define los mensajes de rango de inventario que se muestran en los módulos del sitio. Solo es aplicable si el valor **Total disponible** o el valor **Físicamente disponible** se selecciona para la opción **Nivel de inventario basado en**. Los valores disponibles son **Todos**, **Bajo y agotado** y **Agotado**.

    - Cuando se selecciona **Todos** se mostrarán los mensajes para todos los rangos de inventario, desde en existencias (mensaje "Disponible") hasta agotado (mensaje "Agotado").
    - Cuando se selecciona **Bajo y agotado**, se mostrarán los mensajes para todos los rangos de inventario, excepto en existencias (mensaje "Disponible").
    - Cuando se selecciona **Agotado**, solo se mostrará el mensaje "Agotado".

- **Umbral de agotado**: esta configuración numérica antigua solo tendrá efecto si se selecciona el valor **Umbral de agotado** para la opción **Nivel de inventario basado en**.

> [!IMPORTANT] 
> Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.12. Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Módulos que usan configuraciones de inventario

Cuadro de compra, lista de deseos, carro y los módulos de icono de carro usan configuraciones de inventario para mostrar los rangos de inventario y los mensajes.

En el ejemplo de la siguiente ilustración, un PDP muestra un mensaje de estar en existencias ("Disponible").

![Ejemplo de un módulo PDP que tiene un mensaje de en existencias.](./media/pdp-InStock.png)

En el ejemplo de la siguiente ilustración, un PDP muestra un mensaje de estar "Sin existencias".

![Ejemplo de un módulo PDP que tiene un mensaje de agotado.](./media/pdp-outofstock.png)

En el ejemplo de la siguiente ilustración, un carro muestra un mensaje de estar en existencias ("Disponible").

![Ejemplo de un módulo de carro que tiene un mensaje de en existencias.](./media/cart-instock.png)

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Configurar búferes de inventario y niveles de inventario](inventory-buffers-levels.md)

[Módulo de carro](add-cart-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulos y páginas de gestión de cuentas](account-management.md)

[Módulo de selector de tienda](store-selector.md)

[Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
