---
title: Especificar la disposición de artículos devueltos
description: Especificar la disposición de artículos devueltos.
author: kamaybac
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e609c1c285b34a5416a2058809b2fc4fafb73fca
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571338"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>Especificar la disposición de artículos devueltos

[!include [banner](../includes/banner.md)]

Al gestionar un pedido de devolución, debe especificar un código de motivo de devolución para identificar por qué se devuelve el producto. También debe especificar un código de disposición y una acción de disposición de determinar qué se debe realizar con el producto devuelto en sí.

Un código de disposición se puede aplicar cuando se crea el pedido de devolución, se registra la llegada del artículo o el albarán, se actualiza una llegada de artículo o se finaliza una orden de cuarentena.

Se pueden definir los códigos de disposición necesarios para los procesos empresariales. La tabla siguiente proporciona un conjunto de códigos que se usan habitualmente para asignar la disposición del artículo devuelto.

<table>
<colgroup>
<col />
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Tipo de disposición</p></th>
<th><p>Código común</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cancelación</p></td>
<td><p>SC</p></td>
<td><p>Desechar/Destruir</p></td>
</tr>
<tr class="even">
<td><p>Cancelación</p></td>
<td><p>DC</p></td>
<td><p>Donar a caridad</p></td>
</tr>
<tr class="odd">
<td><p>Cancelación</p></td>
<td><p>TD</p></td>
<td><p>Cancelación de terceros</p></td>
</tr>
<tr class="even">
<td><p>Cancelación</p></td>
<td><p>SL</p></td>
<td><p>Rescatar</p></td>
</tr>
<tr class="odd">
<td><p>Cancelación</p></td>
<td><p>TS</p></td>
<td><p>Venta de terceros (mercados secundarios)</p></td>
</tr>
<tr class="even">
<td><p>Reparación/Modificación</p></td>
<td><p>RW</p></td>
<td><p>Reprocesar</p></td>
</tr>
<tr class="odd">
<td><p>Reparación/Modificación</p></td>
<td><p>RF</p></td>
<td><p>Volver a fabricar/Reacondicionar</p></td>
</tr>
<tr class="even">
<td><p>Reparación/Modificación</p></td>
<td><p>MD</p></td>
<td><p>Modificar</p></td>
</tr>
<tr class="odd">
<td><p>Reparación/Modificación</p></td>
<td><p>RP</p></td>
<td><p>Reparar</p></td>
</tr>
<tr class="even">
<td><p>Reparación/Modificación</p></td>
<td><p>RV</p></td>
<td><p>Devolver al proveedor</p></td>
</tr>
<tr class="odd">
<td><p>Otros</p></td>
<td><p>AI</p></td>
<td><p>Usar tal como está</p></td>
</tr>
<tr class="even">
<td><p>Otro</p></td>
<td><p>RS</p></td>
<td><p>Volver a vender</p></td>
</tr>
<tr class="odd">
<td><p>Otro</p></td>
<td><p>EX</p></td>
<td><p>Cambio</p></td>
</tr>
<tr class="even">
<td><p>Otro</p></td>
<td><p>MS</p></td>
<td><p>Varios</p></td>
</tr>
</tbody>
</table>


Para cada código de disposición definido, debe seleccionar una acción de disposición. La acción de disposición determina las implicaciones físicas y financieras de los códigos de disposición. Por ejemplo, la acción de disposición determina la manipulación física del artículo devuelto, el efecto financiero del artículo devuelto y si un artículo de sustitución se debe enviar al cliente. Puede definir un número ilimitado de códigos de disposición en función de las necesidades de la empresa, pero solo hay seis acciones predefinidas entre las que puede seleccionar. La tabla siguiente proporciona las acciones de disposición y sus definiciones.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Acción de disposición</p></th>
<th><p>Descripción</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Crédito</strong></p></td>
<td><p>Devolver el artículo al inventario y abonar al cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sólo abonar</strong></p></td>
<td><p>Abonar al cliente sin requerir o esperar que el artículo se devuelva.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Residuo</strong></p></td>
<td><p>Cancelar el artículo y abonar al cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Reemplazar y abonar</strong></p></td>
<td><p>Devolver el artículo al inventario, crear un pedido de sustitución y abonar al cliente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reemplazar y cancelar</strong></p></td>
<td><p>Cancelar el artículo, crear un pedido de sustitución abonar al cliente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Devolver al cliente</strong></p></td>
<td><p>Rechazar el artículo devuelto y devolverlo al cliente.</p></td>
</tr>
</tbody>
</table>

## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Seleccione un código de disposición para una orden de cuarentena

1. Vaya a **Gestión del inventario** \> **Periódico** \> **Administración de calidad** \> **Órdenes de cuarentena**.
1. Para una orden de cuarentena existente, seleccione una acción del campo **Código de disposición**, en la ficha **Visión general**.

## <a name="see-also"></a>Consulte también

[Orden de cuarentena (formulario)](/dynamicsax-2012//quarantine-order-form)

[Códigos de disposición (formulario)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
