---
title: Módulo de consentimiento de cookies
description: En este tema se tratan los módulos consentimiento de cookies y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 57c8876f1faf08ce965ccd796551996a8651e2eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213947"
---
# <a name="cookie-consent-module"></a>Módulo de consentimiento de cookies

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos consentimiento de cookies y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

El módulo de consentimiento de cookies solicita a los usuarios del sitio que brinden consentimiento explícito para permitir cookies para cualquier característica o módulo que rastree las cookies del navegador. Se requiere el consentimiento la primera vez que un usuario del sitio navega por un sitio en una nueva sesión de navegador. Cuando se recibe el consentimiento, se realiza un seguimiento y no se volverá a solicitar el consentimiento al usuario del sitio. Para obtener más información, consulte [Cumplimiento de las cookies](cookie-compliance.md).

Si no se recibe el consentimiento de las cookies del usuario del sitio, las funciones o módulos que requieran el consentimiento de las cookies no se mostrarán en la página. Por ejemplo, el módulo de pago, el módulo para compartir en redes sociales y la función de tienda preferida requieren el consentimiento de las cookies y no se mostrarán si no se recibe el consentimiento del usuario del sitio. 

Se puede configurar un módulo de consentimiento de cookies en el fragmento de encabezado de una página para que se pueda hacer cumplir cuando se carga la página. El módulo de consentimiento de cookies debe tener un mensaje claro que informe al usuario del sitio sobre el uso de cookies en el sitio y debe proporcionar un enlace a la página de privacidad del sitio.

La siguiente ilustración destaca un ejemplo de un mensaje de consentimiento de cookies con un enlace a la página de política de privacidad del sitio que se muestra en el encabezado de una página del sitio.
![Ejemplo de un módulo de consentimiento de cookies](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Propiedades del módulo de consentimiento de cookies

| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Texto enriquecido                  | Texto enriquecido | Especifica una notificación de texto enriquecido para los usuarios del sitio de que el sitio utiliza cookies del navegador y que los usuarios deben aceptar el uso de cookies para que el sitio sea completamente funcional. |
| Vínculos | URL | Se pueden agregar uno o más vínculos a la página de privacidad de un sitio que describe los tipos de cookies que se rastrean en el sitio. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Agregar un módulo de consentimiento de cookies a las páginas del sitio

Para agregar de manera eficiente un módulo de consentimiento de cookies a varias páginas del sitio, se puede agregar a un fragmento de encabezado de página compartida. Una vez que se agrega el fragmento de encabezado a todas las páginas del sitio, se presentará automáticamente una notificación de consentimiento de cookies la primera vez que un usuario del sitio navegue a cualquier página del sitio.

Para obtener más información sobre módulos y fragmentos de encabezado, consulte [Módulo de encabezado](author-header-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de encabezado](author-header-module.md) 

[Cumplimiento de cookies](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]