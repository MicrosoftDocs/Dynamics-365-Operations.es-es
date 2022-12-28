---
title: Característica Transacciones entre la liquidación de contabilidad después del cierre de fin de año
description: En este artículo se explica cómo utilizar la función Conocimiento entre liquidaciones de libros mayores después de que se ejecute el proceso de cierre de fin de año del Libro mayor.
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
ms.openlocfilehash: 7efa9d652d74bd836f51b5b1c5f6bfaf8934ea40
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832186"
---
# <a name="awareness-between-ledger-settlement-feature-after-year-end-close"></a>Característica Transacciones entre la liquidación de contabilidad después del cierre de fin de año

[!include [banner](../includes/banner.md)]

## <a name="preparing-for-the-ledger-settlement-awareness-feature-after-year-end-close"></a>Preparativos para la característica de transacciones entre la liquidación de contabilidad después del cierre de fin de año

Un cambio importante de la función **Conciencia entre la liquidación del libro mayor y el cierre de fin de año** (la función **Conciencia**) es que la función la liquidación no se puede hacer a través de los años fiscales. Esta limitación interanual solo es relevante para la liquidación del libro mayor, no para las liquidaciones de Cuentas por cobrar o Cuentas por pagar.

Antes de habilitar la característica **Conciencia**, el año fiscal que tendrá el cierre de fin de año no debe tener transacciones contables que se liquiden entre años fiscales. Específicamente, todas las transacciones que se registraron en el año fiscal para el que está ejecutando el cierre de fin de año deben desliquidarse de las transacciones que se registraron en un año fiscal diferente. Las transacciones luego pueden reajustarse frente a las transacciones en el mismo ejercicio en curso.

En este artículo se describían los pasos necesarios para identificar, anular y reajustar las transacciones contables que se liquidan entre años fiscales. En el ejemplo que se proporciona, se cerró el año fiscal 2022. La atención se centra en preparar las transacciones de liquidación del libro mayor mucho antes de que se ejecute el cierre de fin de año de 2023.

## <a name="example-setup"></a>Ejemplo de configuración

En la siguiente ilustración se muestran las transacciones que e registraron para la cuenta principal 110190. Las transacciones del libro mayor en verde se liquidan en el mismo año fiscal y no tienen que cambiar. Las transacciones en rojo se liquidan en el libro mayor, pero tienen fechas de transacción en diferentes años fiscales. Esas transacciones deben identificarse y es posible que se deba revertir la liquidación del libro mayor.

![Transacciones contables.](./media/afterYEC1.png)

## <a name="example"></a>ejemplo

Siga estos pasos si su organización desea utilizar la función **Conciencia** después de que se ejecute el cierre de fin de año para el año fiscal 2022.

> [!NOTE]
> El cierre de fin de año para 2022 y años fiscales anteriores debe volver a ejecutarse solo si se contabilizan nuevas transacciones en el año fiscal 2022 o antes. Cuando completa el siguiente procedimiento, no se deberían registrar nuevas transacciones en 2022. Por lo tanto, el proceso de cierre de fin de año no tiene que volverf a ejecutarse.
>
> Las transacciones contables que se liquidan a lo largo de los años fiscales pueden permanecer liquidadas en el libro mayor si no se liquidan contra una transacción que se registró en 2023 o posterior. Por ejemplo, si ha liquidado transacciones durante 2019 y 2020, pueden permanecer liquidadas.

1. Complete el cierre de fin de año para 2022 sin la función **Awareness** habilitada.
2. Opcional: después de que se haya completado el cierre de fin de año para 2022, habilite la función **Concienciación**. Un cierre de fin de año se considera completado cuando se registran todos los ajustes y el proceso de cierre de fin de año no se vuelve a ejecutar.

    > [!IMPORTANT]
    > La función **Concienciación** no debe habilitarse si el cierre de fin de año para 2022 se ejecutará nuevamente. El beneficio de habilitar la función ahora es que evita que los usuarios liquiden transacciones contables que se registraron en diferentes años fiscales.

    Si el cierre de fin de año no se completó, aún puede completar los siguientes pasos sin habilitar la función **Concienciación**. Habilitará la función en un paso posterior, como se indica.

