---
title: Facturas originales de referencia en notas de abono (facturas de proveedores)
description: Este artículo describe cómo crear una referencia a una factura original cuando crea una nota de crédito.
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e05dddf056d86513d86ea925349f60ca25f191ca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901500"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Facturas originales de referencia en notas de abono (facturas de proveedores)

[!include [banner](../includes/banner.md)]

Este artículo describe cómo crear una referencia a una factura original cuando crea una nota de crédito.

## <a name="prerequisites"></a>Requisitos previos

En el espacio de trabajo **Gestión de funciones**, habilite la característica **Habilitar la facturación de crédito para facturas de proveedores**. Para más información, consulte [Resumen de administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La funcionalidad que se describe en este artículo se aplica a los siguientes documentos empresariales.

**Proveedores:**

- Pedido de compra
- Diario de facturas
- Registro de facturas

**Contabilidad general:**

- Diario general

## <a name="define-a-reference-to-an-original-invoice"></a>Definir una referencia para una factura original

Utilice los siguientes procedimientos para definir una referencia a una factura original, según los tipos de documentos empresariales especificados.

### <a name="vendor-credit-note-purchase-order"></a>Nota de crédito de proveedor (pedido de compra)

1. Vaya a **Proveedores** \> **Pedidos de compra** \> **Todos los pedidos de compra**.
2. Cree un pedido de compra nuevo o utilice uno existente para crear una nota de crédito.
3. En el panel de acciones, en la ficha **Factura**, en el grupo **Introducir**, seleccione **Factura rectificativa**.
4. Introduzca la referencia a la factura original y seleccione el motivo de la corrección.

### <a name="vendor-credit-note-ledger-journals"></a>Nota de abono del proveedor (diarios contables)

1. Siga uno de estos pasos:

    - Vaya a **Proveedores** \> **Diario de facturas**.
    - Vaya a **Proveedores** \> **Registro de facturas**.
    - Vaya a **Contabilidad general** \> **Movimientos de diario** \> **Diarios generales**.

2. Cree un nuevo diario y nuevas líneas de diario.
3. En el panel de acciones, seleccione **Funciones** \> **Facturación de crédito**.
4. Introduzca la referencia a la factura original y seleccione el motivo de la corrección.

> [!NOTE]
> El comando **Facturación de crédito** es visible en un comprobante de diario general si el campo **Tipo de cuenta** está configurado en **Proveedor**.
