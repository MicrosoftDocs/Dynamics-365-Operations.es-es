---
title: Valores de objeto de inventario
description: Este artículo proporciona información sobre cómo se calculan los valores de un objeto de inventario.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 914c7e8c757664ec791b46924600b74c9c979e8f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967442"
---
# <a name="inventory-object-values"></a>Valores de objeto de inventario

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre cómo se calculan los valores de un objeto de inventario. 

Una nueva funcionalidad que se denomina **cantidad física** le permite ver los valores de un objeto de inventario específico. 

Un objeto de coste representa el nivel de entidad donde se realiza la contabilidad de inventario. Para obtener más información acerca de los objetos de coste, consulte [Objetos de coste](cost-object.md). 

Para ver los valores de un objeto de inventario específico, haga clic en **Cantidad física** en la página **Objeto de coste**. A continuación se ve cómo se calcula el valor de un objeto de inventario: 

Valor de objeto de inventario. Valor = Coste objeto.Coste unitario promedio × Objeto inventario.Cantidad 

El siguiente ejemplo muestra cómo se calculan los valores de un objeto de inventario y un objeto de coste. Dos eventos de recepción de producto se registran en el artículo A:

-   Recepción de producto 1: Cantidad = 100 uds, Importe = 1.000,00 $, Sitio = 1, Almacén =11, N.º de lote = B1
-   Recepción de producto 2: Cantidad = 50 uds, Importe = 800,00 $, Sitio = 1, Almacén =11, N.º de lote = B2

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
<td>C</td>
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



<a name="additional-resources"></a>Recursos adicionales
--------

[Objetos de coste](cost-object.md)

[Entradas de costes](cost-entries.md)

[Novedades y cambios](../../fin-and-ops/get-started/whats-new-changed.md)



