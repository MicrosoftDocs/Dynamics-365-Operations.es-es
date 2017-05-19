---
title: Alternativas de entrega
description: "Los creadores de pedidos de ventas pueden usar la página Alternativas de entrega para detectar opciones de cumplimiento del pedido alternativas."
author: YuyuScheller
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6878303c881b5816c4f80c28b342907b3503721a
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="delivery-alternatives"></a>Alternativas de entrega

[!include[banner](../includes/banner.md)]


Los creadores de pedidos de ventas pueden usar la página Alternativas de entrega para detectar opciones de cumplimiento del pedido alternativas.

En Microsoft Dynamics 365 for Operations versión 1611 (noviembre de 2016), los creadores de pedidos de ventas pueden usar la página **Alternativas de entrega** para detectar opciones de cumplimiento del pedido alternativas. El diseño de página rediseñado ofrece una mejor visión general de todas las opciones alternativas. También permite a los creadores de pedidos buscar oportunidades de cumplimiento más allá de la empresa actual. Pueden ahora ver oportunidades en empresas vinculadas y oportunidades de proveedores externos. Ordenando las opciones por fecha de entrega, los creadores del pedido de ventas pueden ver una lista inteligente de alternativas de la entrega. Además, los parámetros los ayudan a gestionar mejor las entregas sugeridas. Dado que el tiempo de transporte puede afectar a las fechas de entrega, los creadores del pedido de ventas pueden explorar las distintas opciones de transporte que los operadores ofrecen. Dado que se muestra información detallada para cada sugerencia, los creadores de pedidos pueden tomar decisiones informadas directamente desde la página **Alternativas de entrega** .

## <a name="open-the-delivery-alternatives-page"></a>Abrir la página de alternativas de entrega
Puede abrir la página **Alternativas de** **entrega** desde la línea de pedido de ventas.

1.  Haga clic en **Productos y suministro** &gt; **Alternativas de entrega**.
2.  Haga clic en **Detalles de línea** &gt; **Entrega** &gt; **Alternativas de la entrega.**

También puede abrir la página **Alternativas de entrega** abriendo el espacio de trabajo **Consulta y procesamiento de pedido de ventas** y, a continuación haciendo clic en **Pedidos y favoritos** &gt; **Líneas de pedidos retrasadas** &gt; **Alternativas de entrega** **Nota:** puede abrir la página **Alternativas de entrega** si se cumplen las dos condiciones siguientes:

-   Toda la información obligatoria de la línea de ventas está rellenada.
-   El campo **Control de fecha de entrega** se establece en un valor que no es **Ninguno**.

## <a name="delivery-date-control-methods"></a>Métodos de control de fecha de entrega
El método de control de fecha de entrega determina cómo el sistema establece las fechas de entrega, cómo se calculan las opciones alternativas de la entrega, y qué información se muestra. Tenga en cuenta que el control de datos de entrega toma en cuenta los calendarios. Por lo tanto, los calendarios siguientes pueden afectar a la fecha de recepción sugerida: calendario de almacén, calendario de transporte, calendario del proveedor, y calendario de cliente. La tabla siguiente describe cada método de control de fecha de entrega.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Método</strong></td>
<td><strong>Descripción</strong></td>
</tr>
<tr class="even">
<td><strong>Ninguna</strong></td>
<td><ul>
<li>Las alternativas de entrega para líneas de ventas no se admiten. Esta opción desactiva el control de datos de la entrega.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Plazo de ventas</strong></td>
<td><ul>
<li>Las alternativas de la entrega se calculan en función del plazo de ventas predefinido. Los días de transporte se calculan en función del modo de entrega.</li>
<li>Las alternativas de la entrega incluyen los almacenes que tienen inventario disponible y pedidos de oferta/demanda.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>NNC</strong></td>
<td><ul>
<li>Las alternativas de la entrega se calculan en función de la lógica de neto no comprometido (ATP). Se consideran la disponibilidad actual y la disponibilidad futura. Los días de transporte se calculan en función del modo de entrega.</li>
<li>Las alternativas de la entrega incluyen los almacenes que tienen inventario disponible y pedidos de oferta/demanda.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>NNC + Margen de emisión</strong></td>
<td><ul>
<li>Las alternativas de la entrega se calculan como para el método de NNC, pero el margen de emisión se incluye en el cálculo.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>Las alternativas de la entrega se calculan en función de la lógica de capaz de comprometer (CTP). La expansión de MRP se usa para determinar la disponibilidad. Tenga en cuenta que, como mínimo, CTP compensa las fechas de entrega con el plazo de ventas. Los días de transporte se calculan en función del modo de entrega.</li>
<li>Las alternativas de la entrega incluyen sugerencias para los siguientes almacenes:
<ul>
<li>Almacén actual</li>
<li>Almacén predeterminado</li>
<li>Todos los almacenes que tienen inventario disponible</li>
<li>Todos los almacenes que tienen pedidos de suministro</li>
<li>Todos los almacenes que tienen versiones activas de la lista de materiales (L. MAT)</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Ver información acerca de alternativas de la entrega
Esta sección describe la información sobre alternativas de entrega que está disponible en cada ficha de la página **Alternativas de entrega**.

