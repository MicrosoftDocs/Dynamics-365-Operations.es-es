---
title: Módulo de acordeón
description: En este artículo se tratan los módulos de acordeón y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: ec895476770f297825d6c88d0b0a5fef43a5c6ef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279166"
---
# <a name="accordion-module"></a>Módulo de acordeón

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de acordeón y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos de acordeón son módulos en forma de contenedor que se utilizan para organizar la información o los módulos en una página al proporcionar una capacidad contraible tipo cajón. Se puede usar un módulo de acordeón en cualquier página.

Dentro de cada módulo de acordeón, se pueden agregar uno o más módulos de elementos de acordeón. Cada módulo de elementos de acordeón representa un cajón contraible. Dentro de cada módulo de elementos de acordeón, se pueden agregar uno o más módulos. No hay restricciones sobre los tipos de módulos que se pueden agregar a un módulo de elementos de acordeón.

La siguiente imagen muestra un ejemplo de un módulo de acordeón que se utiliza para organizar la información en la página de preguntas frecuentes (FAQ) de una tienda.

![Ejemplo de un módulo de acordeón.](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Propiedades de módulo de acordeón

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera | Texto | Esta propiedad especifica un encabezado de texto opcional para el módulo de acordeón. |
| Ampliar todo | **Verdadero** o **Falso** | Si el valor se establece en **Verdadero**, la funcionalidad de expandir/contraer está activada, de modo que todos los elementos del módulo de acordeón se pueden expandir y contraer. |
| Estilo de interacción | **Independiente** o **Expandir solo un elemento** | Esta propiedad define el estilo de interacción para los elementos de acordeón. Si el valor se establece en **Independiente**, cada elemento de acordeón se puede expandir o contraer de forma independiente. Si el valor se establece en **Expandir solo un elemento**, solo se puede expandir un elemento a la vez. A medida que se expanden los elementos, los elementos previamente expandidos se contraen. |

## <a name="accordion-item-module-properties"></a>Propiedades de módulo de elementos de acordeón

| Nombre de la propiedad | Valores | Descripción |
|----------------|--------|-------------|
| Cargo | Texto | Esta propiedad especifica el texto de título del módulo de elementos de acordeón. Al seleccionar la región del título, los usuarios pueden expandir o contraer la sección. |
| Expandir de forma predeterminada | **Verdadero** o **Falso** | Si el valor se establece en **Verdadero**, el elemento de acordeón se expande de manera predeterminada cuando se carga la página. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Agregar un módulo de acordeón a una página de preguntas frecuentes

Para agregar un módulo de acordeón a una página de preguntas frecuentes y establecer las propiedades en el generador de sitios, siga estos pasos.

1. Vaya a **Páginas**, y use la plantilla de marketing de Fabrikam (o cualquier plantilla que no tenga restricciones) para crear una nueva página con el nombre **Preguntas frecuentes de tienda**.
1. En el espacio **Principal** de la **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Acordeón** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de acordeón, seleccione **Encabezado** al lado del símbolo de lápiz.
1. En el cuadro de diálogo **Encabezado**, en **Texto de encabezado**, introduzca **Preguntas frecuentes**. A continuación seleccione **Aceptar**.
1. En el panel de propiedades del módulo de acordeón, seleccione la casilla **Mostrar Expandir todo** y luego, en el campo **Estilo de interacción**, seleccione **Independiente**.
1. En el espacio **Acordeón**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Elemento acordeón** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de elementos de acordeón, en **Título**, introduzca el texto del título (por ejemplo, **¿Cómo funcionan las devoluciones?**).
1. En el espacio **Elemento de acordeón**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de bloque de texto, introduzca un párrafo de texto (por ejemplo, **Las devoluciones deben procesarse a través del centro de atención telefónica. Póngase en contacto con 1-800-FABRIKAM para devoluciones. Los productos tienen una política de devolución de 30 días. Las devoluciones deben iniciarse dentro de este plazo.**)
1. En el espacio **Acordeón**, agregue algunos módulos de elementos de acordeón más. En cada módulo de elementos de acordeón, agregue un módulo de bloque de texto que tenga contenido.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. La página mostrará un módulo de acordeón que tiene el contenido que agregó.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de contenedor](add-container-module.md)

[Módulo de pestaña](add-tab.md)

[Módulo de bloque de texto](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
