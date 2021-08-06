---
title: Propuesta de finalización de arrendamiento
description: Este tema explica cómo proponer la rescisión de un arrendamiento.
author: moaamer
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseTerminateLeaseListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 003eaa3f9e5ad653daed2e973044f384972b0331
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638497"
---
# <a name="propose-a-lease-for-termination"></a>Proponer un arrendamiento para su rescisión

[!include [banner](../includes/banner.md)]

Si un arrendamiento se rescinde anticipadamente, el arrendamiento de activos puede registrar un asiento de rescisión en el diario para cancelar el pasivo por arrendamiento, el activo por derecho de uso (ROU) y la depreciación acumulada, y registrar una ganancia o una pérdida. El proceso de rescisión anticipada finaliza un arrendamiento y los libros de arrendamiento asociados. No rescinde los libros de arrendamiento individuales. Este tema describe la funcionalidad que le permite proponer un arrendamiento para rescisión y procesar el asiento de diario de rescisión del arrendamiento.

Si un arrendamiento no está clasificado como arrendamiento con tratamiento de arrendamiento diferido y no está asociado con un activo fijo, el arrendamiento de activos produce el siguiente asiento de rescisión en el diario.

| Transacción                           | Débito (Dr.) | Crédito (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Pasivo por arrendamiento                   | X           |              |
| Depreciación acumulada Dr.          | X           |              |
| Dr. Ganancias (pérdidas) en modificación de arrendamiento | X           |              |
| Cr. Activo de arrendamiento                       |             | X            |
| Cr. Ganancias (pérdidas) en modificación de arrendamiento |             | X            |

Si el libro de arrendamiento se clasifica como un libro de arrendamiento diferido, el asiento cancela el saldo del arrendamiento diferido antes de la finalización en la cuenta de pérdidas o ganancias, como se muestra aquí.

| Transacción                           | Débito (Dr.) | Crédito (Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. Arrendamiento diferido                     | X           |              |
| Cr. Ganancias (pérdidas) en modificación de arrendamiento |             | X            |
| Cr. Arrendamiento diferido                     |             | X            |
| Dr. Ganancias (pérdidas) en modificación de arrendamiento | X           |              |

Si el libro de arrendamiento está conectado a un activo fijo, el activo por derecho de uso se contabiliza en Activos fijos. Esta contabilidad incluye la contabilidad de las rescisiones anticipadas. El arrendamiento de activos produce el siguiente asiento de diario para cancelar el pasivo por arrendamiento.

| Transacción                           | Débito (Dr.) | Crédito (Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. Pasivo por arrendamiento                   | X           |              |
| Cr. Ganancias (pérdidas) en modificación de arrendamiento |             | X            |

Para obtener información sobre la forma correcta de deshacerse de un activo por derecho de uso, consulte [Retirar un activo fijo como desechado](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md).

## <a name="propose-a-lease-for-termination"></a>Proponer un arrendamiento para su rescisión

1. Vaya al contrato de arrendamiento que debe rescindirse y, en el panel de acciones, seleccione **Propuesta de rescisión**.

    > [!NOTE]
    > El botón **Propuesta de rescisión** no está disponible si hay entradas de diario sin registrar en algún libro. Antes de que pueda rescindir el arrendamiento, debe publicar o eliminar cualquier asiento de diario que se haya creado para el arrendamiento.

2. En el cuadro de diálogo que aparece, configure los campos **Fecha de vigencia** y **Fecha de registro** para la entrada del diario de rescisión.
3. Seleccione **Propuesta de rescisión** para proponer la rescisión del contrato de arrendamiento.
4. Seleccione **Tras rescisión de arrendamiento** para registrar automáticamente el asiento del diario de rescisión del arrendamiento.
5. En la página **Rescisiones de arrendamiento**, seleccione el id. del arrendamiento cuya rescisión ha propuesto para ver las líneas de rescisión. Las líneas de rescisión muestran los valores en libros del activo por derecho de uso, el pasivo por arrendamiento, la depreciación acumulada, el arrendamiento diferido (si corresponde) y la ganancia o pérdida que deben reconocerse al rescindir el arrendamiento.

El contrato de arrendamiento ya está listo para su rescisión. El valor del campo **Estado de rescisión** del libro de arrendamiento cambia a **Listo para la rescisión**. En este punto, ya no se pueden contabilizar asientos de diario para el arrendamiento, ni ajustarlo o perjudicarlo. 

## <a name="process-leases-that-are-ready-for-termination"></a>Procesar arrendamientos que están listos para su rescisión

Para procesar los arrendamientos que están listos para su rescisión y registrar el asiento del diario de rescisión, siga estos pasos.

1. En la página **Rescisiones de arrendamiento**, seleccione el arrendamiento que desea procesar y, a continuación, seleccione **Rescindir**.
2. En el cuadro de diálogo que aparece, seleccione **Aceptar**.

El sistema registra el movimiento de diario de rescisión. El campo **Estado de arrendamiento** del libro de arrendamiento se establece en **Rescindido** y el campo **Estado de la propuesta de rescisión** se establece en **Rescindido**.

## <a name="reverse-a-lease-termination"></a>Revertir la rescisión de un arrendamiento

Para revertir un movimiento de diario de rescisión de arrendamiento y abrir un arrendamiento rescindido, siga este paso.

- En la página **Rescisiones de arrendamiento**, seleccione el arrendamiento rescindido que desea revertir y, a continuación, seleccione **Revertir rescisión**.

El sistema revierte el movimiento de diario de rescisión. El campo **Estado de arrendamiento** del libro de arrendamiento se establece en **Abierto**. El contrato de arrendamiento ya no aparece en la página **Rescisiones de arrendamiento** y se puede proponer nuevamente para su rescisión.

## <a name="example-of-a-lease-termination"></a>Ejemplo de rescisión de arrendamiento

En este ejemplo, el arrendamiento está asociado con un activo no especializado que no transfiere la propiedad del activo ni otorga al arrendatario la opción de compra del activo.

### <a name="setup"></a>Configurar

Las siguientes tablas muestran los valores que se establecen en las pestañas **General** y **Líneas de programación de pagos** para el arrendamiento que se utiliza en este ejemplo.

**Pestaña General**

| Campo                      | Valor            |
|----------------------------|------------------|
| Valor razonable del activo    | 600,000          |
| Divisa                   | USD              |
| Costes directos iniciales       | 1.000            |
| Tipo de interés incremental del endeudamiento | 7 %               |
| Intervalo de composición       | Anual         |
| Vida útil del activo (meses) | 600              |
| Tipo de anualidad               | Anualidad ordinaria |
| Fecha de inicio          | 1/1/2019         |

**Pestaña Líneas de programación de pagos**

| Campo             | Valor      |
|-------------------|------------|
| Fecha inicial        | 1/1/2019   |
| Intervalo del período   | Mensual    |
| Períodos           | 120        |
| Fecha final          | 31/12/2028 |
| Frecuencia de pago | Anual   |
| Importe del pago    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>Pasos para rescindir el contrato de arrendamiento

1. Después de crear el arrendamiento como se describió anteriormente en este tema, vaya al libro de arrendamiento y confirme la programación de pagos. Luego publique la entrada del diario de reconocimiento inicial. El activo por derecho de uso inicial es de 71 235,81 $ y el pasivo por arrendamiento debe ser de 70 235,81 $. Para este ejemplo, el arrendamiento se clasificó como un arrendamiento operativo según el Tema 842 de codificación de normas de contabilidad (ASC 842).
2. Ejecute el proceso de diario por lotes tres veces para simular el paso de tres años para los pagos por arrendamiento, los gastos por intereses y los gastos de depreciación.
3. Una vez que haya terminado de ejecutar los tres trabajos por lotes, vuelva al libro de arrendamiento y abra las tablas de transacciones de activos y pasivos para ver el valor en libros actual del activo por derecho de uso y el pasivo por arrendamiento. Después de tres años, el valor del pasivo debe ser de aproximadamente -53.893,00 $ y el valor del activo debe ser de aproximadamente 54.593,00 $.

    Una vez transcurridos los tres años, la empresa y el arrendador acuerdan mutuamente rescindir el contrato de arrendamiento. Por lo tanto, ahora debe rescindir el contrato de arrendamiento.

4. Vaya al contrato de arrendamiento que debe rescindirse y, en el panel de acciones, seleccione **Propuesta de rescisión**. 
5. En el cuadro de diálogo que aparece, en los campos **Fecha efectiva** y **Fecha de registro**, introduzca **1/1/2021**.
6. Seleccione **Propuesta de rescisión** para proponer la rescisión del contrato de arrendamiento.

    Aparece la página **Rescisiones de arrendamiento** y muestra el contrato de arrendamiento que se va a rescindir.

7. Para ver las líneas de rescisión, seleccione el id. del arrendamiento cuya rescisión ha propuesto. Las líneas de rescisión muestran los valores en libros del arrendamiento. La tabla siguiente muestra cuáles deberían ser estos valores para este ejemplo. 

    | Campo                                                 | Valor      |
    |-------------------------------------------------------|------------|
    | Saldo en libros del pasivo en la divisa de la transacción | 53 892,89 $ |
    | Activo por derecho de uso en la moneda de la transacción            | 71 235,81 $ |
    | Depreciación acumulada en la divisa de la transacción      | 16 642,92 $ |
    | Ganancias (pérdidas) en la divisa de transacción                   | -700,00 $   |

8. Para registrar el movimiento de diario de rescisión, seleccione el arrendamiento en la página **Rescisiones de arrendamiento** y, a continuación, seleccione **Rescindir**.
9. En el cuadro de diálogo que aparece, seleccione **Aceptar**.
10. Para ver el movimiento de diario de rescisión que se ha creado y registrado, vaya al diario de arrendamiento del activo en el libro de arrendamiento. La tabla siguiente muestra cómo debería ser este movimiento para este ejemplo.

    | Transacción                           | Débito (Dr.) | Crédito (Cr.) |
    |---------------------------------------|-------------|--------------|
    | Dr. Pasivo por arrendamiento                   | 53,892.89   |              |
    | Depreciación acumulada Dr.          | 16,642.92   |              |
    | Dr. Ganancias (pérdidas) en modificación de arrendamiento | 700.00      |              |
    | Cr. Activo de arrendamiento                       |             | 71,235.81    |

11. Para ver el efecto neto de la rescisión, donde el activo por derecho de uso y el pasivo por arrendamiento serán 0 (cero), abra las tablas de transacciones de pasivo y activo.

Ahora el estado de arrendamiento debería ser **Rescindido**. No se registrarán movimientos adicionales en el diario para este contrato de arrendamiento, a menos que se revierta la rescisión.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
