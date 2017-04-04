---
title: "Revalorización de divisa extranjera para Contabilidad general"
description: "Este tema proporciona una visión general de los siguientes pasos para el proceso de revalorización de divisa extranjera de la contabilidad general permite configurar, la ejecución del cálculo proceso, para el proceso, y cómo invertir transacciones de revalorización, en caso necesario."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5d6d13fe44eef7766b4dcaf274c3522bce3da816
ms.lasthandoff: 03/31/2017


---

# <a name="foreign-currency-revaluation-for-general-ledger"></a>Revalorización de divisa extranjera para Contabilidad general

Este tema proporciona una visión general de los siguientes pasos para el proceso de revalorización de divisa extranjera de la contabilidad general permite configurar, la ejecución del cálculo proceso, para el proceso, y cómo invertir transacciones de revalorización, en caso necesario. 

Como parte de una período final, las prácticas contables requieren que los saldos de la cuenta de contabilidad general en divisas extranjeras se revaloricen mediante distintos tipos de cambio (circulante, histórico, medio, etc.). Por ejemplo, un convenio contable requiere que los activos y los pasivos se revaloricen al tipo de cambio actual, los activos fijos al tipo de cambio histórico, y las cuentas de pérdidas y ganancias a la media mensual. La revalorización de divisa extranjera de la contabilidad general se puede usar para revalorizar el balance de situación y las cuentas de pérdidas y ganancias. 

> [!NOTE]
> La revalorización de divisa extranjera también está disponible en los clientes (AR) y los proveedores (AP). Si utiliza los módulos, las transacciones pendientes se deben revalorizar mediante la revalorización de divisa extranjera en ellos. La revalorización de divisa extranjera de las cuentas clientes y proveedores creará una entrada contable en la Contabilidad general para reflejar las pérdidas o ganancias no realizadas, asegurándose de que la contabilidad auxiliar y la contabilidad general se pueden conciliar. Dado que la revalorización de divisa extranjera de las cuentas de clientes y proveedores creará entradas contables en la Contabilidad general, las cuentas de clientes y proveedores principales se deben excluir de la revalorización de divisa extranjera de la contabilidad general. 

Si ejecuta el proceso de revalorización, el saldo en cada cuenta principal que se haya registrado en una divisa extranjera se revalorizará. Las transacciones de pérdidas o ganancias no realizadas que se crean durante el proceso de revalorización son generadas por el sistema. Dos transacciones se pueden crear, una para la divisa de contabilidad y un segundo para la divisa de notificación, si procede. Cada entrada contable enviará al beneficio no realizado o las pérdidas y la cuenta principal que es revalorizada.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Preparación para ejecutar una revalorización de divisa extranjera
Para poder ejecutar el proceso de revalorización, se requiere la siguiente configuración.

-   En la página de **Cuenta principal**:
-   Si la cuenta principal debe revalorizarse en la Contabilidad general, seleccione **Revalorización de divisa extranjera**. Si no debe revalorizarse la cuenta principal (como para las cuentas de clientes y proveedores si se han revalorizado en la contabilidad auxiliar), desactive esta opción.
-   Si la cuenta principal está marcada para su revalorización, especifique el **Tipo de cambio**. Este tipo de cambio se utilizará para revalorizar la cuenta principal. Un campo aparte, **Tipo de cambio para informes financieros**,está disponible para el informe financiero. Los dos campos no se mantienen en sincronización, permitiendo así que se usen distintos tipos de cambio para la revalorización y el informe financiero.

-   En la página **Libro mayor**:
-   Especificar **Tipo de cambio**. Si no se define el tipo de cambio en la cuenta principal, se va a utilizar este tipo de cambio durante la revalorización de divisa extranjera.
-   Especifique las cuentas de ganancias realizadas, pérdida realizada, ganancias no realizadas y pérdida no realizada para la revalorización de divisa. Las cuentas de beneficio realizado y pérdida realizada se usan si al configurar las transacciones de cuentas de clientes y proveedores, y las cuentas de pérdidas y ganancias no realizadas se usan para revalorizar las transacciones abiertas y las cuentas principales de la contabilidad general.

-   En la página de **Cuentas de revalorización de divisa**:
-   Seleccione diferentes cuentas de revalorización de divisa para cada divisa y empresa. Si no se define ninguna cuenta, se usan las cuentas de la página **Libro mayor**.

## <a name="process-foreign-currency-revaluation"></a>Procesamiento de la revalorización de divisa extranjera
Cuando se complete la configuración, use la página **Revalorización de divisa extranjera** para revalorizar los saldos de las cuentas principales. Puede ejecutar el proceso en tiempo real o programarlo para ejecutarlo mediante un lote. 

La página de **Revalorización de divisa extranjera** mostrará el historial de cada proceso de revalorización, incluido cuando el proceso se ejecutó, qué criterios se definieron, un vínculo al asiento creado para la revalorización y un registro si una revalorización anterior se ha invertido. Para ejecutar el proceso de revalorización, seleccione el botón **Revalorización de divisa extranjera**. 

Los valores **Desde la fecha** y **Hasta la fecha** definen el intervalo de fechas para calcular el saldo de la divisa extranjera que se va a revalorizar. Al revalorizar las cuentas de pérdidas y ganancias, se revaloriza la suma de todas las transacciones que se producen en el intervalo de fechas. Cuando se revaloriza las cuentas de balance de situación, se omite el valor Desde la fecha. En su lugar, el saldo que se revalorizará viene determinado desde el inicio del ejercicio hasta el valor Hasta la fecha. 

** Fecha de tasa ** se puede utilizar para definir la fecha para la que el tipo de cambio debe establecer como valor predeterminado. Por ejemplo, puede revalorizar los saldos entre el intervalo de fechas del del 1 de enero al 31 de enero, pero usa el tipo de cambio definido para el 1 de febrero. 

