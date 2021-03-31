---
title: Tipos de registro de arrendamientos
description: Este tema describe los tipos de registro que se utilizan para transacciones de arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b7d8c545c1addaa570d54855bbad6c576783007
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229511"
---
# <a name="lease-posting-types"></a>Tipos de registro de arrendamientos

[!include [banner](../includes/banner.md)]

Este tema describe los tipos de registro que se utilizan para transacciones de arrendamiento de activos.

## <a name="lease-asset"></a>Activo de arrendamiento

La cuenta está asociada con el activo por derecho de uso (ROU). Esta cuenta se carga cuando un arrendamiento se reconoce inicialmente según los nuevos estándares de contabilidad de arrendamientos, el Tema de codificación de normas de contabilidad 842 (ASC 842) y la Norma Internacional de Información Financiera 16 (IFRS 16). Para un arrendamiento modificado, esta cuenta puede ser adeudada o abonada, dependiendo de si la modificación aumenta o disminuye el pasivo por arrendamiento.

**Movimientos de diario de ejemplo:** reconocimiento inicial<br>
**Débito:** activo por arrendamiento XXX<br>
**Crédito:** pasivo por arrendamiento XXX

## <a name="lease-liability"></a>Pasivo por arrendamiento

La cuenta está asociada con el pasivo por arrendamiento que ocurre cuando los pagos se descuentan según las nuevas normas IFRS 16 y ASC 842. Esta cuenta se acredita cuando un arrendamiento se reconoce inicialmente bajo las nuevas normas. Se adeuda para los pagos por arrendamiento y se abona para los intereses acumulados.

**Movimientos de diario de ejemplo:** reconocimiento inicial<br>
**Débito:** activo por arrendamiento XXX<br>
**Crédito:** pasivo por arrendamiento XXX

**Entradas de diario de ejemplo:** intereses acumulados<br>
**Débito:** gasto por intereses XXX<br>
**Crédito:** pasivo por arrendamiento XXX

**Entradas de diario de ejemplo:** pago por arrendamiento<br>
**Débito:** pasivo por arrendamiento XXX<br>
**Crédito:** pagable a proveedores/pago por arrendamiento XXX

## <a name="short-term-lease-liability"></a>Pasivo por arrendamiento a corto plazo

La cuenta está asociada con el pasivo por arrendamiento a corto plazo cuando se contabiliza el asiento de diario de reclasificación del pasivo por arrendamiento a corto plazo. A esta cuenta se le abona el pasivo a corto plazo del programa de amortización el último día del mes. Sin embargo, la misma cantidad se carga el primer día del mes siguiente.

**Entradas de diario de ejemplo:** reclasificación del pasivo por arrendamiento a corto plazo<br>
**Débito:** pasivo por arrendamiento XXX<br>
**Crédito:** pasivo por arrendamiento a corto plazo XXX<br>
**Débito:** pasivo por arrendamiento a corto plazo XXX<br>
**Crédito:** pasivo por arrendamiento XXX

## <a name="depreciation-expense"></a>Gasto de depreciación

La cuenta está asociada con el gasto que está relacionado con la depreciación del activo por derecho de uso según IFRS 16, ASC 842 y arrendamientos financieros según IAS 17 y ASC 840. Esta cuenta se carga cuando un aactivo por derecho de uso se deprecia cada mes.

**Entradas de diario de ejemplo:** depreciación acumulada<br>
**Débito:** gasto de depreciación XXX<br>
**Crédito** depreciación acumulada XXX

## <a name="gainloss-on-lease-modification"></a>Ganancias y pérdidas en modificación de arrendamiento

La cuenta está asociada con cualquier ganancia o pérdida que surja de las modificaciones del arrendamiento. Puede surgir una ganancia durante una modificación de arrendamiento si la modificación disminuye el pasivo por arrendamiento en una cantidad que exceda el valor en libros del activo por derecho de uso.

Por ejemplo, un arrendamiento tiene un valor en libros actual del pasivo por arrendamiento de 150.000 $ y un valor en libros del activo por derecho de uso de 100.000 $. El arrendamiento se modifica y esta modificación produce un nuevo valor presente de los pagos mínimos futuros del arrendamiento (PVFMLP) de 40.000 $. Por lo tanto, el pasivo del arrendamiento se cargará con 110.000 $ (150.000 $ - 40.000 $). Dado que el activo por derecho de uso es de solo 100.000 $, la disminución de 110.000 $ disminuirá el activo más allá de 0 (cero). Por lo tanto, la guía contable establece que el resto debe registrarse en una cuenta de ganancias. En este caso, el movimiento final del diario será un adeudo al pasivo por arrendamiento por 110.000 $, un abono al activo por arrendamiento por 100.000 $ y un abono a la cuenta de ganancias por 10.000 $.

**Entradas de diario de ejemplo:** modificación de arrendamiento<br>
**Débito:** pasivo por arrendamiento XXX<br>
**Crédito:** activo por arrendamiento XXX<br>
**Crédito:** ganancia XXX

## <a name="accumulated-depreciation"></a>Depreciación acumulada

La cuenta está asociada con la cuenta enfrentada al activo del activo por derecho de uso. Se abonará en esta cuenta cuando se registre un gasto de depreciación.

