---
title: Soporte de divisa doble para impuestos
description: Este tema explica cómo ampliar la función de contabilidad de divisa doble en el dominio fiscal y el impacto para el cálculo y la publicación de impuestos
author: EricWang
manager: Ann Beebe
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 3f7ca56fef636431e152b2db424f1f972a507721
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212214"
---
# <a name="dual-currency-support-for-sales-tax"></a>Soporte de divisa doble para impuestos
[!include [banner](../includes/banner.md)]

Este tema explica cómo ampliar la función de contabilidad de divisa doble para impuestos y el impacto para el cálculo, publicación y ajustes de impuestos.

La función de divisa doble para Dynamics 365 Finance se introdujo en la versión 8.1 (octubre de 2018). Cambia la forma en que se calculan las entradas contables en la divisa de notificación.

En versiones anteriores, las transacciones se convirtieron a la divisa de notificación en la siguiente secuencia: 

- El total de la transacción se calculó en la divisa de la transacción > La cantidad de la transacción n se convirtió a la divisa de contabilidad > El monto de la divisa de contabilidad se convirtió a la divisa de notificación

Después de habilitar la función de divisa doble, las transacciones se convirtieron a la divisa de notificación en la siguiente secuencia:

- Importe en divisa de transacción > Importe en divisa de notificación

Para obtener más información sobre la divisa doble, consulte [Divisa doble](dual-currency.md).

Como consecuencia del soporte para divisas dobles, hay dos nuevas funciones disponibles en la administración de funciones: 

- Conversión de impuestos de ventas (nuevo en la versión 10.0.13)

El soporte de divisa doble para los impuestos garantiza que los impuestos se calculen con precisión en la divisa del impuesto, y que el saldo de liquidación de impuestos se calcule con precisión tanto en la divisa de contabilidad como en la divisa de notificación. 

## <a name="sales-tax-conversion"></a>Conversión de impuestos

El parámetro **Conversión de impuestos** proporciona dos opciones para convertir el importe de impuestos de la divisa de transacción a la divisa de impuestos. 

- Divisa de contabilidad: la ruta será "Importe en divisa de transacción > Importe en divisa de contabilidad > Importe en divisa de impuestos". El tipo de cambio de la divisa de contabilidad (establecido en la configuración del libro mayor) se usará para la conversión de divisa.
- Divisa de notificación: la ruta será "Importe en divisa de transacción > Importe en divisa de notificación > Importe en divisa de impuestos". El tipo de cambio de la divisa de notificación (configurado en la configuración del libro mayor) se usará para la conversión de divisa.

### <a name="example"></a>Ejemplo

Un ejemplo simple para demostrar esta funcionalidad es:

Configuración de divisa para libro mayor e impuestos

| Divisa de la transacción | Divisa de contabilidad | Divisa de notificación | Divisa de impuestos |
| -------------------- | ------------------- | ------------------ | ------------ |
| EUR                  | USD                 | GBP                | GBP          |

Tipo de cambio

| Desde divisa | A divisa | Factor | Tipo de cambio |
| ------------- | ----------- | ------ | ------------- |
| EUR           | USD         | 1      | 1.11          |
| EUR           | GBP         | 1      | 0.83          |
| USD           | GBP         | 1      | 0.75          |

Cálculo del importe de impuestos en diferentes opciones de parámetros

Importe de impuesto = 100 EUR

