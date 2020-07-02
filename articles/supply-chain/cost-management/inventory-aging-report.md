---
title: Ejemplos de informes de antigüedad de inventario y lógica
description: Este tema presenta algunos ejemplos que muestran cómo interpretar los resultados de un informe de antigüedad del inventario.
author: RichardLuan
manager: AnnBe
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6c165599c11b84e4064a9303d8b1f59558fc6b9d
ms.sourcegitcommit: 6bf8602333191e5161ba3a9ceecf160c85ff7e79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "3484539"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Ejemplos de informes de antigüedad de inventario y lógica

[!include [banner](../includes/banner.md)]

Este tema presenta algunos ejemplos que muestran cómo interpretar los resultados de un informe de **antigüedad del inventario**. Este informe clasifica la cantidad disponible y los valores de inventario para un artículo seleccionado o grupo de artículos en varios períodos. Este tema también muestra la lógica interna del informe.

Los ejemplos en este tema muestran los resultados que se presentan en un informe de **antigüedad de inventario** estándar. Sin embargo, en general, le recomendamos que utilice la versión [Almacenamiento de informes de antigüedad de inventario](inventory-aging-report-storage.md) de este informe, especialmente cuando tiene muchos artículos y almacenes que deben procesarse. El almacenamiento de informes de antigüedad de inventario guarda cada informe que genera, muestra los resultados como una página interactiva y un gráfico, y le permite exportar cualquier informe guardado.

## <a name="sample-data-that-is-used-in-these-examples"></a>Datos de muestra que se usan en estos ejemplos

Los ejemplos de este tema se basan en los datos de muestra de transacciones de inventario que se describen en esta sección.

### <a name="storage-dimension-setup"></a>Configuración de la dimensión de almacenamiento

El sistema de ejemplo contiene la siguiente configuración de dimensiones de almacenamiento.

| Nombre      | Activas | Inventario físico | Inventario financiero |
|-----------|--------|--------------------|---------------------|
| Sitio      | Sí    | Sí                | Sí                 |
| Almacén | Sí    | Sí                | Nº                  |

### <a name="inventory-model"></a>Modelo de inventario

Para el sistema de ejemplo, el modelo de inventario para los productos publicados es *FIFO*, y la configuración de **Precio de coste** para el modelo de inventario es *Incluir valor físico*.

### <a name="inventory-transactions"></a>Transacciones de inventario

El sistema de ejemplo contiene las siguientes transacciones de inventario para un producto publicado que tiene el número de artículo *1000*.

| Referencia      | Sitio | Almacén | Recepción   | Emitir | Fecha física | Fecha financiera | Cantidad | Importe de coste | Importe de coste físico |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Pedido de compra | 1    | 11        | Comprado |       | 15 de marzo      | 15 de marzo       | 10       | 1.000       | 1.000                |
| Pedido de compra | 2    | 21        | Comprado |       | 15 de marzo      | 15 de marzo       | 10       | 2,000       | 2,000                |
| Pedido de compra | 1    | 11        | Recibida  |       | 15 de abril      |                | 5        |             | 375                  |
| Orden de transferencia | 1    | 11        |           | Vendido  | mayo de 2         | mayo de 2          | -5       | -458,33     | -458,33              |
| Orden de transferencia | 1    | 12        | Comprado |       | mayo de 2         | mayo de 2          | 5        | 458.33      | 458.33               |
| Pedido de ventas    | 1    | 12        |           | Vendido  | mayo de 3         | mayo de 3          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Cómo se calculan las cantidades y los importes en cada cubo de períodos

Al utilizar los datos de ejemplo que se describen en las secciones anteriores, podrá ejecutar un informe de **antigüedad de inventario** que tiene la siguiente configuración:

- **A partir de la fecha:** *9 de mayo de 2020*
- **Sitio:** *Ver*
- **Almacén**: *No*
- **Número de artículo:** *Total*
- **Período de antigüedad:** establezca este campo para generar depósitos mensuales.

En este caso, el contenido del informe generado se parecerá al siguiente ejemplo.

<table>
<thead>
<tr>
    <th rowspan="2">código de artículo</th>
    <th rowspan="2">Sitio</th>
    <th rowspan="2">Cantidad disponible</th>
    <th rowspan="2">Valor disponible</th>
    <th rowspan="2">Cantidad de valor de inventario</th>
    <th rowspan="2">Valor de inventario</th>
    <th rowspan="2">Coste unitario promedio</th>
    <th colspan="2">5/8/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1:Cantidad</th>
    <th>P1:Importe</th>
    <th>P2:Cantidad</th>
    <th>P2:Importe</th>
    <th>P3:Cantidad</th>
    <th>P3:Importe</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 Totales</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

