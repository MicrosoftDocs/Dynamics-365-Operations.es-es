---
title: Visión general de la gestión de la calidad
description: Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b090450c6b39607f9661667f8063998bbe5ff52
ms.sourcegitcommit: c79062ba89498aa3fe3d86e478d9f32484f5f6dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "3224918"
---
# <a name="quality-management-overview"></a>Visión general de la gestión de la calidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.

La gestión de calidad puede ayudarle a gestionar los plazos de entrega cuando maneja productos de disconformidad, independientemente de su punto de origen. Dado que los tipos de diagnóstico están vinculados a la corrección de los informes, Supply Chain Management puede programar las tareas para corregir los problemas y evitar que se repitan.

Además de la funcionalidad para gestionar la no conformidad, la gestión de calidad incluye la funcionalidad de realizar un seguimiento de las incidencias por tipo de problema (incluso problemas internos) y para identificar soluciones a corto plazo o a largo plazo. Las estadísticas acerca de los indicadores clave de rendimiento (KPI) proporcionan información sobre el historial de problemas de disconformidad anteriores y las soluciones utilizadas para corregirlos. Puede usar los datos históricos para revisar la eficacia de las medidas de calidad anteriores y determinar las medidas adecuadas que se deben usar en el futuro.

Al configurar una asociación de calidad, Supply Chain Management puede generar pedidos de calidad para varios procesos empresariales, eventos y condiciones. La asociación de calidad puede cubrir un artículo concreto, un determinado grupo de éstos o todos los artículos.

## <a name="examples-of-the-use-of-quality-management"></a>Ejemplos del uso de la gestión de calidad
La gestión de calidad es flexible y puede ejecutarse de distintas maneras para satisfacer los requisitos de niveles específicos de operaciones de la cadena de suministro. En los ejemplos siguientes se muestran usos posibles de estas características:

-   Inicie automáticamente un proceso de control de calidad en función de los criterios predefinidos (sobre el registro del almacén de un pedido de compra para un proveedor específico).
-   Bloquear el inventario durante la inspección para evitar que el inventario no aprobado se use (bloqueo completo de las cantidades de pedido de compra).
-   Use el muestreo del artículo como parte de una asociación de calidad para definir la cantidad de inventario físico actual que debe inspeccionarse. El muestreo puede basarse en cantidades fijas o en un porcentaje.
-   Crear pedidos de calidad para recepciones parciales. Para crear un pedido de calidad basado en la cantidad que se recibe físicamente con un pedido, debe seleccionar la casilla de verificación **Por cantidad actualizada** en el formulario **Muestreo de artículos** .
-   Permite crear tipos de prueba que incluyen mínimo, máximo y valores de prueba de destino, y realizar pruebas cualitativas en contraposición a cuantitativas que tengan resultados de validación predefinidos.
-   Especifique un nivel de calidad aceptable (AQL) para controlar las tolerancias de medida de calidad.
-   Especifique los recursos que una operación de inspección requiere, por ejemplo instrumentos de prueba y un área de prueba.

## <a name="working-with-quality-associations"></a>Trabajar con asociaciones de calidad
El proceso empresarial que utiliza una asociación de calidad puede estar relacionado con varios documentos de origen, como pedidos de compra, pedidos de ventas o pedidos de producción.

Cada registro de asociación de calidad define el conjunto de pruebas, el nivel de calidad aceptable y el plan de muestreo que se aplica a los pedidos de calidad generados. Debe definir un registro de asociación de calidad para cada variación de un proceso empresarial. Por ejemplo, puede configurar una asociación de calidad que genere un pedido de calidad cuando se actualice una recepción de producto de pedido de compra. En función de la configuración del plan de ejecución, el propio proceso de activación puede bloquearse mientras que haya un pedido de calidad abierto o los siguientes procesos, por ejemplo, una factura de pedido de compra, se pueden bloquear.

**Nota:** mientras haya pedidos de calidad abiertos, las cantidades de inventario se bloquean automáticamente para evitar su emisión. En función del ajuste **Bloqueo completo** de la página **Muestreos de artículos**, la cantidad es la cantidad en el pedido de calidad o la cantidad en la línea del documento de origen.

Para un determinado proceso empresarial, el registro de la asociación de calidad identifica el evento y las condiciones para las que se genera un pedido de calidad. Las condiciones pueden especificarse para un sitio o para una entidad jurídica. Un pedido de calidad que requiera pruebas destructivas solo se puede generar si hay un inventario disponible para el evento.

En los siguientes ejemplos se muestra cómo se define un registro de asociación de calidad para las variantes de cada proceso empresarial. Para cada ejemplo, la siguiente tabla resume los eventos y las condiciones definidos por un registro de asociación de calidad.

