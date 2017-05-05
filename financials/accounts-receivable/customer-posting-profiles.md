---
title: "Perfiles de contabilización del cliente"
description: "Los perfiles de contabilización del cliente controlan el registro de transacciones del cliente en la contabilidad general."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 1f1a13c2716dad153103e77e4e2af34e150cdd7e
ms.lasthandoff: 03/31/2017


---

# <a name="customer-posting-profiles"></a>Perfiles de contabilización del cliente

[!include[banner](../includes/banner.md)]


Los perfiles de contabilización del cliente controlan el registro de transacciones del cliente en la contabilidad general.

<a name="customer-posting-profiles"></a>Perfiles de contabilización del cliente
-------------------------

Los perfiles de registro de cliente le permiten asignar cuentas de contabilidad general y configuración de documentos a todos los clientes, un grupo de clientes o un único cliente. Esta configuración se usará al crear pedidos de venta, facturas de servicios, pagos en efectivo, cartas de cobro y notas de interés. Para algunas transacciones, cuando seleccione un perfil de registro diferente de los perfiles de registro configurados para las transacciones de esta página y que tenga precedencia sobre los mismos. 

El perfil de contabilización predeterminado se define en la ficha desplegable Impuestos y contabilidad en la página Parámetros de clientes. El perfil de contabilización predeterminado se incluye automáticamente en el encabezado de los documentos nuevos donde puede cambiarlo a otro perfil de contabilización si es necesario.

También puede asociar las definiciones de contabilización a los tipos de registro de transacción en la página Definiciones de contabilización de transacción. Permite configurar los perfiles de registro que controlan el registro de transacciones de clientes en la contabilidad general en vez de los perfiles de registro.

## <a name="creating-a-posting-profile"></a>Creación de un perfil de registro
Especifique las cuentas contables que se utilizan en el registro de las transacciones con el perfil de contabilización seleccionado. Seleccione un código de cuenta y, siempre que sea posible, una cuenta o número de grupo para el perfil de registro seleccionado. En el proceso de registro, para buscar el perfil de contabilización más adecuado para cada transacción busque el código de cuenta, el número de cuenta, o el grupo más específico, así como la combinación de números en el siguiente orden:

| Valor del campo **Código de cuenta** | Valor del campo **Número de grupo/cuenta**            | Prioridad de búsqueda |
|------------------------------|-------------------------------------------------|-----------------|
| **Tabla**                    | Cuenta de cliente específica                       | 1               |
| **Grupo**                    | Grupo de clientes asignado al cliente | 2               |
| **Todas**                      | En blanco                                           | 3               |

Si desea que todas las transacciones de clientes tengan el mismo perfil de contabilización, configure solo un perfil de contabilización con valor Todas en el campo Código de cuenta. Especifique los valores siguientes para configurar su perfil de contabilización:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Perfil de contabilización</strong></td>
<td>Permite especificar un código para el perfil de contabilización. Por ejemplo, podría crear dos perfiles de registro para obtener una cuenta para saldos de clientes en la divisa nacional y otra para saldos de clientes en una divisa extranjera. Podría llamar a una cuenta Nacional y a otra Extranjera.</td>
</tr>
<tr class="even">
<td><strong>Descripción</strong></td>
<td>Permite especificar una descripción del perfil de registro. Esto solo se usa para identificar mejor el perfil de contabilización cuando lo ve en esta página.</td>
</tr>
<tr class="odd">
<td><strong>Código de cuenta</strong></td>
<td>Permite especificar si el perfil de registro se aplica a un solo cliente, a un grupo de clientes o a todos los clientes:
<ul>
<li><strong>Tabla</strong>: el perfil de registro se aplica a un único cliente. Seleccione la cuenta de cliente en el campo Número de grupo/cuenta.</li>
<li><strong>Grupo</strong>: el perfil de registro se aplica a un grupo de clientes. Seleccione el grupo de clientes en el campo Número de grupo/cuenta.</li>
<li><strong>Todos</strong>: el perfil de registro se aplica a todos los clientes. Deje en blanco el campo Número de grupo/cuenta.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Número de grupo/cuenta</strong></td>
<td>Si Tabla está seleccionada en el campo Código de cuenta, seleccione el número de cuenta del cliente asociado al perfil de registro. Si ha seleccionado Grupo, seleccione el grupo de clientes. Si Todos está seleccionado, deje este campo en blanco.</td>
</tr>
<tr class="odd">
<td><strong>Extracto de cuenta</strong></td>
<td>Seleccione la cuenta contable que se utilizará como la cuenta de resumen de cliente para los clientes se asocian al perfil de registro.</td>
</tr>
<tr class="even">
<td><strong>Liquidar cuenta</strong></td>
<td>Permite seleccionar la cuenta contable de liquidez que se usa para previsiones de flujo de efectivo. Este campo solo aparecerá si se habilitan las previsiones de flujo de efectivo.</td>
</tr>
<tr class="odd">
<td><strong>Pagos de impuestos por adelantado</strong></td>
<td>Permite seleccionar la cuenta para los impuestos de pagos que se reciben por adelantado.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Nota</strong>:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Use la página Parámetros de clientes para especificar el perfil de registro que se usará cuando un pago se marque como anticipo.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Deudas por efectos descontados</strong></td>
<td>Permite seleccionar la cuenta contable para las deudas por efectos descontados.</td>
</tr>
<tr class="odd">
<td><strong>Secuencia de la carta de cobro</strong></td>
<td>Permite seleccionar el identificador de secuencia de la carta de cobro para los clientes a los que se asigna el perfil de registro.</td>
</tr>
<tr class="even">
<td><strong>Código del interés</strong></td>
<td>Permite seleccionar el código de interés para el cálculo del interés para los clientes a los que se asigna el perfil de contabilización.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Restricciones de tablas**

Para las transacciones que tienen seleccionado el perfil de registro, especifique si las transacciones se liquidarán automáticamente, se calculará el interés y, las cartas de cobro se emitirán. También puede seleccionar la cuenta que se usa al cerrar las transacciones que tienen el perfil de contabilización seleccionado.

Especifique los valores siguientes para configurar su perfil de contabilización:

| Campo                 | Descripción                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Liquidación**        | Seleccione esta opción para habilitar la liquidación automática de las transacciones que tienen este perfil de registro. Si esta opción está desactivada, debe liquidar manualmente las transacciones mediante la página Liquidar transacciones abiertas o la página Introducir pagos de cliente. |
| **Aficiones**          | Active esta opción si el interés se calcula en los saldos pendientes para las cuentas de los clientes que usan este perfil. Si se desactiva esta opción, no se calculará el interés para dichos clientes.                                           |
| **Carta de cobro** | Active esta opción si las cartas de cobro se deben generar para cuentas de clientes que usan este perfil. Si se desactiva esta opción, las cartas de cobro no se generarán para estos clientes.                                                 |
| **Cerrar**             | Seleccionar un perfil de registro al que desee cambiar cuando se cierren las transacciones con este perfil de registro. Una transacción se considera como cerrada cuando se ha liquidado completamente.                                                                           |






