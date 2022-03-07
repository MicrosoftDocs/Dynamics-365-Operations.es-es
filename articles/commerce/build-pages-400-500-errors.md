---
title: Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx
description: Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 16cd6c3dab5502826119b6a517414d23e168e79708e306897b04c7ba8c80404b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741150"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Generar páginas personalizadas de respuesta para los errores de código de estado 4xx/5xx

[!include [banner](includes/banner.md)]

Este tema describe cómo crear páginas de respuestas personalizadas para errores del código de estado 4xx y 5xx mediante las herramientas de creación en Microsoft Dynamics 365 Commerce.

Si una solicitud no es correcta, el servidor emite respuestas de error de código de estado HTTP. Se captura y se devuelve el código de estado 404 si no se encuentra una página, y el código de estado 500 se captura y se devuelve si se produce un error de servidor. En Dynamics 365 Commerce, los usuarios de aplicación pueden generar páginas de respuestas de error de código de estado personalizadas que se muestran a los usuarios para estas respuestas de error de código de estado.

## <a name="build-a-status-code-error-response-page"></a>Crear una página de respuesta de error de código de estado

Para empezar a crear una página de respuesta de error de código de estado, siga estos pasos.

1. En su explorador web preferido, inicie sesión en Dynamics 365 Commerce. 
1. Seleccione el sitio para el que desea crear una página de respuesta de error de código de estado 4xx/5xx.

### <a name="build-the-template"></a>Crear la plantilla

Para crear la plantilla para la página de respuesta de error de código de estado, siga estos pasos.

1. Vaya a **Plantillas**.
1. Seleccione **Nuevo** para crear una plantilla de página.
1. En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, ingrese un nombre para la nueva plantilla y luego seleccione **Aceptar**.
1. Cree la plantilla, en función de la estructura que desea que tenga la página de respuesta de error del código de estado.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla. 

### <a name="build-the-status-code-error-response-page"></a>Crear la página de respuesta de error de código de estado

Para crear la página de respuesta de error de código de estado, siga estos pasos.

1. Vaya a **Páginas**.
1. Seleccione **Nuevo** para crear una página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione una plantilla y luego, debajo de **Nombre de la página**, ingrese un nombre para la página de respuesta de error del código de estado. Deje el campo **URL de página** en blanco.
1. Cree la página.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
