---
title: Solución de problemas de recepción y facturación de productos
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con recepción y facturación de productos.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89effb686d60dde9d11f99be51d4101897ad4ea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437278"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Solución de problemas de recepción y facturación de productos

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con recepción y facturación de productos.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>No puedo registrar más de una factura para una línea de pedido de compra que tiene artículos basados en categorías.

Es obligatorio especificar una cantidad si desea contabilizar facturas. Por lo tanto, si la cantidad total de una línea se ha facturado solo por un importe parcial, no podrá facturar el importe restante en otra factura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Recibo un error de "Referencia de objeto no establecida" durante la confirmación de un pedido de compra, o se produce una excepción "El destino de una invocación ha generado una excepción" durante la contabilización de la factura del proveedor.

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>No puedo consolidar varias recepciones de productos en un solo pedido de compra.

No puede consolidar múltiples recepciones de productos en un solo pedido de compra si las diferentes líneas de recepciones de productos tienen fechas contables distintas.

En versiones anteriores de Microsoft Dynamics 365 Supply Chain Management se permitía la consolidación en esta situación. Sin embargo, esta práctica es propensa a errores. La fecha contable en las líneas de pedido de compra que se crean no debe diferir de la fecha contable en las líneas de recepción de productos a partir de las cuales se crearon esas líneas de pedido de compra. (La fecha contable en las líneas del pedido de compra coincide con la fecha contable en el encabezado del pedido de compra). Por lo tanto, ya no se permite la consolidación de múltiples recepciones de productos en un solo pedido de compra.

La fecha contable se usa, por ejemplo, para reservas presupuestarias y reserva de gasto. Por lo tanto, debe conservarse durante la transición de la recepción del producto al pedido de compra.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>Cuando se cancelan las recepciones de productos, las transacciones se pueden registrar en una cuenta contable suspendida.

### <a name="issue-description"></a>Descripción del problema

Si se cancela la recepción de un producto, el sistema permite que las transacciones se registren en cuentas contables suspendidas, aunque las cuentas principales estén suspendidas.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. En la página **Parámetros de proveedores**, en la pestaña **General**, asegúrese de que la opción **Registrar recepción de producto en el libro mayor** está establecida en *Sí*.
1. Cree un pedido de compra y agregue una línea de pedido que tenga como cantidad *1000* para un producto.
1. Confirme el pedido de compra.
1. Registre la recepción del producto y compruebe los asientos.
1. Suspenda las cuentas principales relevantes, *200140* y *140200*.
1. Cancele la recepción de producto registrada.
1. Tenga en cuenta que las transacciones se pueden registrar en las cuentas de libro mayor suspendidas.

### <a name="issue-resolution"></a>Solución del problema

Las transacciones se pueden contabilizar en las cuentas de libro mayor suspendidas cuando se cancelan recepciones de productos, ya que este comportamiento permite contabilizaciones correctas.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>Se consume un número de asiento de recepción de producto incluso si no se genera ningún comprobante financiero durante la recepción del producto.

Si la opción **Acumular pasivo en la recepción del producto** está establecida en *No* para el grupo de modelos de artículo, no se producirán contabilizaciones en el libro mayor. Sin embargo, se registrará un evento físico con el propósito de contabilizarlo en un libro mayor auxiliar y ese evento requiere un número de asiento. Este número de asiento es el número al que se hace referencia en las transacciones de inventario.

Le recomendamos que establezca la opción **Acumular pasivo en la recepción del producto** en *Sí*, como se describe en la siguiente publicación del blog: [Contabilizar cargos varios en la recepción del producto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>La opción Registrar en la cuenta de gastos del libro mayor no está activada.

### <a name="issue-description"></a>Descripción del problema

Este problema se produce cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la pestaña **Factura** de la página **Parámetros de proveedores**.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. Vaya a **Proveedores \> Configuración \> Parámetros de proveedores**.
1. En la pestaña **Factura**, establezca la opción **Registrar en la cuenta de gastos del libro mayor** en *Sí*.
1. Vaya a **Gestión de inventarios \> Preparar \> Registro \> Registro**.
1. En la pestaña **Pedido de compra**, asegúrese de haber eliminado todas las líneas del gasto de compra del producto.
1. Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.
1. Cree un pedido de compra. En el campo **Cuenta del proveedor**, seleccione *1001 Suministros de oficina Acme*.
1. Agregue una línea de pedido con la siguiente configuración:

    - **Número de artículo:** *Proyector láser D0011*
    - **Sitio**: *1*
    - **Almacén**: *11*
    - **Cantidad:** *4*

1. En el panel de acciones, en la ficha **Compra**, en el grupo **Acción**, seleccione **Confirmar**.
1. En el panel Acciones, en la pestaña **Recepción** del grupo **Generar**, seleccione **Recepción de producto**.
1. En el cuadro de diálogo **Registro de recepción de productos**, en el campo **Recepción de producto**, escriba un número arbitrario y seleccione **Aceptar**.
1. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
1. En el campo **Número**, escriba un número arbitrario como número de factura.
1. Actualice el estado de conciliación y registre.
1. Observe que ahora aparece el siguiente error al generar una factura de un pedido de compra: "Número de cuenta para el tipo de transacción: No existe el gasto de compra del producto".

### <a name="issue-resolution"></a>Solución del problema

Depende de la configuración de parámetros para facturas y grupos de facturas. Para obtener más información, vea la siguiente publicación de blog: [Contabilización del cargo de compra y variación de existencias](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]