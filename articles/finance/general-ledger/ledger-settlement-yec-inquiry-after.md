---
title: Transacciones entre la liquidación de contabilidad después del cierre de fin de año utilizando la página de consultas
description: En este artículo se explica cómo utilizar la función Conocimiento entre liquidaciones de libros mayores utilizando la página de consultas nueva después de que se ejecute el proceso de cierre de fin de año del Libro mayor.
author: kweekley
ms.date: 12/15/2022
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
ms.openlocfilehash: 921d2a17409ae10cd9c22eeca11557ba1248b9bc
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853152"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close-using-the-inquiry-page"></a>Transacciones entre la liquidación de contabilidad después del cierre de fin de año utilizando la página de consultas

Un cambio pirnipcal de la función **Conciencia entre la liquidación del libro mayor y el cierre de fin de año** (la función **Conciencia**) es que la función la liquidación no se puede hacer a través de los años fiscales. Esta limitación interanual solo es relevante para la liquidación del libro mayor, no para las liquidaciones de Cuentas por cobrar o Cuentas por pagar.

Antes de habilitar la característica **Conciencia**, el año fiscal que tendrá el cierre de fin de año no debe tener transacciones contables que se liquiden entre años fiscales. Específicamente, todas las transacciones que se registraron en el año fiscal para el que está ejecutando el cierre de fin de año deben desliquidarse de las transacciones que se registraron en un año fiscal diferente. Las transacciones luego pueden reajustarse frente a las transacciones en el mismo ejercicio en curso.

En este artículo se describen los pasos necesarios para identificar, anular y reajustar las transacciones contables que se liquidan entre años. En el ejemplo que se proporciona, se cerró el año fiscal 2022. La atención se centra en preparar las transacciones de liquidación del libro mayor antes de que se ejecute el cierre de fin de año de 2023.

A partir de la versión 10.0.29 de Microsoft Dynamics 365 Finance, puede identificar, anular y reajustar transacciones contables mediante una nueva página de consulta disponible. Si actualmente no está en Microsoft Dynamics 365 Finance versión 10.0.29 o posterior, puede encontrar los pasos para identificar, anular y reajustar las transacciones del libro mayor en los siguientes artículos:

- [Característica de transacciones entre la liquidación de contabilidad antes del cierre de fin de año](ledger-settle-yec.md)
- [Característica Transacciones entre la liquidación de contabilidad después del cierre de fin de año](ledger-settle-yec-after.md)

Para obtener más información sobre la nueva ventana de consulta, consulte [Consulta de liquidación del libro mayor](ledger-settlement-inquiry.md). 

## <a name="example-setup"></a>Ejemplo de configuración

En la siguiente ilustración se muestran las transacciones que e registraron para la cuenta principal 110200. Las transacciones del libro mayor en verde se liquidaban en el mismo año fiscal y no tienen que cambiar. Las transacciones en rojo se liquidaban en el libro mayor, pero tienen fechas de transacción en diferentes años fiscales. Esas transacciones deben identificarse y es posible que se deba revertir la liquidación del libro mayor.

![Transacciones contables registradas.](./media/excel.png)

## <a name="example"></a>ejemplo

Siga estos pasos si su organización desea utilizar la función **Conciencia** después de que se ejecute el cierre de fin de año para el año fiscal 2022.

> [!NOTE]
> El cierre de fin de año para 2022 y años fiscales anteriores debe volver a ejecutarse solo si se contabilizan nuevas transacciones en el año fiscal 2022 o antes. Cuando completa el siguiente procedimiento, no se registran nuevas transacciones en 2022. Por lo tanto, el proceso de cierre de fin de año no tiene que volverf a ejecutarse.
>
> Las transacciones contables que se liquidan a lo largo de los años fiscales pueden permanecer liquidadas en el libro mayor si no se liquidan contra una transacción que se registró en 2022 o posterior. Por ejemplo, si ha liquidado transacciones en 2019 y 2020, pueden permanecer liquidadas.

1. Complete el cierre de fin de año para 2022 sin la función **Awareness** habilitada.
2. Identifique todas las transacciones que se registraron en otros años fiscales pero que se liquidaron con las transacciones que se registraron en 2023 (el próximo año fiscal que se cerrará).

    > [!NOTE]
    > Las transacciones de 2021 que se liquidaron contra las transacciones de 2022 no son relevantes porque el año ya se cerró para 2022. Esas transacciones se pueden mantener liquidadas.

    1. Seleccione **Revisar liquidación entre años** en la página **Liquidaciones del libro mayor**.
    2. Seleccione el ejercicio 2023 para el que desee realizar el próximo proceso de cierre de fin de año.
    3. Seleccione un valor en el campo **Conjunto de dimensiones financieras** para mostrar las dimensiones financieras que desea ver para la cuenta contable. La cuenta principal siempre se muestra, incluso si el conjunto de dimensiones seleccionado no contiene una cuenta principal.
    4. Seleccione **Mostrar transacciones**.

    La página de consulta mostrará todas las transacciones de otros años fiscales que se liquidan con las transacciones que se registraron en 2023.

    ![Liquidaciones entre ejercicios para 2023.](./media/2023-cross-settlement.png)

3. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la cuadrícula y luego seleccione **Exportar todas las filas**. Estas filas son todas las transacciones que se deben liquidar de las transacciones en 2022 antes de que se pueda ejecutar el cierre de fin de año para el próximo año (2023). Quiere un registro de estas transacciones.

    Después de que todas las transacciones detalladas de 2022 se exporten a Excel, estará listo para desarmar las transacciones mediante la página de consulta.

4. Seleccione todos los registros en la cuadrícula y luego seleccione **Anular registros marcados**. Todas las transacciones seleccionadas en la cuadrícula se anularán.

    Se muestran dos mensajes de advertencia para garantizar que los detalles de la transacción se exporten a Excel antes de que se deshagan las transacciones. Si accidentalmente anula las transacciones del libro mayor antes de enviar los detalles a Excel, no hay forma de revertir la anulación.

    ![Anular liquidaciones entre ejercicios.](./media/revert-settlement.png)

5. Use los datos de Excel para encontrar la cantidad total de transacciones en 2022 que se liquidaron en transacciones en 2023. En este ejemplo, las transacciones para 2023 totalizan $700.
6. Registre un diario general de ajuste para dividir el saldo de apertura de 2022 en dos importes: la parte que se liquidó contra la transacción del año fiscal 2022 y la parte que aún no se liquidó en 2023.

    - **Parte del saldo de apertura que se liquidó contra el año anterior:** El primer monto es $700, según los totales encontrados que se liquidaron en 2021 y 2022.
    - **Porción del saldo inicial que no se liquidó contra el año anterior:** La segunda cantidad es la diferencia entre el saldo inicial y la cantidad liquidada de $700. El importe restante es $1,700 – $700 = $1,000.

    De esta forma, puede liquidar las transacciones de 2023 contra el $700 que se liquidó originalmente contra la transacción de 2022. Este paso es obligatorio porque la liquidación del libro mayor no permite la liquidación parcial.

    1. Vaya al diario general y registre el ajuste. Su organización tendrá que decidir qué fecha de transacción usar, en función de los períodos que estén abiertos en 2023.
    2. Es posible que deba desactivar temporalmente el parámetro **No permitir entrada manual** en la página **Cuenta principal**. Este ajuste no se publicará si la cuenta principal no permite la entrada manual.

    ![Contabilización de un diario general de ajuste.](./media/no-manual4.png)

7. Ahora puede liquidar las transacciones no liquidadas. Vuelva a la página **Liquidaciones contables** y limite el intervalo de fechas del 1 de enero de 2023 al 31 de diciembre de 2023. Luego, use las transacciones detalladas que exportó a Excel para encontrar las transacciones específicas que se deben reajustar. La ilustración que sigue muestra las transacciones no liquidades que existen ahora.

    ![Transacciones no liquidadas en 2023.](./media/2023-unsettled5.png)

    - El saldo inicial de $1,700 se puede liquidar contra el ajuste por -$1,700.
    - Las transacciones detalladas que no se liquidaron por -$700 se pueden liquidar contra el ajuste de $700.00.

8. Habilitar la característica **Concienciación**. Ahora todo está listo para ejecutar el cierre de fin de año.

    - Antes de ejecutar el cierre de fin de año para 2023, considere seleccionar la opción **Mantener detalles** para todas las cuentas del balance en la configuración de liquidación del libro mayor. Para obtener información adicional, consulte [Las transacciones entre la liquidación de contabilidad y el cierre de fin de año](awareness-between-ledger-settlement-year-end-close.md).
    - Cuando comience el cierre de fin de año para 2023, si aún se encuentran transacciones que se liquidaron entre años fiscales, el proceso de cierre de fin de año le notificará de inmediato. Esta situación podría ocurrir si los usuarios liquidaron transacciones en años fiscales antes de que se habilitara la función **Awareness**.
    - Si las transacciones de 2022 y 2023 aún se liquidan, deberá deshabilitar la función **Awareness** nuevamente y luego repetir los pasos anteriores para cancelar esas transacciones. Este enfoque es necesario porque 2022 está cerrado y las transacciones no pueden anularse en un año fiscal cerrado.

Después de que el cierre de fin de año para 2022 se ejecute con éxito, puede dejar habilitada la función **Concienciación** a partir de ahora.
