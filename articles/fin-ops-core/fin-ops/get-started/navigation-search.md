---
title: Búsqueda de navegación
description: Este tema explica cómo usar la función de búsqueda para navegar por páginas.
author: aneesmsft
ms.date: 04/27/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd9b6239a8f5db51ab3f238593197408e641b782
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349117"
---
# <a name="navigation-search"></a>Búsqueda de navegación

[!include [banner](../includes/banner.md)]

Este tema explica cómo usar la función de búsqueda para navegar por páginas.

La aplicación incluye varias áreas y páginas para ayudarle a realizar varias tareas. Para encontrar rápidamente las páginas que necesita para completar las tareas, use la característica de búsqueda de navegación.

Para usar esta característica, haga clic en **Buscar** para que aparezca el cuadro **Buscar**. A continuación, puede elegir escribir una o varias palabras en el cuadro. El sistema busca al instante páginas pertinentes en la aplicación que coincidan con las palabras que ha especificado. Por ejemplo, podría escribir “factura de proveedor” como la entrada y, a continuación, el sistema mostraría los resultados que coinciden con esa entrada.

> [!NOTE]
> El cuadro **Buscar** le ayuda a encontrar páginas y a desplazarse por ellas. No le ayudará a encontrar datos o acciones específicos.

[![cuadro de búsqueda.](media/navigation-search.png "Cuadro de búsqueda")

## <a name="quickly-navigate-to-a-particular-page"></a>Desplácese rápidamente a una página determinada

La característica de búsqueda de navegación también es una excelente manera de navegar con rapidez hasta una página concreta. Por ejemplo, si es un responsable de proveedores que usa con frecuencia la página **Diario de pagos**, puede especificar “diario de pagos” en el cuadro **Buscar**. Dado que la entrada es una coincidencia exacta del título de la página, la página se muestra en la parte superior de los resultados de la búsqueda y podrá navegar rápidamente hasta ella.

La lista de resultados de la búsqueda muestra el título de la página así como la ruta de navegación. Esto muestra la ubicación de la página en la aplicación. También le ayuda a diferenciar entre dos o más páginas similares en los resultados.

Al buscar una página, su entrada se concilia con el título de la página, así como su ruta de navegación. Por ejemplo, si especifica "clientes" en el cuadro de **búsqueda**, verá los resultados de las páginas disponibles para usted en el área Clientes, aunque los títulos de páginas no incluyan la palabra "clientes".

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Desplácese rápidamente a una página basándose en el nombre del formulario técnico

La funcionalidad de búsqueda de navegación también incluye una característica muy solicitada para los usuarios avanzados: la capacidad de navegar rápidamente a una página en función del nombre del formulario técnico. Muchos usuarios conocen tan bien el sistema que saben los nombres de formulario precisos con los que trabajan. Si es uno de estos usuarios, puede especificar **formulario:** seguido del nombre del formulario que busca. Por ejemplo, si especifica **formulario: vendinvoice**, los resultados de la búsqueda mostrarán todas las páginas en las que el nombre del formulario empieza por **vendinvoice**.

## <a name="administration-and-security"></a>Administración y seguridad

Desde una perspectiva de administración y seguridad, la función de búsqueda de navegación solo muestra dos tipos de resultados:

- Páginas que están habilitadas en la configuración actual (mediante las claves de configuración).
- Páginas a las que el usuario tiene acceso en función del rol del usuario.

La lista de resultados de la búsqueda está limitada a 10 artículos. Si no encuentra lo que busca en los resultados, debe intentar restringir o actualizar la entrada.

## <a name="development"></a>Desarrollo

Desde una perspectiva de desarrollo, es sencillo sacar provecho de la funcionalidad de búsqueda de navegación puesto que no hay prácticamente ningún retraso entre el desarrollo de los elementos de menú y su capacidad para aparecer en los resultados de la búsqueda. Siempre que los elementos de menú estén vinculados desde el panel de navegación o el panel de información, permitirán automáticamente las búsquedas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]