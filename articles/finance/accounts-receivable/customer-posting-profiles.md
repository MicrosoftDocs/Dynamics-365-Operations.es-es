---
title: Perfiles de contabilización del cliente
description: Este tema describe perfiles de contabilización de cliente, que controlan la contabilidad de transacciones de clientes en la contabilidad general.
author: JodiChristiansen
ms.date: 12/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 91432a401a8f8a499e9f5e2bbe7157408faac822
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952580"
---
# <a name="customer-posting-profiles"></a>Perfiles de contabilización del cliente

[!include [banner](../includes/banner.md)]

Este tema describe perfiles de contabilización de cliente, que controlan la contabilidad de transacciones de clientes en la contabilidad general.

## <a name="customer-posting-profiles"></a>Perfiles de contabilización del cliente

Los perfiles de registro de cliente le permiten asignar cuentas de contabilidad general y configuración de documentos a todos los clientes, un grupo de clientes o un único cliente. Esta configuración se usará al crear facturas de pedidos de venta, facturas de servicios, facturas de proyecto, diarios de pago, cartas de cobro y notas de interés. 

El perfil de contabilización predeterminado se define en la pestaña **Impuestos y contabilidad** en la página **Parámetros de clientes**. Luego se incluye automáticamente en el encabezado de los documentos nuevos. Puede cambiarlo allí si se requiere un perfil de publicación diferente. 

Las organizaciones que aceptan prepagos de los clientes a menudo configuran un segundo perfil de publicación para prepagos y lo vinculan en los parámetros como el perfil de publicación predeterminado para prepagos. Para obtener más información, consulte [Prepagos de cliente](customer-prepayments.md).

