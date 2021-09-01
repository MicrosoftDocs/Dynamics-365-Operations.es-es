---
title: Asociaciones de calidad
description: Este tema describe cómo puede usar asociaciones de calidad en Microsoft Dynamics 365 Supply Chain Management para generar automáticamente pedidos de calidad relacionados con sus procesos de venta, compra y producción.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0705af8f8c40db82e412f294f45f704b7a628c1ced679cef25ce77d49642feb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724853"
---
# <a name="quality-associations"></a>Asociaciones de calidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo puede usar asociaciones de calidad en Microsoft Dynamics 365 Supply Chain Management para generar automáticamente pedidos de calidad relacionados con sus procesos de venta, compra y producción.

Una asociación de calidad define toda la información siguiente para un pedido de calidad que se genera:

- El evento de transacción
- El conjunto de pruebas que se deben realizar en los artículos
- Nivel de calidad aceptable (AQL)
- El plan de muestreo

Debe definir una asociación de calidad para cada variación de un proceso empresarial que requiera la generación automática de pedidos de calidad. Por ejemplo, un pedido de calidad se puede generar en los procesos empresariales para los pedidos de compra, pedidos de cuarentena, pedidos de ventas y pedidos de producción.

## <a name="working-with-quality-associations"></a>Trabajar con asociaciones de calidad

El proceso empresarial que utiliza una asociación de calidad puede estar relacionado con varios documentos de origen, como pedidos de compra, pedidos de ventas o pedidos de producción.

Cada registro de asociación de calidad define el conjunto de pruebas, el nivel de calidad aceptable y el plan de muestreo que se aplica a los pedidos de calidad generados. Debe definir un registro de asociación de calidad para cada variación de un proceso empresarial. Por ejemplo, puede configurar una asociación de calidad que genere un pedido de calidad cuando se actualice una recepción de producto de pedido de compra. Dependiendo de la configuración del plan de ejecución, el proceso de desencadenamiento en sí puede bloquearse mientras haya un pedido de calidad abierto. Alternativamente, se pueden bloquear los procesos posteriores, como la facturación de pedidos de compra.

> [!NOTE]
> Mientras haya pedidos de calidad abiertos, las cantidades de inventario se bloquean automáticamente para evitar su emisión. En función de la configuración del campo **Bloqueo completo** de la página **Muestreos de artículos**, la cantidad es la cantidad del pedido de calidad o la cantidad de la línea del documento de origen. Para más información, consulte [Muestreo de elementos de gestión de calidad](quality-item-sampling.md).

Para un determinado proceso empresarial, el registro de la asociación de calidad identifica el evento y las condiciones para las que se genera un pedido de calidad. Las condiciones pueden especificarse para un sitio o para una entidad jurídica. Un pedido de calidad que requiera pruebas destructivas solo se puede generar si hay un inventario disponible para el evento.

Para trabajar con asociaciones de calidad, vaya a **Gestión del inventario \> Configuración \> Control de calidad \> Asociaciones de calidad**. En los siguientes ejemplos se muestra cómo se define un registro de asociación de calidad para las variantes de cada proceso empresarial. Para cada ejemplo, la siguiente tabla resume los eventos y las condiciones definidos por un registro de asociación de calidad.

<table>
<thead>
<tr>
<th>Tipo de referencia</th>
<th>Tipo de evento</th>
<th>Ejecución</th>
<th>Bloqueo de eventos</th>
<th>Referencia del documento</th>
</tr>
</thead>
<tbody>
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
<td rowspan="2">Antes</td>
<td>None</td>
<td rowspan="3">Id. específico, Grupo o Todo, y Recurso específico, Grupo o Todo</td>
</tr>
<tr>
<td>Notificar como terminado</td>
</tr>
<tr>
<td>Posterior</td>
<td>None</td>
</tr>
<tr>
<td rowspan="3">Producción de coproductos</td>
<td>Registro</td>
<td>No aplicable</td>
<td rowspan="3">None</td>
<td rowspan="3">Todos</td>
</tr>
<tr>
<td rowspan="2">Notificar como terminado</td>
<td>Antes</td>
</tr>
<tr>
<td>Posterior</td>
</tr>
</tbody>
</table>

