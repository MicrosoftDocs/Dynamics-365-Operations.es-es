---
title: Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx
description: Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001155"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx


[!include [banner](includes/banner.md)]

Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Si una solicitud no es correcta, el servidor emite respuestas de error de código de estado HTTP. Se captura y se devuelve el código de estado 404 si no se encuentra una página, y el código de estado 500 se captura y se devuelve si se produce un error de servidor. En Dynamics 365 Commerce, los usuarios de aplicación pueden generar páginas de respuestas de error de código de estado personalizadas que se muestran a los usuarios para estas respuestas de error de código de estado.

## <a name="build-a-status-code-error-response-page"></a>Crear una página de respuesta de error de código de estado

Para empezar a crear una página de respuesta de error de código de estado, siga estos pasos.

1. En su explorador web preferido, inicie sesión en Dynamics 365 Commerce. 
1. Seleccione el sitio para el que desea crear una página de respuesta de error de código de estado 4xx/5xx.

### <a name="build-the-template"></a>Crear la plantilla

Para crear la plantilla para la página de respuesta de error de código de estado, siga estos pasos.

1. Vaya a **Plantillas \> Nueva plantilla**.
1. Asigne un nombre a la nueva plantilla.
1. Cree la plantilla, en función de la estructura que desea que tenga la página de respuesta de error del código de estado.
1. Proteja la plantilla y publíquela.

### <a name="build-the-status-code-error-response-page"></a>Crear la página de respuesta de error de código de estado

Para crear la página de respuesta de error de código de estado, siga estos pasos.

1. Vaya a **Páginas \> Nueva página**.
1. Asigne un nombre a la página de respuesta de error de código de estado, pero **no** establezca el campo **URL**.
1. Cree la página.
1. Proteja la página y publíquela.

> [!NOTE]
> Puede crear las páginas de respuesta de error de código de estado independientes para errores de código de estado 4xx y 5xx. También puede usar la misma página de respuesta de error de código de estado general para ambas categorías de error.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Configurar una redirección para la página de respuesta de error de código de estado

Para configurar una redirección para la página de respuesta de error de código de estado, siga estos pasos.

1. Vaya a **Direcciones URL \> Nuevo \> Nuevo alias** y seleccione la página de respuesta de error del código de estado que se creó anteriormente.
1. En el campo **Alias**, escriba **default-4xx** o **default-5xx**, en función de la página de respuesta de error de código de estado para la que está configurando una redirección. Estos alias se deben publicar. De lo contrario, la redirección no funcionará.
1. Seleccione **Aceptar** para confirmar la vinculación.

> [!NOTE]
> Si utiliza una sola página de respuesta de error de código de estado para ambas categorías de error, repita este procedimiento para vincular un alias para la otra categoría de error a la misma página.

## <a name="additional-resources"></a>Recursos adicionales

[Trabajar con plantillas](work-with-templates.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Crear un URL de página](create-page-url.md)
