---
title: Perfiles de contabilización del proveedor
description: Los perfiles de contabilización controlan el registro de transacciones de proveedores en la contabilidad general.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae019ebec2788fc499b0f2ef27a7eb2832ceaa9d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "346534"
---
# <a name="vendor-posting-profiles"></a>Perfiles de contabilización del proveedor

[!include [banner](../includes/banner.md)]

Los perfiles de contabilización controlan el registro de transacciones de proveedores en la contabilidad general.

<a name="vendor-posting-profiles"></a>Perfiles de contabilización del proveedor
-----------------------

Los perfiles de contabilización de proveedor le permiten asignar cuentas de contabilidad general y configuración de documentos a todos los proveedores, un grupo de proveedores o un único proveedor. Esta configuración se usará al crear pedidos de compra, facturas de proveedor y pagos en efectivo. Para algunas transacciones, cuando seleccione un perfil de registro diferente de los perfiles de registro configurados para las transacciones de esta página y que tenga precedencia sobre los mismos. El perfil de contabilización predeterminado se define en la ficha desplegable Impuestos y contabilidad en la página Parámetros de proveedores. El perfil de contabilización predeterminado se incluye automáticamente en el encabezado de los documentos nuevos donde puede cambiarlo a otro perfil de contabilización si es necesario.

También puede asociar las definiciones de contabilización a los tipos de registro de transacción en la página Definiciones de contabilización de transacción. Permite configurar los perfiles de registro que controlan el registro de transacciones de proveedores en la contabilidad general en vez de los perfiles de registro.

## <a name="creating-a-posting-profile"></a>Creación de un perfil de registro
### <a name="setup"></a>**Configuración**

Especifique las cuentas contables que se utilizan en el registro de las transacciones con el perfil de contabilización seleccionado. Seleccione un código de cuenta y, siempre que sea posible, una cuenta o número de grupo para el perfil de registro seleccionado. En el proceso de registro, para buscar el perfil de contabilización más adecuado para cada transacción busque el código de cuenta, el número de cuenta, o el grupo más específico, así como la combinación de números en el siguiente orden:

| Valor del campo **Código de cuenta** | Valor del campo **Número de grupo/cuenta**        | Prioridad de búsqueda |
|------------------------------|---------------------------------------------|-----------------|
| **Tabla**                    | Cuenta específica del proveedor                     | 1               |
| **Grupo**                    | grupo de proveedores asignado al proveedor | 2               |
| **Todas**                      | En blanco                                       | 3               |

Si desea que todas las transacciones de proveedores tengan el mismo perfil de contabilización, configure solo un perfil de contabilización con valor Todas en el campo Código de cuenta. Especifique los valores siguientes para configurar su perfil de contabilización:

<table>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Perfil de contabilización</strong></td>
<td>Permite especificar un código para el perfil de contabilización. Por ejemplo, podría crear dos perfiles de registro para obtener una cuenta para saldos de proveedores en la divisa nacional y otra para saldos de proveedores en una divisa extranjera. Podría llamar a una cuenta Nacional y a otra Extranjera.</td>
</tr>
<tr class="even">
<td><strong>Descripción</strong></td>
<td>Permite especificar una descripción del perfil de registro.</td>
</tr>
<tr class="odd">
<td><strong>Código de cuenta</strong></td>
<td>Especificar si el perfil de contabilización se aplica a un proveedor específico, a un grupo de proveedores o a todos los proveedores:
<ul>
<li><strong>Tabla</strong>: el perfil de registro se aplica a un único proveedor. Seleccione la cuenta de proveedor en el campo Número de grupo/cuenta.</li>
<li><strong>Grupo</strong>: el perfil de registro se aplica a un grupo de proveedores. Seleccione el grupo de proveedores en el campo Número de grupo/cuenta.</li>
<li><strong>Todos</strong>: el perfil de registro se aplica a todos los proveedores. Deje en blanco el campo Número de grupo/cuenta.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Número de grupo/cuenta</strong></td>
<td>Si Tabla está seleccionada en el campo Código de cuenta, seleccione el número de cuenta del proveedor asociado al perfil de registro. Si la opción Grupo está seleccionada, seleccione un grupo de proveedores. Si Todos está seleccionado, deje este campo en blanco.</td>
</tr>
<tr class="odd">
<td><strong>Extracto de cuenta</strong></td>
<td>Seleccionar la cuenta contable que se usará como la cuenta de resumen para los proveedores con los que está relacionado el perfil de registro.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Billete" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Nota</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Si la opción Usar definiciones de contabilización está seleccionada en la página Parámetros de contabilidad general, se usa la definición de registro de transacción para facturas de proveedor en lugar de la cuenta de resumen.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Liquidar cuenta</strong></td>
<td>Permite seleccionar la cuenta contable de liquidez que se usa para previsiones de flujo de efectivo. Este campo solo está disponible si está habilitada la previsión de flujo de efectivo.</td>
</tr>
<tr class="odd">
<td><strong>Pagos de impuestos por adelantado</strong></td>
<td>Seleccionar la cuenta para pagos de impuestos que se reciben por adelantado.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Billete" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Nota</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>El perfil de contabilización que se usa cuando se marca el pago como un pago por adelantado está seleccionado en el campo Perfil de registro con asiento del diario de anticipos del área Impuestos y contabilidad de la página Parámetros de proveedores.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Llegada</strong></td>
<td>Seleccionar la cuenta contable en la que se registra la información sobre facturas de proveedores no aprobadas. La información se indica en el Diario de registro de facturas. Por ejemplo, un usuario escribe información muy básica acerca de las facturas de los proveedores cuando se reciben en el registro de facturas. Cuando se registra el registro de facturas, las transacciones se registran en la cuenta especificada aquí y en el campo Cuenta de contrapartida. Cuando se aprueban las facturas, la deuda se transfiere desde la cuenta de llegadas a la cuenta de resumen del proveedor.</td>
</tr>
<tr class="odd">
<td><strong>Cuenta de contrapartida</strong></td>
<td>Seleccionar la cuenta contable que se usa para la compensación de facturas de proveedores no aprobadas actualizadas a través del registro de facturas. La cuenta de contrapartida actúa como la cuenta de contrapartida para las transacciones que se registran en las cuentas de llegada. Por tanto, la cuenta contiene compras de proveedor que aún no se han aprobado.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Restricciones de tablas**

Para las transacciones que tienen seleccionado el perfil de registro, especifique si las transacciones se liquidarán automáticamente, se calculará el interés y, las cartas de cobro se emitirán. También puede seleccionar la cuenta que se usa al cerrar las transacciones que tienen el perfil de contabilización seleccionado.

Especifique los valores siguientes para configurar su perfil de contabilización:

| Campo          | Descripción                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Liquidación** | Seleccione esta opción para habilitar la liquidación automática de las transacciones que tienen este perfil de registro. Si esta opción está desactivada, debe liquidar manualmente las transacciones mediante la página Liquidar transacciones abiertas. |
| **Cancelar**     | Seleccione esta opción si desea poder cancelar transacciones que tengan este perfil de registro.                                                                                                               |
| **Cerrar**      | Seleccionar un perfil de registro al que desee cambiar cuando se cierren las transacciones con este perfil de registro. Una transacción se considera como cerrada cuando se ha liquidado completamente.                                       |





