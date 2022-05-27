---
title: El impuesto no está calculado o el importe del impuesto es cero
description: Este tema proporciona información para la resolución de problemas que puede resultar útil cuando el importe del impuesto es 0 (cero) o no se calcula el impuesto.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7237980f8d330a7b3f5c966d5bd3fff0eda8b21a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685867"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>El impuesto no está calculado o el importe del impuesto es cero

[!include [banner](../includes/banner.md)]

Una transacción puede tener un importe de línea que no sea 0 (cero), pero puede ser que el impuesto no se ha calculado o que el importe del impuesto calculado es 0. Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Verifique que los códigos de impuestos estén seleccionados correctamente por la transacción

Si la transacción no selecciona los códigos de impuestos correctos, o si no selecciona ningún código de impuestos, los impuestos no se calcularán sobre ella. Siga estos pasos para verificar que los códigos de impuestos estén seleccionados correctamente por la transacción. 

1. En la línea de transacción, en la ficha desplegable **Detalles de línea**, en la pestaña **Configuración**, en la sección **Impuesto**, verifique que los grupos de impuestos correctos estén seleccionados en los campos **Grupo de impuestos de artículos** y **Grupo de impuestos**. Si no están seleccionados los grupos de impuestos correctos, selecciónelos.

    [![Campos Grupos de impuestos de artículos y Grupo de impuestos.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos**.
3. Seleccione el grupo de impuestos apropiado y luego, en la ficha desplegable **Configuración**, anote el código de impuestos en el campo **Código de impuesto**.

    [![Página de grupos de impuestos.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos de artículos**.
5. Seleccione el grupo de impuestos del artículo apropiado y, a continuación, en la ficha desplegable **Configuración**, verifique que el código de impuestos del campo **Código de impuesto** coincide con el código de impuestos del grupo de impuestos.

    [![Página de grupos de impuestos de artículos.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Si los códigos de impuestos no coinciden, actualice el código de impuestos para uno de los grupos.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Verificar que los códigos de impuestos seleccionados no sean de tipo exento y que tengan el valor de tipo impositivo correcto

Si los códigos de impuestos son de tipo exento o si el tipo impositivo es 0 (cero), el resultado del cálculo de impuestos será 0. Siga estos pasos para determinar si los códigos de impuestos seleccionados están exentos y para verificar que se les aplique el tipo impositivo correcto.

1. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos**.
2. Seleccione el grupo de impuestos apropiado y luego, en la ficha desplegable **Configuración**, verifique que está desactivada la casilla **Exento**. Si está seleccionado, elimínelo.

    [![Casilla de exento en la página de grupos de impuestos.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos**.
4. Seleccione el código de impuesto apropiado y luego verifique que el valor del tipo impositivo en el campo **Valor** no sea 0 (cero). Si es 0, actualice el campo para que esté configurado con ell tipo impositivo correcto.

    [![Campo Valor en la página de valores de código de impuesto.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Determinar si cero es el importe de impuestos correcto

En algunos escenarios, un importe de 0 (cero) es correcto. Siga estos pasos para determinar si 0 es el importe de impuestos correcto para su transacción.

1. Vaya a **Contabilidad general** \> **Configuración de contabilidad** \> **Parámetros de Contabilidad general**.
2. En la pestaña **Impuesto**, en el campo **Método de cálculo**, verifique que está seleccionado **Total**.

    [![Campo de método de cálculo en la página Parámetros de contabilidad general.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos**.
4. Seleccione el código de impuesto apropiado, seleccione **Cálculo** \> **Base marginal** y verifique que la base marginal esté establecida en **Importe neto del saldo de la factura** o **Total de factura incluidos otros importes de impuestos**. Para obtener más información, consulte el [Total de factura incluidos otros importes de impuestos](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts).
5. Si están establecidos los valores correctos en los pasos 2 y 4, determine si el importe total de la transacción es 0 (cero). Si el importe total es 0, el resultado esperado es un importe de impuestos de 0. Debido a que el cálculo de impuestos se basa en el importe total del saldo de la factura, y ese importe no va línea por línea, el importe de impuestos de 0 se asignará a cada línea después del cálculo de impuestos.

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización

Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización. Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
