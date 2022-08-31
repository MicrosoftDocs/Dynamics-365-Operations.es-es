---
title: Crear variantes de productos predefinidas
description: Este procedimiento le guía por la creación de variantes de productos para un producto maestro mediante las combinaciones de dimensiones de productos.
author: t-benebo
ms.date: 08/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a26439b8c7346cdce2b4c9804493fea94c29ac31
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335927"
---
# <a name="predefined-product-variants"></a>Variantes de productos predefinidas

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Escenario de ejemplo: crear variantes de productos predefinidas

Este escenario de ejemplo le muestra cómo crear variantes de productos para un producto maestro mediante las combinaciones de dimensiones de productos.

### <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Para seguir este escenario con los valores sugeridos aquí, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica *USMF*.

### <a name="step-1-create-a-product-master"></a>Paso 1: crear un producto maestro

Para crear un producto maestro:

1. Vaya a **Gestión de información de productos > Productos > Productos maestros**.
1. Seleccione **Nuevo**.
1. Si el campo **Número de producto** aún no muestra un número, en ese caso introduzca un valor. Este paso solo es necesario si no se ha configurado ninguna secuencia numérica para este campo.
1. Introduzca un nombre en el campo **Nombre de producto**.
1. En el campo **Grupo de dimensiones de producto**, seleccione el grupo de dimensiones del producto *SizeCol* (Tamaño y color).
1. Seleccione **Aceptar** para crear y abrir el nuevo producto maestro.

### <a name="step-2-add-product-dimensions"></a>Paso 2: agregar dimensiones de productos

Este ejemplo muestra cómo especificar manualmente dimensiones de producto. También puede elegir seleccionar un grupo de tamaños, colores o estilos que incluya los valores de dimensiones de productos que desea usar.

Para agregar dimensiones de productos:

1. Con su nuevo producto maestro aún abierto, seleccione **Dimensiones del producto** en el panel de acciones.
1. Abra la pestaña **Tamaño** y seleccione **Nuevo** en la barra de herramientas para agregar una fila a la cuadrícula. Realice las siguientes configuraciones para la nueva fila:
    - **Tamaño:** seleccione un valor de tamaño.
    - **Nombre:** escriba un nombre para el tamaño.
1. Seleccione **Nuevo** en la barra de herramientas y agregue un segundo tamaño a la cuadrícula con un nuevo **Tamaño** y **Nombre**.
1. Abra la pestaña **Coores** y seleccione **Nuevo** en la barra de herramientas para agregar una fila a la cuadrícula. Realice las siguientes configuraciones para la nueva fila:
    - **Color:** seleccione un valor de color.
    - **Nombre:** escriba un nombre para el color.
1. Seleccione **Nuevo** en la barra de herramientas y agregue un segundo color a la cuadrícula con un nuevo **Color** y **Nombre**.
1. Seleccione **Guardar**.
1. Cierre la página para volver a su nuevo producto maestro.

### <a name="step-3-generate-product-variants"></a>Paso 3: generar variantes de productos

> [!NOTE]
> Esta sección describe cómo generar variantes de producto cuando la función *Mejoras en la página de sugerencias de variantes* no está habilitada. Consulte la siguiente sección para obtener detalles sobre cómo generar variantes de productos cuando esa función está disponible.

Para generar variantes de productos:

1. Con su nuevo producto maestro aún abierto, seleccione **Variantes del producto** en el panel de acciones.
1. Seleccione **Sugerencias de variantes** en el panel de acciones.
1. El sistema genera una lista con todas las combinaciones posibles de los tamaños y colores que definió para el producto. Seleccione **Seleccionar todo** en la barra de herramientas.
    - En este ejemplo, seleccione todas las variantes posibles. Si solo desea utilizar un subconjunto de las posibles combinaciones de dimensiones del producto, seleccione solo las casillas requeridas, según sea necesario.  
1. Seleccione **Crear**.
1. Seleccione **Guardar**.

## <a name="improved-variant-suggestions"></a>Sugerencias de variantes mejoradas

La característica *Mejoras en la página de sugerencias de variantes* mejora la página **Sugerencias de variantes** para abordar problemas de rendimiento y usabilidad para empresas que tienen un gran número de combinaciones de dimensiones de productos. El proceso mejorado para seleccionar los valores de dimensión de producto para los que generar sugerencias de variantes hace que sea más rápido y más fácil identificar y liberar el conjunto relevante de variantes de producto.

Esta característica agrega las siguientes mejoras:

- **Generación diferida de sugerencias de variantes:** la página **Sugerencias de variantes** ya no muestra sugerencias cuando la abre por primera vez. En su lugar, debe elegir explícitamente qué valores necesitará y luego seleccionar el botón **Sugerir** para generar las combinaciones. Esto hace que el proceso sea más visible e interactivo.
- **Selección de valores de dimensiones:** cuando tiene muchos valores de dimensión, normalmente le interesa generar sugerencias de variantes que incluyan solo algunos de ellos (por ejemplo, al introducir un nuevo conjunto de colores o estilos). Con el diseño mejorado, puede seleccionar los valores de dimensión para los que desea generar sugerencias de variantes de producto. Esto aumenta enormemente la relevancia de las variantes sugeridas y mejora tanto el rendimiento del sistema como la productividad del usuario.

### <a name="turn-the-variant-suggestions-page-improvements-feature-on-or-off"></a>Activar o desactivar la característica de mejoras de la página de sugerencias de variantes

Para usar esta característica, debe estar activada para su sistema. A partir de la versión 10.0.25 de Supply Chain Management, la característica está activada de forma predeterminada. A partir de la versión 10.0.29 de Supply Chain Management, la característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Mejoras de la página de sugerencias de variantes* en el espacio de trabajo [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="work-with-the-improved-variant-suggestions"></a>Trabajar con las sugerencias de variantes mejoradas

Para generar sugerencias de variantes de producto cuando la función *Mejoras de la página de sugerencias de variantes* no está habilitada:

1. Abra o cree un producto maestro y agregue las dimensiones de producto requeridas, como se describe en la sección anterior.
1. Con el nuevo producto maestro aún abierto, seleccione **Variantes del producto** en el panel de acciones.
1. Seleccione **Sugerencias de variantes** en el panel de acciones.
1. Seleccione los valores que desee usar para cada una de las dimensiones.
1. En la barra de herramientas superior, seleccione **Sugerir**.
1. El sistema genera una lista con todas las combinaciones posibles de los tamaños y colores que haya seleccionado. En la ficha desplegable **Variantes sugeridas**, seleccione la casilla para cada combinación de dimensión de producto que desee utilizar, o seleccione **Seleccionar todo** en la barra de herramientas para seleccionarlos todos.  
1. Seleccione **Crear** para agregar las variantes al producto maestro actual.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
