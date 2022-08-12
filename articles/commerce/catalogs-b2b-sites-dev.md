---
title: Impacto de extensibilidad de los catálogos de Commerce para personalizaciones B2B
description: Este artículo describe el impacto de extensibilidad de los catálogos de Commerce para la característica B2B en Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 06d304226270c9c63c6907190dc1038a38f70e44
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136810"
---
# <a name="extensibility-impact-of-commerce-catalogs-for-b2b-customizations"></a>Impacto de extensibilidad de los catálogos de Commerce para personalizaciones B2B

[!include [banner](includes/banner.md)]

Este artículo describe el impacto de extensibilidad de los catálogos de **Commerce para la característica B2B** en Microsoft Dynamics 365 Commerce.

Si está interesado en ampliar el contexto del catálogo a escenarios personalizados, es posible que deba actualizar sus personalizaciones. Esta actualización sigue el proceso estándar que los clientes deben seguir, ya que es posible que sus personalizaciones no admitan automáticamente las funciones más recientes después de realizar las actualizaciones. Si sus personalizaciones incluyen alguna característica nueva o correcciones de errores en sus experiencias, le recomendamos que actualice el código de personalización en consecuencia. Esta actualización se asemeja a los cambios que Microsoft podría haber realizado para el código principal.

Revise los casos de personalización que siguen para determinar si sus personalizaciones deben actualizarse.

> [!NOTE]
> - Todas las interfaces de programación de aplicaciones (API) de comercialización deben tener en cuenta el catálogo. Por lo tanto, es fundamental que apruebe el parámetro **CatalogID**.
> - El catálogo predeterminado (**CatalogID**=**0**) no es un catálogo válido para usuarios de empresa a empresa (B2B) que hayan iniciado sesión. Por lo tanto, todas las llamadas API que pasen "0" o usen un valor predeterminado fallarán, porque los usuarios del sitio no tienen acceso al catálogo 0. Para obtener la experiencia correcta, las llamadas API del cliente deben actualizarse para que pasen el ID de catálogo que se seleccionó en el selector de catálogo. Si usa un valor predeterminado y el usuario cambia de catálogo, el sitio web debe proporcionar los datos para el catálogo seleccionado. Por lo tanto, para que coincidan con las API que se ejecutan desde el código principal de Commerce, las API personalizadas deben pasar el catálogo seleccionado.

Los siguientes casos de personalización requieren actualizaciones de desarrollo:

- **Caso 1:** Un cliente presenta su propia [acción de datos](e-commerce-extensibility/data-actions.md) que llama a una acción de datos o API relacionada con el producto. Los pasos de actualización siguientes son obligatorios:

    1. Si la acción de datos usa una llamada API directa, actualice la acción de datos para que pase el ID de catálogo, como se muestra en la siguiente ilustración de ejemplo.

        ![Acción de datos actualizada que pasa el ID del catálogo.](./media/customization1_a.png)

    1. Si la acción de datos llama a una acción de datos diferente relacionada con el producto dentro de la personalización, el código debe actualizarse para que pase algunos parámetros nuevos, como **requestContext**. El parámetro **requestContext** se utiliza para recuperar el ID de catálogo actual, como se muestra en la siguiente ilustración de ejemplo.

        ![Acción de datos actualizada que pasa el nuevo parámetro.](./media/customization1_b.png)

- **Caso 2:** Un cliente tiene una [acción de datos anulada](e-commerce-extensibility/data-action-overrides.md). El paso de actualización siguientes es obligatorio:

    - Actualice la acción de datos como en el caso 1.

- **Caso 3:** Un cliente tiene una extensión de vista, un módulo inyector de script o [módulo clonado](e-commerce-extensibility/modules-overview.md#clone-a-module-library-module) que incluye llamadas a API o acciones de datos. El paso de actualización siguientes es obligatorio:

    - Actualice el código como en el caso 1, como se muestra en la siguiente ilustración de ejemplo.

       ![Código actualizado que pasa el nuevo parámetro.](./media/customization3.png)

- **Caso 4:** Un cliente utiliza una llamada API **getById**. El paso de actualización siguientes es obligatorio:

    - Cambie a la llamada API **getByIds** en su lugar, porque la llamada APT **getById** tiene algunas limitaciones y no es compatible con el conocimiento del catálogo.

- **Caso 5:** Un cliente tiene una acción de datos que recupera información de varios productos que pueden ser de diferentes catálogos. El paso de actualización siguientes es obligatorio:

    - Divida las llamadas API por ID de catálogo. Por ejemplo, para las API del carrito, el carrito puede contener productos de diferentes catálogos. Las líneas de productos deben agruparse por ID de catálogo y deben llamar a la API para cada catálogo por separado, como se muestra en la siguiente ilustración de ejemplo.

        ![Acción de datos actualizada que agrupa líneas de productos por ID de catálogo.](./media/customization5.png)

## <a name="additional-resources"></a>Recursos adicionales

[Crear catálogos de Commerce para sitios B2B](catalogs-b2b-sites.md)

[Catálogos comerciales para preguntas frecuentes B2B](catalogs-b2b-sites-FAQ.md)

[Módulo de selector de catálogos](catalog-picker.md)
