---
title: Aplicar agregar producto a la configuración del carrito
description: En este artículo se trata la configuración de "Agregar producto al carrito" y se describe cómo aplicarla a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 16644e6746d182cd86a40861c4e30a85a9d3d478
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277037"
---
# <a name="apply-add-product-to-cart-settings"></a>Aplicar agregar producto a la configuración del carrito

[!include [banner](includes/banner.md)]

En este artículo se trata la configuración de **Agregar producto al carrito** y se describe cómo aplicarla a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Se admiten diferentes flujos de trabajo cuando se agrega un producto al carrito en un sitio de comercio electrónico de Dynamics 365 Commerce. Por ejemplo, se puede llevar al usuario del sitio a la página del carrito. Alternativamente, el usuario puede permanecer en la página actual pero recibir una notificación que confirma que el producto se agregó al carrito.

Para apoyar los diferentes flujos de trabajo, un campo **Agregar producto al carrito** está disponible en **Ajustes \> Extensiones** en el creador de sitios de comercio. Seleccione una de las siguientes opciones de configuración para implementar el flujo de trabajo correspondiente:

- **Navegar a la página del carro** - Cuando los usuarios agregan un artículo al carrito, van a la página del carro.
- **Mostrar notificación** - Cuando los usuarios agregan un artículo al carrito, reciben una notificación de confirmación y pueden continuar navegando en la página de detalles del producto (PDP).
- **Mostrar mini carrito** - Cuando los usuarios agregan un artículo al carrito, se muestra el contenido del mini carrito. Los usuarios pueden revisar todos los artículos en el carrito y pueden proceder al pago si están listos.
- **Mostrar notificación usando el módulo de notificaciones** - Cuando los usuarios agregan un artículo al carrito, el módulo de notificaciones se usa para mostrar una notificación de confirmación. Para que esta opción de configuración funcione, el módulo de notificaciones debe agregarse al encabezado de la página.
- **No navegar a la página del carro** - Cuando los usuarios agregan un artículo al carrito, permanecen en la página actual.

La siguiente ilustración muestra un ejemplo de las opciones de configuración de **Agregar producto al carrito** en el creador de sitios.

![Ejemplo de opciones de configuración Agregar producto al carrito en el creador de sitios](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - La configuración de sitio **Agregar producto al carro** está disponible en Dynamics 365 Commerce versión 10.0.11. Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener información sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).
> - La opción de configuración **Mostrar mini carrito** está disponible a partir de la versión 10.0.20 de Dynamics 365 Commerce. Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener información sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

La siguiente ilustración muestra un ejemplo de una notificación de confirmación de "agregado al carro" en el sitio de Fabrikam.

![Ejemplo de una notificación de confirmación de "agregado al carro" en el sitio de Fabrikam](./media/ecommerce-addtocart-notifications.PNG)

La siguiente ilustración muestra un ejemplo de una notificación de confirmación de "agregado al carro" en el sitio de Adventure Works.

![Ejemplo de una notificación de confirmación de "agregado al carro" en el sitio de Adventure Works](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de selector de tienda](store-selector.md)
