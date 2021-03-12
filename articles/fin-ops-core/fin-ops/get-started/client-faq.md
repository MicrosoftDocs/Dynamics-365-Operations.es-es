---
title: Preguntas frecuentes de clientes
description: Este artículo proporciona respuestas a preguntas frecuentes acerca del cliente de Finance and Operations.
author: jasongre
manager: AnnBe
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fe6da2575b7de866de614ad399c8ad5c0110d9a
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798508"
---
# <a name="client-faq"></a>Preguntas frecuentes de clientes

[!include [banner](../includes/banner.md)]

Este artículo proporciona respuestas a preguntas frecuentes acerca del cliente de Finance and Operations.

## <a name="why-arent-symbols-loaded"></a>¿Por qué los símbolos no se cargan?

Las opciones de seguridad del explorador pueden impedir que los símbolos se carguen correctamente. Para resolver este problema, pruebe los siguientes pasos:

- Si tiene este problema en Internet Explorer, haga clic en **Herramientas** y después haga clic en **Opciones de Internet**. En el cuadro de diálogo Opciones de Internet, en la pestaña **Privacidad**, haga clic en **Nivel personalizado** y asegúrese de que la opción **Descarga de fuentes** está activada.
- De lo contrario, puede que tenga que agregar el sitio de la aplicación a la lista de sitios de confianza.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>No veo la cinta de opciones de Dynamics AX 2012. ¿Puedo mantener las pestañas del Panel de acciones abiertas todo el tiempo?

Estamos planeando implementar esta característica pronto. Los usuarios podrán elegir entonces mantener las pestañas de los paneles de acciones abiertas todo el tiempo. De lo contrario, las pestañas se contraerán cuando no se usen, para lograr más espacio en la pantalla para la página.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>¿Por qué a veces veo diferentes para menús contextuales cuando hago clic con el botón secundario?

Si hace clic con el botón secundario en un campo editable (o si se selecciona texto), se mostrará el menú contextual del explorador. Este menú le concede acceso a los comandos **Cortar**, **Copiar** y **Pegar**. No podemos integrar estos comandos en los menús contextuales porque, por motivos de seguridad, los exploradores no nos permiten obtener acceso mediante programación al portapapeles del sistema.

Si hace clic con el botón secundario en una etiqueta de campo o el valor de un control de solo lectura, verá el menú contextual.

Para facilitar el acceso al teclado, planeamos implementar un método abreviado de teclado en el futuro que abra el menú contextual.

## <a name="where-is-the-view-details-functionality"></a>¿Dónde se encuentra la funcionalidad Ver detalles?

La opción **Ver detalles** solo está disponible de dos formas diferentes:

- Si un control tiene capacidades **Ver detalles**, y si el control tiene un valor, ese valor se muestra como hipervínculo. Puede hacer clic en el hipervínculo para abrir una página que contiene detalles adicionales.
- **Ver detalles** también es una opción en los menús contextuales. Para obtener más información acerca de cuándo se muestran los menús contextuales al hacer clic con el botón secundario, consulte la sección anterior.
