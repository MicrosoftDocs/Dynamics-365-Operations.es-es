---
title: Configuración de parámetros para registrar un pedido de empresas vinculadas
description: En este tema se explica cómo configurar parámetros para contabilizar un pedido de empresas vinculadas
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c728f2f491948ae1c8550396ba4d72f76f46fe85
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548514"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Configuración de parámetros para registrar un pedido de empresas vinculadas

[!include [banner](../../includes/banner.md)]

Cuando se registra una factura de cliente de empresas vinculadas, puede configurarla para registrar el pedido de compra de empresas vinculadas y la factura de cliente original automáticamente.

> [!NOTE]
> Antes de realizar este procedimiento, configure la gestión de impresión en su organización para seleccionar la impresora de factura correcta. Con esto, se asegurará de que la factura del pedido de ventas original se imprima en la impresora correcta.

Es necesario configurar los siguientes parámetros:

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**. Seleccionar el pedido de ventas con el que desea trabajar.
1. En el pedido de ventas, en el panel de acciones, seleccione **Vista de encabezado** y después seleccione la ficha desplegable **Configuración de empresas vinculadas** y ábrala.
1. Vaya al panel de acciones, en la ficha **Pedido de ventas**, seleccione **Editar**.
1. Vuelva a la ficha desplegable **Configuración de empresas vinculadas** y seleccione **Entrega directa** para habilitar la entrega directa en la cadena de empresas vinculadas (todos los pedidos).
1. Seleccione **Guardar** para guardar el pedido de ventas con la nueva configuración. Después seleccione **Cerrar** para cerrar el pedido de ventas.
1. Vaya a **Adquisición y abastecimiento \> Proveedores \> Todos los proveedores**. En la ficha **General**, seleccione **Empresas vinculadas**.
1. En la página **Empresas vinculadas** , seleccione el vínculo **Directivas de pedidos de compras**. En el grupo de campo **Pedido de compras de empresas vinculadas (entrega directa)**, seleccione **Contabilizar la factura automáticamente** y quite la marca de verificación del campo **Imprimir factura automáticamente**.
1. En el grupo de campo **Pedido de compras de original (entrega directa)**, seleccione los campos **Contabilizar la factura automáticamente** e **Imprimir factura automáticamente**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
