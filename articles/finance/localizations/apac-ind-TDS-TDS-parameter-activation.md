---
title: Configurar los parámetros de TDS
description: Este tema explica cómo configurar parámetros para activar la característica de impuestos deducidos en el origen (TDS) en transacciones específicas. Este es un paso necesario para utilizar la característica de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b74a1ab6d0f17367fc16f795e1b28ff5d0c5508e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358251"
---
# <a name="set-the-tds-parameters"></a>Configurar los parámetros de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar parámetros para activar la característica de impuestos deducidos en el origen (TDS) en transacciones específicas. Este es un paso necesario para utilizar la característica de impuestos deducidos en el origen (TDS).

1. Vaya a **Contabilidad general \> Configuración de contabilidad \> Parámetros de Contabilidad general**.
2. En la pestaña **Impuestos directos**, en la sección **Impuesto deducido en el origen**, establezca la opción **Activar TDS** a **Sí** para activar la característica de TDS y las páginas y campos que se utilizan para ello.
3. Establezca la opción **Factura** a **Sí** para activar los campos que se utilizan para calcular y deducir el TDS a nivel de factura.
4. Establezca la opción **Pago** a **Sí** para activar los campos que se utilizan para calcular y deducir el TDS a nivel de pagos.

    [![Pestaña de impuestos directos.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. En la pestaña **Secuencias numéricas**, busque la fila donde el campo **Referencia** está configurado en **Pago de retención de impuestos**. En el campo **Código de secuencia numérica** para la fila, seleccione el código de secuencia numérica. El código de secuencia numérica se utiliza para generar números de asiento para el proceso de liquidación periódica de TDS.

    > [!NOTE]
    > Para ejecutar el proceso de liquidación periódica de TDS, vaya a **Impuesto \> Declaraciones \> Retención de impuestos \> Pago de retención de impuestos**.

    [![Ficha Secuencias numéricas.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Cierre la página.