> [!NOTE]
> La característica *Gestión de calidad para procesos de almacén* agrega capacidades para el procesamiento de pedidos de calidad para la producción cuando el campo **Tipo de evento** está establecido en *Informar como terminado* y el campo **Ejecución** está establecido en *Después*, y para compras con el campo **Tipo de evento** establecido en *Registro*. Para más información, consulte [Administración de calidad para procesos de almacén](quality-management-for-warehouses-processes.md).

La siguiente tabla proporciona más información acerca de cómo se pueden generar los pedidos de calidad para tipos de procesos concretos.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Tipo de proceso</th>
<th>Cuando los pedidos de calidad se pueden generar automáticamente</th>
<th>Cuando los pedidos de calidad se pueden generar si se requiere una prueba destructiva</th>
<th>Información acerca de la condición</th>
<th>Información acerca de la generación manual</th>
</tr>
</thead>
<tbody>
<tr>
<td>Pedido de compra</td>
<td>Antes o después de que se registre una lista de recepciones o una recepción de producto del material recibido</td>
<td>Después del registro de la recepción de producto, ya que el material debe estar disponible para la prueba destructiva</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor específico, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a un pedido de compra puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Orden de cuarentena</td>
<td>Antes o después de que se notifique que ha finalizado la orden de cuarentena</td>
<td>No se pueden generar pedidos de calidad que necesiten pruebas destructivas. Se supone que la funcionalidad de la orden de cuarentena gestiona la disposición del material destruido.</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor específico, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a una orden de cuarentena puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Pedido de ventas</td>
<td>Antes de una actualización programada del proceso de selección o del albarán para los artículos que se envían</td>
<td>En cualquier paso</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un cliente específico, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a un pedido de ventas puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Pedido de producción</td>
<td>Antes o después de que se registre la cantidad finalizada del pedido de producción</td>
<td>Después de que se registre la cantidad finalizada del pedido de producción</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio o un artículo específico, o una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a un pedido de producción puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Pedido de producción con una operación de ruta</td>
<td>Antes o después de finalizar el informe de la operación</td>
<td>Después de finalizar el informe de producción de la última operación</td>
<td>El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un recurso de operaciones específicos, además de una combinación de estas condiciones.</td>
<td>Un pedido de calidad generado manualmente que hace referencia a una operación de ruta puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</td>
</tr>
<tr>
<td>Inventario</td>
<td>Un pedido de calidad no se puede generar automáticamente para una transacción en un diario de inventario ni para las transacciones de un pedido de transferencia.</td>
<td></td>
<td></td>
<td>Un pedido de calidad se debe crear manualmente para la cantidad de inventario de un artículo. Se requiere el inventario físico disponible.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Ejemplos de generación automática de pedidos de calidad

### <a name="purchasing"></a>Compras

En la compra, si establece el campo **Tipo de evento** en *Recepción de producto* y el campo **Ejecución** en *Después* en la página **Asociaciones de calidad**, obtiene los resultados siguientes:

- Si la opción **Por cantidad actualizada** se establece en *Sí*, un pedido de calidad se genera para cada recepción con el pedido de compra, en función de la cantidad y los valores recibidos en el muestreo de artículos. Cada vez que una cantidad se reciba contra el pedido de compra, los nuevos pedidos de calidad se generan en función de la cantidad recién recibida.
- Si la opción **Por cantidad actualizada** se establece en *No*, un pedido de calidad se genera para la primera recepción con el pedido de compra, en función de la cantidad recibida. Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento. Los pedidos de calidad no se generan para las recepciones posteriores con el pedido de compra.

### <a name="production"></a>Producción

En la producción, si establece el campo **Tipo de evento** en *Informar como completado* y el campo **Ejecución** en *Después* en la página **Asociaciones de calidad**, obtiene los resultados siguientes:

