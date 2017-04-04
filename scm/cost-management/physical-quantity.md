---
title: "Recepción del inventario la configuración del objeto"
description: "Este artículo proporciona información sobre cómo se calculan los valores de un objeto de inventario."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-07 09 - 09 - 05
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 8898d5d91ffb4f73ea68f1251e1a99440e81bcd4
ms.lasthandoff: 03/29/2017


---

# <a name="inventory-object-values"></a>Recepción del inventario la configuración del objeto

Este artículo proporciona información sobre cómo se calculan los valores de un objeto de inventario. 

Una nueva funcionalidad que se denomina ** cantidad física ** permite tener en cuenta los valores de un objeto específico del inventario. Un objeto de coste representa el nivel de entidad donde se realiza la contabilidad de inventario. Para obtener más información acerca de los objetos de coste, consulte [Objetos de coste](cost-object.md). Para ver los valores del inventario específico SQL, haga clic en ** cantidad física ** en ** objeto de coste ** la página. Aquí es cómo el valor de un objeto de inventario se calcula: Objeto de inventario. Valor = objeto coste. Objeto medio del inventario del × del coste unitario. Cantidad las presentaciones el siguiente ejemplo que los valores de un objeto de inventario y un objeto de coste se calculan. Dos eventos de recepción de producto se registran en el artículo A:

-   Recepción de producto 1: Cantidad = 100 equipos., importe = $1,000.00 sitio, = 1, almacén, =11 lote no. = B1
-   Recepción de producto 2: Cantidad = 50 equipos., importe = $800.00 sitio, = 1, almacén, =11 lote no. = B2

La tabla siguiente muestra el resultado del cálculo de un objeto de coste. Puede ver el resultado en la página **Objeto de coste**.

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de objeto</th>
<th>Número de artículo</th>
<th>Sitio</th>
<th>Cantidad</th>
<th>Unidad de inventario</th>
<th>Valor</th>
<th>Coste unitario promedio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Objeto de coste</td>
<td>A</td>
<td>1</td>
<td>150</td>
<td>Periodos</td>
<td><p>1800,00 $</p></td>
<td><p>12,00 $</p></td>
</tr>
</tbody>
</table>

La tabla siguiente muestra el resultado del cálculo de un objeto de inventario. Puede ver el resultado haciendo clic en **Cantidad física** en la página **Objeto de coste**.

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de objeto</th>
<th>Número de artículo</th>
<th>Sitio</th>
<th>Almacén</th>
<th>N.º de lote</th>
<th>Cantidad</th>
<th>Unidad de inventario</th>
<th>Valor</th>
<th>Coste unitario promedio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Objeto de inventario</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>Periodos</td>
<td><p>1200,00 $</p></td>
<td><p>12,00 $</p></td>
</tr>
<tr class="even">
<td>Objeto de inventario</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>Periodos</td>
<td><p>600,00 $</p></td>
<td><p>12,00 $</p></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Consulte también
--------

[Cost objects](cost-object.md)

[Cost entries](cost-entries.md)

[Novedades y cambiado en Microsoft Dynamics AX (/dynamics365/operations/dev-itpro/get-started/what] - es nueva cambiar)