También puede asociar las definiciones de contabilización a los tipos de registro de transacción en la página **Definiciones de contabilización de transacción**. Permite configurar los perfiles de registro que controlan el registro de transacciones de clientes en la contabilidad general en vez de los perfiles de registro. Para obtener más información, consulte [Definiciones de contabilización](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Creación de un perfil de registro
Especifique las cuentas contables que se utilizan en el registro de las transacciones con el perfil de contabilización seleccionado. Seleccione un código de cuenta y, siempre que sea posible, una cuenta o número de grupo para el perfil de registro seleccionado. En el proceso de registro, para buscar el perfil de contabilización más adecuado para cada transacción busque el código de cuenta, el número de cuenta, o el grupo más específico, así como la combinación de números en el siguiente orden:

| Valor del campo Código de cuenta | Valor del campo Número de grupo/cuenta                | Prioridad de búsqueda |
|--------------------------|-------------------------------------------------|-----------------|
| Tabla                    | Cuenta de cliente específica                       | 1               |
| Grupo                    | Grupo de clientes asignado al cliente | 2               |
| Todo                      | En blanco                                           | 3               |

Si desea que todas las transacciones de cliente tengan el mismo perfil de contabilización, configure solo un perfil de contabilización con valor **Todas** en el campo **Código de cuenta**. Especifique los valores siguientes para configurar su perfil de contabilización.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>Perfil de registro</td>
<td>Permite especificar un código para el perfil de contabilización. Por ejemplo, podría crear dos perfiles de registro para obtener una cuenta para saldos de clientes en la divisa nacional y otra para saldos de clientes en una divisa extranjera. Podría llamar a una cuenta Nacional y a otra Extranjera.</td>
</tr>
<tr>
<td>Description</td>
<td>Permite especificar una descripción del perfil de registro. Esto solo se usa para identificar mejor el perfil de contabilización cuando lo ve en esta página.</td>
</tr>
<tr>
<td>Código de cuenta</td>
<td>Permite especificar si el perfil de registro se aplica a un solo cliente, a un grupo de clientes o a todos los clientes:
<ul>
<li><b>Tabla</b>: el perfil de registro se aplica a un único cliente. Seleccione la cuenta de cliente en el campo <b>Número de grupo/cuenta</b>.</li>
<li><b>Grupo</b>: el perfil de registro se aplica a un grupo de clientes. Seleccione el grupo de clientes en el campo <b>Número de grupo/cuenta</b>.</li>
<li><b>Todos</b>: el perfil de registro se aplica a todos los clientes. Deje en blanco el campo <b>Número de grupo/cuenta</b>.</li>
</ul>
</td>
</tr>
<tr>
<td>Número de grupo/cuenta</td>
<td>Si <b>Tabla</b> está seleccionada en el campo <b>Código de cuenta</b>, seleccione el número de cuenta del cliente asociado al perfil de registro. Si ha seleccionado <b>Grupo</b>, seleccione el grupo de clientes. Si <b>Todos</b> está seleccionado, deje este campo en blanco.</td>
</tr>
<tr>
<td>Extracto de cuenta</td>
<td>Seleccione la cuenta principal que se utilizará como la cuenta de resumen de cliente para los clientes se asocian al perfil de registro. Esta cuenta es la cuenta para el tipo de publicación <b>Saldo del cliente</b>.</td>
</tr>
<tr>
<td>Cuenta de liquidez para pagos</td>
<td>Permite seleccionar la cuenta contable de liquidez que se usa para previsiones de flujo de efectivo. Este campo solo aparecerá si se habilitan las previsiones de flujo de efectivo.</td>
</tr>
<tr>
<td>Pagos de impuestos por adelantado</td>
<td><p>Permite seleccionar la cuenta para los impuestos de pagos que se reciben por adelantado.</p>
<p><strong>Nota:</strong> Use la página <b>Parámetros de clientes</b> para especificar el perfil de registro que se usará cuando un pago se marque como anticipo.</p>
</td>
</tr>
<tr>
<td>Deudas por efectos descontados</td>
<td>Permite seleccionar la cuenta contable para las deudas por efectos descontados.</td>
</tr>
<tr>
<td>Secuencia de la carta de cobro</td>
<td>Permite seleccionar el identificador de secuencia de la carta de cobro para los clientes a los que se asigna el perfil de registro.</td>
</tr>
<tr>
<td>Código del interés</td>
<td>Permite seleccionar el código de interés para el cálculo del interés para los clientes a los que se asigna el perfil de contabilización.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>Ejemplos de contabilización

La siguiente tabla muestra ejemplos de los tipos de contabilización predeterminados con ejemplos de cuentas principales y descripciones. La columna **Débito/Crédito** indica si la transacción suele ser Débito o Crédito o, en algunos casos, puede contabilizarse. La columna **Cuenta de compensación** indica que el tipo de contabilización es una cuenta de compensación. Esto significa que el monto registrado en esta cuenta se revierte automáticamente cuando se registra una transacción posterior. 

| Tipo de registro | Ejemplo de cuenta principal | Ejemplo de nombre de cuenta principal | Tipo de cuenta | Debe/Haber | Cuenta de compensación | Description |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Saldo del cliente | 130100 | Operación de clientes | Activo | Ambas | No | Especifique la cuenta en el campo **Resumen de cuenta**.|
| Ninguna | 110110 | Cuenta bancaria | Activo | Ambas | No | Especifique la cuenta principal en el **Cuenta de liquidez para pagos**. Esta cuenta no se utiliza para publicar. Se utiliza únicamente para la previsión de flujo de caja. |
| Pagos de impuestos por adelantado | 202900 | Pago de impuestos | Pasivo | Ambas | Sí | Permite seleccionar la cuenta para los impuestos de pagos que se reciben por adelantado. |
| Deudas por efectos descontados | 250600 | Ingresos diferidos y descuentos | Pasivo | Ambas | Sí | Permite seleccionar la cuenta contable para las deudas por descuentos.|     

### <a name="table-restrictions"></a>Restricciones de tablas

Para las transacciones que tienen seleccionado el perfil de registro, especifique si las transacciones se liquidarán automáticamente, se calculará el interés y, las cartas de cobro se emitirán. También puede seleccionar la cuenta que se usa al cerrar las transacciones que tienen el perfil de contabilización seleccionado.

Especifique los valores siguientes para configurar su perfil de contabilización:

| Campo                 | Descripción                                           |
|-----------------------|-------------------------------------------------------|
| Liquidación        | Seleccione esta opción para habilitar la liquidación automática de las transacciones que tienen este perfil de registro. Si esta opción está desactivada, debe liquidar manualmente las transacciones mediante la página **Liquidar transacciones abiertas** o la página **Introducir pagos de cliente**. |
| Interés          | Active esta opción si el interés se calcula en los saldos pendientes para las cuentas de los clientes que usan este perfil. Si se desactiva esta opción, no se calculará el interés para dichos clientes.                                           |
| Carta de cobro | Active esta opción si las cartas de cobro se deben generar para cuentas de clientes que usan este perfil. Si se desactiva esta opción, las cartas de cobro no se generarán para estos clientes.                                                 |
| Cerrar             | Seleccionar un perfil de registro al que desee cambiar cuando se cierren las transacciones con este perfil de registro. Una transacción se considera como cerrada cuando se ha liquidado completamente.             |



Para obtener más información, consulte [Resumen de pagos del cliente](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
