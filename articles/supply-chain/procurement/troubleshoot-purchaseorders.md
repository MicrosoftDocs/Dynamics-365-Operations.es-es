---
title: Solución de problemas de pedidos de compra
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de compra.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 5959b098082ac1a0c8ea768795fa63b13950a9c7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242526"
---
# <a name="troubleshoot-purchase-orders"></a>Solución de problemas de pedidos de compra

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de compra.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>Una acción solo se puede completar después de que el número de línea esté completamente distribuido.

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>Cuando los pedidos de compra se importan a través de la administración de datos, los números de línea del pedido de compra no siguen el incremento definido en los parámetros del sistema.

### <a name="issue-description"></a>Descripción del problema

De forma predeterminada, los números de línea generados automáticamente para las líneas de pedido de compra que se importan a través de la entidad de datos *Líneas de pedido de compra V2* no usan el incremento de número de línea del sistema que se especifica en los parámetros del sistema. Si crea manualmente un pedido de compra y agrega líneas a través de la interfaz de usuario, los números de línea se incrementan correctamente. Sin embargo, si usa el marco de administración de datos (DMF), no se incrementan correctamente.

Este problema se produce porque, cuando importa líneas a través de DMF, si los números de línea aún no están asignados en la entidad importada, el sistema usa el método de DMF para asignarlos. Ese método siempre incrementa los números de línea en una unidad.

### <a name="issue-workaround"></a>Solución del problema

Asegúrese de que los números de línea deseados ya estén incluidos en los campos de número de línea de la entidad de datos cuando importe las líneas del pedido de compra. En este caso, DMF no sobrescribirá los números de línea.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>Un grupo de impuestos predeterminado y un descuento por pronto pago predeterminado no se rellenan desde la cuenta de factura.

Si utiliza una cuenta de factura que difiere de la cuenta de cliente, un grupo de impuestos predeterminado y un descuento por pronto pago predeterminado no se rellenarán desde la cuenta de factura cuando se cree un pedido de compra.

Este comportamiento se debe al diseño. Los valores predeterminados para el grupo de impuestos, descuentos por pronto pago y otra información de precios se basan en la cuenta del cliente, no en la cuenta de la factura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Recibo un error de "Referencia de objeto no establecida" durante la confirmación de un pedido de compra, o se produce una excepción "El destino de una invocación ha generado una excepción" durante la contabilización de la factura del proveedor.

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Una o más distribuciones contables están distribuidas en exceso o en defecto.

### <a name="issue-description"></a>Descripción del problema

Aparece el siguiente error: "Una o más distribuciones contables están distribuidas en exceso o en defecto".

### <a name="issue-resolution"></a>Solución del problema

Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.

Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**. Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>¿Puedo mostrar solo los pedidos de compra que he creado?

Esta funcionalidad no está disponible actualmente.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>¿Puedo reservar inventario y crear transacciones con el inventario registrado en un pedido de compra?

### <a name="issue-description"></a>Descripción del problema

Puede reservar el inventario incluso cuando los elementos están en un *Registrado* en un pedido de compra. En otras palabras, puede crear transacciones con el inventario registrado.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. Cree un pedido de compra.
2. Registre la línea de pedido de compra.
3. Tenga en cuenta que puede generar reservas o transacciones con el inventario registrado.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. La expectativa es que los artículos registrados hayan llegado físicamente al almacén o al inventario y, por lo tanto, estén disponibles para reserva.

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Los pedidos de compra no reflejan la configuración de idioma de la entidad jurídica.

### <a name="issue-description"></a>Descripción del problema

El nombre del producto en un pedido de compra se muestra en el idioma del sistema, no en el idioma establecido para la entidad jurídica donde se creó el pedido de compra.

### <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. Establezca el idioma del sistema en *EN-US* (inglés americano).
1. Asegúrese de que haya un producto donde se mantienen los idiomas *EN-US* y *DE* (alemán) para las traducciones del nombre del producto.
1. Cambie el idioma de una entidad jurídica a *DE*.
1. En la entidad jurídica donde *DE* está configurado como idioma, cree un pedido de compra que incluya el producto.
1. Tenga en cuenta que el nombre del producto se sigue mostrando en inglés de EE.UU. (el idioma del sistema).

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. En los pedidos de compra, el producto siempre se muestra en el idioma del sistema. El idioma del pedido de compra se utiliza cuando se crea un diario de confirmación.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>La lista de proveedores aprobados por entidad de producto no permite cambiar la fecha de vigencia.

### <a name="issue-description"></a>Descripción del problema

Un producto tiene un proveedor aprobado que tiene, por ejemplo, una fecha de vigencia del 11 de enero de 2018 (*11/01/2018*) y *Nunca* como fecha de vencimiento. Si intenta cambiar la fecha de vigencia al 10 de enero de 2018 (*10/01/2018*) o al 12 de enero de 2018 (*12/01/2018*), aparecerá el siguiente error:

> No se puede crear un registro en la lista de proveedores aprobados (PdsApproveVendorList). El valor de 'Vencimiento' debe ser mayor o igual que el valor de 'Vigencia'.

### <a name="issue-resolution"></a>Solución del problema

Solo puede ampliar el período para el que está aprobado el proveedor. Se aplican las siguientes reglas:

- Para cambiar la fecha de vigencia de modo que sea anterior a cualquiera de los registros (períodos) existentes para el proveedor del artículo, la fecha de vencimiento del nuevo período debe ser anterior a todas las fechas de vencimiento de los registros existentes.
- Para cambiar la fecha de vencimiento de forma que sea posterior a cualquiera de los períodos existentes, la fecha de vigencia debe ser posterior a la última fecha de vencimiento en cualquier registro existente.
- Para reducir el período general para el que está aprobado el proveedor, debe eliminar o modificar los registros existentes. Como alterna, puede utilizar el modificador **truncate** durante la importación. Este modificador elimina todos los registros existentes en la tabla de proveedores aprobados por artículo.

Para el escenario de ejemplo que se describe en la descripción del problema, donde un registro tiene como fecha de vigencia *11/01/2018* y *Nunca* como fecha de vencimiento, puede importar un nuevo registro que tenga como fecha de vigencia *10/01/2018* y *Nunca* como fecha de vencimiento. Sin embargo, no puede reducir el período para que la fecha de vigencia se actualice a *12/01/2018* a través de la administración de datos. Debe realizar este cambio a través de la interfaz de usuario.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-name-isnt-synced"></a>Después de cambiar la dirección de entrega en el encabezado de un pedido de compra, no se sincroniza el nombre de entrega.

### <a name="issue-description"></a>Descripción del problema

La dirección en el encabezado de un pedido de compra se actualiza a una dirección que no es una dirección de entrega. Aunque la dirección se actualiza en el pedido de compra, el nombre de entrega no se actualiza según la dirección actualizada.

### <a name="issue-resolution"></a>Solución del problema

Este comportamiento se debe al diseño. La dirección seleccionada debe clasificarse como dirección de entrega. De lo contrario, el nombre de entrega no se actualiza en función de la dirección seleccionada.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>¿Puedo encontrar al usuario que canceló un pedido de compra?

Esta información solo se sigue si el pedido de compra está sujeto a la administración de cambios. Si usa la administración de cambios, puede ver quién envió el cambio (la cancelación) y quién lo aprobó.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]