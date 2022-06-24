---
title: Agregar un aviso de derechos de autor
description: En este artículo se describe cómo agregar un aviso de derechos de autor a su sitio web de comercio electrónico.
author: psimolin
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a1e394b9a582b48c44bbec26ef42a90d50918f87
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851226"
---
# <a name="add-a-copyright-notice"></a>Agregar un aviso de derechos de autor

[!include [banner](includes/banner.md)]

En este artículo se describe cómo agregar un aviso de derechos de autor a su sitio web de comercio electrónico.

## <a name="prerequisites"></a>Requisitos previos

Para poder agregar un aviso de derechos de autor al sitio, debe tener los siguientes elementos:

- Una plantilla que incluya un fragmento de pie de página compartido.
- Una página que use esa plantilla.

## <a name="add-a-copyright-notice"></a>Agregar un aviso de derechos de autor

Para agregar un aviso de derecho de autor a la parte inferior de cada página que usa una plantilla específica, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo**.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Pie de página** y asigne un nombre al fragmento. Por ejemplo, escriba **Pie de página-Derechos de autor**.
1. Seleccione **Aceptar**.
1. En el panel de navegación, seleccione los puntos suspensivos (**...**) junto a **Pie de página** y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo, seleccione **Categoría de pie de página** y después seleccione **Aceptar**.
1. En el panel de navegación, seleccione los puntos suspensivos (...) junto a **Categoría de pie de página** y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo, seleccione **Bloque de texto** y después seleccione **Aceptar**.
1. En el panel de navegación, seleccione **Bloque de texto**.
1. En el panel de propiedades de la derecha, en el campo **Párrafo**, agregue su mensaje de derechos de autor. Por ejemplo, especifique **(C) Fabrikam 2019**.
1. Seleccione **Guardar**, **Finalizar edición** y **Publicar**.
1. Vaya a **Plantillas**, seleccione la plantilla y, a continuación, seleccione **Editar**.
1. En **página Esquema**, expanda **Cuerpo** y, a continuación, expanda **Página predeterminada**.
1. Seleccione el botón de puntos suspensivos junto a **Espacio de pie de página** y, a continuación, seleccione **Agregar fragmento**.
1. Seleccione el fragmento que haya creado anteriormente y después, **Seleccionar**.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

El pie de página que contiene el aviso de derechos de autor aparece automáticamente en la parte inferior de todas las páginas que utilicen la plantilla seleccionada.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md)

[Agregar un icono de favoritos](add-favicon.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
