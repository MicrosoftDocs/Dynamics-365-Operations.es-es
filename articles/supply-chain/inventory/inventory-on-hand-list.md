---
title: Lista de inventario disponible
description: Este tema describe cómo usar la página de Lista disponible para inspeccionar los detalles del inventario disponible. Muestra algunas de las formas en que las diversas opciones de filtrado y clasificación funcionan juntas, y cómo esas opciones a veces pueden producir resultados inesperados cuando se combinan.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 33e5ccc454191e27e33835a05094b823ec54e891
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437269"
---
# <a name="inventory-on-hand-list"></a>Lista de inventario disponible

[!include [banner](../includes/banner.md)]

Este tema describe cómo usar la página de **Lista disponible** para inspeccionar los detalles del inventario disponible. Muestra algunas de las formas en que las diversas opciones de filtrado y clasificación funcionan juntas, y cómo esas opciones a veces pueden producir resultados inesperados cuando se combinan.

## <a name="query-your-on-hand-inventory"></a>Consulta el inventario disponible

Para comprobar la disponibilidad de inventario, vaya a **Gestión del inventario \> Consultas e informes \> Lista disponible**.

La página **Lista disponible** se actualiza automáticamente cuando se realizan transacciones en el inventario. Esas transacciones pueden ser pronosticadas, físicas o financieras.

Use las siguientes herramientas para encontrar el conjunto de productos que está buscando:

