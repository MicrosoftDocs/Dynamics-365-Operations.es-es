---
title: Liquidaciones de contabilidad
description: Este artículo explica cómo usar la página de las liquidaciones de contabilidad para liquidar las transacciones contables e inventir liquidaciones.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 39fd6c6677565a4b1e9a9bf6f43a4c630cb5e07b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902498"
---
# <a name="ledger-settlements"></a>Liquidaciones de contabilidad

[!include [banner](../includes/banner.md)]

La liquidación de contabilidad es el proceso de coincidir las transacciones de débito y crédito en la contabilidad general. La liquidación de los montos de débito y crédito se utiliza para conciliar el saldo de la cuenta mayor con las transacciones detalladas que componen ese saldo.

Las transacciones liquidadas se pueden excluir de consultas e informes. De esta forma, es más fácil analizar las transacciones abiertas del libro mayor que componen el saldo de la cuenta del libro mayor.

> [!IMPORTANT] 
> La liquidación compara la cuenta contable de clientes/proveedores de la factura y el pago. Cuando se produce una liquidación en los libros auxiliares AR y AP, los asientos contables correspondientes no se liquidan automáticamente.

## <a name="ledger-settlement-features"></a>Características de la liquidación de contabilidad
En Microsoft Dynamics 365 Finance versión 10.0.21, la opción **Habilitar la liquidación avanzada del libro mayor** se eliminó de la página **Parámetros del libro mayor**. La liquidación avanzada del libro mayor ahora está siempre habilitada.
En Finance versión 10.0.25, se introdujo la función **Conciencia entre la liquidación del libro mayor y el cierre de fin de año**. Esta característica cambia la funcionalidad fundamental tanto en la liquidación del libro mayor como en el cierre de fin de año del libro mayor. Antes de habilitar esta característica en el espacio de trabajo **Gestión de características**, vea [Conciencia entre la liquidación del libro mayor y el cierre de fin de año](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Configurar la liquidación contable
Debe seleccionar las cuentas principales para las que desea realizar la liquidación del libro mayor. Hay dos formas de seleccionar estas cuentas principales.

1. Vaya a **Contabilidad general** > **Configuración de contabilidad** > **Parámetros de Contabilidad general**.
2. Sobre la pestaña **Liquidaciones del libro mayor**, seleccione los planes de cuentas de los que desea seleccionar las cuentas principales.
3. Seleccione las cuentas principales para las que va a realizar la liquidación contable. Dado que los planes de cuentas son globales, todas las empresas a las que se asignan los planes de cuentas seleccionados tendrán las mismas cuentas principales seleccionadas para la liquidación del libro mayor.

  – O bien –

1. Vaya a **Contabilidad general** > **Tareas periódicas** > **Liquidaciones de contabilidad**.
2. Seleccione **Cuentas de liquidación del libro mayor**.
3. En el cuadro de diálogo, seleccione los planes de cuentas y las cuentas principales para realizar la liquidación del libro mayor. Este cuadro de diálogo es un acceso directo. Cualquier cuenta principal que agregue aquí también se reflejará en la página **Parámetros del libro mayor**.

Puede utilizar los mismos procedimientos básicos para eliminar las cuentas principales de la liquidación del libro mayor en cualquier momento. La eliminación de una cuenta principal no tiene efecto en las liquidaciones anteriores del libro mayor. Sin embargo, la cuenta principal y las transacciones ya no aparecerán en la página **Liquidación del libro mayor**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Liquidar transacciones
Para liquidar transacciones de contabilidad, siga estos pasos.

1. Vaya a **Contabilidad general** > **Tareas periódicas** > **Liquidaciones de contabilidad**.
2. Establezca los filtros en la parte superior de la página:

    - Seleccione un rango de fechas. Alternativamente, seleccione un código de intervalo de fechas para completar automáticamente el intervalo de fechas. No recomendamos que realice la liquidación del libro mayor para las transacciones que cruzan años fiscales.
    - Cambie la capa de registro según necesite. No puede liquidar transacciones que están en diferentes niveles de contabilización.
    - Para mostrar la cuenta principal y las dimensiones por separado, seleccione un conjunto de dimensiones financieras.

3. Seleccione **Mostrar transacciones** para mostrar todas las transacciones que coinciden con los filtros que establece y la lista de cuentas que especificó al configurar la lista del plan de cuenta de la sección anterior.

    - Si cambia alguno de los filtros o los conjuntos de dimensiones, debe volver a seleccionar **Mostrar transacciones**.
    - Para filtrar las transacciones a una cuenta principal individual, use el filtro en el campo **cuenta contable**. No recomendamos que realice la liquidación del libro mayor para las transacciones que se registran en diferentes cuentas principales.

4. Seleccione las líneas de liquidación. El valor en el campo **Importe seleccionado** en la parte superior de la página aumenta o disminuye para reflejar el importe total de las líneas seleccionadas.
5. Cuando haya terminado de seleccionar transacciones, seleccione **Marcar seleccionada**. Para cada transacción seleccionada, aparece una marca de verificación en la columna **Marcado**. Además, el valor en el campo **Importe marcado** en la parte superior de la cuadrícula aumenta o disminuye para reflejar el importe total de las líneas marcadas.
6. Cuando el valor del campo **Importe marcado** es **0** (cero), seleccione **Liquidar transacciones marcadas**. El estado de las transacciones marcadas se actualiza a **Liquidada**.

    > [!IMPORTANT]
    > Se liquidarán todas las transacciones que haya marcado para la liquidación de la entidad jurídica activa, incluso si no se muestran actualmente en la página de liquidación del Libro mayor porque aplicó un filtro.

## <a name="make-transactions-easier-to-find"></a>Facilite encontrar las transacciones
La página **Liquidaciones de contabilidad** incluye capacidades que facilitan ver las transacciones que necesita para la liquidación.

- Use el filtro **Marcado** para filtrar transacciones en función de si la casilla **Marcado** para ellas esta seleccionada.
- Use el filtro **Estado** para filtrar las transacciones en función de su estado.
- Seleccione **Ordenar por cantidad absoluta** para ordenar los importes por valor absoluto. De esta forma, puede agrupar débitos y créditos que tengan la misma cantidad.

## <a name="reverse-a-settlement"></a>Invertir una liquidación
Puede invertir una liquidación que se ha realizado por error.

1. Siga los pasos 1 a 3 en la sección [Liquidar transacciones](#settle-transactions) para mostrar las transacciones que le interesan.
2. En el campo **Estado**, seleccione **Liquidado**.
3. Seleccione las líneas de reversión.
4. Seleccione **Revertir transacciones marcadas**. El estado de todas las transacciones que tienen el mismo ID de liquidación se actualiza a **Sin liquidar**.

    > [!IMPORTANT]
    > Todas las transacciones que tengan el mismo ID de liquidación se revertirán, incluso si no están marcadas. Por ejemplo, se marcaron y asentaron cuatro líneas. Las cuatro líneas tienen el mismo ID de liquidación. Si marca una de esas cuatro líneas y luego selecciona **Transacciones marcadas inversamente**, las cuatro líneas se invertirán.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
