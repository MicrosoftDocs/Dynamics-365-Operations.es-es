---
title: Deteriorar activos por derecho de uso
description: Este tema describe la funcionalidad que registra un deterioro y ajusta el programa de depreciación de activos de un arrendamiento operativo del Tema 842 de Codificación de Normas de Contabilidad (ASC 842).
author: moaamer
ms.date: 12/03/2021
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
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b104cec399a368ada64a73688c42476e6fbd9e52
ms.sourcegitcommit: 304a482dfcc31dcb61849f710ae73432324ddef3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/29/2021
ms.locfileid: "7947349"
---
# <a name="impair-right-of-use-assets"></a>Deteriorar activos por derecho de uso

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Si el valor en libros de un activo por derecho de uso (ROU) no es recuperable, es posible que deba probar si el activo está deteriorado. Si determina que el activo está deteriorado, el arrendamiento de activos puede registrar el deterioro y ajustar el programa de depreciación en consecuencia. Este tema describe la funcionalidad que registra el deterioro y ajusta el programa de depreciación de activos de un arrendamiento operativo del Tema 842 de Codificación de Normas de Contabilidad (ASC 842). El mismo método también se aplica a los arrendamientos de la Norma Internacional de Información Financiera 16 (IFRS 16).

El saldo restante del activo por derecho de uso se amortizará de forma lineal por el número de períodos que queden, independientemente de si el arrendamiento se clasificó como arrendamiento financiero según IFRS 16 o como arrendamiento operativo según ASC 842.

## <a name="impair-an-rou-asset"></a>Deterioro de un activo por derecho de uso

1. Vaya al arrendamiento deteriorado y seleccione **Libros**.
2. En el panel de acciones, seleccione **Deterioro**.
3. En el cuadro de diálogo que aparece, en el campo **Importe del deterioro**, introduzca el importe del deterioro del activo. Para disminuir el activo por derecho de uso, debe introducir un valor positivo.
4. En el campo **Fecha de Transacción**, introduzca la fecha en la que se debe publicar la entrada de deterioro.
5. En el campo **Periodos restantes**, introduzca el número restante de meses para amortizar.
6. Establezca la opción **Vista previa** para ver el saldo de activos propuesto y el movimiento financiero antes de que se creen o publiquen.
7. Establezca la opción **Cerrar libro** en **Sí** para cerrar el libro de arrendamiento. Puede deshacer esta acción utilizando el estado **Reabrir arrendamiento**. Las entradas no se pueden registrar en arrendamientos cerrados y los arrendamientos cerrados no se pueden ajustar. 
8. Seleccione **Publicar** para crear o publicar la entrada de deterioro.

    > [!NOTE]
    > Una vez que se registra la transacción de deterioro, se crea una nueva versión del libro.

    > Si el arrendamiento se clasifica como arrendamiento operativo, la depreciación mensual después del deterioro se calculará utilizando la depreciación lineal.

9. Para ver la programación de depreciación de activos deteriorados, abra la programación de depreciación de activos del libro de arrendameinto en cuestión. El activo ahora se depreciará de forma lineal durante el número de meses que introdujo en el campo **Periodos restantes**.
10. Para ver el asiento de diario de gastos por deterioro, seleccione **Diario de arrendamiento de activos** en el panel de acciones del libro de arrendamiento deteriorado. El sistema crea un asiento de diario que adeuda la cuenta de registro de gastos por deterioro y abona la cuenta de registro de activos de arrendamiento. 
11. Para ver el nuevo valor en libros del activo por derecho de uso, seleccione **Transacciones de activos** en el panel de acciones del libro de arrendamiento.

## <a name="example-of-rou-asset-impairment"></a>Ejemplo de deterioro de activos por derecho de uso

En este ejemplo, el arrendamiento es un activo no especializado que no transfiere la propiedad ni otorga al arrendatario la opción de compra.

### <a name="setup"></a>Configurar

Las siguientes tablas muestran los valores que se establecen en las pestañas **General** y **Líneas de programación de pagos** para el arrendamiento que se utiliza en este ejemplo.

**Pestaña General**

| Campo                      | Valor            |
|----------------------------|------------------|
| Valor razonable del activo    | 600,000          |
| Tipo de interés incremental del endeudamiento | 7 %               |
| Intervalo de composición       | Anual         |
| Vida útil del activo (meses) | 600              |
| Tipo de anualidad               | Anualidad ordinaria |
| Fecha de inicio          | 01/01/2019       |

**Pestaña Líneas de programación de pagos**

| Campo             | Valor      |
|-------------------|------------|
| Fecha inicial        | 1/1/2019   |
| Intervalo del período   | Mensual    |
| Períodos           | 120        |
| Fecha final          | 31/12/2028 |
| Frecuencia de pago | Anual   |
| Importe del pago    | 10,000     |

### <a name="steps"></a>Etapas

1. Después de crear el arrendamiento como se describió anteriormente en este tema, vaya al libro de arrendamiento y confirme la programación de pagos. Luego publique la entrada del diario de reconocimiento inicial. El activo por derecho de uso inicial y el pasivo por arrendamiento deben ser de 70.235,81 $. Para este ejemplo, el arrendamiento se clasificó como arrendamiento operativo según ASC 842.
2. Ejecute el proceso de diario por lotes tres veces para simular el paso de tres años para los pagos por arrendamiento, los gastos por intereses y los gastos de depreciación.
3. Una vez que haya terminado de ejecutar los tres trabajos por lotes, vuelva al libro de arrendamiento y abra las tablas de transacciones de activos y pasivos para ver el valor en libros actual del activo por derecho de uso y el pasivo por arrendamiento. Después de tres años, el valor del pasivo debe ser de aproximadamente -53.893,00 $ y el valor del activo debe ser de aproximadamente 53.893,00 $. 

    Después de tres años, la empresa realiza pruebas de deterioro y determina que el activo por derecho de uso tiene un deterioro de 35.000 $. Ahora debe registrar este deterioro.
    
4. Vaya al libro de arrendamiento y luego, en el panel de acciones, seleccione **Deterioro**.
5. En la página **Parámetro de deterioro**, introduzca los siguientes detalles.

    | Campo                  | Valor    |
    |------------------------|----------|
    | Importe de deterioro      | 35,000   |
    | Fecha movimiento       | 1/1/2022 |
    | Períodos restantes      | 84       |
    | Registrar                   | Sí      |
    | Vista previa antes del registro | No       |
    | Cerrar libro             | No       |

6. Se ha creado y registrado un asiento de diario de gastos por deterioro. Para verlo, vaya al diario de arrendamiento del activo en el libro de arrendamiento. Observe que el importe del deterioro se adeudó en la cuenta de registro de gastos por deterioro y se abonó en la cuenta de registro de activo por derecho de uso.

7. Para ver el efecto neto del deterioro, vaya a las tablas de transacciones de activos y pasivos. Observe que el gasto por deterioro ha disminuido el activo por derecho de uso, pero el valor en libros del pasivo por arrendamiento no ha cambiado.

El deterioro tiene otro efecto que debe considerar. Debido a que el monto del activo por derecho de uso es ahora mucho menor que el pasivo por arrendamiento, el importe debe depreciarse de manera diferente a como era antes. Específicamente, el activo ahora se deprecia de manera lineal durante los 84 meses restantes del arrendamiento, comenzando en la fecha de la transacción.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