| Parámetros de conversión de impuestos | Divisa de la transacción (EUR) | Divisa de contabilidad (USD) | Divisa de notificación (GBP) | Divisa de impuestos (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Divisa de contabilidad             | 100                        | 111                       | 83                       | **83.25**          |
| Divisa de notificación              | 100                        | 111                       | 83                       | **83**             |

Este parámetro se puede configurar en función de la necesidad de cumplimiento de la autoridad fiscal.


### <a name="upgrade-consideration"></a>Consideraciones sobre la actualización

Esta función solo se aplicará a las transacciones nuevas. Para las transacciones de impuestos ya guardadas en la tabla TAXTRANS pero aún no liquidadas, el sistema no volverá a calcular el monto del impuesto en la divisa del impuesto porque el tipo de cambio en el momento de contabilizar el impuesto ya no se encuentra.

Para evitar el escenario anterior, recomendamos cambiar el valor de este parámetro en un nuevo período de liquidación de impuestos (limpio) que no contenga ninguna transacción de impuestos sin resolver. Para cambiar este valor en la mitad de un período de liquidación de impuestos, ejecute el programa "Liquidación y post impuesto" para el período de liquidación de impuestos actual antes de cambiar este valor de parámetro.


## <a name="track-reporting-currency-tax-amount"></a>Seguir la cantidad de impuestos de divisa de notificación

Se agregaron tres nuevos campos a las tablas relacionadas con impuestos para rastrear los importes en la divisa de notificación. Estos campos están dentro de las tablas TAXUNCOMMITTED y TAXTRANS:

- TaxAmountRep: importe de impuestos en la divisa de notificación
- TaxBaseAmountRep: importe base en la divisa de notificación
- TaxInCostPriceRep: cantidad no deducible en la divisa de notificación

Para los impuestos solo guardados en la tabla TAXUNCOMMITTED pero aún no contabilizados, el sistema volverá a calcular el importe de los impuestos en la divisa de notificación al contabilizar y guardar en la tabla TAXTRANS.

Esta versión no incluirá cambios en los informes y formularios que muestren el importe del impuesto en la divisa de notificación. Los cambios en los informes y formularios se añadirán en la versión futura.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>Saldo automático de liquidación de impuestos en la divisa de notificación

Si la liquidación de impuestos no está equilibrada en la divisa de notificación por alguna razón, como en el caso de que la ruta de conversión de impuestos sea "Divisa de contabilidad", o la modificación del tipo de cambio en un solo período de liquidación de impuestos, el sistema generará automáticamente entradas contables para ajustar la variación del importe del impuesto y compensar la cuenta de ganancias/pérdidas de cambio realizadas, que se establece en la configuración del libro mayor.

Utilizando el ejemplo anterior para demostrar esta característica, suponga que los datos en la tabla TAXTRANS en el momento de la publicación son los siguientes.

| Parámetros de conversión de impuestos | Divisa de la transacción (EUR) | Divisa de contabilidad (USD) | Divisa de notificación (GBP) | Divisa de impuestos (GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| Divisa de contabilidad             | 100                        | 111                       | 83                       | **83.25**          |
| Divisa de notificación              | 100                        | 111                       | 83                       | **83**             |

Cuando ejecute el programa de liquidación de impuestos al final del mes, la entrada contable será la siguiente:
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>Escenario: conversión de impuestos = "Divisa de contabilidad"

| Cuenta principal           | Divisa de la transacción (GBP) | Divisa de contabilidad (USD) | Divisa de notificación (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Impuestos repercutidos/soportados | -83,25                     | -111                      | -83,25                   |
| Liquidación de impuestos         | 83.25                      | 111                       | 83.25                    |
| Pérdidas/ganancias realizadas     | 0                          | 0                         | -0,25                    |
| Impuestos repercutidos/soportados | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>Escenario: conversión de impuestos = "Divisa de notificación"


| Cuenta principal           | Divisa de la transacción (GBP) | Divisa de contabilidad (USD) | Divisa de notificación (GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| Impuestos repercutidos/soportados | -83                        | -110,67                   | -83                      |
| Liquidación de impuestos         | 83                         | 110.67                    | 83                       |
| Pérdidas/ganancias realizadas     | 0                          | 0.33                      | 0                        |
| Impuestos repercutidos/soportados | 0                          | -0,33                     | 0                        |



Para obtener más información, consulte los siguientes temas:

- [Divisa dual](dual-currency.md)
- [Visión general de impuestos](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]