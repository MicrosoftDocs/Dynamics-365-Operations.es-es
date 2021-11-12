---
title: Referencias a facturas originales en notas de crédito
description: Este tema explica cómo configurar e imprimir los números de factura originales en notas de crédito relacionadas.
author: ilkond
ms.date: 10/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 7147c5bea5273f385b004effe0844b5f4541a881
ms.sourcegitcommit: 2113678369f47944f8725ca656f461fa159f87f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2021
ms.locfileid: "7700364"
---
# <a name="references-to-original-invoices-in-credit-notes"></a>Referencias a facturas originales en notas de crédito

[!include [banner](../includes/banner.md)]


En algunos países y regiones, existe un requisito legal de que las notas de crédito impresas incluyan referencias a las facturas originales. Este tema explica cómo configurar e imprimir los números de factura originales en notas de crédito relacionadas.

## <a name="prerequisites"></a>Requisitos previos

- En espacio de trabajo **Administración de características**, active la característica **Diseño de facturación de crédito para informes de facturas de ventas y proyectos**. Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Los formatos imprimibles de los documentos necesarios deben configurarse en la Administración de impresión.

La funcionalidad que se describe en este tema se aplica a los siguientes documentos:

**Clientes**

- Nota de abono de texto sin formato
- Nota de abono de cliente

**Gestión y contabilidad de proyectos**

- Nota de abono de proyecto

## <a name="configure-accounts-receivable-parameters"></a>Configurar los parámetros de clientes

Siga estos pasos para configurar el parámetro que controla si las referencias a las facturas originales se imprimen en notas de crédito relacionadas.

1. Vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes**.
2. En la pestaña **Actualizaciones**, en la ficha desplegable **Factura**, establezca la opción **Aplicar el diseño de facturación de crédito en informes de facturas de proyectos y ventas** en **Sí**.

![Configurar los parámetros de clientes.](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a>Definir referencias a facturas originales

Utilice los siguientes procedimientos para definir referencias a facturas originales, según el tipo de documento.

### <a name="free-text-credit-note"></a>Nota de abono de texto sin formato

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. Cree una nota de abono nueva o seleccione una nota de abono existente.
3. Abra la factura.
4. En el panel de acciones, en la ficha **Factura**, en el grupo **Funciones**, seleccione **Factura rectificativa**.
5. Introduzca la referencia a la factura original y seleccione el motivo de la corrección.

![Definición de la referencia para una factura de servicios.](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a>Nota de abono de cliente

1. Vaya a **Clientes** \> **Pedidos** \> **Todos los pedidos de ventas**.
2. Seleccione y abra el pedido de ventas facturado que hay que corregir.
3. En el panel de acciones en la ficha **Vender**, en el grupo **Nota de abono**, seleccione **Nota de abono**.
4. Especifique el motivo de la corrección. La referencia a la factura original se establece automáticamente.

![Definición de la referencia para un pedido de ventas.](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a>Nota de abono de proyecto

1. Vaya a **Gestión y contabilidad de proyectos** \> **Facturas del proyecto** \> **Facturas del proyecto**.
2. Seleccione y abra la factura de proyecto que hay que corregir.
3. En el panel de acciones, en la ficha **Factura de proyecto**, en el grupo **Funciones**, seleccione **Seleccionar para nota de abono**.
4. Seleccione **Factura rectificativa**.
5. Especifique el motivo de la corrección. La referencia a la factura original se establece automáticamente.

![Definición de la referencia para una factura de proyecto.](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a>Imprimir notas de abono

Al imprimir notas de abono de texto libre, clientes y proyectos, incluirán la referencia a la factura original y el motivo de la corrección.

![Nota de abono impresa.](media/credit-note-FTI.jpg)

> [!NOTE]
> Asegúrese de que los formatos imprimibles de los documentos estén configurados correctamente, asumiendo que se imprimirán referencias a facturas originales.

## <a name="references-to-original-invoices-in-debit-notes"></a>Referencias a facturas originales en notas de débito

De forma predeterminada, se pueden ingresar referencias a facturas originales para notas de crédito. Por ejemplo, puede ingresar referencias cuando realiza correcciones negativas (decrecientes) de facturas originales.

Para ingresar referencias cuando realiza correcciones positivas (crecientes) de facturas originales, debe habilitar la característica **Referencias a facturas originales en notas de débito** en el espacio de trabajo **Gestión de funciones**.  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
