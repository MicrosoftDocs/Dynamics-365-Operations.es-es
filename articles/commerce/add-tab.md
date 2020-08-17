---
title: Módulo de pestañas
description: En este tema se tratan los módulos de pestañas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b4187dfd704c78d506d7840b04c986687fe807a3
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621022"
---
# <a name="tab-module"></a>Módulo de pestañas

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de pestañas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los módulos de pestañas son módulos tipo contenedor que se utilizan para organizar la información de una página del sitio en pestañas. Se pueden usar en cualquier página donde la información deba presentarse en pestañas.

En cada módulo de pestañas, se pueden agregar uno o más elementos de pestaña. Cada módulo de elemento de pestaña representa una sola pestaña. En cada módulo de elemento de pestaña, se pueden agregar uno o más módulos. No hay restricciones sobre los tipos de módulos que se pueden agregar a un módulo de elementos de pestaña.

La siguiente imagen muestra un ejemplo de un módulo de pestañas en una página de sitio. En este ejemplo, está seleccionada la pestaña **Envío**.

![Ejemplo de un módulo de pestañas](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Propiedades de los módulos de pestañas

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera | Texto | Esta propiedad especifica un encabezado de texto opcional para el módulo de pestañas. |
| Índice de pestaña activa | Número | Esta propiedad especifica la pestaña que debería estar activa por defecto cuando se carga una página. Si no se proporciona ningún valor, el primer elemento de la pestaña está activo de forma predeterminada. |

## <a name="tab-item-module-properties"></a>Propiedades de los módulos de elementos de pestaña

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cargo | Texto | Esta propiedad especifica el texto de título del módulo de elementos de pestaña. |

## <a name="add-a-tab-module-to-a-page"></a>Agregar un módulo de pestaña a una página

Para agregar un módulo de pestaña a una página y establecer las propiedades, siga estos pasos.

1. Use la plantilla de marketing de Fabrikam (o cualquier plantilla que no tenga restricciones) para crear una nueva página con el nombre **Página de directivas de tienda**.
1. En el espacio **Principal** de la **página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Pestaña** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de pestañas, seleccione **Encabezado** al lado del símbolo de lápiz.
1. En el cuadro de diálogo **Encabezado**, en **Texto de encabezado**, introduzca el texto del encabezado (por ejemplo, **Directivas**). A continuación seleccione **Aceptar**.
1. En el espacio **Pestaña**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento de pestaña** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de elementos de pestaña, en **Título**, introduzca el texto del título (por ejemplo, **Entrega**).
1. En el espacio **Elemento de pestaña**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de bloque de texto, en **Texto enriquecido**, introduzca un párrafo de texto.
1. En el espacio **Pestaña**, agregue algunos módulos de elementos de pestaña que tengan títulos. En cada módulo de elementos de pestaña, agregue un módulo de bloque de texto que tenga contenido.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. La página mostrará un módulo de pestañas que contiene módulos de elementos de pestaña que tienen el contenido que agregó.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de acordeón](add-accordion.md)

[Módulo de bloque de texto](add-content-rich-block.md)
