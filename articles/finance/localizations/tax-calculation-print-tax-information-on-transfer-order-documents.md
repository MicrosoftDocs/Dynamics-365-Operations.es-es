---
title: Imprimir información fiscal en los documentos del pedido de transferencia
description: Este tema explica cómo se puede imprimir la información fiscal determinada por el servicio de cálculo de impuestos en los documentos del pedido de transferencia.
author: Kai-Cloud
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-10-12
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: d55767ef47e01edd11099f644134cfa48ea70e18
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675746"
---
# <a name="print-tax-information-on-transfer-order-documents"></a>Imprimir información fiscal en los documentos del pedido de transferencia

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Este tema explica cómo imprimir información fiscal en documentos de pedidos de transferencia. Puede imprimir el documento de factura proforma de un pedido de transferencia para transferencias de stock que se consideran suministros intracomunitarios y adquisiciones intracomunitarias según las regulaciones del impuesto al valor agregado (IVA) de la Unión Europea (UE). 

Los siguientes datos relevantes para impuestos se agregan a los documentos del pedido de transferencia:

- Los nombres y las direcciones de envío y destino para la transferencia de stock
- Los números de identificación fiscal del proveedor y del destinatario
- El precio unitario y el importe gravable de los bienes suministrados
- El código impositivo, la tasa impositiva, el importe del impuesto y las directivas impositivas

Para configurar estos datos, debe completar los siguientes pasos principales.

1. [Habilitar y configurar la característica de impuestos para pedidos de transferencia](tasks/Tax-feature-support-for-transfer-order.md).
2. [Crear y configurar varios números de registro de impuestos para una entidad jurídica](emea-multiple-vat-registration-numbers.md).
3. Configure el código de exención, la descripción, las directivas de impuestos y el código de impresión en los códigos de impuestos. Para este ejemplo, se crean y se sincronizan tres códigos de impuestos en Microsoft Dynamics 365 Finance: **NL-Exento**, **BE-RC-21** y **BE-RC+21**.

    1. En Finance, vaya a **Impuesto** \> **Configuración** \> **Impuestos** \> **Códigos de exención de impuestos**.
    2. Seleccione **Editar** e introduzca una descripción para código de exención **EC**. Por ejemplo, introduzca **Envíos EC libres de impuestos con número de registro jurídico**.
    3. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos**.
    4. Seleccione el código de impuestos **BE-RC-21** código de impuestos y luego seleccione **Directivas de impuestos**.
    5. Seleccione **Nuevo**.
    6. En el campo **Idioma**, seleccione **EN-US**. Después, en el campo **Texto**, introduzca **Documento por el que se establece la cesión de bienes en el sentido del artículo 138. 2. c) de la Directiva de la UE sobre el IVA 2006/112/EC**.
    7. Cierre la página.
    8. En la ficha desplegable **General**, en el campo **Imprimir**, seleccione **Índice de impuestos**.
    8. Seleccione el código de impuestos **NL-Exento** y, después, en la ficha desplegable **General**, en el campo **Imprimir**, seleccione **Índice de impuestos**.

    > [!NOTE] 
    > El código impositivo, la tasa impositiva y la descripción de exención de impuestos no se imprimen en los documentos del pedido de transferencia si no se mantienen una descripción del código de exención o directivas impositivas para el código impositivo.

## <a name="print-the-transfer-order---shipment-document"></a>Imprimir el pedido de transporte: documento de envío

Después de enviar una transferencia, siga estos pasos para imprimir el pedido de transferencia: documento de envío.

1. Vaya a **Administración de inventario** \> **Consultas e informes** \> **Pedidos de transferencia** \> **Envío**.
2. En la pestaña **Parámetros**, en el grupo **Imprimir**, habilite **Información fiscal**.
3. En la pestaña **Registros que incluir**, seleccione **Filtrar**, seleccione el número de pedido de transferencia y luego seleccione **Aceptar**.
4. Seleccione **Aceptar** para imprimir el pedido de transporte: documento de envío.

## <a name="print-the-transfer-order---receipt-document"></a>Imprimir el pedido de transporte: documento de recepción

Después de recibir una transferencia, siga estos pasos para imprimir el pedido de transferencia: documento de recepción.

1. Vaya a **Administración de inventario** \> **Consultas e informes** \> **Pedidos de transferencia** \> **Recepción**.
2. En la pestaña **Parámetros**, en el grupo **Imprimir**, habilite **Información fiscal**.
3. En la pestaña **Registros que incluir**, seleccione **Filtrar**, seleccione el número de pedido de transferencia y luego seleccione **Aceptar**.
4. Seleccione **Aceptar** para imprimir el pedido de transporte: documento de recepción.

## <a name="print-the-transfer-overview-document"></a>Imprima el documento de descripción general de la transferencia

Siga estos pasos para imprimir el documento de descripción general de la transferencia.

> [!NOTE]
> La información fiscal está disponible solo cuando el pedido de transferencia se ha enviado o recibido.

1. Vaya a **Administración de inventario** \> **Consultas e informes** \> **Pedidos de transferencia** \> **Visión general de la transferencia**.
2. En la pestaña **Parámetros**, en el grupo **Imprimir**, habilite **Información fiscal**.
3. En la pestaña **Registros que incluir**, seleccione **Filtrar**, seleccione el número de pedido de transferencia y luego seleccione **Aceptar**.
4. Seleccione **Aceptar** para imprimir el documento de visión general de la tranferencia.

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