**Entradas de diario de ejemplo:** depreciación acumulada<br>
**Débito:** gasto de depreciación XXX<br>
**Crédito:** depreciación acumulada XXX

## <a name="retained-earnings"></a>Ganancias retenidas

La cuenta que está asociada con los ingresos retenidos. Esta cuenta puede adeudarse o abonarse en un movimiento de diario de ajuste de transición utilizando el método retrospectivo completo o el método de opción A de recuperación acumulativa. La diferencia entre el activo por derecho de uso inicial y el pasivo por arrendamiento se registra en los ingresos retenidos. En casos raros, las ganancias retenidas también pueden verse afectadas durante la modificación del arrendamiento, si la clasificación de un arrendamiento se cambia de financiero a operativo para registrar un aumento o disminución del activo por derecho de uso para que sea igual al pasivo por arrendamiento.

**Entradas de diario de ejemplo:** ajuste de transición (método de opción A de recuperación total retrospectiva o acumulativa)<br>
**Débito:** pasivo por arrendamiento XXX<br>
**Crédito:** activo por arrendamiento XXX<br>
**Crédito:** ingresos retenidos XXX

## <a name="variable-payment"></a>Pago variable

La cuenta está asociada con los pagos de arrendamiento variables que se producen por una revalorización del índice en arrendamientos ASC 842, ASC 840 e IAS 17. En la programación de pagos de arrendamiento, los pagos variables se incluyen en la columna **Pago variable**. Esta cuenta se carga cuando se crea una factura contra una línea de programación de pagos que contiene un pago variable.

**Entradas de diario de ejemplo:** pago por arrendamiento<br>
**Débito:** pasivo por arrendamiento XXX<br>
**Débito:** pago variable XXX<br>
**Crédito:** pagable a proveedores/pago por arrendamiento XXX

## <a name="deferred-rent-asset-liability"></a>Activo de arrendamiento diferido (pasivo)

La cuenta está asociada con el activo o pasivo por arrendamiento diferido que se produce por un arrendamiento con tratamiento de arrendamiento diferido. Esta cuenta se adeuda cuando se contabiliza una factura contra un arrendamiento con tratamiento de arrendamiento diferido, si el importe del pago del arrendamiento es mayor que el gasto de alquiler lineal del período. Se abona si el pago del arrendamiento es menor que el gasto de alquiler lineal del período.

**Entradas de diario de ejemplo:** pago de arrendamiento (arrendamiento con tratamiento de arrendamiento diferido)<br>
**Débito:** gastos de arrendamiento XXX<br>
**Crédito** pasivo de arrendamiento diferido XXX<br>
**Crédito:** pagable a proveedores/pago por arrendamiento XXX

## <a name="lease-expense"></a>Gasto de arrendamiento

La cuenta se asocia con el gasto por arrendamiento si el arrendamiento se clasifica como arrendamiento con tratamiento de arrendamiento diferido. Esta cuenta se adeuda cuando se contabiliza una factura contra un contrato de arrendamiento con tratamiento de arrendamiento diferido.

**Entradas de diario de ejemplo:** pago de arrendamiento (arrendamiento con tratamiento de arrendamiento diferido)<br>
**Débito:** gastos de arrendamiento XXX<br>
**Crédito** pasivo de arrendamiento diferido XXX<br>
**Crédito:** pagable a proveedores/pago por arrendamiento XXX

## <a name="impairment-expense"></a>Gasto de deterioro

La cuenta se registra en contra cuando se deteriora un contrato de arrendamiento. Esta cuenta se adeuda, mientras que la cuenta de activos por derecho de uso se abona directamente.

**Entradas de diario de ejemplo:** pago por arrendamiento<br>
**Débito:** gasto de deterioro XXX<br>
**Crédito:** activo por derecho de uso XXX

## <a name="lease-payment"></a>Pago por arrendamiento

La cuenta se registra en contra si el parámetro **Pagar al proveedor** está desactivado. Esta cuenta se abona contra la de pagadero al proveedor si el parámetro está desactivado.

**Entradas de diario de ejemplo:** pago por arrendamiento<br>
**Débito:** pasivo por arrendamiento XXX<br>
**Crédito:** pago de arrendamiento XXX

## <a name="expense-type-postings"></a>Registros de tipo de gasto

La cuenta que se selecciona para cada tipo de gasto se adeuda cuando se genera un pago para ese tipo de gasto. Por ejemplo, la cuenta que se especifica para el tipo de gasto **Seguro** se carga cada vez que se crea una factura o un asiento de diario de pagos a partir de la programación de gastos a cargo del arrendatario en un arrendamiento de capital para gastos de seguro.

**Entradas de diario de ejemplo:** pago por seguro<br>
**Débito:** cuenta de tipo de gasto de seguro XXX<br>
**Crédito:** Cuenta de contrapartida XXX

> [!NOTE]
> La cuenta de contrapartida se selecciona a nivel de arrendamiento en las líneas para el programa de pago de gastos a cargo del arrendatario en un arrendamiento de capital. Esta cuenta de contrapartida se puede asociar con el proveedor o con una cuenta contable.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]