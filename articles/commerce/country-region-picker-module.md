---
title: Módulo selector de país/región
description: En este artículo se describe el modulo de selección de país/región y se describe cómo configurarlo en Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: d20b3be008a37b1c86e6fefe0ccc90c581e18340
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862001"
---
# <a name="countryregion-picker-module"></a>Módulo selector de país/región

[!include [banner](includes/banner.md)]

En este artículo se describe el modulo de selección de país/región y se describe cómo configurarlo en Microsoft Dynamics 365 Commerce.

El módulo selector de país/región utiliza la característica de [detección y redirección geográfica](geo-detection-redirection.md) de Dynamics 365 Commerce para mostrar los sitios recomendados a los clientes que soliciten una URL de un sitio de comercio electrónico que no esté asociada con su país o región.

Por ejemplo, un cliente de Canadá solicita una URL de sitio que no está asociada con un país que no sea Canadá. En este caso, el módulo selector de país / región muestra un cuadro de diálogo que recomienda las URL del sitio que están asociadas con Canadá. 

## <a name="how-it-works"></a>Cómo funciona

Cuando la detección geográfica y la redirección están habilitadas para un sitio, y un cliente solicita una URL del sitio, el país que se detecta para el cliente y la URL que solicitó se utilizan para determinar si esa URL está asignada al país donde se encuentra el cliente. La asignación entre URL y países se define en la página **Canales** de **Configuración del sitio** en el creador de sitios de Commerce. 

Si la URL de la solicitud no coincide con ninguna URL asignada al país del cliente, se devuelve en la respuesta la lista de una o más URL asignadas a ese país. El selector de país/región compara cada URL de esa lista con las URL que se configuraron en el módulo de país/región. Para cada coincidencia exacta que se encuentra, el selector de país/región muestra el encabezado, el subencabezado y la imagen de visualización para esa URL, y vincula esos elementos mediante la URL.

Cuando un cliente selecciona una opción en el selector de país/región, se le lleva a la URL hipervinculada. Esa URL se escribe en la cookie **\_msdyn365\_\_\_site\_** para que pueda utilizarse como preferencia de sitio del cliente. Luego, la próxima vez que el cliente solicite la URL que no está asociada con su país o región, será redirigido automáticamente a su país preferido. Por lo tanto, le recomendamos que también utilice el [módulo selector de sitio](site-selector.md) en su sitio de comercio electrónico, para que los clientes tengan una forma de anular o actualizar su preferencia de sitio. 

Si un cliente cierra el cuadro de diálogo del selector de país/región, no se escribe ninguna cookie y el cliente permanece en el sitio actual. 

La ilustración siguiente muestra un ejemplo del cuadro de diálogo del selector de país/región.

![Ejemplo de un cuadro de diálogo selector de país / región en una página de inicio.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Propiedades del módulo selector de país/región

| Nombre de la propiedad              | Valor       | Descripción                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Cabecera                    | Texto        | El encabezado que aparece en la parte superior del cuadro de diálogo.       |
| Subtítulo                 | Texto        | El subtítulo que aparece debajo del encabezado.               |
| País: cadena de visualización    | Texto        | El nombre para mostrar de una opción de URL (por ejemplo, "Canadá").   |
| País: subcadena de visualización | Texto        | Una subcadena de visualización opcional para una opción de URL (por ejemplo, "inglés" o "francés"). |
| País: imagen del país     | Activo de medios | Una imagen opcional que está asociada con una opción de URL (por ejemplo, una imagen de la bandera canadiense). |
| País: URL del país       | Texto        | La URL del sitio para el país/región que se está configurando. Esta URL debe coincidir exactamente con la URL que especificó para este país/región en la página **Canales**, en **Configuración del sitio**, en el creador de sitios de Commerce. Además, el dominio de la URL debe ser el dominio personalizado que se especifica en el campo **Coincidencia de dominio** de la página **Canales**, no la dirección de trabajo del sitio que proporciona Commerce cuando crea su entorno de comercio electrónico (por ejemplo, la URL `https://<yourcompany>.commerce.dynamics.com/`). |
| Vínculo de acción                | Vínculo de acción | Un enlace opcional que aparece en la parte inferior del cuadro de diálogo. Por ejemplo, este enlace puede apuntar a una página interna que proporciona una lista de todos los países y regiones que admite el sitio. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Agregar un módulo selector de país / región a una página

El módulo selector de país / región se puede agregar al módulo de encabezado directamente o mediante un fragmento compartido. Para obtener más información sobre módulos de encabezado, consulte [Módulo de encabezado](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configure el módulo selector de país / región en el creador de sitios de comercio

> [!NOTE]
> Las URL que recomiende a sus clientes deben configurarse como objetos de país en el módulo selector de país / región.

Para cada URL de sitio que desee mostrar y recomendar a los clientes, siga estos pasos en el creador de sitios de Commerce.

1. Seleccione la ranura del módulo selector de país / región.
1. En el panel de propiedades, en **Lista de países**, seleccione **Agregar pais**.
1. Seleccione el nuevo cuadro **País**.
1. En el campo **Cadena de visualización**, ingrese un nombre para mostrar (por ejemplo, **Canadá**).
1. Opcional: en el campo **Mostrar subcadena**, introduzca una subcadena de visualización (por ejemplo, **francés** o **fr-ca**).
1. Opcional: seleccione una imagen de la biblioteca de medios.
1. En el campo **URL de país**, especifique la URL. Esta URL debe coincidir exactamente con la URL que aparece en la página **Canales** y que se asigna al canal, incluida la configuración regional asociada con el país o la región. 
1. Seleccione **Aceptar**.
1. Repita estos pasos para las URL de cualquier otro país que desee que muestre el módulo selector de país / región.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar la detección geográfica y la redirección](geo-detection-redirection.md)

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de selector de sitios](site-selector.md)

[Módulo de navegación](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
