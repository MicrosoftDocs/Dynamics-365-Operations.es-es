---
title: "Búsqueda de acción"
description: "Este artículo describe la funcionalidad de búsqueda de la acción en Microsoft Dynamics 365 para las operaciones. La búsqueda de acción le ayudará a encontrar y a ejecutar acciones en una página."
author: jasongre
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 689d8f9fb0501c5007db21d41f126737af77b89e
ms.lasthandoff: 03/31/2017


---

# <a name="action-search"></a>Búsqueda de acción

Este artículo describe la funcionalidad de búsqueda de la acción en Microsoft Dynamics 365 para las operaciones. La búsqueda de acción le ayudará a encontrar y a ejecutar acciones en una página.

<a name="introduction"></a>Introducción
------------

Las páginas de Microsoft Dynamics 365 para las operaciones exponen principalmente comandos en los paneles de acciones, el panel de acciones estándar que aparece en la parte superior de una página y de las barras de herramientas que aparecen en las distintas secciones de la página. En versiones anteriores, una característica de las sugerencias de teclas le dejó rápidamente tener acceso a cualquier botón en el panel de acciones presionando la tecla de Alt y después una serie de letras. 

![keyTipsAX6 [] (. /media/keytipsax6.png])(. /media/keytipsax6.png) Sin embargo, en la versión actual de Dynamics 365 para las operaciones, las sugerencias de teclas no estarán disponibles pero han sido reemplazados por la función de búsqueda de la acción. Esta característica nueva le permite rápidamente buscar y ejecutar un botón del Panel de acciones visible.

## <a name="using-action-search"></a>Usar búsqueda de acciones
Para usar la característica de búsqueda de acciones, siga estos pasos.

1.  En el panels de acciones, haga clic en el campo **búsqueda de acciones**. (El campo **búsqueda de acción** contiene un icono de lupa.)
2.  Escriba todo o parte del nombre del botón que desea ejecutar. También puede buscar palabras mediante ruta desde el botón de la”. (Para obtener más información, consulte la sección siguiente del artículo). Normalmente, aparecerá un botón cerca de la parte superior de la lista de resultados después de que se haya escrito dos a cuatro caracteres.
3.  Busque y ejecute el botón en la lista de resultados (mediante el ratón o el teclado).

Después de ejecutar el botón, el foco se devuelve a la última posición de la página, de manera que pueda continuar trabajando. 

[acción-Buscar-campo de![] (. /media/action-search-field.png])(. /media/action-search-field.png)

También puede iniciar la búsqueda de acciones presionando Ctrl+/ or Alt+Q. Presione el método abreviado de teclado de nuevo para devolver el foco a su última posición en la página.

## <a name="understanding-the-results-list"></a>Comprensión de la lista de los resultados
Con frecuencia, en Dynamics 365 para las operaciones, debe conocer la ubicación y el contexto de un botón para comprender completamente el propósito de ese botón. Por lo tanto, la información adicional se muestra para cada artículo de la lista de resultados, para ayudarle a comprender exactamente qué botones aparecen en la lista. Concretamente, se muestra la "ruta" del botón. Esta ruta puede incluir las etiquetas de los siguientes elementos de la IU, según corresponda:

-   Ficha Panel de acciones
-   Grupo de botones
-   Botón de menú (si el botón está dentro de un botón de menú)
-   Separador de menú (si el botón está dentro de un grupo con nombre dentro de un botón de menú)
-   Grupo o separador o en la página (por ejemplo, el nombre de una ficha Desplegable)

Por ejemplo, si escribió **bebé** en el campo **búsqueda de acciones** y ahora está examinando la lista de los resultados. La primera entrada, para un botón se denomina ** que los totales **, queda resaltado. Una ruta del botón ** pedido de ventas ** &gt; ** de la vista ** también se mostrará. ** Pedido de ventas ** la parte de la ruta corresponde ** pedido de ventas ** en la ficha del panel de acciones, y ver ** ** la parte de la ruta corresponde ** ver ** el grupo en la ficha. De forma similar, la ruta ** descuento total ** del botón (** venta ** &gt; ** calcule **) le informa de que este botón se encuentra en ** calcula ** grupo en ** la venta ** ficha del panel de acciones. Por lo tanto, esta información le ayuda a comprender exactamente el botón que sea desencadenado por búsqueda de acción (si se selecciona el botón en la lista de resultados). 

[acción-Buscar-campo-con- datos![(]. /media/action-search-field-with-data.png])(. /media/action-search-field-with-data.png) 

En el ejemplo anterior, la búsqueda de acción muestra resultados del panel de acciones estándar en la parte superior de una página. Sin embargo, la búsqueda de acciones también muestra resultados de barra de herramientas visibles situadas en otros lugares en la página. Por ejemplo, desea buscar ** inventario disponible ** botón que se encuentra en ** las líneas de pedido de ventas ** la ficha desplegable. En este caso, la ruta del botón en la lista de resultados (** las líneas de pedido de ventas ** &gt; ** inventario ** &gt; ** ver **) le informa de que este botón se encuentra bajo ** ver ** encabezado en ** inventario ** el botón de menú de ** las líneas de pedido de ventas ** la ficha desplegable. 

[![inventario disponible (-]. mano de inventory.png - /media/on])(. mano de inventory.png /media/on -)

## <a name="action-search-vs-navigation-search"></a>Búsqueda de acciones frente a búsqueda de navegación
Por contra que la búsqueda de acción está pensada para buscar y las acciones de la ejecución en una página, hay un mecanismo independiente de búsqueda para buscar y navegar a páginas de Dynamics 365 para las operaciones. Para obtener más información sobre dicha característica, vea la búsqueda [] de exploración (navigation-search.md artículo).


