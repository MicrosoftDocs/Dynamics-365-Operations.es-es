---
title: Facturas originales de referencia en notas de abono (facturas de proveedores)
description: Este artículo describe cómo crear una referencia a una factura original cuando crea una nota de crédito.
author: AdamTrukawka
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.search.form: ''
ms.openlocfilehash: 39cf4eb7eef1a83abeb7bd44fa7b2abefee0806e
ms.sourcegitcommit: 8eb0cafe5ad20be2c4fff684e88d7d3f2249f820
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409674"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Facturas originales de referencia en notas de abono (facturas de proveedores)

[!include [banner](../includes/banner.md)]

En algunos países y regiones, existe un requisito legal de que las notas de crédito impresas o los procesos de informes incluyan referencias a las facturas originales. Este artículo describe cómo crear una referencia a una factura original cuando crea una nota de crédito.

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

La definición de una referencia a una factura original incluye los siguientes pasos de alto nivel:
1. Crear y registrar una factura de proveedor.
2. Crear una nota de abono de proveedor.
3. Utilice la función Factura rectificativa para vincular la factura con una nota de abono.
4. Registrar la nota de abono.

Utilice los siguientes procedimientos para definir una referencia a una factura original, según los tipos de documentos empresariales especificados.

### <a name="vendor-credit-note-purchase-order"></a>Nota de crédito de proveedor (pedido de compra)

1. Vaya a **Proveedores** > **Pedidos de compra** > **Todos los pedidos de compra**.
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