<table>
<tbody>
<tr>
<th>Tipo de referencia</th>
<th>Tipo de evento</th>
<th>Ejecución</th>
<th>Bloqueo de eventos</th>
<th>Referencia del documento</th>
</tr>
<tr>
<td>Inventario</td>
<td>No aplicable</td>
<td>No aplicable</td>
<td>Ninguna</td>
<td>Todas</td>
</tr>
<tr>
<td rowspan="7">Ventas</td>
<td rowspan="4">Proceso de picking programado</td>
<td rowspan="4">Anterior</td>
<td>Ninguna</td>
<td rowspan="22">Solo Id. específico, Grupo o Todo</td>
</tr>
<tr>
<td>Proceso de picking</td>
</tr>
<tr>
<td>Albarán</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="3">Albarán</td>
<td rowspan="3">Anterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Albarán</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="15">Compra</td>
<td rowspan="7">Lista de recepciones</td>
<td rowspan="4">Anterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Lista de recepciones</td>
</tr>
<tr>
<td>Recepción de producto</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="3">Posterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Recepción de producto</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="3">Registro</td>
<td rowspan="3">No aplicable</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Recepción de producto</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="5">Recepción de producto</td>
<td rowspan="3">Anterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Recepción de producto</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="2">Posterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Factura</td>
</tr>
<tr>
<td rowspan="8">Producción</td>
<td rowspan="3">Registro</td>
<td rowspan="3">No aplicable</td>
<td>Ninguna</td>
<td rowspan="12">Todas</td>
</tr>
<tr>
<td>Notificar como terminado</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="5">Notificar como terminado</td>
<td rowspan="3">Anterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Notificar como terminado</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="2">Posterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td rowspan="4">Cuarentena</td>
<td rowspan="3">Notificar como terminado</td>
<td rowspan="2">Anterior</td>
<td>Notificar como terminado</td>
</tr>
<tr>
<td>Fin</td>
</tr>
<tr>
<td>Posterior</td>
<td>Fin</td>
</tr>
<tr>
<td>Fin</td>
<td>Anterior</td>
<td>Fin</td>
</tr>
<tr>
<td rowspan="3">Operación de ruta</td>
<td rowspan="3">Notificar como terminado</td>
<td rowspan="2">Anterior</td>
<td>Ninguna</td>
<td rowspan="3">Id. específico, Grupo o Todo, y Recurso específico, Grupo o Todo</td>
</tr>
<tr>
<td>Notificar como terminado</td>
</tr>
<tr>
<td>Posterior</td>
<td>Ninguna</td>
</tr>
<tr>
<td rowspan="3">Producción de coproductos</td>
<td>Registro</td>
<td>No aplicable</td>
<td rowspan="3">Ninguna</td>
<td rowspan="3">Todas</td>
</tr>
<tr>
<td rowspan="2">Notificar como terminado</td>
<td>Anterior</td>
</tr>
<tr>
<td>Posterior</td>
</tr>
</tbody>
</table>

La siguiente tabla proporciona más información acerca de cómo se pueden generar los pedidos de calidad para tipos de procesos concretos.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Tipo de proceso</th>
<th>Cuando los pedidos de calidad se pueden generar automáticamente</th>
<th>Cuando los pedidos de calidad se pueden generar si se requiere una prueba destructiva</th>
<th>Información acerca de la condición</th>
<th>Información acerca de la generación manual</th>
</tr>
<tr>
<td>Pedido de compra</td>
<td>Antes o después de que se registre una lista de recepciones o una recepción de producto del material recibido</td>
<td>Después del registro de la recepción de producto, ya que el material debe estar disponible para la prueba destructiva</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a un pedido de compra puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Orden de cuarentena</td>
<td>Antes o después de que se notifique que ha finalizado la orden de cuarentena</td>
<td>No se pueden generar pedidos de calidad que necesiten pruebas destructivas. Se supone que la funcionalidad de la orden de cuarentena gestiona la disposición del material destruido.</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a una orden de cuarentena puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Pedido de ventas</td>
<td>Antes de una actualización programada del proceso de selección o del albarán para los artículos que se envían</td>
<td>En cualquier paso</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un cliente concreto, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a un pedido de ventas puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Pedido de producción</td>
<td>Antes o después de que se registre la cantidad finalizada del pedido de producción</td>
<td>Después de que se registre la cantidad finalizada del pedido de producción</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio o un artículo concreto, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a un pedido de producción puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Pedido de producción con una operación de ruta</td>
<td>Antes o después de finalizar el informe de la operación</td>
<td>Después de finalizar el informe de producción de la última operación</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un recurso de operaciones concreto, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a una operación de ruta puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Inventario</td>
<td>Un pedido de calidad no se puede generar automáticamente para una transacción en un diario de inventario o para las transacciones de un pedido de transferencia.</td>
<td></td>
<td></td>
<td>Un pedido de calidad se debe crear manualmente para la cantidad de inventario de un artículo. Se requiere el inventario físico disponible.</td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a>Ejemplos de la generación automática del pedido de calidad

