---
title: Reducir la depreciación del saldo después de una división
description: Este tema describe el método que se usa en Activos fijos para calcular la depreciación después de que un activo se haya dividido mediante el método de reducción de saldo.
author: moaamer
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8e59ff1ef2b06a7203c1023bade7f06019479f3929dfbd582860f102c46b49f0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737710"
---
# <a name="reduce-balance-depreciation-after-a-split"></a>Reducir la depreciación del saldo después de una división

[!include [banner](../includes/banner.md)]

Este tema describe el método que se usa en Activos fijos para calcular la depreciación después de que un activo se haya dividido en forma de otro activo mediante el método de reducción de saldo. El año de depreciación que se configura en el libro de activos es el año fiscal. Para más información, consulte [Reducir la depreciación del saldo](reduce-balance-depreciation.md) y [Dividir un activo fijo](tasks/split-fixed-asset.md).

Si divide un activo fijo durante un período fiscal posterior al período en el que se adquirió el activo, la depreciación del saldo reducido contabilizará el valor neto en los libros (NBV) del activo para el año anterior. También tendrá en cuenta las transacciones de ajuste de adquisición y depreciación que se generaron a partir de la transacción que dividió el activo. Este comportamiento supone que el activo se adquirió en un año fiscal y se dividió en un año fiscal posterior. El monto que debe depreciarse para el activo original después de la división refleja el NBV del activo antes de que se dividiera el activo y la transacción de ajuste de adquisición y depreciación que se registró para la división.

Por ejemplo, están en vigor las siguientes condiciones:

- El período fiscal es del 30 de junio al 1 de julio.
- El porcentaje de saldo de reducción es del 18 por ciento, y un activo se adquiere en junio de 2019 a un precio de adquisición de 10.000 $.
- La depreciación del primer año fiscal es igual a 18.000 $, la depreciación mensual es igual a 150 $, y luego el activo se deprecia hasta noviembre de 2019, por un importe de 738,75 $.
- En noviembre de 2019, el 80 por ciento del activo se divide en otro activo fijo.

[![Reducir la depreciación del saldo después de una división.](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)

La cantidad a depreciar del activo original es 1.822,25 $. Esta cantidad es igual al NBV antes de que se contabilice la transacción dividida (9.111,25), más el ajuste de adquisición que se genera durante la contabilización de la transacción dividida (- 8.000 $), más el ajuste de depreciación que se genera durante la transacción dividida (711 $). Por lo tanto, la depreciación para el segundo año es (1.822,25 × 18 por ciento) ÷ 12 = 27,33 $.

La cantidad a depreciar para el nuevo activo fijo en el primer año es (8.000 × 18 por ciento) ÷ 12 = 120 $.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]