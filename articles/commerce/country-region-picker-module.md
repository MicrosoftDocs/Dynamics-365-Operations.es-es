---
title: Módulo selector de país/región
description: En este tema se describe el modulo de selección de país/región y se describe cómo configurarlo en Microsoft Dynamics 365 Commerce.
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 1a8eebb589372051272573895a0ae5b4203eef62
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109790"
---
# <a name="countryregion-picker-module"></a>Módulo selector de país/región

[!include [banner](includes/banner.md)]

En este tema se describe el modulo de selección de país/región y se describe cómo configurarlo en Microsoft Dynamics 365 Commerce.

El módulo selector de país/región utiliza la función de [detección y redirección geográfica](geo-detection-redirection.md) de Dynamics 365 Commerce para mostrar las URL recomendadas a los clientes que soliciten una URL de un sitio de comercio electrónico que no esté asociada con su país o región.

Por ejemplo, un cliente de Canadá solicita una URL de sitio que no está asociada con Canadá. En este caso, el módulo selector de país / región muestra un cuadro de diálogo que recomienda las URL del sitio que están asociadas con Canadá. La ilustración siguiente muestra un ejemplo del cuadro de diálogo del selector de país/región.

![Ejemplo de un cuadro de diálogo selector de país / región en una página de inicio.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Propiedades del módulo selector de país/región

| Nombre de la propiedad              | Valor       | Descripción |
| -------------------------- | ----------- | ----------- |
| Cabecera                    | Texto        | El encabezado que aparece en la parte superior del cuadro de diálogo. |
| Subtítulo                 | Texto        | El subtítulo que aparece debajo del encabezado. |
| País: cadena de visualización    | Texto        | El nombre para mostrar de una opción de URL (por ejemplo, "Canadá"). |
| País: subcadena de visualización | Texto        | Una subcadena de visualización opcional para una opción de URL (por ejemplo, "inglés" o "francés"). |
| País: imagen del país     | Activo de medios | Una imagen opcional que está asociada con una opción de URL (por ejemplo, una imagen de la bandera canadiense). |
| País: URL del país       | Texto        | La URL que corresponde al canal y la configuración regional configurados para el país o región en la página **Canales** en el creador de sitios de Commerce (**Configuración del sitio \> Canales**). Esta URL debe coincidir exactamente con la URL configurada en la página **Canales**. |
| Vínculo de acción                | Vínculo de acción | Un enlace opcional que aparece en la parte inferior del cuadro de diálogo. Por ejemplo, este enlace puede apuntar a una página interna que proporciona una lista de todos los países y regiones que admite el sitio. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Agregar un módulo selector de país / región a una página

El módulo selector de país / región se puede agregar al módulo de encabezado directamente o mediante un fragmento compartido. Para obtener más información sobre módulos de encabezado, consulte [Módulo de encabezado](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configure el módulo selector de país / región en el creador de sitios de comercio

> [!NOTE]
> Las URL que recomiende a sus clientes deben configurarse como objetos de país en el módulo selector de país / región.

Para cada URL que desee mostrar y recomendar a los clientes, siga estos pasos en el creador de sitios de Commerce.

1. Seleccione la ranura del módulo selector de país / región.
1. En el panel de propiedades, en **Lista de países**, seleccione **Agregar pais**.
1. Seleccione el nuevo cuadro **País**.
1. En el campo **Cadena de visualización**, ingrese un nombre para mostrar (por ejemplo, **Canadá**).
1. Opcional: en el campo **Mostrar subcadena**, introduzca una subcadena de visualización (por ejemplo, **francés** o **fr-ca**).
1. Opcional: seleccione una imagen de la biblioteca de medios.
1. En el campo **URL de país**, especifique la URL. Esta URL debe coincidir exactamente con la URL que aparece en la página **Canales** y se asigna al canal, incluida la configuración regional asociada con el país o la región.
1. Seleccione **Aceptar**.
1. Repita estos pasos para las URL de cualquier otro país que desee que muestre el módulo selector de país / región.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar la detección geográfica y la redirección](geo-detection-redirection.md)

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de selector de sitios](site-selector.md)

[Módulo de navegación](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