### <a name="purchasing"></a>Compras

En la compra, si establece el campo **Tipo de evento** en **Recepción de producto** y el campo **Ejecución** en **Después** en la página **Asociaciones de calidad**, obtiene los resultados siguientes: 

- Si la opción **Por cantidad actualizada** se establece en **Sí**, un pedido de calidad se genera para cada recepción con el pedido de compra, en función de la cantidad y los valores recibidos en el muestreo de artículos. Cada vez que una cantidad se reciba contra el pedido de compra, los nuevos pedidos de calidad se generan en función de la cantidad recién recibida.
- Si la opción **Por cantidad actualizada** se establece en **No**, un pedido de calidad se genera para la primera recepción con el pedido de compra, en función de la cantidad recibida. Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento. Los pedidos de calidad no se generan para las recepciones posteriores con el pedido de compra.

### <a name="production"></a>Producción

En la producción, si establece el campo **Tipo de evento** en **Informar como completado** y el campo **Ejecución** en **Después** en la página **Asociaciones de calidad**, obtiene los resultados siguientes:

- Si la opción **Por cantidad actualizada** se establece en **Sí**, un pedido de calidad se genera para cada cantidad y valores completados en el muestreo de artículos. Cada vez que una cantidad se notifique como terminado con el pedido de producción, los nuevos pedidos de calidad se generan en función de la cantidad recién terminada. Esta lógica de la generación es coherente con la compra.
- Si la opción **Por cantidad actualizada** se establece en **No**, un pedido de calidad se genera para la primera vez que una cantidad se notifica como terminada, en función de la cantidad terminada. Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento del muestreo del artículo. Los pedidos de calidad no se generan para las cantidades finalizadas posteriores.

