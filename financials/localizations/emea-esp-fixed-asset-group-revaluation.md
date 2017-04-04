---
title: "Grupos de revalorización de activos fijos"
description: "Este tema proporciona información sobre los grupos de revalorización de activos fijos para España."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 264994
ms.assetid: 50ed4cae-7606-4ded-a07b-992848ece5ae
ms.search.region: Spain
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 982bbfe80435c3870adb4b1d9f1f4c0d46f2611d
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-revaluation-groups"></a>Grupos de revalorización de activos fijos

Este tema proporciona información sobre los grupos de revalorización de activos fijos para España.

Los grupos de revalorización para establecer las condiciones de revalorización para el activo fijo. Por ejemplo, el grupo de revalorización podría ser factor o una fecha de revalorización. El valor del grupo de revalorización se usará en el diario de activos fijos para las propuestas de revalorización y para los ajustes de valores individuales de transacciones de revalorización. Para revalorizar un activo fijo, debe especificar el grupo de revalorización en las ** Libretas ** la página. El valor del grupo de revalorización se usará en el diario de activos fijos para las propuestas de revalorización y para los ajustes de valores individuales de transacciones de revalorización.

## <a name="revaluation-group-setup"></a>Configuración del grupo de revalorización
Puede configurar un grupo de revalorización en ** los grupos de revalorización ** la página. El panel superior, cree un identificador para el grupo de revalorización. En el panel inferior, especifique la fecha de la revalorización y el factor por el que se aumentará o disminuirá el valor.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Field</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><strong>Revaluation group</strong></td>
<td>Especificar la identificación del grupo de revalorización. En el caso de los activos fijos que se van a configurar para la revalorización, el grupo de revalorización se debe asignar al activo fijo por modelo de valor.</td>
</tr>
<tr class="odd">
<td><strong>Description</strong></td>
<td>Escriba la descripción del grupo de revalorización que describe el propósito de cada grupo.</td>
</tr>
<tr class="even">
<td><strong>Fecha</strong></td>
<td>Especificar la fecha a partir de la cual es válido el factor de revalorización.</td>
</tr>
<tr class="odd">
<td><strong>Factor</strong></td>
<td>Especificar el factor y el precio de adquisición que determina la propuesta de revalorización del activo fijo. Por ejemplo, supongamos que el importe de la adquisición es de 100.000. Mediante la ecuación <em>Importe de adquisición - (importe de adquisición * factor),</em> la siguiente tabla muestra el resultado de distintos factores.
<table>
<tbody>
<tr class="odd">
<td><strong>Factor</strong></td>
<td><strong>Formula</strong></td>
<td><strong>Transacción</strong> </td>
</tr>
<tr class="even">
<td>1</td>
<td>100.000 - (100.000 * 1)</td>
<td>Sin transacción</td>
</tr>
<tr class="odd">
<td>10</td>
<td>100.000 - (100.000 * 10)</td>
<td>Débito 900.000</td>
</tr>
<tr class="even">
<td>0.5</td>
<td>100.000 - (100.000 * 0,5)</td>
<td>Crédito 50.000</td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>




