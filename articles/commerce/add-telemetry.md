---
title: Agregar secuencia de comandos a páginas del sitio para admitir telemetría
description: Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.
author: bicyclingfool
manager: annbe
ms.date: 03/20/2020
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
ms.openlocfilehash: 4f26ed5b6674566f579e801f4b7be63c2d0dc38d
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686823"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a>Agregar secuencia de comandos a páginas del sitio para admitir telemetría

[!include [banner](includes/banner.md)]

Este tema describe cómo agregar código de script del lado cliente a las páginas del sitio para admitir la colección de telemetría del cliente.

## <a name="overview"></a>Visión general

Los análisis web son una herramienta esencial cuando desea comprender de qué manera interactúan los clientes con el sitio y toman decisiones que ayudarán a optimizar la experiencia para la conversión máxima. Muchos paquetes de análisis web están disponibles para ayudarle a alcanzar estos objetivos, como Google Analytics, Clicky, Moz Analytics y KISSMetrics. La mayoría de los paquetes de análisis web requieren que agregue código de script del lado cliente en el elemento **\<head\>** del código HTML para todas las páginas del sitio.

> [!NOTE]
> Las directrices de este tema también se aplican a otra funcionalidad del lado cliente personalizada que Microsoft Dynamics 365 Commerce no ofrece de manera nativa.

## <a name="create-a-reusable-page-fragment-for-your-script-code"></a>Crear una página reutilizable para su código de script

Un fragmento de página le permite reutilizar código de script externo o en línea en todas las páginas de su sitio, independientemente de la plantilla que utilicen.

### <a name="create-a-reusable-page-fragment-for-your-inline-script-code"></a>Crear una página reutilizable para su código en línea de script

Para crear un fragmento de página reutilizable para su código de script en línea en el generador de sitios, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo**.
1. En el cuadro de diálogo **Nuevo fragmento de página**, seleccione **Script en línea**.
1. En **Nombre del fragmento de página**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.
1. Debajo del fragmento de página que creó, seleccione el módulo **Script en línea predeterminado**.
1. En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente. Luego configure otras opciones según lo requiera.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Seleccione **Publicar**.

### <a name="create-a-reusable-page-fragment-for-your-external-script-code"></a>Crear una página reutilizable para su código externo de script

Para crear un fragmento de página reutilizable para su código de script externo en el generador de sitios, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo**.
1. En el cuadro de diálogo **Nuevo fragmento de página**, seleccione **Script externo**.
1. En **Nombre del fragmento de página**, introduzca un nombre para el fragmento y luego seleccione **Aceptar**.
1. Debajo del fragmento de página que creó, seleccione el módulo **Script externo predeterminado**.
1. En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo. Luego configure otras opciones según lo requiera.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Seleccione **Publicar**.

## <a name="add-a-page-fragment-that-includes-script-code-to-a-template"></a>Agregar un fragmento de página que incluya código de script a una plantilla

Para agregar un fragmento de página que incluye código de script a una plantilla en el generador de sitios, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.
1. En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.
1. En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar fragmento de página**.
1. Seleccione el fragmento que ha creado para su código de script.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Seleccione **Publicar**.

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a>Agregue un script externo o un script en línea directamente a una plantilla

Si desea insertar un script en línea o externo directamente en un conjunto de páginas controladas por una sola plantilla, no tiene que crear primero un fragmento de página.

### <a name="add-an-inline-script-directly-to-a-template"></a>Agregar un script en línea directamente a una plantilla

Para agregar un script en línea directamente a una plantilla en el generador de sitios, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.
1. En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.
1. En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Script en línea**.
1. En el panel de propiedades a la derecha, debajo de **Script en línea**, introduzca su script del lado del cliente. Luego configure otras opciones según lo requiera.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Seleccione **Publicar**.

### <a name="add-an-external-script-directly-to-a-template"></a>Agregar un script externo directamente a una plantilla

Para agregar un script externo directamente a una plantilla en el generador de sitios, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla para las páginas en las que desea agregar el código de script.
1. En el panel izquierdo, expanda la jerarquía de la plantilla para mostrar la franja **Encabezado HTML**.
1. En el espacio **Encabezado HTML**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione **Script externo**.
1. En el panel de propiedades a la derecha, debajo de **Fuente de script**, agregue una URL externa o relativa para la fuente del script externo. Luego configure otras opciones según lo requiera.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. Seleccione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar un mensaje de bienvenida](add-welcome-message.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)
