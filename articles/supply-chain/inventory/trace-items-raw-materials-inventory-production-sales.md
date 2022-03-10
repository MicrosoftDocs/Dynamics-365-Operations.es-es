---
title: Seguimiento de artículos y materias primas en el inventario, la producción y las ventas
description: Este tema se describe cómo puede usar el seguimiento de artículos para identificar dónde se han usado los artículos o las materias primas, dónde se están usando o dónde se usarán en los procesos de producción y ventas.
author: yufeihuang
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95f59a3eca20634d03520ad88f71a3096309e23e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571818"
---
# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Seguimiento de artículos y materias primas en el inventario, la producción y las ventas

[!include [banner](../includes/banner.md)]

Este tema se describe cómo puede usar el seguimiento de artículos para identificar dónde se han usado los artículos o las materias primas, dónde se están usando o dónde se usarán en los procesos de producción y ventas.

La funcionalidad de seguimiento de artículo está disponible en la página **Seguimiento de artículos**. Las siguientes secciones describen cómo puede usar el seguimiento de artículos y cuáles son las opciones y las limitaciones.

## <a name="what-is-item-tracing"></a>¿Qué es el seguimiento de artículos?
El seguimiento de artículos es una herramienta de inteligencia empresarial (BI) que proporciona visibilidad en el origen y el destino de los artículos y las materias primas en la cadena de suministro. Los fabricantes pueden realizar el seguimiento de los artículos, las materias primas o los ingredientes hasta el proveedor y luego hacia la producción y la venta del producto terminado. El seguimiento de artículos ayuda a los fabricantes a cumplir los requisitos normativos y también ayuda a los agentes de calidad y los directores de producción a analizar y tomar medidas para tratar las desviaciones de la calidad de los productos y los materiales. Estos son algunos ejemplos de las maneras en las que los fabricantes pueden usar seguimiento de artículos:

-   Identificar la cantidad de un artículo o materia prima que está actualmente en el inventario, y dónde se almacena.
-   Determinar qué cantidad del artículo o materia prima se ha enviado, y a qué clientes se envía.
-   Identificar los envíos planificados que incluyen el artículo o la materia prima.
-   Localizar los pedidos de producción que usan el artículo o la materia prima y que están planificados, en proceso o notificados como terminado.
-   Descubrir dónde se compraron el artículo o la materia prima.
-   Investigar dónde un artículo o la materia prima se consumieron en la producción de otro artículo.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>¿De qué elementos se puede hacer un seguimiento? ¿Hay limitaciones?
Puede realizar el seguimiento de las transacciones de inventario históricas para los artículos y las materias primas según un número de artículo y una dimensión de seguimiento, como un número de serie, número de lote o número de lote de proveedor. Puede realizar el seguimiento de un artículo o una materia prima solo si tiene una dimensión de seguimiento asignada. Dado que el seguimiento se basa en las transacciones de inventario, existen algunas limitaciones al realizar el seguimiento de los artículos. Por ejemplo, hay limitaciones relacionadas con las transacciones para los proyectos, los activos fijos y el comercio. Además, en los detalles del seguimiento se muestran los coproductos, pero no los productos derivados. El seguimiento incluye todas las transacciones de almacén de una ubicación a otra. Por tanto, los usuarios pueden encontrar abrumadora la cantidad de información. El seguimiento se muestra para una entidad jurídica cada vez. No hay capacidades entre empresas en un contexto de empresas vinculadas. Debe iniciar un nuevo seguimiento para cada empresa donde se recibe o se emite un artículo.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>¿Qué criterios se pueden especificar para el seguimiento de un artículo?
Los criterios necesarios para el seguimiento de un artículo son el número de artículo, una dimensión de seguimiento (como el número de lote o número de serie) y la dirección. En la tabla siguiente se describen los criterios que se puede utilizar en el seguimiento de un artículo.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Grupo de campos</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Número de artículo</td>
<td>Especifique el identificador del artículo o la materia prima del que realiza el seguimiento.</td>
</tr>
<tr class="even">
<td>Dimensiones de producto</td>
<td>Opcional: realice un seguimiento de aspectos específicos de la definición del producto, tal como una configuración, un tamaño, un color o un estilo.</td>
</tr>
<tr class="odd">
<td>Dimensiones de seguimiento</td>
<td>Especifique un número de lote, un número de lote de proveedor o la dimensión de seguimiento del número de serie. Cuando use el número de lote como criterio, se muestra el número de lote de proveedor si ha capturado esa información.</td>
</tr>
<tr class="even">
<td>Dimensiones de almacenamiento</td>
<td>Opcional: realice un seguimiento de los artículos que se han almacenado en una ubicación concreta.</td>
</tr>
<tr class="odd">
<td>Periodo</td>
<td>Opcional: especifique fechas para limitar el seguimiento a un período específico. Los detalles de seguimiento mostrarán solo los documentos y las transacciones que se hayan creado entre estas fechas.</td>
</tr>
<tr class="even">
<td>Adelante o atrás</td>
<td>Seleccione la dirección para el seguimiento. Puede realizar un seguimiento hacia adelante o hacia atrás:
<ul>
<li><strong>Regresivo</strong>: realizar un seguimiento descendente para identificar el origen, la cantidad que queda disponible y cualquier pedido de producción que se haya informado al menos como parcialmente terminado.</li>
<li><strong>Hacia adelante</strong>: realizar un seguimiento ascendente para identificar el destino. Puede buscar los pedidos de ventas y los clientes a los que se haya enviado parcialmente el artículo o la materia prima del que realiza el seguimiento.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>¿Qué información se incluye en los detalles de seguimiento?
Los resultados de un seguimiento aparecen en orden cronológico en el árbol de la ficha desplegable **Detalles** de la página **Seguimiento de artículos**. El orden varía en función de la dirección de seguimiento. Los detalles incluyen todas las transacciones desde la compra del artículo al proveedor hasta la venta del artículo al cliente. Los resultados de seguimiento también incluyen los productos provisionales relacionados con el artículo o la dimensión de seguimiento que se especificó en los criterios de seguimiento. El nodo superior muestra la cantidad del artículo, en la unidad de inventario, que permanece disponible en función las dimensiones de almacenamiento especificadas en los criterios de seguimiento. **Nota:** Los detalles de seguimiento proporciona una instantánea de la información que estaba disponible cuando se realizó el seguimiento. Los detalles de seguimiento no se actualizan si la información cambia después de que se haya realizado el seguimiento.

