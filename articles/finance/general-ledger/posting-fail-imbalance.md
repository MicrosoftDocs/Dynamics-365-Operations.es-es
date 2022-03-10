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
ms.openlocfilehash: 0f1f49a7da2f015d90987587fc251a36cfe82d49
ms.sourcegitcommit: cd7f1c63f48542a8ebcace7b3d512eb810d4b56e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903259"
---
# <a name="journal-posting-failure-because-of-imbalance"></a>Error de publicación de diario debido a desequilibrio

[!include [banner](../includes/banner.md)]

Este tema explica por qué es posible que los débitos y créditos no se equilibren en las transacciones de comprobantes, de modo que las transacciones no se puedan contabilizar. El tema también incluye pasos para solucionar el problema.

## <a name="symptom"></a>Síntoma

En algunos casos, no se puede contabilizar un diario y se muestra el siguiente mensaje: "Las transacciones de un comprobante específico no se equilibran en una fecha determinada (divisa de contabilidad: 0.01 - divisa de notificación: 0.06)". ¿Por qué no se puede contabilizar el diario?

## <a name="resolution"></a>Resolución

Durante la contabilización en el Libro mayor, cada comprobante debe estar equilibrado en la divisa de la transacción, la divisa de contabilidad y la divisa de notificación, si esas divisas están definidas en la página **Configuración del libro mayor**. (Los comprobantes se equilibran cuando el total de débitos es igual al total de créditos).

En la parte inferior de la página de líneas del diario, los totales se muestran en la divisa de contabilidad y en la divisa de notificación. **No** se muestran en la divisa de la transacción para las transacciones en divisa extranjera. Además, el mensaje de error que reciben los usuarios durante la simulación o la contabilización muestra las diferencias solo en la divisa de contabilidad y la divisa de notificación. No los muestra en la divisa de la transacción porque un solo comprobante puede tener más de una divisa de transacción y el diario puede incluir comprobantes en diferentes divisas de transacción. Por lo tanto, es importante que verifique manualmente que los importes de la moneda de la transacción para cada comprobante que tenga solo una moneda de la transacción estén equilibrados.

### <a name="transaction-currency"></a>Divisa de la transacción

Durante la simulación y la contabilización, el sistema verifica que todos los comprobantes que solo tienen una moneda de transacción estén equilibrados en la divisa de la transacción. Por cada comprobante que se introduce, puede haber una o más divisas para la divisa de la transacción. Por ejemplo, un comprobante que se introduce en el diario general puede tener dos divisas de transacción cuando se transfiere efectivo desde una cuenta bancaria que usa euros (EUR) a una cuenta bancaria que usa dólares canadienses (CAD).

Si un comprobante tiene solo una divisa de transacción, los débitos totales deben ser iguales a los créditos totales en la divisa de la transacción para ese comprobante. Los clientes se han encontrado con los siguientes escenarios en los que la contabilización falló correctamente porque los importes en la divisa de la transacción no estaban equilibrados:

- Los débitos y créditos totales **no** estaban equilibrados en la divisa de la transacción, pero estaban equilibrados para la divisa contable y la divisa de notificación. Un cliente asumió que, aún así, el comprobante se contabilizaría. Sin embargo, esa suposición era incorrecta. **Los importes en la divisa de transacción en un comprobante siempre deben equilibrarse cuando todas las líneas del comprobante tienen la misma divisa de la transacción.**
- El comprobante se importó con una entidad de datos a través del marco de gestión de datos (DMF) y el usuario pensó que los importes de la divisa de la transacción estaban equilibrados. En el archivo de importación, algunos de los importes numéricos tenían más de dos decimales y se incluyeron más de dos decimales cuando se importaron los importes. Por lo tanto, los débitos no igualaron a los créditos, porque estaban desviados por una fracción de céntimo. El diario no reflejó esta diferencia en las líneas del comprobante porque las cantidades que se muestran tienen solo dos decimales.
- El comprobante se importó con una entidad de datos a través de DMF y el usuario pensó que los importes en la divisa de la transacción estaban equilibrados. Aunque el **comprobante** estaba equilibrado, algunas líneas del comprobante tenían diferentes fechas de transacción. Si agregó el total de débitos y créditos en la divisa de la transacción por **comprobante y fecha de transacción**, no se equilibraron. Este requisito se aplica cuando introduce un comprobante a través del diario general en el sistema. Sin embargo, no se aplica cuando se importa un comprobante con una entidad de datos a través de DMF.

