---
title: Habilite el tipo de tasa de cambio de moneda de retención de impuestos global y la configuración del tipo de fecha
description: Este artículo explica cómo habilitar la configuración global del tipo de tasa de cambio de moneda de retención de impuestos y el tipo de fecha.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9db9cf41381b8b4de7dffe1c755a7df805a003ea
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573234"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>Habilite el tipo de tasa de cambio de moneda de retención de impuestos global y la configuración del tipo de fecha

[!include[banner](../includes/banner.md)]

Este artículo explica cómo habilitar la configuración global del tipo de tasa de cambio de moneda de retención de impuestos y el tipo de fecha. Ahora puede seleccionar un tipo de tasa de cambio dedicado y un tipo de fecha de cálculo de tasa de cambio para la moneda de retención de impuestos. Estas selecciones determinan el tipo de cambio de moneda extranjera que se utiliza para calcular el importe de retención de impuestos, en la moneda de retención de impuestos, en las transacciones de pago.

Esta función está disponible en las versiones 10.0.29 y posteriores de Microsoft Dynamics 365 Finance.

1. Vaya a **Impuestos** \> **Configuración** \> **Parámetros** \> **Parámetros de contabilidad general**.
2. Sobre la pestaña **Retención de impuestos**, configure la opción **Habilitar moneda de retención de impuestos avanzada** como **Sí**.
3. En el campo **Tipo de cambio**, seleccione un tipo de cambio para la moneda de retención de impuestos.
4. En el campo **Tipo de fecha de cálculo**, seleccione un tipo de fecha de cálculo que determine el tipo de cambio de moneda de retención de impuestos:

    - **Fecha de pago** – Determinar el tipo de cambio en función de la fecha de contabilización del diario de pagos.
    - **Fecha de factura** – Determinar el tipo de cambio en función de la fecha de factura del diario de factura. Si la fecha de factura del comprobante está en blanco, se utilizará la fecha de contabilización de la factura. 
    - **Fecha de documento** – Determine el tipo de cambio en función de la fecha de documento del diario de pagos. Si la fecha de documento del comprobante está en blanco, se utilizará la fecha de pago.

5. Seleccione **Guardar**.

Si la divisa de la transacción difiere de la divisa de retención de impuestos definida en el código de retención de impuestos, el importe en la divisa de retención de impuestos se calculará a partir de la divisa de la transacción, en función de la configuración anterior, y se registrará en las transacciones de retención de impuestos registradas.
