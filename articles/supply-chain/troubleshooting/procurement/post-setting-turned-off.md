---
title: La opción Registrar en la cuenta de gastos del libro mayor no está activada
description: Este problema se produce cuando se factura un pedido de compra, si la opción "Registrar en la cuenta de gastos del libro mayor" está habilitada en la pestaña "Factura" de la página "Parámetros de proveedores".
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477544"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>La opción Registrar en la cuenta de gastos del libro mayor no está activada

## <a name="symptoms"></a>Síntomas

Este problema se produce cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la pestaña **Factura** de la página **Parámetros de proveedores**.

## <a name="reproduce-the-issue"></a>Reproducir el problema

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

## <a name="resolution"></a>Resolución

Depende de la configuración de parámetros para facturas y grupos de facturas. Para obtener más información, vea la siguiente publicación de blog: [Contabilización del cargo de compra y variación de existencias](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
