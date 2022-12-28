---
title: Divisa de notificación fuera de saldo al cierre de fin de año
description: Este artículo explica cómo la moneda de informe puede estar desequilibrada cuando se ejecuta el cierre de fin de año.
author: kweekley
ms.date: 12/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 31f79791330e076d4fbd7b604ba9f9c6cd9b9195
ms.sourcegitcommit: 44f0b4ef8d74c86b5c5040be37981e32eb43e1a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2022
ms.locfileid: "9850267"
---
# <a name="reporting-currency-out-of-balance-when-the-year-end-close-is-run"></a>Divisa de notificación fuera de saldo al cierre de fin de año

Después de habilitar la función **Reconocimiento entre la liquidación del libro mayor y el cierre de fin de año** (la función **Reconocimiento**), las transacciones del libro mayor que liquidados ya no se incluirán en el saldo de apertura del próximo año fiscal cuando se ejecute el cierre de fin de año del libro mayor. La exclusión de las transacciones del libro mayor que se liquidan podrían presentar un desafío para los clientes al cierre del año si se define una divisa de notificación para el libro.

La liquidación de contabilidad se realiza solo para la divisa de contabilidad. Cuando se liquidan las transacciones del libro mayor, la validación solo confirma que los débitos en divisa de contabilidad sean iguales a los créditos en divisa de contabilidad. Los importes en divisa de notificación para esas transacciones del libro mayor no están validados y es posible que no tengan débitos = créditos. Además, la liquidación de contabilidad no calcula ni registra automáticamente una ganancia/pérdida en la divisa de notificación.

Debido a estas limitaciones, debe existir una transacción de ganancias/pérdidas en la divisa de notificación al realizar la liquidación de contabilidad. Si no se incluye ganancia/pérdida en la liquidación de contabilidad, se mostará un mensaje de descuadre al cerrar el año.

El siguiente ejemplo repasa los pasos para abordar este problema antes de que se ejecute el cierre de fin de año.

## <a name="example-setup"></a>Ejemplo de configuración

Para configurar este ejemplo, habilite la función **Reconocimiento** y configure la cuenta principal 110180 para la liquidación del libro mayor. La siguiente ilustración muestra las transacciones contables que se registraron en la entidad jurídica DEMF. La moneda de contabilidad para DEMF es el dólar estadounidense (USD) y la moneda de informe es el euro (EUR).

![Transacciones contables registradas en la moneda de informe.](./media/reporting-currency-1.png)

La página **Liquidaciones del libro mayor** muestra las transacciones del libro mayor para la cuenta principal 110180. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la cuadrícula y luego seleccione **Insertar columnas**. Agregue la columna **Cantidad en moneda de informe** para que se muestren las cantidades en moneda de transacción, moneda de contabilidad y moneda de informe.

![Monto en la columna de moneda de informe agregado a la página de liquidaciones del libro mayor.](./media/Ledger-settlement2.png)

Las dos primeras transacciones contables para 100.00 EUR se liquidan como un grupo y las siguientes dos transacciones contables para 200.00 EUR se liquidan como otro grupo. (Las dos transacciones tendrán diferentes ID de liquidación). Esta configuración muestra que las organizaciones tendrán varios grupos de transacciones contables que se liquidan en diferentes momentos y tienen diferentes fechas de liquidación. Cuando se compelta la liquidación, la página **Liquidaciones del libro mayor** muestra la siguiente información cuando se filtra para mostrar las transacciones con estado **Luiqidado**.

![Transacciones liquidadas en la página de liquidaciones de contabilidad.](./media/Settled-trans-filtered3.png)

En la página **Liquidaciones contables**, seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Importe** y luego seleccione para **totalizar por la columna**. Repita este paso para las columnas **Cantidad en moneda de informe**. La moneda de contabilidad debe tener una diferencia de 0 (cero) para que se produzca la liquidación. Sin embargo, no hay validación del monto de liquidación para la moneda de informe. La siguiente ilustración muestra una diferencia de -27,79 USD para la moneda de informe.

![Diferencia de la divisa de notificación.](./media/Difference4.png)

## <a name="year-end-close"></a>Cierre de fin de año

Si el cierre de fin de año ahora se ejecuta para 2022, el proceso terminará con un error de fuera de balance. Este error se debe directamente al hecho de que la divisa de notificación no tiene un importe de liquidación contable que se reduzca a 0 (cero).

