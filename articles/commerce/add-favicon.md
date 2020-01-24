---
title: Agregar un icono de favoritos
description: En este tema se explica cómo agregar un icono de favoritos al sitio.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 18e12cbe46650fcf024a56b6de9a8cb2903d2bf8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914592"
---
# <a name="add-a-favicon"></a>Agregar un icono de favoritos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se explica cómo agregar un icono de favoritos al sitio.

## <a name="overview"></a>Visión general

Un icono de favoritos es un pequeño archivo gráfico que se muestra en una pestaña del explorador web, en la barra de direcciones, en el historial de exploración, y en marcadores o favoritos, entre otros lugares. Recomendamos que agregue un icono de favoritos al sitio, ya que representa y refuerza su marca, y ayuda a diferenciar el sitio de otros que los clientes visitan.

Aunque puede agregar varios iconos favoritos de diversos tamaños y tipos de archivos al sitio, este tema muestra cómo agregar un icono favorito único. Sin embargo, se utilizan el mismo proceso y ubicación para agregar más iconos favoritos.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Cargue un icono favorito en la colección de activos del sitio

Para cargar un icono favorito en la colección de activos del sitio, siga estos pasos.

1. Vaya a **Activos \> Cargar \> Cargar activos**.
1. Busque y seleccione el icono de favoritos en el sistema de archivos local.
1. Especifique un título y, a continuación, seleccione **Aceptar**. 
1. En el panel de propiedades de la derecha, copie la dirección URL pública del icono favorito.

> [!NOTE]
> Si no selecciona la opción **Publicar activos tras la carga**, debe volver a la página **Activos** y publicar manualmente el icono favorito posteriormente.

## <a name="create-the-html-for-the-favicon"></a>Crear el HTML para el icono favorito

Para crear el HTML para el icono favorito, use el siguiente fragmento de código HTML. Para el atributo **href**, reemplace **"URL\_pública\_para\_su\_icono favorito"** por la dirección URL pública que ha copiado antes.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a>Agregar el HTML para el icono favorito al elemento \<head\> de sus páginas

Para agregar un icono favorito al sitio, use el mismo procedimiento usado para agregar cualquier tipo de HTML o script al elemento **\<head\>** de las páginas de su sitio.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md) 

[Agregar un mensaje de bienvenida](add-welcome-message.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)

