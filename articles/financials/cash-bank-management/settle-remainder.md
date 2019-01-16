---
title: "Resto de liquidación"
description: "Puede liquidar el importe restante de la actividad de liquidación aplicando dicho importe a una cuenta contable."
author: mikefalkner
manager: aolson
ms.date: 10/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 075d0f5dc0c9dc4e46dc92a2da75da9f7a207472
ms.openlocfilehash: e67bd36adc92bffea48087d0322ab14e9c066a4e
ms.contentlocale: es-es
ms.lasthandoff: 12/06/2018

---

# <a name="settle-remainder"></a>Resto de liquidación

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

Puede liquidar el importe restante de la actividad de liquidación aplicando dicho importe a una cuenta contable o a otro cliente. Puede liquidar el resto cuando liquide los importes especificados en un diario o cuando este liquidando solo transacciones abiertas.

## <a name="setting-up-defaults"></a>Configuración de las opciones predeterminadas 
Debe habilitar la función de resto de Liquidación y configurar los valores predeterminados antes de utilizar el resto de liquidación.

1)  Haga clic en **Clientes > parámetros > Liquidaciones** o en **Proveedores > parámetros > liquidaciones**
2)  Seleccione la pestaña **Liquidación** y haga clic en **Habilitar resto de liquidación**.
3)  En **Código de motivo predeterminado**, seleccione un código de motivo predeterminado. Los códigos de motivo se deben haber configurado ya en **Clientes > Configurar > Códigos de motivo de cancelación de cliente** o **Proveedores > Configurar > Códigos de motivo de cancelación de cliente**. La opción **Cuenta predeterminada del resto de liquidación** tendrá como valor predeterminado la cuenta asignada al código de motivo de cancelación.
3)  Actualice la opción **Cuenta predeterminada del resto de liquidación** según sea necesario.
4)  En el **Nombre predeterminado de diario**, seleccione un diario de pagos que se usará si desea crear un diario de pagos cuando sólo liquide transacciones abiertas. Si activa la función del resto de liquidación, debe agregar un nombre de diario predeterminado.

## <a name="settle-remainder-from-a-journal"></a>Resto de Liquidación de un diario
Si no habilita la función **Resto de Liquidación**, puede introducir una transacción en un diario y después liquidar transacciones con él como ha hecho en el pasado. Al hacer clic en el botón **Aceptar** , el saldo de apertura en la factura se reduce por el importe de efectivo. Si el efectivo no liquida completamente la factura, la factura se deja abierta con un importe pendiente de liquidación en otro momento.

Cuando se habilita la función **Resto de liquidación**, puede liquidar el importe restante en una cuenta contable. También puede transferir el resto a la cuenta de otro cliente (para las transacciones de cliente) u otro proveedor (para las transacciones de proveedor) en lugar de dejar las facturas abiertas. 

Para liquidar el resto desde la página **Liquidación**, realice los pasos siguientes:

1)  En la página **Liquidación** , marque las facturas o las transacciones que desee liquidar.
2)  Haga clic en el botón **Resto de liquidación**.
3)  Un cuadro de diálogo se mostrará, mostrando el importe que se liquida con una cuenta contable, la fecha que se usará para establecer el resto, el código de motivo predeterminado de los parámetros, y la cuenta predeterminada de los parámetros. 
4)  Seleccione un nuevo motivo para la liquidación si desea cambiar el motivo predeterminado. La cuenta de liquidación se cambiará a la cuenta asociada al código de motivo.
5)  Edite la cuenta de liquidación si desea cambiarla.
6)  Si está liquidando transacciones de cliente y desea que el resto se mueva a otro cliente, seleccione un cliente en **Resto de liquidación frente a cuenta de cliente**. Si está liquidando transacciones de proveedor y desea que el resto se mueva a otro proveedor, seleccione un proveedor en **Resto de liquidación frente a cuenta de proveedor**.
6)  Haga clic en **Resto de liquidación**.
7)  Se abrirá la página **Diario**. Una línea de diario adicional se agregará al diario con el importe del resto de liquidación como importe y a la cuenta de resto de liquidación como la cuenta de contrapartida. Si ha agregado a un cliente o un proveedor para poder mover el importe de liquidación a otro cliente o proveedor, otra línea se agregará al diario para mover el importe de liquidación a dicho cliente o proveedor.

Cuando registre el diario, la transacción abierta se liquidará totalmente. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Liquide el resto cuando esté liquidando solo transacciones abiertas.
También puede liquidar el resto cuando esté liquidando transacciones abiertas sin un diario.

Para liquidar el resto, realice los pasos siguientes:

1)  En la página **Liquidación** , marque las facturas o las transacciones que desee liquidar.
2)  Haga clic en **Resto de liquidación**.
3)  Un cuadro de diálogo se mostrará, mostrando el importe que se liquida con una cuenta contable, la fecha que se usará para establecer el resto, el código de motivo predeterminado de los parámetros, y la cuenta predeterminada de los parámetros. 
4)  Seleccione un nuevo motivo para la liquidación si desea cambiar el motivo predeterminado. La cuenta de liquidación se cambiará a la cuenta asociada al código de motivo.
5)  Edite la **cuenta de liquidación** si desea cambiarla.
6)  Si está liquidando transacciones de cliente y desea que el resto se mueva a otro cliente, seleccione un cliente en **Resto de liquidación frente a cuenta de cliente**. Si está liquidando transacciones de proveedor y desea que el resto se mueva a otro proveedor, seleccione un proveedor en **Resto de liquidación frente a cuenta de proveedor**.
7)  También puede elegir crear un diario de pagos con el resto de liquidación o solo publicarlo sin un diario. Seleccione **Sí** para **Editar en diario** para crear un diario de pagos. Podrá editar el diario de pagos que cree.
8)  Haga clic en **Resto de liquidación**. Si elige crear un diario, el botón cambiará a **Crear diario**. Haga clic en **Crear diario** en su lugar.
9)  Si ha creado un diario de pagos, la página del diario se abrirá tras hacer clic en **Resto de liquidación**. Una línea de diario se agregará al diario con el importe del resto de liquidación como importe y a la cuenta de resto de liquidación como la cuenta de contrapartida. Si ha agregado a un cliente o un proveedor para poder mover el importe de liquidación a otro cliente o proveedor, otra línea se agregará al diario para mover el importe de liquidación a dicho cliente o proveedor.