3. En la página **Liquidación contable**, identifique el total de todas las transacciones que se liquidan en los años fiscales 2022 y 2023. Tenga en cuenta que las transacciones de 2021 que se liquidaron contra las transacciones de 2022 no son relevantes porque el año ya se cerró. Esas transacciones se pueden mantener liquidadas.

    1. Especifique un rango de fechas para todo el año fiscal 2022. Por ejemplo, especifique el 1 de enero de 2022 al 31 de diciembre de 2022, si está utilizando un año calendario como año fiscal.
    2. En el campo **Estado**, seleccione **Liquidado**.
    3. Filtre en una cuenta contable a la vez.

        - Tendrá que repetir estos pasos para cada cuenta contable para la que se produzca la liquidación contable.
        - Si otras cuentas del libro mayor ya no están configuradas para la liquidación del libro mayor, es posible que deba volver a agregarlas temporalmente a la configuración de la liquidación del libro mayor. Luego complete estos pasos si esas cuentas contables tienen transacciones en 2023 que se liquidan contra transacciones en 2022 o antes.

    4. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Estado** y luego seleccione para agrupar por la columna.
    5. Seleccione y mantenga presionado (o haga clic con el botón derecho) en la columna **Importe en divisa de transacción** y luego seleccione para totalizar por la columna.

        - Si liquidó transacciones solo en 2022, el total será 0 (cero).
        - Si tiene transacciones que se liquidaron en años fiscales, el total no será 0 (cero).

    6. Identifique qué transacciones se liquidaron entre 2022 y 2023 filtrando según el valor de **Fecha de liquidación**. Si filtra en una fecha de liquidación del 1 de enero de 2023 al 31 de diciembre de 2023, obtiene un total de $700, que es el total de transacciones que se liquidaron en el libro mayor entre 2022 y 2023.

    ![Transacciones de contabilidad general totales en 2022.](./media/afterYEC2.png)

4. Repita el paso 3 para el año fiscal 2023. El total debe coincidir con el $700 de 2022 porque no se liquidaron transacciones de 2023 contra transacciones de 2024.

    ![Transacciones de contabilidad general totales en 2023.](./media/afterYEC3.png)

5. Si habilitó la función **Concioencia** en el paso 2, desactívela antes de pasar al paso 6. En los siguientes pasos, revertirá la liquidación del libro mayor que cruzó los años fiscales. Si la función **Conciencia** está habilitada, la liquidación del libro mayor no se puede revertir para el año fiscal 2022. Por lo tanto, debe deshabilitar la funcionalidad antes de continuar.
6. Después de desactivar la función **Conciencia**, use los mismos filtros en la página **Liquidación contable** para revertir la liquidación contable de las transacciones detalladas.

    1. Vuelva a la página **Liquidación contable** y filtre por fechas de transacción para 2023. Luego busque las transacciones detalladas que componen el total $700. Filtrar esta información puede no ser fácil. Es posible que deba enviar los datos a Microsoft Excel para evaluarlos.
    2. Una vez que tenga la lista de transacciones, seleccione las transacciones del libro mayor en la página **Liquidación del libro mayor** y seleccione **Marcar seleccionado**. No es necesario que vea ambos lados de las transacciones del libro mayor que se liquidaron. Si marca el débito o el crédito, todo lo que tenga el mismo valor de **ID de liquidación** se invertirá, incluso si el **monto marcado** no es **0** (cero).
    3. Seleccione **Revertir transacciones marcadas** para anular las transacciones.

    ![Revertir transacciones.](./media/afterYEC4.png)

7. Registre un diario general de ajuste para dividir el saldo de apertura de 2023 en dos importes: la parte que se liquidó contra la transacción del año fiscal 2022 y la parte que aún no se liquidó en 2023.

    - **Parte del saldo de apertura que se liquidó contra el año anterior:** El primer monto es $700, según los totales encontrados que se liquidan en 2022 y 2023.
    - **Porción del saldo inicial que no se liquida contra el año anterior:** La segunda cantidad es la diferencia entre el saldo inicial y la primera cantidad de $525. El importe restante es $1700 – $700 = $1000.

    De esta forma, puede liquidar las transacciones de 2023 contra el $700 que se liquidó originalmente contra la transacción de 2022. Este paso es obligatorio porque la liquidación del libro mayor no permite la liquidación parcial.

    1. Vaya al diario general y registre el ajuste. Su organización tendrá que decidir qué fecha de transacción usar, en función de los períodos que estén abiertos en 2023.
    2. Es posible que deba desactivar temporalmente el parámetro **No permitir entrada manual** en la página **Cuenta principal**. Este ajuste no se publicará si la cuenta principal no permite la entrada manual.

    ![Ajuste no registrado.](./media/afterYEC5.png)

8. Ahora puede liquidar las transacciones no liquidadas. Vuelva a la página **Liquidación contable** y limite el intervalo de fechas del 1 de enero de 2022 al 31 de diciembre de 2022. La ilustración que sigue muestra las transacciones no liquidades que existen ahora.

    ![Transacciones no liquidadas.](./media/afterYEC6.png)

    - El saldo inicial de $1,700 se puede liquidar contra el ajuste por -$1,700.
    - Las transacciones detalladas que no se liquidaron por -$700 se pueden liquidar contra el ajuste de $700.00.

9. Volver a habilitar la característica **Concienciación**.
10. Una vez que la función **Conciencia** está habilitada, la liquidación del libro mayor no se puede realizar entre años fiscales. Es posible que deba dividir aún más el saldo restante de $1,000 en cantidades más pequeñas antes de poder liquidar nuevas transacciones en 2023. Algunos clientes eligen publicar ese detalle durante el paso 8, donde $1,000 se divide aún más para representar las transacciones no liquidadas de 2022. Este enfoque básicamente imita lo que hace la función **Concienciación** solo para el año en curso. El próximo año, se realizará automáticamente usando la configuración **Mantener detalles** en la configuración de liquidación del libro mayor.
