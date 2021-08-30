---
title: Seleccionar un tema de sitio
description: Este tema describe cómo establecer o cambiar el tema del sitio en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: cd110a94991659036ac5cee1cd5f77e0cd3ba7356be902bdae37e957247535ea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737539"
---
# <a name="select-a-site-theme"></a>Seleccionar un tema de sitio

[!include [banner](includes/banner.md)]

Este tema describe cómo establecer o cambiar el tema del sitio en Microsoft Dynamics 365 Commerce.

El diseño y el estilo de un sitio (por ejemplo, fuentes, tamaños y colores) se definen por el tema que seleccione y aplica al sitio. Un tema se creado y se implementa por un desarrollador de su empresa. Para obtener una descripción general de los temas, consulte [Visión general de creación de temas](e-commerce-extensibility/theming.md). Para obtener más información acerca de cómo crear e implementar temas, consulte [Crear un tema nuevo](e-commerce-extensibility/create-theme.md).

De forma predeterminada, al crear un sitio por primera vez, utiliza un tema con el nombre **Fabrikam**. Este tema predeterminado se proporciona como parte de la biblioteca de módulos de Commerce. Una vez haya implementado temas adicionales para su sitio, puede configurar el sitio de modo que use uno de ellos en su lugar.

## <a name="select-the-site-theme"></a>Seleccionar el tema de sitio

Para seleccionar el tema que se aplica al sitio, siga estos pasos.

1. En el entorno de creación de sitios, vaya al sitio.
1. Vaya a **Administración del sitio** \> **Extensibilidad**.
1. En **Tema**, seleccione un tema en el menú desplegable.
1. Para aplicar el tema seleccionado al sitio, seleccione **Guardar y publicar**.

> [!NOTE]
> El tema que seleccione se publica en el sitio en cuanto seleccione **Guardar y publicar** en la página **Extensibilidad**. Para obtener una vista previa de un tema de su sitio antes de aplicarlo, puede usar su entorno de espacio aislado o desarrollo.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar un mensaje de bienvenida](add-welcome-message.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)

[Visión general de creación de temas](e-commerce-extensibility/theming.md)

[Crear un tema nuevo](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
