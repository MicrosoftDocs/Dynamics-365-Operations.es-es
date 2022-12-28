---
title: Característica de transacciones entre la liquidación de contabilidad antes del cierre de fin de año
description: En este artículo se explica cómo utilizar la función Conocimiento entre liquidaciones de libros mayores antes de que se ejecute el proceso de cierre de fin de año del Libro mayor.
author: kweekley
ms.date: 12/02/2022
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
ms.openlocfilehash: c79b6f50296560e1534be0621bb2aa8eaa2c1dc8
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832179"
---
# <a name="awareness-between-ledger-settlement-feature-before-year-end-close"></a>Característica de transacciones entre la liquidación de contabilidad antes del cierre de fin de año

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-before-year-end-close"></a>Preparativos para la característica de transacciones entre la liquidación de contabilidad antes del cierre de fin de año

Un cambio importante de la función **Conciencia entre la liquidación del libro mayor y el cierre de fin de año** (la función **Conciencia**) es que la función la liquidación no se puede hacer a través de los años fiscales. Esta limitación interanual solo es relevante para la liquidación del libro mayor, no para las liquidaciones de Cuentas por cobrar o Cuentas por pagar.

Antes de habilitar la característica **Conciencia**, el año fiscal que tendrá el cierre de fin de año no debe tener transacciones contables que se liquiden entre años fiscales. Específicamente, todas las transacciones que se registraron en el año fiscal para el que está ejecutando el cierre de fin de año deben desliquidarse de las transacciones que se registraron en un año fiscal diferente. Las transacciones luego pueden reajustarse frente a las transacciones en el mismo ejercicio en curso.

En este artículo se describen los pasos necesarios para identificar, anular y reajustar las transacciones contables que se liquidan entre años fiscales. En el ejemplo que se proporciona, se cerró el año fiscal 2021 y se está preparando para ejecutar el cierre de fin de año para el año fiscal 2022.

## <a name="example-setup"></a>Ejemplo de configuración

En la siguiente ilustración se muestran las transacciones que e registraron para la cuenta principal 110190. Las transacciones del libro mayor en verde se liquidan en el mismo año fiscal y no tienen que cambiar. Las transacciones en rojo se liquidan en el libro mayor, pero tienen fechas de transacción en diferentes años fiscales. Esas transacciones deben identificarse y es posible que se deba revertir la liquidación del libro mayor.

![Transacciones contables.](./media/YEC1.png)

## <a name="example"></a>ejemplo

Siga estos pasos si su organización desea utilizar la función **Conciencia** antes de que se ejecute el cierre de fin de año para el año fiscal 2022.

> [!NOTE]
> El cierre de fin de año para 2021 y años fiscales anteriores debe volver a ejecutarse solo si se contabilizan nuevas transacciones en el año fiscal 2021 o antes. Cuando completa el siguiente procedimiento, no se registran nuevas transacciones en 2021. Por lo tanto, el proceso de cierre de fin de año no tiene que volverf a ejecutarse.
>
> Las transacciones contables que se liquidan a lo largo de los años fiscales pueden permanecer liquidadas en el libro mayor si no se liquidan contra una transacción que se registró en 2022 o posterior. Por ejemplo, si ha liquidado transacciones durante 2019 y 2020, pueden permanecer liquidadas.

1. Opcional: habilite temporalmente la función **Concienica**.

    - Si elige habilitar la función, deberá deshabilitarla en pasos posteriores, como se indica. El beneficio de habilitar la función ahora es que evita temporalmente que los usuarios liquiden transacciones contables que se registraron en diferentes años fiscales.
    - Si elige no habilitar la función, le recomendamos que le pida a su equipo que no liquide transacciones entre años fiscales. Si la liquidación interanual ocurre después de completar los siguientes pasos, tendrá que repetir los pasos para identificar y cancelar las transacciones del libro mayor.

