---
title: Registrar arrendamientos en divisa extranjera
description: Este artículo explica cómo registrar los arrendamientos en divisas distintas de la divisa de notificación o de contabilidad.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 56c15e648d6aa515192a6f41ba06df6405ca79f2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878113"
---
# <a name="record-leases-in-foreign-currencies"></a>Registrar arrendamientos en divisa extranjera

[!include [banner](../includes/banner.md)]

Las cuentas de arrendamiento de activos para arrendamientos que están en divisas distintas a la divisa contable o la divisa de notificación se establecen en la página **Configuración del libro mayor**. Todos los arrendamientos deben introducirse en su divisa de transacción. En otras palabras, deben introducirse en la divisa que se especifica en el contrato de arrendamiento. Este artículo explica cómo registrar los arrendamientos en divisas distintas de la divisa de notificación o de contabilidad.

Si introduce un arrendamiento en una divisa extranjera, el activo por derecho de uso (ROU) se deprecia tanto en la divisa contable como en la divisa de notificación. Estas divisas están configuradas en la página **Configuración del libro mayor**. Este comportamiento también se utiliza en activos fijos. Cuando crea un arrendamiento en una divisa extranjera, seleccione la divisa de la transacción en el campo **Divisa**.

El tipo de cambio de la divisa contable es el valor predeterminado en el campo **Tipo de cambio de divisa contable**. El tipo de cambio de la divisa contable es el valor predeterminado en el campo **Tipo de cambio de divisa contable**. Estos tipos de cambio eran efectivos en la fecha de inicio del arrendamiento. Los campos **Tipo de cambio de divisa contable** e **Informe del tipo de cambio de divisa de notificación** están en la ficha desplegable **Información de cambio financiera y de notificación**, en la página **Detalles del arrendamiento**.

1. Seleccione la casilla **Tasa fija** para anular la tasa de cambio que se introdujo automáticamente y luego introduzca la nueva tasa.
2. En los otros campos, introduzca la información que se requiere para el arrendamiento y luego seleccione **Crear programaciones**.
3. En la nueva página **Detalles de arrendamientos**, seleccione **Libros**.
4. En la página **Libro de arrendamiento**, en la pestaña **Información de cambio financiera y de notificación**, verifique los valores de los campos **Activo por derecho de uso inicial de divisa contable** y **Activo por derecho de uso inicial de divisa de notificación**. Cada uno de estos campos muestra el saldo del activo por derecho de uso en la divisa correspondiente. Estos campos se actualizan cada vez que cambia cualquier información financiera. Seleccione **Crear programaciones** antes de confirmar la programación de pagos.

    El movimiento de diario de reconocimiento inicial registra el activo por derecho de uso que usa los tipos de cambio de divisa que se enumeran en el arrendamiento. La entrada de diario también incluye los valores de los campos **Activo por derecho de uso inicial de divisa contable** y **Activo por derecho de uso inicial de divisa de notificación**.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>Medición posterior para arrendamientos en divisa extranjera

La programación de depreciación muestra los importes de gastos de depreciación esperados en la divisa de notificación, la divisa de contabilidad y la divisa de la transacción.

Para ver los saldos de activos por derecho de uso y los importes de depreciación en la divisa de notificación o en la divisa de contabilidad, abra la página **Programación de depreciación de activos** y seleccione la casilla **Mostrar importes de divisa contable** o **Mostrar importes de divisa de notificación**.

Cuando crea los movimientos de diario de gastos de depreciación contra un arrendamiento que está denominado como de una divisa extranjera, el movimiento utiliza los tipos de cambio que se enumeran en el arrendamiento. También utiliza los valores de los campos **Activo por derecho de uso inicial de divisa contable** y **Activo por derecho de uso inicial de divisa de notificación**.

El importe final del gasto de depreciación se puede calcular utilizando un tipo de cambio ligeramente diferente, de modo que el activo por derecho de uso se deprecie por completo tanto en la divisa de contabilidad como en la divisa de notificación.

Si el arrendamiento se ha reclasificado como **Arrendamiento diferido**, el sistema borra automáticamente los tipos de cambio de las divisas de contabilidad y de notificación, si ya se han definido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
