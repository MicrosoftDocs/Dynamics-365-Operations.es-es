---
title: "Búsqueda de acción"
description: "Este artículo describe la funcionalidad de búsqueda de acción en Microsoft Dynamics 365 for Finance and Operations. La búsqueda de acción le ayudará a encontrar y ejecutar acciones en una página."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62303
ms.assetid: 62c70de0-fdde-4417-8e08-0583fb095a40
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6563b6f422eb5562e9fc67c3734cf753a49d466d
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="action-search"></a>Búsqueda de acción

[!INCLUDE [banner](../includes/banner.md)]

Este artículo describe la funcionalidad de búsqueda de acción en Microsoft Dynamics 365 for Finance and Operations. La búsqueda de acción le ayudará a encontrar y ejecutar acciones en una página.

<a name="introduction"></a>Introducción
------------

Las páginas de Microsoft Dynamics 365 for Finance and Operations exponen principalmente comandos en los paneles de acciones, tanto el panel de acciones estándar que aparece en la parte superior de una página como las barras de herramientas que aparecen en las distintas secciones de la página. En versiones anteriores, una característica de las sugerencias de teclas le permite acceder rápidamente a cualquier botón de un panel de acciones presionando la tecla Alt y, a continuación, una serie de letras. 

[![keyTipsAX6](./media/keytipsax6.png)](./media/keytipsax6.png) Sin embargo, en la versión actual de Finance and Operations, las sugerencias de teclas no están disponibles pero han sido sustituidas por la función de búsqueda de acciones. Esta característica nueva le permite rápidamente buscar y ejecutar un botón del Panel de acciones visible.

## <a name="using-action-search"></a>Usar búsqueda de acciones
Para usar la característica de búsqueda de acciones, siga estos pasos.

1.  En el panels de acciones, haga clic en el campo **búsqueda de acciones**. (El campo **búsqueda de acción** contiene un icono de lupa.)
2.  Escriba todo o parte del nombre del botón que desea ejecutar. También puede buscar usando palabras de la "ruta" del botón. (Para obtener más información, consulte la siguiente sección del artículo). Normalmente, aparecerá un botón cerca de la parte superior de la lista de resultados una vez que haya escrito de dos a cuatro caracteres.
3.  Busque y ejecute el botón en la lista de resultados (mediante el ratón o el teclado).

Después de ejecutar el botón, el foco se devuelve a la última posición de la página, de manera que pueda continuar trabajando. 

[![action-search-field](./media/action-search-field.png)](./media/action-search-field.png)

También puede iniciar la búsqueda de acciones presionando Ctrl+/ or Alt+Q. Presione el método abreviado de teclado de nuevo para devolver el foco a su última posición en la página.

## <a name="understanding-the-results-list"></a>Comprensión de la lista de los resultados
A menudo, en Finance and Operations, debe conocer la ubicación y el contexto de un botón para comprender completamente el propósito de dicho botón. Por lo tanto, la información adicional se muestra para cada elemento en la lista de resultados, para ayudarle a comprender exactamente qué botones aparecen en la lista. Concretamente, se muestra la "ruta" del botón. Esta ruta puede incluir las etiquetas de los siguientes elementos de la IU, según corresponda:

-   Ficha Panel de acciones
-   Grupo de botones
-   Botón de menú (si el botón está dentro de un botón de menú)
-   Separador de menú (si el botón está dentro de un grupo con nombre dentro de un botón de menú)
-   Grupo o separador o en la página (por ejemplo, el nombre de una ficha Desplegable)

Por ejemplo, si escribió **bebé** en el campo **búsqueda de acciones** y ahora está examinando la lista de los resultados. La primera entrada destaca un botón que se llama **Totales**. También aparece una ruta de botón **Pedido de ventas** &gt; **Visualización**. La parte de **Pedido de ventas** de la ruta de acceso corresponde a la pestaña **Pedido de ventas** del panel Acciones, y la parte **Vista** de la ruta de acceso corresponde al grupo **Vista** de esa pestaña. Igualmente, la ruta de acceso del botón **Descuento total** (**Vender** &gt; **Calcular**) le informa que el botón se ubicó en el grupo **Calcular** de la pestaña **Vender** del panel Acciones. Por lo tanto, esta información le ayuda a entender exactamente qué botón se activará con la búsqueda de acciones (si selecciona ese botón en la lista de resultados). 

[![action-search-field-with-data](./media/action-search-field-with-data.png)](./media/action-search-field-with-data.png) 

En el ejemplo anterior, la búsqueda de acción muestra resultados del panel de acciones estándar en la parte superior de una página. Sin embargo, la búsqueda de acciones también muestra resultados de barra de herramientas visibles situadas en otros lugares en la página. Por ejemplo, si está buscando el botón de **Inventario disponible** ubicado en la pestaña desplegable **Líneas de pedidos de ventas**. En este caso, la ruta del botón en la lista de resultados (**Líneas de pedidos de ventas** &gt; **Inventario** &gt; **Visualización**) le informa de que este botón se encuentra debajo del encabezado de **Visualización** en el botón de menú **Inventario** en la pestaña desplegable **Líneas de pedidos de ventas**. 

[![on-hand-inventory](./media/on-hand-inventory.png)](./media/on-hand-inventory.png)

## <a name="action-search-vs-navigation-search"></a>Búsqueda de acciones frente a búsqueda de navegación
Mientras que la búsqueda de acciones se va a utilizar para encontrar y ejecutar acciones en una página, hay un mecanismo independiente de la búsqueda para encontrar y desplazarse a las páginas en Finance and Operations. Para obtener más información sobre dicha característica, consulte el artículo [Búsqueda de navegación](navigation-search.md).