### <a name="products"></a>Productos

Esta ficha muestra un resumen del producto y los detalles de la línea de ventas actual.

### <a name="delivery-alternatives"></a>Alternativas de entrega

Esta ficha muestra una lista de alternativas de entrega que se clasifica por datos de recepción. Encima de la lista, puede seleccionar en qué opciones basar las sugerencias. También puede seleccionar el modo de entrega, que determina los días de transporte. Están disponibles las siguientes opciones:

-   **Incluir otras variantes del producto** - Esta opción está disponible para los productos que tienen variantes de producto. Incluirá alternativas de entrega para otras variantes del producto. Esta opción no está disponible para CTP.
-   **Incluir cantidad parcial** - De forma predeterminada, solo las sugerencias que cumplen la cantidad completa de la línea de ventas se incluyen. Seleccione esta opción para incluir las sugerencias que cumplen parcialmente la línea de pedido. Esta opción es útil si el cliente solicita una fecha de entrega anterior y acepta una entrega parcial.
-   **Incluir fechas posteriores** - De forma predeterminada, se muestran solo las sugerencias que son mejores (anteriores) que las fechas actuales de la línea de ventas. Seleccione esta opción para incluir fechas posteriores. Esta opción puede ser útil en situaciones en las que tienen prioridad parámetros que no son la fecha. Por ejemplo, podría preferirse un proveedor o un almacén específico.
-   **Modo de entrega** - Seleccione el modo de entrega preferido para optimizar el tiempo y el coste de transporte. Verá inmediatamente el efecto en las alternativas sugeridas de entrega. Por lo tanto, es fácil comparar alternativas.
-   **Obtención compra** - Cuando se active la compra, las alternativas de entrega sugeridas incluyen opciones para comprar de proveedores externos y de otras empresas de la empresa (empresas vinculadas). La opción **Incluir compra** se admite para el control de la fecha de entrega NNC y NNC + Margen de emisión. Las opciones de compra del proveedor predeterminado de la compra del producto y todos los proveedores aprobados para el producto se incluyen.
-   Para los proveedores externos, el cálculo se basa en el plazo de compra.
-   Para empresas vinculadas, el cálculo examina qué está disponible en la empresa de abastecimiento, en función del control de fecha de entrega en la empresa de abastecimiento.
-   **Tipo de entrega** (Relevante para la adquisición)
    -   **Existencias** - Los productos se envían desde el almacén de abastecimiento al sitio/al almacén de la línea de ventas. A continuación se envían desde ese almacén al cliente.
    -   **Entrega directa** - Los productos se envían directamente desde el almacén de abastecimiento al cliente.

### <a name="availability-information"></a>Información de disponibilidad

La información de esta ficha está relacionada con la línea alternativa de entrega que está seleccionada. La siguiente información se muestra, en función del control de fecha de entrega para la línea de ventas:

-   **Plazo de ventas**
    -   **Disponible hoy** - Muestra el inventario de cantidad física actual disponible, el inventario físico reservado y el inventario físico disponible.
    -   **Parámetros** - Muestra la unidad de inventario y el plazo de ventas.

-   **NNC y NNC + Margen de emisión**
    -   **Disponible hoy** - Muestra el inventario de cantidad física actual disponible, el inventario físico reservado y el inventario físico disponible.
    -   **Parámetros** - Muestra la unidad de inventario y el plazo de ventas.
    -   **Disponibilidad futura** - Muestra una representación gráfica de la disponibilidad actual y futura para el sitio y el almacén seleccionados en **Alternativas de entrega**. Puede hacer clic en las columnas del gráfico para ver más detalles sobre la disponibilidad futura del producto. El control deslizante muestra una lista de pedidos relevantes de oferta y demanda en el límite de tiempo del NNC.

-   **CTP**
    -   **Disponible hoy** - Muestra el inventario de cantidad física actual disponible, el inventario físico reservado y el inventario físico disponible.
    -   **Parámetros** - Muestra la unidad de inventario y el plazo de ventas.
    -   **Expansión** - Muestra una expansión de suministro de la alternativa de entrega seleccionada. Puede usar la **Configuración** para cambiar los campos y las dimensiones de inventario que se muestran en la expansión.

### <a name="impact-of-selected-alternative"></a>Impacto de la alternativa seleccionada

Esta ficha destaca el impacto de la alternativa seleccionada de entrega. Si hace clic en **Aceptar**, la línea de ventas se actualiza con los valores resaltados en las columnas SELECCIONADAS. Tenga en cuenta que, si la cantidad de la alternativa seleccionada de entrega es inferior a la cantidad de la línea de ventas, se crea una programación de entrega y la línea de pedido se divide en dos líneas: una línea para la cantidad seleccionada y una línea para la cantidad restante. También puede actualizar la línea comercial para que coincida con las líneas de la programación y afecte a los precios.

<a name="see-also"></a>Consulte también
--------

[Compromisos de pedidos](http://ax.help.dynamics.com/en/wiki/delivery-dates-and-available-to-promise-calculations/)