2. En la página **Liquidación contable**, identifique el total de todas las transacciones que se liquidan en los años fiscales 2021 y 2022.

    1. Especifique un rango de fechas para todo el año fiscal 2021. Por ejemplo, ingrese del 1 de enero de 2021 al 31 de diciembre de 2021, si está utilizando un año calendario como año fiscal.

        Si la función **Awareness** está habilitada, recibirá una advertencia de que las transacciones no se pueden liquidar o anular para un año fiscal cerrado. La advertencia no es relevante porque no se produce ninguna liquidación ni anulación en este paso.

    2. En el campo **Estado**, seleccione **Liquidado**.
    3. Filtre en una cuenta contable a la vez.

        - Tendrá que repetir estos pasos para cada cuenta contable para la que se produzca la liquidación contable.
        - Si otras cuentas del libro mayor ya no están configuradas para la liquidación del libro mayor, es posible que deba volver a agregarlas temporalmente a la configuración de la liquidación del libro mayor. Luego complete estos pasos si esas cuentas contables tienen transacciones en 2022 que se liquidan contra transacciones en otro año fiscal.

    4. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Estado** y luego seleccione para agrupar por la columna.
    5. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Importe en divisa de transacción** y luego seleccione para totalizar por la columna.

        - Si liquidó transacciones solo en 2021, el total será 0 (cero).
        - Si tiene transacciones que se liquidaron en años fiscales, el total no será 0 (cero).

        En la siguiente ilustración, hay un saldo de $525.00. Este saldo es el total de las transacciones que se liquidaron contra transacciones en un ejercicio fiscal diferente. Su total puede incluir transacciones que se liquidaron entre 2021 y 2022 y transacciones que se liquidaron entre 2022 y 2023.

        ![Transacciones contables 2021–2022.](./media/YEC2.png)

    6. Identifique qué transacciones se liquidaron entre 2020 y 2021 filtrando más en el valor de **Fecha de liquidación**. Especifique un filtro de intervalo de fechas del 1 de enero de 2021 al 31 de diciembre de 2021. No se muestran transacciones porque no se liquidaron transacciones de 2020 contra transacciones que se contabilizaron en 2021.
    7. Identifique qué transacciones se liquidaron entre 2021 y 2022 cambiando el filtro de fecha en el valor **Fecha de liquidación**. Especifique un filtro de intervalo de fechas del 1 de enero de 2022 al 31 de diciembre de 2022. Las transacciones se muestran nuevamente y el total es $525.00 porque todas las transacciones se liquidaron entre 2021 y 2022.

3. En la página **Liquidación contable**, identifique el total de todas las transacciones que se liquidan en los años fiscales 2021 y 2022.

    1. Especifique un rango de fechas para todo el año fiscal 2022. Por ejemplo, especifique el 1 de enero de 2022 al 31 de diciembre de 2022, si está utilizando un año calendario como año fiscal.
    2. En el campo **Estado**, seleccione **Liquidado**.
    3. Filtre en una cuenta contable a la vez.
    4. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Estado** y luego seleccione para agrupar por la columna.
    5. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Importe en divisa de transacción** y luego seleccione para totalizar por la columna.

        ![Importes totales de la transacción contable](./media/YEC3.png)

    6. Agregue un filtro adicional en el valor de **Fecha de liquidación**. Especifique un filtro de intervalo de fechas del 1 de enero de 2022 al 31 de diciembre de 2022. Se muestra el mismo total de $525.00. Este resultado valida que el monto total de transacciones que se liquidan entre 2021 y 2022 es $525.00.

        ![Transacciones contables para fechas de liquidación en 2022 y 2023.](./media/YEC4.png)

    7. Cambie el filtro adicional en el valor de **Fecha de liquidación**. Especifique un filtro de intervalo de fechas del 1 de enero de 2023 al 31 de diciembre de 2023. Se muestra un nuevo total de $700. Este total es el monto total de las transacciones que se liquidaron entre 2022 y 2023.
 