- En el Panel de acciones, seleccione [**Dimensiones**](#dimensions) para abrir un cuadro de diálogo donde puede agregar o eliminar columnas que se muestran en la cuadrícula **Disponible**.
- En el [panel **Filtros**](#filters-pane), especifique valores para campos específicos para mostrar solo registros que coincidan con esos valores. Tenga en cuenta que los filtros que defina aquí se aplican a las tablas de origen que pueden agregarse más tarde, de acuerdo con las dimensiones que ha seleccionado para mostrar. Para obtener información sobre cómo este comportamiento puede afectar sus resultados, consulte [ejemplos](#examples) en este tema.
- En el panel **Filtros**, seleccione **Aplicar** para generar la lista de inventario disponible que la cuadrícula **Inventario**.
- En la cuadrícula **Inventario**, seleccione cualquier encabezado de columna para ordenar o filtrar por valores en esa columna. Un filtro rápido en la parte superior de la cuadrícula proporciona opciones de filtrado adicionales. Estos filtros se aplican a los resultados, no a las tablas de origen. Para obtener información sobre cómo este comportamiento puede afectar sus resultados, consulte [ejemplos](#examples) en este tema.

Para cada elemento coincidente, la cuadrícula **Inventario** proporciona las siguientes columnas de información de inventario.

| Columna | Descripción |
|---|---|
| Inventario físico | La cantidad física disponible en el inventario. |
| Física reservada | La cantidad total del lote que se ha reservado físicamente. |
| Física disponible | La cantidad disponible (no reservada) física disponible en el inventario físico.<p>La cantidad **física disponible** es un campo calculado. El valor es igual a **Inventario físico** menos el valor **Físico reservado**.</p> |
| Físico disponible según dimensiones adicionales | La cantidad física disponible para todas las dimensiones que se muestran en la cuadrícula. |
| Pedido en total | La cantidad total que se incluye en los pedidos entrantes o que tiene una cantidad positiva en varios diarios de inventario. |
| En pedido | La cantidad total que se incluye en los pedidos salientes o que tiene una cantidad negativa en varios diarios de inventario. |
| Ordenada reservada | La cantidad total del lote que se ha reservado en recepciones solicitadas. El valor en este campo representa la cantidad total de artículos en transacciones salientes que tienen un estado de _Pedido reservado_. Los artículos reservados como pedidos no están físicamente disponibles en el inventario. Por lo tanto, no se pueden recoger y entregar directamente. |
| Disponible para reserva | Cantidad total del inventario disponible que se puede reservar.<p>**Nota:** Si la casilla **Reservar artículos pedidos** está seleccionada en la página **Parámetros de gestión de inventario y almacén**, el valor en este campo incluye los recibos esperados. Si la casilla de verificación está desactivada, el valor excluye los recibos esperados.</p> |
| Total disponible | La cantidad total disponible.<p>La cantidad **total disponible** es un campo calculado. El valor es igual al valor **Físico disponible** más el valor **Pedido en total** menos el valor **En pedido**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>Aplicar filtros para encontrar los registros que está buscando

Utilizar el panel **Filtros** para filtrar la lista de inventario disponible para que solo incluya registros donde los valores de campo coincidan con los criterios de filtrado. Para definir un filtro, siga estos pasos.

1. En el panel **Filtros**, busque el campo en el que desea filtrar.
2. En el campo debajo del nombre del campo de destino, seleccione un operador lógico (por ejemplo, *comienza con*, *igual a* o *mayor que*).
3. Escriba o seleccione el valor a buscar.

> [!IMPORTANT]
> La página **Lista disponible** se obtiene de una tabla detallada de inventario disponible que incluye todas las dimensiones disponibles. Sin embargo, la lista en esta página es un resumen. Por lo tanto, podría combinar filas de la tabla de origen agregando valores de acuerdo con las dimensiones que se muestran.
>
> Los filtros que defina en el panel **Filtros** se aplican a la tabla de origen, no a la lista agregada. Este comportamiento a veces puede producir resultados inesperados. Para obtener información sobre cómo este comportamiento puede afectar sus resultados, consulte [ejemplos](#examples) en este tema.
> 
> Sin embargo, los [filtros que se proporcionan en la cuadrícula](#grid-filters) *sí* se aplican a la lista agregada. Estos filtros incluyen tanto el filtro rápido en la parte superior de la cuadrícula como el filtro para cada encabezado de columna.

Puede modificar el conjunto de filtros que está disponible en el panel **Filtros** siguiendo estos pasos.

- Para eliminar un filtro del panel, seleccione su botón **Cerrar** (**X**).
- Para agregar un filtro, seleccione **Agregar** en la parte superior del panel **Filtros**. El cuadro de diálogo **Agregar campos de filtro** que aparece muestra una lista de los campos disponibles. También muestra información sobre el tipo de datos y la tabla para cada campo. Use los encabezados de columna para filtrar y ordenar la lista según lo requiera, y luego seleccione la casilla de verificación para cada campo que desee agregar al panel **Filtrar**. Cuando haya terminado, seleccione **Insertar** para aplicar sus cambios.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>Seleccione qué dimensiones mostrar

Las dimensiones le brindan más información sobre cada elemento de la lista de inventario disponible y le brindan más formas de ordenar y filtrar la lista. Las dimensiones que selecciona para mostrar también afectan cómo se agregan las filas en la página **Lista disponible**. Esta agregación, a su vez, puede afectar cómo se combinan las filas de las tablas de origen en los resultados que ve. Para obtener información sobre cómo este comportamiento puede afectar sus resultados, consulte [ejemplos](#examples) en este tema.

Para personalizar la selección de dimensiones de inventario que se muestra, siga estos pasos.

1. En el panel Acciones, seleccione **Dimensiones**.

    El cuadro de diálogo **Visualización de dimensiones** que aparece muestra cada dimensión.

2. Seleccione la casilla para cada dimensión que desee incluir en la cuadrícula.
3. Si desea que su selección se use de forma predeterminada la próxima vez que abra la página **Lista disponible**, configure la opción **Guardar configuración** en **Sí**. Si configura esta opción en **No**, su selección se usará solo durante la sesión actual. Por lo tanto, la próxima vez que abra la página, se utilizará la selección predeterminada actual.
4. Seleccione **Aceptar** para aplicar sus cambios y cerrar el cuadro de diálogo.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>Filtrar en las resultados de la lista de inventario disponible

Puede seleccionar cualquier encabezado de columna en la cuadrícula **Inventario**, para ordenar o filtrar por valores en esa columna. Un filtro rápido en la parte superior de la cuadrícula proporciona opciones de filtrado adicionales. Estos filtros se aplican a los resultados, no a las tablas de origen. Para obtener información sobre cómo este comportamiento puede afectar sus resultados, consulte [ejemplos](#examples) en este tema.

> [!NOTE]
> No puede filtrar y ordenar por todas las columnas. La mayoría de las columnas de cantidad no incluyen controles de clasificación y filtrado, porque son campos calculados. La columna **En orden** es una excepción.

## <a name="examples"></a><a name="examples"></a>Ejemplo

Su sistema incluye una tabla de inventario detallada (no agregada) que muestra el siguiente inventario disponible.

| Número de artículo | Sitio | Almacén | Inventario físico | Físico disponible |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>Escenario 1

La página **Lista disponible** está configurada para mostrar las siguientes dimensiones finales:

- código de artículo
- Sitio
- Almacén

En el panel **Filtros**, se configuran los siguientes criterios de filtrado:

- **Número de artículo** \| **es exactamente** \| _IA0001_
- **Físico disponible** \| **menor o igual** \| _1_

Este es el resultado.

| Número de artículo | Sitio | Almacén | Inventario físico | Físico disponible |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>Escenario 2

La página **Lista disponible** está configurada para mostrar las siguientes dimensiones finales:

- código de artículo
- Sitio

En el panel **Filtros**, se configuran los siguientes criterios de filtrado:

- **Número de artículo** \| **es exactamente** \| _IA0001_
- **Físico disponible** \| **menor o igual** \| _1_

Este es el resultado.

| Número de artículo | Sitio | Inventario físico | Físico disponible |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

Tenga en cuenta que la configuración en el panel **Filtros** se aplica a la tabla de inventario detallada (no agregada) que se muestra al comienzo de esta sección. Por lo tanto, el criterio **Físico disponible** \| **menor o igual** \| _1_ encuentra dos filas de esa tabla (la primera y la tercera fila, cada una de las cuales muestra un valor **Físico disponible** de _1_). Sin embargo, en este escenario, la página **Lista disponible** no está configurada para mostrar la dimensión **Almacén**. Por lo tanto, agrega las dos filas originales en una sola fila resultante, porque ambas filas tienen valores idénticos en todas las dimensiones que se muestran. Esta fila parece infringir el criterio de filtrado, porque el valor **Físico disponible** se muestra como _2_. Sin embargo, el resultado es correcto, porque la configuración en el panel **Filtros** se aplica a la tabla de origen, no a la tabla agregada que se muestra en la página **Lista disponible**.
