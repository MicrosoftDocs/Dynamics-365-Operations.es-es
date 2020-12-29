---
title: Liquidaciones de contabilidad
description: Este tema explica cómo usar la página de las liquidaciones de contabilidad para liquidar las transacciones contables e inventir liquidaciones.
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: d41a69bed3d1340736cc7df35aa3ded032d4d79d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447517"
---
# <a name="ledger-settlements"></a>Liquidaciones de contabilidad

[!include [banner](../includes/banner.md)]

Las liquidaciones de contabilidad le permiten coincidir las transacciones de débito y crédito en la contabilidad general, y marcarlas como liquidadas. De esta manera, se asegura de que se hayan borrado las transacciones relacionadas. También puede invertir liquidaciones si se han realizado por error.

## <a name="enable-advanced-ledger-settlements"></a>Habilitar liquidaciones de contabilidad avanzada

La página avanzado de las liquidaciones de contabilidad avanzada proporciona capacidades adicionales para filtrar y seleccionar transacciones. Para habilitar la página de liquidaciones de contabilidad avanzada, siga estos pasos.

1. Seleccione **Contabilidad general** \> **Configuración de contabilidad** \> **Parámetros de Contabilidad general**. 
2. En la pestaña **Liquidaciones de contabilidad**, establezca la opción **Liquidación de contabilidad avanzada** en **Sí** para activar la funcionalidad avanzada de liquidación de contabilidad. La página **Liquidaciones de contabilidad** avanzada se usará cuando seleccione **Liquidaciones de contabilidad** en **Tareas periódicas**. 
3. Debe especificar la lista de cuentas que se usarán para las liquidaciones de contabilidad para cada plan de cuentas. Esta lista se usa para filtrar la lista de transacciones que aparece en la página **Liquidaciones de contabilidad**. En el lista **plan de cuentas**, seleccione un plan contable y, a continuación, seleccione **Nuevo** para agregar nuevas cuentas a la lista.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Liquidar transacciones mediante la página de las liquidaciones de contabilidad avanzadas

Para liquidar transacciones de contabilidad, siga estos pasos.

1. Seleccione **Contabilidad general** \> **Tareas periódicas** \> **Liquidaciones de contabilidad**.
2. Establezca los filtros en la parte superior de la página:

    - Seleccione un intervalo de fechas, o seleccione **Código de intervalo de fechas** para completar automáticamente el intervalo de fechas.
    - Cambie la capa de registro según necesite.
    - Para mostrar la cuenta contable y las dimensiones por separado, seleccione un conjunto de dimensiones financieras.

3. Seleccione **Mostrar transacciones** para mostrar todas las transacciones que coinciden con los filtros que establece y la lista de cuentas que especificó al configurar la lista del plan de cuenta de la sección anterior. Si cambia alguno de los filtros o los conjuntos de dimensiones, debe volver a seleccionar **Mostrar transacciones**.
4. Seleccione una o más líneas que esté teniendo en cuenta para la liquidación. El valor del campo **Importe seleccionado** en la parte superior de la página aumenta o disminuye por el importe total de las líneas que ha seleccionado.
5. Una vez que haya terminado de seleccionar transacciones, seleccione **Marcar seleccionada**. Una marca de verificación aparece en la columna **Marcado** para cada transacción que ha seleccionado. Además, el valor del campo **Importe marcado** en la parte superior de la cuadrícula aumenta o disminuye por el importe total de las líneas que ha marcado.
6. Cuando el valor **Importe marcado** es **0** (cero), seleccione **Liquidar transacciones marcadas**. El estado de las transacciones marcadas se actualiza a **Liquidada**.

## <a name="make-transactions-easier-to-find"></a>Facilite encontrar las transacciones

La página **Liquidaciones de contabilidad** incluye capacidades que facilitan ver las transacciones que necesita para la liquidación.

- El botón **Desmarcar artículos seleccionados** borra el campo **Marcado** para todas las líneas que están seleccionadas.
- El filtro **Marcado** permite filtrar transacciones en función de si el campo **Marcado** para ellas esta seleccionado o desactivado.
- El filtro **Estado** permite filtrar transacciones en función de si su estado es **Establecido** o **No liquidado**.
- El botón **Ordenar por importe absoluto** le permite ordenar los importes por valor absoluto, de modo que pueda agrupar conjuntamente débitos y créditos que tienen la misma cantidad.

## <a name="reverse-a-settlement"></a>Invertir una liquidación

Puede invertir una liquidación que se ha realizado por error.

1. Siga los pasos 1 a 3 de la sección “Liquidar transacciones mediante la página de las liquidaciones de contabilidad avanzadas” para mostrar las transacciones que busca.
2. En el campo **Estado**, seleccione **Liquidado**.
3. Seleccione una o más líneas que esté teniendo en cuenta para revertirlas. El valor del campo **Importe seleccionado** en la parte superior de la página aumenta o disminuye por el importe total de las líneas que ha seleccionado.
4. Una vez que haya terminado de seleccionar transacciones, seleccione **Marcar seleccionada**. Una marca de verificación aparece en la columna **Marcado** para cada transacción que ha seleccionado. Además, el valor del campo **Importe marcado** en la parte superior de la página aumenta o disminuye por el importe total de las líneas que ha marcado.
5. Cuando el valor **Importe marcado** es **0** (cero), seleccione **Revertir transacciones marcadas**. El estado de las transacciones marcadas se actualiza a **No liquidado**.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>Actualice la lista de cuentas que se incluyen en la lista de transacciones

Seleccione **Cuentas de liquidación de contabilidad** para abrir un cuadro de diálogo donde puede editar las cuentas que se incluyen en la lista de transacciones. Seleccione **Nuevo** para agregar nuevas cuentas a la lista. Esta lista se usa para filtrar la lista de transacciones que aparece en la página **Liquidaciones de contabilidad**.