4. Repita el paso 3 para el año fiscal 2023. El total debe coincidir con el $700 de 2022 porque no se liquidaron transacciones de 2023 contra transacciones de 2024.
5. Si habilitó la función **Concioencia** en el paso 1, desactívela antes de pasar al paso 6. En los siguientes pasos, revertirá la liquidación del libro mayor que cruzó los años fiscales. Si la función **Conciencia** está habilitada, la liquidación del libro mayor no se puede revertir para el año fiscal 2021. Por lo tanto, debe deshabilitar la funcionalidad antes de continuar.
6. Después de desactivar la función **Conciencia**, use los mismos filtros en la página **Liquidación contable** para revertir la liquidación contable de las transacciones detalladas.

    1. Vuelva a la página **Liquidación contable** y filtre por fechas de transacción para 2021. Agregue un filtro adicional en el valor de **Fecha de liquidación**. Especifique un filtro de intervalo de fechas desde el 1 de enero de 2022 al 31 de diciembre de 2022. Luego busque las transacciones detalladas que componen el total $525. Filtrar esta información puede no ser fácil. Es posible que deba enviar los datos a Microsoft Excel para evaluarlos.
    2. Una vez que tenga la lista de transacciones, seleccione las transacciones del libro mayor en la página **Liquidación del libro mayor** y seleccione **Marcar seleccionado**. No es necesario que vea ambos lados de las transacciones del libro mayor que se liquidaron. Si marca el débito o el crédito, todo lo que tenga el mismo valor de **ID de liquidación** se invertirá, incluso si el **monto marcado** no es **0** (cero).
    3. Seleccione **Revertir transacciones marcadas** para anular las transacciones.

    ![Revertir transacciones marcadas.](./media/YEC5.png)

7. Repita el paso 6 para revertir la liquidación de las transacciones que se liquidaron entre 2022 y 2023.

    ![Revertir transacciones contables.](./media/YEC6.png)

8. Registre un diario general de ajuste para dividir el saldo de apertura de 2022 en dos importes: la parte que se liquidó contra la transacción del año fiscal 2021 y la parte que aún no se liquidó en 2022.

    - **Parte del saldo de apertura que se liquidó contra el año anterior:** El primer monto es $525, según los totales encontrados que se liquidaron en 2021 y 2022.
    - **Porción del saldo inicial que no se liquida contra el año anterior:** La segunda cantidad es la diferencia entre el saldo inicial y la cantidad liquidada de $525. El importe restante es $1025 – $525 = $500.

    De esta forma, puede liquidar las transacciones de 2022 contra el $525 que se liquidó originalmente contra la transacción de 2021. Este paso es obligatorio porque la liquidación del libro mayor no permite la liquidación parcial.

    1. Vaya al diario general y registre el ajuste. Su organización tendrá que decidir qué fecha de transacción usar, en función de los períodos que estén abiertos. Es posible que estas transacciones se hayan liquidado utilizando una fecha de liquidación de enero o febrero de 2022, pero es posible que el ajuste deba registrarse en diciembre si ese es el único período abierto.
    2. Es posible que deba desactivar temporalmente el parámetro **No permitir entrada manual** en la página **Cuenta principal**. Este ajuste no se publicará si la cuenta principal no permite la entrada manual.

    ![Ajuste no registrado.](./media/YEC7.png)

9. Ahora puede liquidar las transacciones no liquidadas. Vuelva a la página **Liquidación contable** y limite el intervalo de fechas del 1 de enero de 2022 al 31 de diciembre de 2022. La ilustración que sigue muestra las transacciones no liquidades que existen ahora.

    ![Transacciones no liquidadas.](./media/YEC8.png)

    - El saldo inicial de $1,025 se puede liquidar contra el ajuste por -$1,025.
    - Las transacciones detalladas que no se liquidaron por -$400, -$50 y -$75 se pueden liquidar contra el ajuste de $525.00.

    ![Transacciones detalladas.](./media/YEC9.png)

10. Habilitar la característica **Concienciación**. Ahora todo está listo para ejecutar el cierre de fin de año.

    - Antes de ejecutar el cierre de fin de año, considere seleccionar la opción **Mantener detalles** en la configuración de liquidación del libro mayor para todas las cuentas del balance. Para obtener más información sobre los beneficios de completar este paso, consulte el documento de sensibilización.
    - Cuando comience el cierre de fin de año para 2022, si aún se encuentran transacciones que se liquidan entre años fiscales, el proceso de cierre de fin de año le notificará de inmediato.
    - Si las transacciones de 2021 y 2022 aún se liquidan, deberá deshabilitar la función **Awareness** nuevamente y repetir los pasos anteriores para cancelar las transacciones. Este enfoque es necesario porque 2021 está cerrado y las transacciones no pueden anularse en un año fiscal cerrado.
    - Si las transacciones de 2022 y 2023 aún se liquidan, **no** tiene que deshabilitar la función **Concienciación**. Debido a que ni 2022 ni 2023 están cerrados, puede usar los pasos anteriores para desarmar las transacciones.

Después de que el cierre de fin de año para 2022 se ejecute con éxito, puede dejar habilitada la función **Concienciación** a partir de ahora.
