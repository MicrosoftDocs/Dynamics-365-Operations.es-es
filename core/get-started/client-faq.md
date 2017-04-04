---
title: "Dinámica 365 para las preguntas más frecuentes de cliente entre las operaciones"
description: "Este artículo proporciona respuestas a las preguntas más frecuentes acerca de Microsoft Dynamics 365 del cliente de las operaciones."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 2c99b2e1f7ddecb61be62832ca1a8d3ac1fd21a8
ms.lasthandoff: 03/31/2017


---

# <a name="dynamics-365-for-operations-client-faq"></a>Dinámica 365 para las preguntas más frecuentes de cliente entre las operaciones

Este artículo proporciona respuestas a las preguntas más frecuentes acerca de Microsoft Dynamics 365 del cliente de las operaciones.

<a name="why-arent-symbols-loaded-when-i-use-dynamics-365-for-operations"></a>¿Por qué los símbolos no se cargan a utilizo Dynamics 365 para las operaciones?
-----------------------------------------------------------------

Las opciones de seguridad del explorador pueden impedir que los símbolos se carguen correctamente. Para resolver este problema, pruebe los siguientes pasos:

-   Si está experimentando este problema en Internet Explorer, haga clic en ** las herramientas **, y haga clic en ** las opciones de Internet **.  En el cuadro de diálogo de las opciones de Internet, en ** privacidad ** la ficha, haga clic ** personalizados ** nivel, y garantiza que ** descarga de fuentes ** la opción está seleccionada.
-   Si no, puede que tenga que agregar Dynamics 365 para el sitio de las operaciones a la lista de sitios de confianza.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Falto la cinta de opciones de Dynamics AX 2012. ¿Puedo mantener las fichas del panel de acciones abierto todo el tiempo?
Nos planifican para implementar esta característica pronto. Los usuarios podrán elegir continuación mantener las fichas de los paneles de acciones abierto todo el tiempo. De lo contrario, las pestañas se contraerán cuando no se usen, para lograr más espacio en la pantalla para la página.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a>¿Por qué consulto a veces varios menús contextuales cuando rightclick?
Si hace clic con el botón secundario en un campo editable (o si se selecciona texto), se mostrará el menú contextual del explorador. Este menú le concede acceso a los comandos **Cortar**, **Copiar** y **Pegar**. No podemos especificar estos comandos en Dynamics 365 para menús contextuales de las operaciones porque, por motivos de seguridad, los exploradores no permite que programáticamente tengamos acceso al portapapeles del sistema.

Si hace clic con una etiqueta de campo o el valor de un control de sólo lectura, verá Dynamics 365 para el menú contextual de las operaciones.

Para crear el acceso de teclado más sencilla, planificar para implementar un método abreviado de teclado en el futuro que abra Dynamics 365 para el menú contextual de las operaciones.

## <a name="where-is-the-view-details-functionality-in-dynamics-365-for-operations"></a>Lugar es la funcionalidad de los detalles de la vista de Dynamics 365 para las operaciones?
La opción **Ver detalles** solo está disponible de dos formas diferentes:

-   Si un control tiene capacidades **Ver detalles **, y si el control tiene un valor, ese valor se muestra como hipervínculo. Puede hacer clic en el hipervínculo para abrir una página que contiene detalles adicionales.
-   ** Los detalles de la vista ** también es una opción en Dynamics 365 para menús contextuales de las operaciones. Para obtener más información acerca de cuándo las Dynamics 365 para menús contextuales de las operaciones se muestran al hacer clic con el botón secundario, consulte la sección anterior.



