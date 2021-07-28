---
title: Imprimir el informe Pago de impuestos por código
description: Este tema proporciona información sobre la configuración y las acciones necesarias para imprimir el pago de impuestos por informe de código en la divisa del código contable o fiscal.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: dad1cad6dcda1c7768f9be8bd7bd4426be7fbcbb
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358866"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Imprimir el informe Pago de impuestos por código 

[!include [banner](../includes/banner.md)]

Para imprimir el informe **Pago de impuestos por código**, vaya a **Impuestos** \> **Consultas e informes** \> **Informes de impuestos** \> **Pago de impuestos por código**. De forma predeterminada, los importes de los informes se generan en la divisa contable de la entidad jurídica para todos los códigos de informes que se configuran en la página **Códigos de informe de impuestos**.

También puede generar este informe para que muestre los importes de pago de impuestos en las divisas de los códigos del impuesto para todos los códigos de informe asignados a los códigos del impuesto en la página **Códigos de impuestos** página.

## <a name="turn-on-the-feature"></a>Activar la característica

En el espacio de trabajo **Gestión de características**, active la siguiente: **Generar el pago de impuestos por informe de código en la divisa del código de los impuestos**.

## <a name="run-the-report"></a>Ejecute el informe

1. Vaya a **Impuestos** \> **Consultas e informes** \> **Informes de impuestos** \> **Pago de impuestos por código**.
2. En el campo **Informe de divisa**, seleccione uno de los siguientes valores:

    - **Divisa de contabilidad** - Imprime los importes del informe en la divisa de contabilidad.
    - **Divisa del código de impuestos** - Imprime los importes del informe en las divisas de los códigos de impuestos.

    ![Cuadro de diálogo pago de impuestos por código.](media/Sales-tax-payment-by-code.png)

La ilustración siguiente muestra un ejemplo del informe que se genera. El informe muestra que el código de informe **101** tiene la divisa **EUR** si el campo **Divisa de impuestos** se establece en **EUR** para el código de impuestos al que está asignado el código de informe.

![Ejemplo de pago de impuestos por código de informe.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]