En un escenario admitido, un comprobante puede tener más de una divisa de transacción. En este caso, el sistema **no** verifica que los débitos sean iguales a los créditos en la divisa de la transacción, porque las divisas no coinciden. En cambio, el sistema verifica que los importes de la divisa contable y la divisa de notificación estén equilibrados.

### <a name="accounting-currency"></a>Divisa de contabilidad

Si todas las líneas de un comprobante tienen la misma divisa de transacción y si los importes en la divisa de la transacción están equilibrados, el sistema verifica que los importes en la divisa contable estén equilibrados. Si el comprobante se introducen en una divisa extranjera, el tipo de cambio en las líneas del comprobante se utiliza para convertir los importes en la divisa de la transacción a la divisa contable. Primero, cada línea del comprobante se traduce y se redondea a dos decimales. Luego, las líneas se suman para determinar el total de débitos y créditos. Debido a que se traduce cada línea, es posible que los débitos totales y los créditos totales no estén equilibrados. Sin embargo, si el valor absoluto de la diferencia está dentro del valor de **Diferencia máxima de céntimo** que se define en la página **Parámetros del libro mayor**, se publicará el comprobante y la diferencia se contabilizará automáticamente en la cuenta de diferencia de céntimos.

Si el comprobante tiene más de una divisa de transacción, cada línea del comprobante se convierte a la divisa contable y se redondea dos decimales, y luego se suman las líneas para determinar el total de débitos y créditos. Para que se consideren equilibrados, los débitos y créditos deben estar equilibrados en la divisa contable.  Una cuenta de diferencia de decimales nunca se agrega al comprobante en la moneda contable para equilibrar los débitos y créditos. 

### <a name="reporting-currency"></a>Divisa de notificación

Si todas las líneas de un comprobante tienen la misma divisa de transacción y si los importes en la divisa de la transacción están equilibrados, el sistema verifica que los importes en la divisa de notificación estén equilibrados. Si el comprobante se introducen en una divisa extranjera, el tipo de cambio en las líneas del comprobante se utiliza para convertir los importes en la divisa de la transacción a la divisa de notificación. Primero, cada línea del comprobante se traduce y se redondea a dos decimales. Luego, las líneas se suman para determinar el total de débitos y créditos. Debido a que se traduce cada línea, es posible que los débitos totales y los créditos totales no estén equilibrados. Sin embargo, si la diferencia está dentro del valor de **Redondeo máximo de céntimos en divisa de notificación** que se define en la página **Parámetros del libro mayor**, se publicará el comprobante y la diferencia se contabilizará automáticamente en la cuenta de diferencia de céntimos.

Si el comprobante tiene más de una divisa de transacción, cada línea del comprobante se convierte a la divisa de notificación y se redondea dos decimales, y luego se suman las líneas para determinar el total de débitos y créditos. Para que se consideren equilibrados, los débitos y créditos deben estar equilibrados en la divisa de notificación.  Una cuenta de diferencia de decimales nunca se agrega al comprobante en la divisa de notificación para equilibrar los débitos y créditos.

### <a name="example-for-an-accounting-currency-imbalance"></a>Ejemplo de un desequilibrio de divisa contable

> [!NOTE]
> El importe de la moneda de notificación se calcula a partir del importe de la moneda de la transacción de la misma forma que el importe de la moneda contable.

Tipo de cambio: 1,5

| Línea | Comprobante | Cuenta | Divisa | Débito (transacción) | Crédito (transacción) | Débito (contabilidad) | Crédito (contabilidad) |
|---|---|---|---|---|---|---|---|
| 1 | 001 | 1101-01 | EUR | 3.33 | | 5.00 (4.995) | |
| 2 | 001 | 1101-02 | EUR | 3.33 | | 5.00 (4.995) | |
| 3 | 001 | 1101-03 | EUR | 3.34 | | 5.01 | |
| 4 | 001 | 4101- | EUR | | 10,00 | | 15.00 |
| **Total** | | | | **10.00** | **10.00** | **15.01** | **15.00** |

La divisa contable no está equilibrada por 0,01. Sin embargo, siempre que el redondeo máximo de centavos en la divisa contable sea al menos 0,01, la diferencia se registrará automáticamente en la cuenta de diferencia de centavos y el comprobante se registrará correctamente.