- Si la opción **Por cantidad actualizada** se establece en *Sí*, un pedido de calidad se genera para cada cantidad y valores completados en el muestreo de artículos. Cada vez que una cantidad se notifique como terminada frente al pedido de producción, los nuevos pedidos de calidad se generan en función de la cantidad recién terminada. Esta lógica de la generación es coherente con la compra.
- Si la opción **Por cantidad actualizada** se establece en *No*, un pedido de calidad se genera para la primera vez que una cantidad se notifica como terminada, en función de la cantidad terminada. Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento del muestreo del artículo. Los pedidos de calidad no se generan para las cantidades finalizadas posteriores.

<table>
<thead>
<tr>
<th>Especificación de calidad</th>
<th>Por cantidad actualizada</th>
<th>Por dimensión de seguimiento</th>
<th>Resultado</th>
</tr>
</thead>
<tbody>
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
<li>Pedido de calidad 1 para 3 (10 % de 30)</li>
</ul>
</li>
<li>Notificar como terminado para 70
<ul>
<li>Pedido de calidad 2 para 7 (10 % de la cantidad de pedidos restantes, que es 70 en este caso)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Cantidad fija: 1</td>
<td>N.º</td>
<td>
<p>Número de lote: No</p>
<p>Número de serie: No</p>
</td>
<td>Cantidad de pedido: 100
<ol>
<li>Notificar como terminado para 30
<ul>
<li>El pedido de calidad 1 para 1 (para la primera cantidad notificada como terminada, que tiene un valor fijo de 1)</li>
<li>El pedido de calidad 2 para 1 (para la cantidad restante, que todavía tiene un valor fijo de 1)</li>
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
<li>Informe como terminado para 3: 1 para el número de lote b1, número de serie s1; 1 para el número de lote b2, número de serie s2; y 1 para el número de lote b3, número de serie s3
<ul>
<li>Pedido de calidad 1 para 1 del número de lote b1, número de serie s1</li>
<li>Pedido de calidad 2 para 1 del número de lote b2, número de serie s2</li>
<li>Pedido de calidad 3 para 1 del número de lote b3, número de serie s3</li>
</ul>
</li>
<li>Informe como terminado para 2: 1 para el número de lote b4, número de serie s4; y 1 para el número de lote b5, número de serie s5
<ul>
<li>Pedido de calidad 4 para 1 del número de lote b4, número de serie s4</li>
<li>Pedido de calidad 5 para 1 del número de lote b5, número de serie s5</li>
</ul>
</li>
</ol>
<p><strong>Nota:</strong> El lote se puede volver a utilizar.</p>
</td>
</tr>
<tr>
<td>Cantidad fija: 2</td>
<td>N.º</td>
<td>
<p>Número de lote: Sí</p>
<p>Número de serie: Sí</p>
</td>
<td>
<p>Cantidad de pedido: 10</p>
<ol>
<li>Informe como terminado para 4: 1 para el número de lote b1, número de serie s1; 1 para el número de lote b2, número de serie s2; y 1 para el número de lote b3, número de serie s3; y 1 para el número de lote b4, número de serie s4
<ul>
<li>Pedido de calidad 1 para 1 del número de lote b1, número de serie s1</li>
<li>Pedido de calidad 2 para 1 del número de lote b2, número de serie s2</li>
<li>Pedido de calidad 3 para 1 del número de lote b3, número de serie s3</li>
<li>Pedido de calidad 4 para 1 del número de lote b4, número de serie s4</li>
</ul>
<ul>
<li>Pedido de calidad 5 para 2, sin una referencia a un número de lote y un número de serie</li>
</ul>
</li>
<li>Informe como terminado para 6: 1 para el número de lote b5, número de serie s5; 1 para el número de lote b6, número de serie s6; 1 para el número de lote b7, número de serie s7; 1 para el número de lote b8, número de serie s8; 1 para el número de lote b9, número de serie s9; y 1 para el número de lote b10, número de serie s10
<ul>
<li>No se crea ningún pedido de calidad.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionales

- [Procesos de administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
