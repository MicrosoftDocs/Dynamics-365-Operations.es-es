---
title: Módulo de vista rápida
description: En este tema se tratan los módulos de vista rápida y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d7e88163fd9b8dc4f5636ed29e2c4248aece52bf
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792180"
---
# <a name="quick-view-module"></a>Módulo de vista rápida

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de vista rápida y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

El módulo de vista rápida permite a los usuarios ver rápidamente la información del producto cuando buscan productos en una página de lista, y agregar uno o más productos al carro desde la página de lista, sin tener que ir a la página de detalles del producto (PDP). El módulo de vista rápida proporciona una descripción general de la información del producto que los usuarios necesitan para tomar la decisión de "agregar al carrito". También proporciona un vínculo a la PDP, para que los usuarios puedan ver detalles adicionales del producto y opciones de compra.

El módulo de vista rápida es compatible con los módulos de [colección de productos](product-collection-module-overview.md) y [resultados de búsqueda](search-result-module.md).

> [!IMPORTANT]
> El módulo de vista rápida está disponible a partir de la versión 10.0.17 de Commerce.

La siguiente ilustración muestra un ejemplo de un módulo de vista rápida en una página de lista de productos.

![Ejemplo de módulo de vista rápida en una página de lista de productos](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Propiedades del módulo

El módulo de vista rápida admite algunas de las mismas funciones que el módulo de caja de compra. Por lo tanto, las propiedades de un módulo de vista rápida se asemejan a las de un módulo de caja de compra.

| Propiedad | Valores | Descripción |
|----------------|--------|-------------|
| Etiqueta de título | **H1**, **H2**, **H3**, **H4**, **H5** o **H6** | Esta propiedad define la etiqueta de encabezado para el título del producto. Si el módulo de vista rápida está en la parte superior de la página, esta propiedad debe establecerse en **H1** para cumplir los estándares de accesibilidad. |
| Permitir precio personalizado | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, el usuario podrá introducir un precio personalizado. |
| Precio mínimo | Entero | Esta propiedad solo es aplicable si la propiedad **Permitir precio personalizado** está establecida en **Verdadero**. Define el precio mínimo que el usuario puede introducir (por ejemplo, $1). |
| Precio máximo | Entero | Esta propiedad solo es aplicable si la propiedad **Permitir precio personalizado** está establecida en **Verdadero**. Define el precio máximo que el usuario puede introducir (por ejemplo, $1000). |

## <a name="commerce-site-builder-settings"></a>Configuración del generador de sitios de Commerce

Al igual que el módulo de caja de compra, el módulo de vista rápida respeta la configuración en **Configuración del sitio \> Extensiones \> Agregar producto al carro**. Sin embargo, se pasa por alto la opción **Navegar a la página del carro**, ya que no es coherente con el propósito del módulo de vista rápida, que es permitir a los usuarios explorar varios productos en una página de lista y agregarlos al carrito sin salir de la página de lista.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Agregar un módulo de vista rápida a un módulo de colección de productos

El módulo de vista rápida se puede agregar a los módulos de colección de productos y resultados de búsqueda.

Para agregar un módulo de vista rápida a un módulo de colección de productos en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Páginas** y, a continuación, seleccione la página de inicio el sitio de Fabrikam.
1. Vaya a cualquier módulo **Colección de productos** en la página de inicio, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Vista rápida** y, a continuación, seleccione **Aceptar**.
1. En el panel de propiedades del módulo **Vista rápida**, seleccione **Título**. En el cuadro de diálogo **Título**, establezca el **Nivel de encabezado** en **H2** y seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de colección de productos](product-collection-module-overview.md)

[Módulo de resultados de búsqueda](search-result-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
