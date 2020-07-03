---
title: Módulo de navegación
description: En este tema se tratan los módulos de navegación y se describe cómo agregarlos a las páginas de sitios en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1c6d846686e3214e976a55271694382d7c5973ed
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417401"
---
# <a name="breadcrumb-module"></a>Módulo de navegación

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de navegación y se describe cómo agregarlos a las páginas de sitios en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los módulos de navegación se utilizan para proporcionar navegación secundaria en las páginas del sitio. Por lo general, se muestran en la parte superior de las páginas, debajo del encabezado. Aunque los módulos de navegación se pueden agregar a cualquier página, se usan con mayor frecuencia en páginas de detalles de productos (PDP), para mostrar la jerarquía de categorías de productos y proporcionar una forma rápida de moverse por un sitio. Un módulo de navegación también se puede utilizar para mostrar un vínculo "Volver a los resultados" cuando los usuarios abren un PDP desde una página de búsqueda o lista. De esta manera, los usuarios pueden regresar rápidamente a su página de lista filtrada para continuar comprando.

En las páginas que tienen contexto de categoría de producto, como PDP y páginas de categorías, los módulos de navegación muestran la jerarquía de categoría. En las páginas que no tienen contexto de categoría, los módulos de navegación muestran de forma predeterminada **&lt;Raíz del sitio &gt; / &lt;Página actual &gt;**. Los módulos Navegación también se pueden configurar manualmente en otros tipos de páginas de sitio para mostrar vínculos a páginas específicas del sitio.

La siguiente imagen muestra un ejemplo de un módulo de navegación que muestra la jerarquía de categorías en un PDP.

![Ejemplo de un módulo de navegación](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Configuración del módulo de navegación

El módulo de navegación se basa en la opción **Tipo de visualización de navegación en PDP**, que se define en **Configuración del sitio \> Extensiones** en el generador de sitios. Esta opción tiene tres valores posibles:

- **Mostrar jerarquía de categoría**: cuando se selecciona este valor, el módulo de navegación mostrará la jerarquía de categoría completa del producto que se visualiza en el PDP.
- **Mostrar de nuevo los resultados**: cuando se selecciona este valor, el módulo de navegación mostrará un vínculo "Volver a resultados" en un PDP si el usuario abrió el PDP desde un módulo que permite un vínculo "Volver a resultados". Esta funcionalidad está disponible cuando los usuarios navegan desde páginas de categorías, búsquedas, listas y listas de recomendaciones. Para admitir esta funcionalidad, los módulos de colección de productos y resultados de búsqueda tienen una propiedad que se denomina **Permitir volver a los resultados en PDP**. Esta propiedad le brinda la flexibilidad de definir qué módulos deben admitir la funcionalidad de vínculo "Volver a los resultados" en el PDP. Por ejemplo, cuando se selecciona **Mostrar de nuevo los resultados** para la opción **Tipo de visualización de navegación en PDP** del módulo de navegación y se selecciona **Permitir volver a los resultados en PDP** para el módulo de resultados de búsqueda de la página de búsqueda, se mostrará un vínculo "Volver a los resultados" cuando los usuarios naveguen desde la página de búsqueda a un PDP.
- **Mostrar jerarquía de categoría y volver a los resultados**: este valor es una combinación de los dos anteriores. Cuando se selecciona este valor, el módulo de navegación mostrará tanto la jerarquía de categoría completa como un vínculo "Volver a resultados" (si está configurado) en un PDP.

## <a name="breadcrumb-module-properties"></a>Propiedades del módulo de navegación

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Raíz | Texto o vínculo| Esta propiedad opcional especifica el texto del vínculo y un destino del vínculo para la raíz del sitio de navegación. Si esta propiedad no está configurada, no se definirá ninguna raíz. |
| vínculo de navegación | vínculo | Esta propiedad opcional especifica vínculos para una ruta de exploración configurada manualmente, si se requieren estos vínculos. Los vínculos aparecen en el orden en que se enumeran. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Agregar un módulo de navegación a una página nueva

Para agregar un módulo de navegación a un PDP y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Configuración del sitio /> Extensiones** y luego, para la opción **Tipo de visualización de navegación en PDP**, seleccione **Mostrar jerarquía de categoría**.
1. Vaya a **Plantillas** y seleccione la plantilla PDP.
1. En el espacio **Contenedor** que contiene el módulo de caja de compra, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Navegación** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y abra un PDP que use la plantilla PDP. Si aún no existe un PDP, cree uno.
1. En el espacio **Contenedor** que contiene el módulo de caja de compra, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Navegación** y, a continuación, **Aceptar**.
1. En el panel de propiedades del espacio **Navegación**, en **Raíz**, seleccione **Texto del vínculo**.
1. En el cuadro de diálogo **Texto del vínculo**, introduzca **Inicio** y luego, en **Víncular objetivo**, seleccione **Agregar un vínculo**.
1. En el cuadro de diálogo **Agregar un vínculo**, seleccione un vínculo para la raíz de navegación y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Visión general de la página de aterrizaje de categoría predeterminada y la página de resultados de la búsqueda](category-search-page-overview.md)

[Módulos de colección de productos](product-collection-module-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)