Seleccione las cuentas principales a revalorizar: Todas, balance de situación o las de pérdidas y ganancias. Sólo las cuentas principales marcadas para la revalorización (en la página de la cuenta principal) se revalorizadas. Si desea limitar aún más el intervalo de cuentas principales, use los registros ** incluir ** ficha para definir un intervalo de cuentas principales, o de cuentas principales individuales. 

El proceso de revalorización se puede ejecutar para una o más entidades jurídicas. La búsqueda mostrará sólo las entidades jurídicas a las que tiene acceso. Seleccionar las entidades jurídicas para los que desea ejecutar el proceso de revalorización. 

La revalorización se puede ejecutar para una o más divisas extranjeras. La búsqueda incluirá todas las divisas que se han registrado en el intervalo de fechas relevante para el tipo de cuenta principal (balance de situación o las pérdidas y ganancias), ya que las entidades jurídicas seleccionadas revalorizar. La divisa de contabilidad se incluirá en la lista, pero no se revalorizará nada si se selecciona la divisa de contabilidad. 

Conjunto ** vista previa antes de enviar ** ** Sí ** si desea revisar el resultado de la revalorización de la contabilidad general. La vista previa en contabilidad general es diferente de la simulación de la revalorización de divisa extranjera de clientes y de proveedores. La simulación en clientes y proveedores es un informe, pero Contabilidad general tiene una vista previa que se pueda enviar, sin tener que ejecutar el proceso de revalorización de nuevo. Los resultados de la vista previa se pueden exportar a Microsoft Excel para guardar el historial de cómo se calcularon los importes. No puede usar el procesamiento por lotes si desea obtener una vista previa de los resultados de la revalorización. En la vista previa, el usuario tiene la opción de publicar los resultados de todas las entidades jurídicas mediante el botón **Publicar**. Si hay un problema con los resultados para una entidad jurídica, el usuario también tiene la opción de publicar un subconjunto de las entidades jurídicas mediante el botón **Seleccionar entidades jurídicas para publlicar**. 

Una vez finalizado el proceso de revalorización de divisa extranjera, un registro se creará el seguimiento del historial de cada vez.  Un registro individual se creará para cada entidad jurídica y la capa de registro.

## <a name="calculate-unrealized-gainloss"></a>Calcule las pérdidas/ganancias no realizadas
Las transacciones de pérdidas/ganancias no realizadas se crean de forma diferente entre la revalorización de la Contabilidad general y el proceso de revalorización de cuentas de clientes y proveedores. En las cuentas de clientes y proveedores, la revalorización anterior se invierte completamente (si se supone que la transacción no se establece aún) y se crea una nueva transacción de revalorización para las pérdidas/ganancias no realizadas en base al nuevo tipo de cambio. Esto se debe a que revalorizamos cada transacción individual de cuentas de clientes y proveedores. En contabilidad general, la revalorización anterior no se invierte. En su lugar, se realiza una transacción para el delta entre el saldo de la cuenta principal, incluidos los revalorización correspondientes, anterior y el nuevo valor basado en el tipo de cambio de la fecha del índice. 

** Ejemplo ** los saldos siguientes existen para la cuenta principal 110110.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Fecha**   | **Cuenta contable** | **Importe de transacción** | **Importe contable** |
| 20 de enero | 110110 (Efectivo)      | 500 EUR (Débito)        | 1000 USD (Débito)      |

La cuenta principal que se revaloriza el 31 de enero.  Se calculan al beneficio no realizado/pérdidas del modo siguiente.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Saldo actual en divisa de transacción** | **Saldo actual en divisa contable** | **Tipo de cambio en la revalorización** | **Nuevo importe de la divisa contable** | **Pérdidas/ganancias no realizadas**    |
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833,33 EUR (500 x 1,666667)        | 166,67 loss (833,33 – 1000) |

Se creará el asiento contable siguiente.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **Fecha**   | **Cuenta contable**       | **Débito** | **Crédito** |
| 31 de enero | 110110 (Efectivo)            |           | 166.67     |
| 31 de enero | 801400 (Pérdida no realizada) | 166.67    |            |

No se registra ninguna nuevas transacciones para el mes de febrero.  La cuenta principal que se revaloriza el 28 de febrero.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Saldo actual en divisa de transacción** | **Saldo actual en divisa contable** | **Tipo de cambio en la revalorización** | **Nuevo importe de la divisa contable** | **Pérdidas/ganancias no realizadas**    |
| 500 EUR                                     | 833,33 USD (1000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | Ganancias de 416,67 (1250 – 833,33) |

Se creará el asiento contable siguiente.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **Fecha**    | **Cuenta contable**       | **Débito** | **Crédito** |
| 28 de febrero | 110110 (Efectivo)            | 416.67    |            |
| 28 de febrero | 801600 (Ganancias no realizadas) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Invertir revalorización de divisa extranjera
Si necesita invertir la transacción de revalorización, seleccione el botón **Invertir transacción** de la página de **Revalorización de divisa extranjera**. Un nuevo registro histórico de la revalorización de divisa extranjera se creará para mantener la traza de auditoría histórica de cuándo se produjo o se ha invertido la revalorización. 

Puede invertir los resultados del pedido obsoleto de revalorización, pero puede ser necesario invertir también una revalorización más reciente para asegurarse de que los saldos correctos para cada cuenta principal revalorizada. Las inversiones pueden producir pedido obsoleto porque no es posible de controlar las cuentas principales que se revalorizan y la frecuencia cuando se revalorizan. Por ejemplo, una organización puede elegir para revalorizar las cuentas principales de efectivo trimestralmente, pero el resto de las cuentas principales mensuales.