## <a name="why-dont-some-nodes-contain-any-details"></a>¿Por qué algunos nodos no contienen detalles?
Para reducir la cantidad de información en los detalles de seguimiento, solo el nodo para la primera instancia del artículo o la materia prima incluye los detalles. Si un nodo seleccionado no contiene detalles, puede ver el nodo que no contiene detalles haciendo clic en **Ir a línea con seguimiento**. A continuación, puede regresar al nodo que había abandonado haciendo clic en **Atrás**.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>¿Se puede ver solo un determinado tipo de documento? Por ejemplo, ¿se pueden ver solo los pedidos de producción, los clientes o los proveedores?
Sí, desde los detalles de seguimiento, se pueden abrir las páginas de lista que incluyen solo un determinado tipo de documento o transacción. Puede obtener acceso a estas páginas en el elemento de menú **Seguimiento** del Panel de acciones, en los grupos **Artículo**, **Ventas**, **Compra**, **Producción** y **Calidad**. Por ejemplo, para ver una lista de proveedores en los detalles de seguimiento, haga clic en **Seguimiento** &gt; **Compra** &gt; **Proveedores**. Las páginas de lista resumen los documentos o las transacciones desde los detalles de seguimiento. Las páginas de lista **Transacciones pendientes**, **Pedidos pendientes** y **Pedidos de ventas no enviados** también muestran otra información que no se incluye en los detalles de seguimiento. Además, siempre muestran los resultados a partir de la fecha actual, incluso si se especificó un intervalo de fechas. En la tabla siguiente se describen los detalles adicionales que estas páginas pueden incluir.

| Listas                    | Descripción                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pedidos de ventas no enviados | Permite ver las líneas de pedido de ventas que no se han seleccionado y, por tanto, no se muestran en los detalles de seguimiento.                                                                                                                                                                                                                        |
| Pedidos pendientes           | Permite ver todos los pedidos de producción pendientes para el artículo del que se realiza el seguimiento, independientemente de las dimensiones de seguimiento que se usaron en los criterios de seguimiento. También puede ver los pedidos de producción pendientes en los que el artículo del que se realiza el seguimiento es un ingrediente y donde no se ha realizado ningún registro y no se ha notificado ninguna transacción como terminada para el pedido. |
| Transacciones pendientes     | Permite ver las transacciones de inventario pendientes del artículo del que se realiza un seguimiento que incluye las dimensiones de seguimiento especificadas o una dimensión de seguimiento en blanco. También puede ver las transacciones de inventario pendientes para las combinaciones de artículo y dimensión de seguimiento, o un valor en blanco, en los detalles de seguimiento.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>¿Se puede realizar el seguimiento ascendente o descendente de cuántos niveles en una L. MAT o una fórmula?
Puede realizar el seguimiento ascendente o descendente un nivel en una lista de materiales (L. MAT) o una fórmula. Por ejemplo, si ejecuta un seguimiento de las materias primas, puede ver el producto terminado y los coproductos. Sin embargo, si realiza el seguimiento de un coproducto, los detalles de seguimiento no incluyen el producto terminado.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>¿Cómo se pueden ver más detalles sobre un documento o una transacción en los detalles de seguimiento?
En la ficha desplegable **Detalles**, hay dos maneras de ver más información acerca de un documento o una transacción seleccionados en los detalles de seguimiento:

-   Cuando selecciona un nodo en los detalles de seguimiento en la ficha desplegable **Detalles**, las demás fichas desplegables muestran la información de visualización de la página sobre el documento o la transacción en el nodo.
-   Abra la página de detalles para el documento en un nodo seleccionado haciendo clic en **Ver detalles**. Por ejemplo, si selecciona un nodo que describe un pedido de producción y hace clic en **Ver detalles**, se muestra el formulario de detalles **Pedidos de producción**.

