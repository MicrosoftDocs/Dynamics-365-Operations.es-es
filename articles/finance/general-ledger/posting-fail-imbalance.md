---
title: Error de publicación de diario debido a desequilibrio
description: Este tema explica por qué es posible que los débitos y créditos no se equilibren en las transacciones de comprobantes, de modo que las transacciones no se puedan contabilizar. El tema también incluye pasos para solucionar el problema.
author: kweekley
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-8-03
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a59724ff698b6ad0e84b0642240da5f8953ab3d1
ms.sourcegitcommit: 9642494da87c0d237f9fcbe15df14315d9e88fa2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2021
ms.locfileid: "7385732"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Error de publicación de diario debido a desequilibrio

[!include [banner](../includes/banner.md)]

Este tema explica por qué es posible que los débitos y créditos no se equilibren en las transacciones de comprobantes, de modo que las transacciones no se puedan contabilizar. El tema también incluye pasos para solucionar el problema.

## <a name="symptom"></a>Síntoma

En algunos casos, no se puede contabilizar un diario y se muestra el siguiente mensaje: "Las transacciones de un comprobante específico no se equilibran en una fecha determinada (divisa de contabilidad: 0.01 - divisa de notificación: 0.06)". ¿Por qué no se puede contabilizar el diario?

## <a name="resolution"></a>Resolución

Durante la contabilización en el Libro mayor, cada comprobante debe estar equilibrado en la divisa de la transacción, la divisa de contabilidad y la divisa de notificación, si esas divisas están definidas en la página **Configuración del libro mayor**. (Los comprobantes se equilibran cuando el total de débitos es igual al total de créditos).

En la parte inferior de la página de líneas del diario, los totales se muestran en la divisa de contabilidad y en la divisa de notificación. **No** se muestran en la divisa de la transacción para las transacciones en divisa extranjera. Además, el mensaje de error que reciben los usuarios durante la simulación o la contabilización muestra las diferencias solo en la divisa de contabilidad y la divisa de notificación. No los muestra en la divisa de la transacción porque un solo comprobante puede tener más de una divisa de transacción y el diario puede incluir comprobantes en diferentes divisas de transacción. Por lo tanto, es importante que verifique que los importes en divisa de la transacción para cada comprobante estén equilibrados.

### <a name="transaction-currency"></a>Divisa de la transacción

Durante la simulación y la contabilización, el sistema verifica que todos los comprobantes estén equilibrados en la divisa de la transacción. Por cada comprobante que se introduce, puede haber una o más divisas para la divisa de la transacción. Por ejemplo, un comprobante que se introduce en el diario general puede tener dos divisas de transacción cuando se transfiere efectivo desde una cuenta bancaria que usa euros (EUR) a una cuenta bancaria que usa dólares canadienses (CAD).

Si un comprobante tiene solo una divisa de transacción, los débitos totales deben ser iguales a los créditos totales para ese comprobante. Los clientes se han encontrado con los siguientes escenarios en los que la contabilización falló correctamente porque los importes en la divisa de la transacción no estaban equilibrados:

- Los débitos y créditos totales **no** estaban equilibrados en la divisa de la transacción, pero estaban equilibrados para la divisa contable y la divisa de notificación. Un cliente asumió que, aún así, el comprobante se contabilizaría. Sin embargo, esa suposición era incorrecta. **Los importes en la divisa de transacción en un comprobante siempre deben equilibrarse cuando todas las líneas del comprobante tienen la misma divisa.**
- El comprobante se importó a través de Microsoft Excel y el usuario pensó que los importes en la divisa de la transacción estaban equilibrados. En el libro de Excel, los importes que se importaron se establecieron como valores **Numéricos**, no valores de **Divisa**. En este escenario, los importes numéricos del libro tenían más de dos decimales y se incluyeron más de dos decimales cuando se importaron los importes. Por lo tanto, los débitos no igualaron a los créditos, porque estaban desviados por una fracción de céntimo. El diario no reflejó esta diferencia en las líneas del comprobante porque las cantidades que se muestran tienen solo dos decimales.
- El comprobante se importó a través de Excel y el usuario pensó que los importes en la divisa de la transacción estaban equilibrados. Aunque el comprobante estaba equilibrado, algunas líneas del comprobante tenían diferentes fechas de transacción. Si agregó el total de débitos y créditos por comprobante y fecha de transacción, no se equilibraron. El sistema ahora evita este escenario. Un comprobante solo puede tener una fecha de transacción. Este requisito se aplica cuando introduce un comprobante a través del diario general en el sistema. Sin embargo, originalmente no se hizo cumplir cuando se importó un comprobante a través de Excel.

En un escenario admitido, un comprobante puede tener más de una divisa de transacción. En este caso, el sistema **no** verifica que los débitos sean iguales a los créditos en la divisa de la transacción, porque las divisas no coinciden. En cambio, el sistema verifica que los importes de la divisa contable estén equilibrados.

### <a name="accounting-currency"></a>Divisa de contabilidad

Si todas las líneas de un comprobante tienen la misma divisa de transacción y si los importes en la divisa de la transacción están equilibrados, el sistema verifica que los importes en la divisa contable estén equilibrados. Si el comprobante se introducen en una divisa extranjera, el tipo de cambio en las líneas del comprobante se utiliza para convertir los importes en la divisa de la transacción a la divisa contable. Primero, se traduce cada línea del comprobante. Luego, las líneas se suman para determinar el total de débitos y créditos. Debido a que se traduce cada línea, es posible que los débitos totales y los créditos totales no estén equilibrados. Sin embargo, si la diferencia está dentro del valor de **Diferencia máxima de céntimo** que se define en la página **Parámetros del libro mayor**, se publicará el comprobante y la diferencia se contabilizará automáticamente en la cuenta de diferencia de céntimos.

Si el comprobante tiene más de una divisa de transacción, cada línea del comprobante se convierte a la divisa contable y luego se suman las líneas para determinar el total de débitos y créditos. Para que se consideren equilibrados, los débitos y créditos deben estar equilibrados y no debe haber diferencia de redondeo de céntimos.

### <a name="reporting-currency"></a>Divisa de notificación

Si todas las líneas de un comprobante tienen la misma divisa de transacción y si los importes en la divisa de la transacción están equilibrados, el sistema verifica que los importes en la divisa de notificación estén equilibrados. Si el comprobante se introducen en una divisa extranjera, el tipo de cambio en las líneas del comprobante se utiliza para convertir los importes en la divisa de la transacción a la divisa de notificación. Primero, se traduce cada línea del comprobante. Luego, las líneas se suman para determinar el total de débitos y créditos. Debido a que se traduce cada línea, es posible que los débitos totales y los créditos totales no estén equilibrados. Sin embargo, si la diferencia está dentro del valor de **Redondeo máximo de céntimos en divisa de notificación** que se define en la página **Parámetros del libro mayor**, se publicará el comprobante y la diferencia se contabilizará automáticamente en la cuenta de diferencia de céntimos.

Si el comprobante tiene más de una divisa de transacción, cada línea del comprobante se convierte a la divisa de notificación y luego se suman las líneas para determinar el total de débitos y créditos. Para que se consideren equilibrados, los débitos y créditos deben estar equilibrados y no debe haber diferencia de redondeo de céntimos.
