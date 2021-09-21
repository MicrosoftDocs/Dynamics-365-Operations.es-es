---
title: El número máximo de decimales para la referencia de almacén es 0
description: 'Al registrar una transacción de inventario o una reserva de inventario, recibe el error: "El número máximo de decimales para la referencia de almacén es 0".'
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9dec198e2d77efd2253c80e14d15791cc37f88e1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477563"
---
# <a name="maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>El número máximo de decimales para la referencia de almacén es 0


## <a name="symptoms"></a>Síntomas

Cuando intenta registrar una transacción de inventario o una reserva de inventario, recibe el siguiente mensaje de error:

> El número máximo de decimales para la referencia de almacén es 0.

Este problema se produce cuando la cantidad de la transacción de inventario se especifica como un valor decimal que está por debajo del nivel de precisión que admite el campo. Por ejemplo, se ha especificado una cantidad de *0,5* para una transacción de inventario, pero solo se admiten cantidades de enteros. Por lo tanto, el valor debe ser *1* en lugar de *0,5*.

## <a name="resolution"></a>Resolución

1. Ejecute el siguiente script en su instancia de SQL Server para redondear cantidades en las transacciones de inventario. Este script corregirá valores en la tabla **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Ejecute una comprobación de coherencia disponible donde la opción **arreglar error** está activada. Esta comprobación corregirá valores en la tabla **inventSum**.

> [!IMPORTANT]
> Recomendamos encarecidamente que edite cuidadosamente el script según sea necesario para su entorno, lo pruebe en un entorno de prueba y luego compruebe los datos resultantes antes de ejecutar el script en un entorno de producción.