Algunas fichas desplegables ofrecen acceso a información adicional acerca del nodo seleccionado. Por ejemplo, en la ficha desplegable **No conformidades**, puede hacer clic **Consultar** para investigar si hay un historial de disconformidades. En la ficha desplegable **Lote**, puede hacer clic en **Disponible** para ver la cantidad de inventario físico que está actualmente disponible y las transacciones de inventario que impliquen el lote.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>¿Se puede ejecutar más de un seguimiento y luego comparar los detalles?
Después de haber ejecutado el seguimiento, puede usar las siguientes opciones del botón **Hacer seguimiento a partir del nodo** para ejecutar un nuevo seguimiento en la transacción del nodo seleccionado:

-   **Regresivo** o **Hacia adelante**: se inicia un nuevo seguimiento para el nodo seleccionado y se sobrescriben los detalles del seguimiento actual.
-   **Nuevo regresivo** o **Nuevo progresivo**: se inicia un nuevo seguimiento en una ventana nueva y se conservan los detalles del seguimiento actual.

Si desea usar la opción **Nuevo regresivo** o **Nuevo progresivo**, debe usar la función de **Abrir en una nueva ventana** para que aparezca un nuevo seguimiento en una nueva ventana.

## <a name="can-i-save-the-trace-details"></a>¿Se pueden guardar los detalles de seguimiento?
Puede guardar la información de la pestaña <strong>Detalles</strong> como archivo XML haciendo clic en <strong>Exportar</strong> debajo de la acción *<strong><em>Seguimiento</em></strong>* en el Panel de acciones. Además de los detalles de seguimiento, el archivo XML incluye los criterios de seguimiento, el nodo principal y la cantidad disponible. La capacidad de guardar los detalles de un seguimiento es de utilidad si, por ejemplo, desea asociar información a un pedido de calidad o a otra documentación de cumplimiento. Puede especificar dónde se guarda el archivo. Para ver el archivo inmediatamente, seleccione la opción <strong>Mostrar documento</strong>. <strong>Nota:</strong> El archivo se guarda siempre, incluso si solo desea verlo. De forma predeterminada, el archivo XML se abre en una ventana del explorador. Sin embargo, puede hacer clic con el botón secundario en el archivo, seleccionar <strong>Abrir con</strong> y seleccionar el programa que se debe usar para visualizar el contenido.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>¿Se puede calcular un saldo para un artículo o ingrediente concreto?
Puede exportar la información de las páginas de resumen a Microsoft Excel. Abra la página relevante, haga clic en el icono **Abrir en Microsoft Office** y, a continuación, seleccione **Exportar a Microsoft Excel**. Esta funcionalidad es especialmente útil si desea calcular un saldo total para un artículo o ingrediente desde la página de **Resumen de transacciones**. En la página **Resumen de transacciones**, puede filtrar el artículo o ingrediente, y opcionalmente el lote y, a continuación, exportar la información a Excel. En Excel, puede aislar, por ejemplo, la cantidad disponible, la cantidad vendida y la cantidad que se usó en la producción.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>¿Se puede investigar si hay un historial de problemas con los artículos o las materias primas?
Los detalles de seguimiento incluyen información sobre los pedidos de calidad y las no conformidades que implican el artículo o la materia prima. Para ver un resumen de los pedidos de calidad y las disconformidades, haga clic en **Pedidos de calidad** o en **No conformidades** en el Panel de acciones. **Note:** Los pedidos de calidad destructivos pueden aparecer más de una vez en los detalles de seguimiento. Cuando un pedido de calidad destructivo se crea para un documento, tal como un pedido de compra, aparece para cada transacción de dicho documento.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>¿Hay capacidades de generación de informes relacionadas con el seguimiento de artículos?
Puede generar el informe **Enviado a los clientes** para identificar la cantidad del artículo o la materia prima que se ha enviado y los clientes a los que se envió. Para una consulta relacionada con la conformidad, puede generar el informe para todos los clientes. Para una consulta relacionada con el servicio al cliente, puede generar el informe para un cliente seleccionado. Si el producto era una materia prima que se usó en la producción de un artículo terminado, el artículo terminado también se incluye. **Nota:** Si está usando las características para eliminar o archivar los pedidos de ventas, los resultados del informe también incluyen los pedidos de ventas que se han eliminado o archivado.

## <a name="can-i-trace-coproducts-and-byproducts"></a>¿Se puede realizar el seguimiento de los coproductos y los productos derivados?
Puede realizar el seguimiento de los coproductos, pero no de los productos derivados porque las dimensiones de seguimiento no suelen asignarse a ellos. Cuando realiza el seguimiento de un artículo, los detalles de seguimiento incluyen los coproductos relacionados. Un nodo que contiene un coproducto incluye la palabra "coproducto" en los detalles. También puede ver detalles acerca de un coproducto si selecciona el nodo en los detalles de seguimiento y, a continuación, hace clic en la ficha desplegable **Producción**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]