![Mensaje de error que indica que el importe de liquidación del libro mayor no es 0 (cero).](./media/YEC5.png)

## <a name="posting-reporting-currency-gainloss"></a>Registro de pérdidas y ganancias en la divisa de notificación

Para que el cierre de fin de año se ejecute con éxito, la diferencia en el monto de la moneda de informe debe contabilizarse, generalmente como una ganancia o pérdida, e incluirse en la liquidación del libro mayor. La ganancia/pérdida de la moneda de informe se puede registrar de varias maneras:

- Si la cuenta principal son cuentas por pagar o cuentas por cobrar, la liquidación AR/AP de esos documentos generará la ganancia/pérdida requerida. Ese asiento contable debe incluirse en la liquidación del libro mayor cuando se liquiden las transacciones del libro mayor correspondientes a la factura, pagos, notas de crédito, etc.
- Si la cuenta principal es cualquier cuenta además de cuentas por pagar o cuentas por cobrar, la ganancia/pérdida debe ingresarse manualmente. Cuando se registra la ganancia/pérdida, su organización determina el nivel de detalle del asiento contable.
- Para cada cuenta principal, identifique el monto de la ganancia/pérdida de la moneda de informe que se debe contabilizar.

Como se describió anteriormente, esta contabilización se puede realizar en la página **Liquidaciones contables**.

1. Filtre hasta el rango de fechas para el que desea publicar la ganancia/pérdida. Si planea publicar una ganancia/pérdida por mes, filtre por cada mes. Si planea registrar una ganancia/pérdida por año fiscal, filtre por todo el año.
2. Filtrar en la cuenta principal.
3. Filtre por estado, de modo que solo se muestren las transacciones **Liquidadas**.
4. Agregue un total en la columna **Cantidad en moneda de informe**.
5. Si desea publicar la ganancia/pérdida en un nivel más granular, puede realizar un filtrado adicional en el ID de liquidación, las dimensiones financieras, etc. El importe total de la columna **Cantidad en moneda de informe** representa el importe por el que se contabilizará la ganancia/pérdida.
6. Vaya a **Contabilidad general \> Movimientos de diario \> Diarios de ajuste de moneda de informe**.
7. Introduzca la transacción para la pérdida/ganancia. Este diario registrará un ajuste solo en la moneda de informe. Los importes de moneda de transacción y moneda de contabilidad que se contabilizan son siempre 0 (cero). Si este diario no se ha usado antes, es posible que deba crear un nombre de diario que tenga un tipo de diario de **Ajuste de moneda de informe** en **General Libro mayor \> Configuración de diarios \> Nombres de diarios**.
8. Si la cuenta principal no permite la entrada manual, este ajuste no se publicará. Por lo tanto, es posible que deba desactivar temporalmente el parámetro **No permitir entrada manual** en la página **Cuenta principal**.

![Entrada manual en la página Asiento del diario.](./media/Manual-entry6.png)

Después de contabilizar el diario de ajustes, regrese a la página **Liquidaciones contables** y seleccione la cuenta principal para la que registró la ganancia/pérdida. El ajuste de ganancias/pérdidas debe incluirse en una liquidación contable. Debido a que el monto de la moneda de informe no tiene que ser neto a 0 (cero), puede cancelar cualquier transacción anterior y luego liquidarla nuevamente, pero esta vez incluya la ganancia/pérdida. Qué tan preciso desea ser para la contabilización de la ganancia/pérdida y la liquidación de esa ganancia/pérdida en las liquidaciones contables depende de su organización.

La siguiente ilustración muestra que las transacciones para 200 EUR no se liquidaron y luego se marcaron para liquidación nuevamente. Esta vez, incluirán el ajuste de ganancias/pérdidas.

![Ajuste de ganancias/pérdidas en la página Liquidaciones del libro mayor.](./media/gain-loss7.png)

Después de liquidar las transacciones, cambie el filtro **Estado** para que la página muestre **Transacciones** liquidadas. El total de la columna **Cantidad en moneda de informe** es ahora 0 (cero). El cierre de fin de año ahora se puede ejecutar con éxito.

![Cierre de fin de año correcto.](./media/Zero-settled8.png)
