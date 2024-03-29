---
title: Grupos de revalorización de activos fijos
description: Este artículo proporciona información acerca de la revalorización de activos fijos para España.
author: EvgenyPopovMBS
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetRevaluationGroup, AssetBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 264994
ms.search.region: Spain
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a5fcd4db95b97577d8002a19673b19852b5801ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855314"
---
# <a name="fixed-asset-revaluation-groups"></a>Grupos de revalorización de activos fijos

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la revalorización de activos fijos para España.

Los grupos de revalorización se usan para configurar condiciones de revalorización para el activo fijo. Por ejemplo, el grupo de revalorización podría ser un factor o una fecha de revalorización. El valor del grupo de revalorización se usará en el diario de activos fijos para las propuestas de revalorización y para los ajustes de valores individuales de transacciones de revalorización. Para revalorizar un activo fijo debe especificar el grupo de revalorización en la página **Libros**. El valor del grupo de revalorización se usará en el diario de activos fijos para las propuestas de revalorización y para los ajustes de valores individuales de transacciones de revalorización.

## <a name="revaluation-group-setup"></a>Configuración de grupo de revalorización
Puede configurar un grupo de revalorización en la página **Grupos de revalorización**. El panel superior, cree un identificador para el grupo de revalorización. En el panel inferior, especifique la fecha de la revalorización y el factor por el que se aumentará o disminuirá el valor.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Campo</strong></td>
<td><strong>Descripción</strong></td>
</tr>
<tr class="even">
<td><strong>Grupo de revalorización</strong></td>
<td>Especificar la identificación del grupo de revalorización. En el caso de los activos fijos que se van a configurar para la revalorización, el grupo de revalorización se debe asignar al activo fijo por modelo de valor.</td>
</tr>
<tr class="odd">
<td><strong>Descripción</strong></td>
<td>Especifique la descripción del grupo de revalorización que describe el propósito de cada grupo.</td>
</tr>
<tr class="even">
<td><strong>Fecha</strong></td>
<td>Especificar la fecha a partir de la cual es válido el factor de revalorización.</td>
</tr>
<tr class="odd">
<td><strong>Factor</strong></td>
<td>Especificar el factor y el precio de adquisición que determina la propuesta de revalorización del activo fijo. Por ejemplo, supongamos que el importe de la adquisición es de 100.000. Con la ecuación <em>Importe de la adquisición - (importe de adquisición * factor)</em>, la siguiente tabla muestra el resultado de distintos factores.
<table>
<tbody>
<tr class="odd">
<td><strong>Factor</strong></td>
<td><strong>Fórmula</strong></td>
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







[!INCLUDE[footer-include](../../includes/footer-banner.md)]