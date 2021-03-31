---
title: Comprobar la accesibilidad de contenido de página
description: En este tema se describe cómo comprobar la accesibilidad del contenido de las páginas en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 186044fc7a360f227cecffb39bad0e225245dd4d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210980"
---
# <a name="verify-page-content-accessibility"></a>Verificar accesibilidad de contenido de página


[!include [banner](includes/banner.md)]

En este tema se describe cómo comprobar la accesibilidad del contenido de las páginas en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Cuando haya terminado de modificar una página debe asegurarse de que el contenido sea accesible para todos en la web. En las herramientas de creación de Commerce, puede comprobar fácilmente la accesibilidad del contenido de página mediante el servicio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrado. Este servicio comprueba el contenido de su página siguiendo las directrices más recientes de [Accesibilidad del World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).

La integración de [Microsoft Accessibility Insights](https://accessibilityinsights.io/) debe estar activada a nivel de suscriptor o sitio antes de poder usarla.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>Active Microsoft Accessibility Insights para todos los sitios de su suscriptor

Para activar la integración de [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para todos los sitios de Commerce en su suscriptor, siga estos pasos.

> [!NOTE]
> Para acceder a la configuración del suscriptor debe iniciar sesión en Commerce como administrador del sistema.

1. Inicie sesión en Commerce como administrador del sistema.
1. En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.
1. En **Configuración del suscriptor**, seleccione **Características**.
1. Establezca la opción **Comprobación de accesibilidad** en **Activada**.

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>Active Microsoft Accessibility Insights para un solo sitio

Para activar la integración de [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para un solo sitio de Commerce, siga estos pasos.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación izquierdo, seleccione **Valores de configuración del sitio** para expandirlo
1. En **Valor de configuración del sitio**, seleccione **Características**.
1. Establezca la opción **Comprobación de accesibilidad** en **Activada**.

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>Compruebe la accesibilidad del contenido en la página de inicio

Para utilizar el servicio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrado para escanear y comprobar el contenido de su página de inicio en Commerce, siga estos pasos.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación izquierdo, seleccione **Páginas**.
1. Busque y seleccione la página principal para abrirla en el editor de páginas.
1. En la barra de comandos, seleccione **Comprobar accesibilidad**. Se abre la página **Comprobar accesibilidad**.
1. Una vez completado el escaneo, revise el contenido del informe.
1. En caso de error de alguna comprobación, marque el elemento para expandirlo y ver más detalles.
1. Para cerrar el informe una vez que haya terminado de revisarlo, desplácese hasta la parte inferior de la página **Comprobar accesibilidad** y seleccione **Aceptar**.

## <a name="additional-resources"></a>Recursos adicionales

[Modificar una página de sitio existente](modify-existing-page.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)

[Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Enriquecer una página de aterrizaje de categoría](enrich-category-page.md)

[Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]