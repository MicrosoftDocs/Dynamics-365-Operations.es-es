---
title: Cuentas de contrapartida predeterminadas para diarios de facturas de proveedor y diarios de aprobación de facturas
description: Este tema le ayudará a decidir dónde debe asignar cuentas predeterminadas para diarios de facturas.
author: abruer
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b2ad808d5008d9a4b2d3ee975d15fa1ee13ed7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003504"
---
# <a name="default-offset-accounts-for-vendor-invoice-and-invoice-approval-journals"></a>Cuentas de contrapartida predeterminadas para diarios de facturas de proveedor y diarios de aprobación de facturas

[!include [banner](../includes/banner.md)]

Las cuentas de contrapartida predeterminadas se usan en las siguientes páginas de diario de facturas de proveedor:

-   Diario de facturas
-   Diario de aprobación de facturas

Use la siguiente tabla para decidir dónde debe asignar cuentas predeterminadas y cuentas de contrapartida para diarios de facturas.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Configure las cuentas predeterminadas aquí</th>
<th>Dónde se proporcionan cuentas predeterminadas</th>
<th>Cómo afecta esta opción al procesamiento</th>
<th>Cuándo debe usar esta opción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Grupo de proveedores</strong>: configure cuentas de contrapartida predeterminadas para grupos de proveedores en la página <strong>Configuración de cuenta predeterminada</strong>, la cual puede abrir desde la página <strong>Grupos de proveedores</strong>.</td>
<td><ul>
<li>Cuenta de proveedor</li>
<li>Entradas del diario para las cuentas de proveedores en el grupo de proveedores, si no se especifican cuentas predeterminadas para las cuentas de proveedor</li>
</ul></td>
<td>Las cuentas de contrapartida predeterminadas para grupos de proveedores se muestran como cuentas de contrapartida predeterminadas para proveedores en la página <strong>Configuración de cuenta predeterminada</strong>. Puede abrir esta página desde la página de lista <strong>Todos los proveedores</strong>.</td>
<td>Use esta opción si paga normalmente los mismos tipos de elementos de los mismos grupos de proveedores en el transcurso del tiempo.</td>
</tr>
<tr class="even">
<td><strong>Cuenta de proveedor</strong>: configure cuentas predeterminadas para cuentas de proveedor en la página <strong>Configuración de cuenta predeterminada</strong>, la cual puede abrir desde la página <strong>Proveedores</strong>.</td>
<td>Entradas del diario para la cuenta de proveedor</td>
<td>Las cuentas de contrapartida predeterminadas para cuentas de proveedor se muestran como cuentas de contrapartida predeterminadas para entradas de diario para la cuenta del proveedor.</td>
<td>Use esta opción si paga normalmente los mismos tipos de elementos de los mismos proveedores en el transcurso del tiempo.</td>
</tr>
<tr class="odd">
<td><strong>Nombres de diarios</strong>: configure cuentas de contrapartida predeterminadas para los diarios en la página <strong>Nombres de diarios</strong>. Seleccione la opción <strong>Cuenta de contrapartida fija</strong>. Tenga en cuenta que no puede especificar cuentas de contrapartida predeterminadas en nombres de diario si el tipo de diario de los nombres es <strong>Registro de facturas</strong> o <strong>Aprobación</strong>.</td>
<td><ul>
<li>Encabezado de diario que usa el nombre del diario</li>
<li>Entradas del diario en diarios que usan el nombre del diario</li>
</ul></td>
<td>Si la opción <strong>Cuenta de contrapartida fija</strong> de la página <strong>Nombres de diarios</strong> está seleccionada, la cuenta de contrapartida para el nombre de diario anula la cuenta de contrapartida predeterminada para el proveedor o el grupo de proveedores.</td>
<td>Use esta opción para configurar diarios para costes y gastos específicos que se cobran en cuentas específicas, independientemente de quién sea el proveedor o el grupo de proveedores del que forman parte.</td>
</tr>
<tr class="even">
<td><strong>Nombres de diarios</strong>: configure cuentas de contrapartida predeterminadas para los diarios en la página <strong>Nombres de diarios</strong>. Anule la opción <strong>Cuenta de contrapartida fija</strong>. Tenga en cuenta que no puede especificar cuentas de contrapartida predeterminadas en nombres de diario si el tipo de diario de los nombres es <strong>Registro de facturas</strong> o <strong>Aprobación</strong>.</td>
<td><ul>
<li>Cabecera de diario</li>
<li>Entradas del diario en diarios que usan el nombre del diario</li>
</ul></td>
<td>Estas entradas predeterminadas se usan en las páginas de encabezado de diario y la cuenta de contrapartida de la página del encabezado de diario se usa como entrada predeterminada en las páginas de asiento de diario. Las cuentas predeterminadas de la página <strong>Nombres de diarios </strong>se usan solo si no hay cuentas predeterminadas configuradas para la cuenta del proveedor.</td>
<td>Use esta opción para configurar las cuentas predeterminadas para utilizarlas si no se ha asignado una cuenta de contrapartida de proveedor predeterminada.</td>
</tr>
<tr class="odd">
<td><strong>Cabecera de diario</strong>: configure una cuenta de contrapartida predeterminada para un diario para utilizarla como entrada predeterminada en las páginas de asiento de diario. Tenga en cuenta que no puede especificar cuentas de contrapartida predeterminadas en el encabezado de diario si el tipo de diario de los nombres es <strong>Registro de facturas</strong> o <strong>Aprobación</strong>.</td>
<td>Entradas de diario en el diario</td>
<td>La cuenta de contrapartida predeterminada para un diario se utiliza como entrada predeterminada en las páginas de asiento de diario.</td>
<td>Use esta opción para ayudar a acelerar la entrada de datos si la mayoría de las entradas de un diario tiene la misma cuenta de contrapartida.</td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]