---
title: Agregar secuencia de comandos a páginas del sitio para admitir telemetría
description: Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697345"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Agregar secuencia de comandos a páginas del sitio para admitir telemetría

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.

## <a name="overview"></a>Visión general

Los análisis web son una herramienta esencial cuando desea comprender de qué manera interactúan los clientes con el sitio y toman decisiones que ayudarán a optimizar la experiencia para la conversión máxima. Muchos paquetes de análisis web están disponibles para ayudarle a alcanzar estos objetivos, como Google Analytics, Clicky, Moz Analytics y KISSMetrics. La mayoría de los paquetes de análisis web requieren que agregue código de script del lado cliente en el elemento **\<head\>** del HTML para todas las páginas del sitio.

> [!NOTE]
> Las directrices de este tema también se aplican a otra funcionalidad del lado cliente personalizada que Microsoft Dynamics 365 Commerce no ofrece de manera nativa.

## <a name="create-a-reusable-fragment-for-your-script-code"></a>Crear un fragmento reutilizable para su código de script

Después de crear un fragmento para su código de script, se puede reutilizar en todas las páginas de su sitio.

1. Vaya a **Fragmentos \> Nuevo fragmento de página**.
2. Seleccione **Script externo**, especifique un nombre para el fragmento y, a continuación seleccione **Aceptar**.
3. En la jerarquía del fragmento, seleccione el elemento secundario del módulo **inyector de script** del fragmento que acaba de crear.
4. En el panel de propiedades de la derecha, agregue su script del lado cliente y establezca otras opciones de configuración según sea necesario.

## <a name="add-the-fragment-to-templates"></a>Agregar el fragmento a plantillas

1. Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.
2. En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.
3. Seleccione el botón de puntos suspensivos (**...**) para la franja **Encabezado HTML** y, a continuación, seleccione **Agregar fragmento**.
4. Seleccione el fragmento que ha creado para su código de script.
5. Guarde la plantilla y protéjala.

> [!NOTE]
> Una vez que haya terminado, debe publicar el fragmento y la plantilla maestra. 

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar un mensaje de bienvenida](add-welcome-message.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