<table>
<tbody>
<tr>
<th>Especificación de calidad</th>
<th>Por cantidad actualizada</th>
<th>Por dimensión de seguimiento</th>
<th>Resultado</th>
</tr>
<tr>
<td>Porcentaje: 10 %</td>
<td>Sí</td>
<td>
<p>Número de lote: No</p>
<p>Número de serie: No</p>
</td>
<td>
<p>Cantidad de pedido: 100</p>
<ol>
<li>Notificar como terminado para 30
<ul>
<li>Pedido de calidad #1 para 3 (10 % de 30)</li>
</ul>
</li>
<li>Notificar como terminado para 70
<ul>
<li>Pedido de calidad #2 para 7 (10% de la cantidad de pedido restantes, que es igual a 70 en este caso)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Cantidad fija: 1</td>
<td>No</td>
<td>
<p>Número de lote: No</p>
<p>Número de serie: No</p>
</td>
<td>Cantidad de pedido: 100
<ol>
<li>Notificar como terminado para 30
<ul>
<li>El pedido de calidad #1para 1 (para la primera cantidad notificada como terminada, que tiene un valor fijo de 1)</li>
<li>El pedido de calidad #2 para 1 (para la cantidad restante, que todavía un valor fijo de 1)</li>
</ul>
</li>
<li>Notificar como terminado para 10
<ul>
<li>No se crea ningún pedido de calidad.</li>
</ul>
</li>
<li>Notificar como terminado para 60
<ul>
<li>No se crea ningún pedido de calidad.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Cantidad fija: 1</td>
<td>Sí</td>
<td>
<p>Número de lote: Sí</p>
<p>Número de serie: Sí</p>
</td>
<td>
<p>Cantidad de pedido: 10</p>
<ol>
<li>Notificar como terminado para 3: 1 para #b1, #s1; 1 para #b2, #s2; y 1 para #b3, #s3
<ul>
<li>Pedido de calidad #1 para 1 del lote #b1, serie #s1</li>
<li>Pedido de calidad #2 para 1 del lote #b2, serie #s2</li>
<li>Pedido de calidad #3 para 1 del lote #b3, serie #s3</li>
</ul>
</li>
<li>Notificar como terminado para 2: 1 para #b4, #s4; y 1 para #b5, #s5
<ul>
<li>Pedido de calidad #4 para 1 del lote #b4, serie #s4</li>
<li>Pedido de calidad #5 para 1 del lote #b5, serie #s5</li>
</ul>
</li>
</ol>
<p><strong>Nota:</strong> El lote se puede volver a utilizar.</p>
</td>
</tr>
<tr>
<td>Cantidad fija: 2</td>
<td>No</td>
<td>
<p>Número de lote: Sí</p>
<p>Número de serie: Sí</p>
</td>
<td>
<p>Cantidad de pedido: 10</p>
<ol>
<li>Notificar como terminado para 4: 1 para #b1, #s1; 1 para #b2, #s2; 1 para #b3, #s3; y 1 para #b4 #s4
<ul>
<li>Pedido de calidad #1 para 1 del lote #b1, serie #s1</li>
<li>Pedido de calidad #2 para 1 del lote #b2, serie #s2</li>
<li>Pedido de calidad #3 para 1 del lote #b3, serie #s3</li>
<li>Pedido de calidad #4 para 1 del lote #b4, serie #s4</li>
</ul>
<ul>
<li>Pedido de calidad #5 para 2, sin una referencia a un lote y un número de serie</li>
</ul>
</li>
<li>Notificar como terminado para 6: 1 para #b5, #s5; 1 para #b6, #s6; 1 para #b7, #s7; 1 para #b8, #s8; 1 para #b9, #s9; y 1 para #b10, #s10
<ul>
<li>No se crea ningún pedido de calidad.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a>Páginas de administración de calidad
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Página</th>
<th>Descripción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Asociaciones de calidad</td>
<td>Consulte las secciones anteriores de este artículo.</td>
<td>Una asociación de calidad define toda la información siguiente para un pedido de calidad que se genera:
<ul>
<li>El evento de transacción</li>
<li>El conjunto de pruebas que se deben realizar en los artículos</li>
<li>El nivel de calidad aceptable</li>
<li>El plan de muestreo</li>
</ul>
Debe definir una asociación de calidad para cada variación de un proceso empresarial que requiera la generación automática de pedidos de calidad. Por ejemplo, un pedido de calidad se puede generar en los procesos empresariales para los pedidos de compra, pedidos de cuarentena, pedidos de ventas y pedidos de producción.</td>
</tr>
<tr class="even">
<td>Pruebas</td>
<td>Utilice esta página para definir y visualizar las pruebas individuales que determinan si sus productos cumplen las especificaciones de calidad. Puede asignar una o varias pruebas individuales a un grupo de pruebas. En este caso, también especifica la información específica de la prueba, como los valores de medida aceptables. Los valores de medida se usan para pruebas cuantitativas y las variables de prueba se usan para las pruebas cualitativas.
<ul>
<li>Una prueba cuantitativa tiene un tipo de prueba de <strong>Entero</strong> o <strong>Fracción</strong> y una unidad de medida designada. Las especificaciones de calidad y los resultados de la prueba se expresan como números.</li>
<li>Una prueba cualitativa tiene una prueba de tipo <strong>Opción</strong>. Las pruebas cualitativas requieren información adicional sobre la variable de prueba que se está midiendo y sus opciones enumeradas. Las especificaciones de calidad y los resultados de la prueba se expresan en función de un resultado.</li>
</ul></td>
<td>Una empresa de fabricación realiza dos pruebas en el material adquirido: una prueba cuantitativa sobre la calidad del material y una prueba cualitativa sobre los daños de embalaje. La empresa define información adicional sobre la prueba cualitativa para identificar la variable de prueba (embalaje dañado) y sus resultados. La empresa usa la página <strong>Grupos de prueba</strong> para asignar las dos pruebas a un grupo de pruebas y para especificar la información específica de la prueba. El grupo de pruebas se asigna a un pedido de calidad, de modo que la empresa puede informar de los resultados de la prueba para las dos pruebas.</td>
</tr>
<tr class="odd">
<td>Grupos de prueba</td>
<td>Use esta página para establecer, editar y ver los grupos de prueba y las pruebas individuales asignadas a un grupo de prueba. En el panel superior se muestran los grupos de pruebas y en el inferior se muestran las pruebas asignadas a un grupo de pruebas seleccionado. A un grupo de pruebas se le asignan varias directivas, por ejemplo, un plan de muestreo, un nivel de calidad aceptable (AQL) y el requisito de la prueba destructiva. Al asignar una prueba individual a un grupo de prueba, define información adicional, como la secuencia, los documentos, y las fechas de validez. Para una prueba cuantitativa, la información que define también incluye los valores de medida aceptables. Para una prueba cualitativa, la información incluye la variable de prueba y el resultado predeterminado. El grupo de prueba asignado a un pedido de calidad define el conjunto predeterminado de pruebas que se tienen que realizar sobre el artículo especificado. No obstante, puede agregar, cambiar o eliminar las pruebas en el pedido de calidad. Los resultados de prueba se notifican para cada prueba de un pedido de calidad.</td>
<td>Un fabricante define un grupo de pruebas para cada variación de sus criterios de calidad. Los distintos grupos de pruebas reflejan las diferencias de los planes de muestreo, los conjuntos de pruebas que se deben realizar en conjunto, el AQL y otros factores. Para las pruebas cuantitativas también hay diferencias en los valores de medida aceptables. Para aplicar sus criterios de calidad, la empresa asigna un grupo de prueba a cada regla con el fin de generar automáticamente pedidos de calidad en la página <strong>Asociaciones de calidad</strong> y también asigna un grupo de prueba a los pedidos de calidad creados manualmente.</td>
</tr>
<tr class="even">
<td>Grupos de calidad de artículos</td>
<td>Use esta página para configurar, editar y ver los artículos asignados a un grupo de calidad o a los grupos de calidad asignados a un artículo. Un grupo de calidad representa requisitos de prueba comunes para los artículos. Cuando haya definido los requisitos de prueba en la página <strong>Grupos de prueba</strong>, puede definir las reglas para generar automáticamente pedidos de calidad. Para simplificar el proceso, no se definen reglas para artículos individuales. En su lugar, puede definir las reglas para un grupo de calidad mediante la página <strong>Asociaciones de calidad</strong>. También puede usar la página <strong>Grupos de calidad de artículos</strong> para un grupo de calidad seleccionado para asignar artículos relevantes a dicho grupo. También puede usar la página <strong>Grupos de calidad de artículos</strong> para un artículo seleccionado para asignar grupos de calidad relevantes a dicho artículo.</td>
<td>Un fabricante compra varias materias primas con los mismos requisitos de prueba para una inspección entrante. La empresa define un grupo de calidad y, después, le asigna números de artículo asociados con las materias primas para ese grupo. Más adelante, la empresa compra un nuevo tipo de materia prima con los mismos requisitos de prueba. En lugar de configurar requisitos de prueba nuevos para el nuevo material, la empresa añade el número de artículo del nuevo material al grupo de calidad existente. El mismo fabricante también produce artículos con los mismos requisitos de prueba y envía artículos con los mismos requisitos para las pruebas anteriores al envío. La empresa define dos grupos de calidad adicionales y, después, asigna números de artículo pertinentes a cada grupo.</td>
</tr>
<tr class="odd">
<td>Variables de prueba</td>
<td>Use esta página para definir y ver las variables asociadas a una prueba cualitativa. Para cada variable, define los resultados enumerados que representan las posibles opciones. Puede definir pruebas en la página <strong>Pruebas</strong>. Para las pruebas cualitativas, debe definir el tipo de prueba en <strong>Opción</strong>. Use la página <strong>Grupos de prueba</strong> para asignar una variable de prueba a una prueba individual.</td>
<td>Una fábrica de galletas utiliza una prueba de inspección para el producto terminado. Esta prueba de inspección tiene varias variables. Una variable es el gusto y los posibles resultados para esta variable son bueno y malo. Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</td>
</tr>
<tr class="even">
<td>Resultados de la variable de prueba</td>
<td>Utilice esta página para configurar, editar y visualizar los resultados posibles de una variable de prueba asociada a una prueba cualitativa. Para cada resultado, asigne un estado de <strong>correcto</strong> o <strong>erróneo</strong>. Deberá definir una variable y sus resultados para cada prueba cualitativa definida en la página <strong>Pruebas</strong>. (Para las pruebas cualitativas, el tipo de prueba se establece en <strong>Opción</strong> en la página <strong>Pruebas</strong>). Utilice la página <strong>Grupos de prueba</strong> para asignar una variable de prueba y el resultado predeterminado a una prueba cualitativa individual.</td>
<td>Una fábrica de galletas utiliza una prueba de inspección para el producto terminado. Esta prueba de inspección tiene varias variables. Una variable es el gusto y los posibles resultados para esta variable son bueno y malo. Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto. Cada resultado tiene asignado un estado de <strong>correcto</strong> o <strong>erróneo</strong>. Durante la prueba de inspección de cada variable, el inspector notifica el resultado de la prueba seleccionando uno de los resultados.</td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Recursos adicionales
--------

[Procesos de administración de la calidad](quality-management-processes.md)

[Gestión de disconformidad](enable-nonconformance-management.md)