Tenga en cuenta los siguientes detalles en este informe de ejemplo:

- Los valores **Cantidad de valor de inventario**, **Valor de inventario** y **Coste unitario promedio** que se muestran en el informe son valores para la dimensión de inventario financiero (**Sitio**, en este caso).

    Por ejemplo, para el sitio 1, el informe muestra la siguiente información:

    - El valor **Cantidad de valor de inventario** es *14* (= 10 + 5 - 5 + 5 - 1).
    - El valor **Cantidad de valor de inventario** es *1283,33* (= 1000 + 375 - 458,33 + 458,33 - 91,67).
    - El valor **Coste unitario promedio** es *91,67*.
    - El valor **Valor disponible** y el valor **Importe** en cada período se calcula utilizando el valor **Coste unitario promedio**.

- El informe determina la cantidad disponible para cada cubo de períodos resumiendo la cantidad de inventario total recibida para cada cubo de períodos. Luego aplica el principio de primero en entrar, primero en salir (FIFO) para deducir la cantidad total emitida, independientemente del modelo de inventario que usan los artículos.

Si ejecuta el mismo informe nuevamente, pero esta vez configura los campos **Sitio** y **Almacén** en *Ver*, el nuevo informe se parecerá al siguiente ejemplo.

<table>
<thead>
<tr>
    <th rowspan="2">código de artículo</th>
    <th rowspan="2">Sitio</th>
    <th rowspan="2">Almacén</th>
    <th rowspan="2">Cantidad disponible</th>
    <th rowspan="2">Valor disponible</th>
    <th rowspan="2">Cantidad de valor de inventario</th>
    <th rowspan="2">Valor de inventario</th>
    <th rowspan="2">Coste unitario promedio</th>
    <th colspan="2">5/8/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1:Cantidad</th>
    <th>P1:Importe</th>
    <th>P2:Cantidad</th>
    <th>P2:Importe</th>
    <th>P3:Cantidad</th>
    <th>P3:Importe</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 Totales</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

Esta vez, el sitio 1 se divide en dos filas, una para el almacén 11 y otra para el almacén 12. Sin embargo, los valores **Cantidad de valor de inventario**, **Valor de inventario** y **Coste unitario promedio** son los mismos porque **Almacén** no es una dimensión de inventario financiera.

Además, observe que la distribución de cantidad del sitio 1 es diferente. En el primer informe que ejecutó, el sistema ignoró la orden de transferencia que ocurrió en el mismo sitio y dedujo la cantidad de la factura de venta del cubo de periodos **31/03/2020 - 1/3/2020** en el sitio 1. Sin embargo, en el nuevo informe, el sistema deduce la cantidad de la factura de venta del cubo de períodos **8/05/2020 - 5/1/2020** en el almacén 12.

## <a name="effects-of-inventory-closing"></a>Efectos del cierre del inventario

Si ejecuta el cierre de inventario para mayo y luego vuelve a ejecutar el informe anterior, pero configura el campo **A partir de la fecha** en el *31 de mayo de 2020*, verá los siguientes resultados:

- Los valores **Valor de inventario** y **Coste unitario promedio** se actualizan.
- El valor **Valor disponible** y todos los valores de **Importe** en cada cubo de períodos se actualizan en consecuencia.

El informe nuevo se parecerá al ejemplo siguiente.

<table>
<thead>
<tr>
    <th rowspan="2">código de artículo</th>
    <th rowspan="2">Sitio</th>
    <th rowspan="2">Almacén</th>
    <th rowspan="2">Cantidad disponible</th>
    <th rowspan="2">Valor disponible</th>
    <th rowspan="2">Cantidad de valor de inventario</th>
    <th rowspan="2">Valor de inventario</th>
    <th rowspan="2">Coste unitario promedio</th>
    <th colspan="2">5/31/2020 - 5/1/2020</th>
    <th colspan="2">4/30/2020 - 4/1/2020</th>
    <th colspan="2">3/31/2020 - 3/1/2020</th>
</tr>
<tr>
    <th>P1:Cantidad</th>
    <th>P1:Importe</th>
    <th>P2:Cantidad</th>
    <th>P2:Importe</th>
    <th>P3:Cantidad</th>
    <th>P3:Importe</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 Totales</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>
