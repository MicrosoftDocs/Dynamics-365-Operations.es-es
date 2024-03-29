---
title: Importe completo y opciones de cálculo de intervalo para los códigos de impuestos
description: Este artículo explica las opciones del campo Método de cálculo en códigos de impuestos y cómo se calculan los impuestos para los intervalos y los importes completos.
author: kailiang
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b81780e60825021ad7a700d85257ba0f5a2447a
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715287"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Importe completo y opciones de cálculo de intervalo para los códigos de impuestos

[!include [banner](../includes/banner.md)]

Este artículo explica las opciones del campo **Método de cálculo** en códigos de impuestos y cómo se calculan los impuestos para los intervalos y los importes completos.

Puede configurar un código de impuestos para que se calcule en función de un importe completo o de un importe de intervalo. En la página de **códigos de impuestos**, use el campo **Método de cálculo** en la ficha desplegable **Cálculo** para seleccionar el método de cálculo de un código de impuestos.
- Importe completo: el índice de impuestos se aplica al importe gravable completo.
- Intervalo: el importe gravable se divide en partes, cada una de las cuales pertenece a un intervalo que tenga un índice de impuestos específico. La parte del importe que pertenece a un intervalo determinado se grava según el índice de impuestos para dicho intervalo. Los impuestos son la suma de los importes de impuestos que se calculan para cada importe de intervalo.
  > [!NOTE]                                                                                                                              
  > La opción Intervalo solo está disponible cuando selecciona el campo Método de cálculo en el área Impuestos de la página Parámetros de contabilidad general. 

Los intervalos están colocados en la página de los valores de código de impuestos especificando los importes de límite mínimo y máximo por cada índice de impuestos. Para calcular los impuestos sobre los importes gravables, independientemente del método de cálculo seleccionado, los intervalos deben cumplir las siguientes reglas:
-   El primer intervalo debe tener un límite mínimo de cero.
-   El último intervalo debe tener un límite máximo de cero, que indica infinito.
-   El límite máximo de un intervalo debe ser el límite mínimo del intervalo siguiente.

Si un importe es el límite máximo del intervalo anterior y el límite mínimo del intervalo siguiente, se aplicará al importe el índice de impuestos del primer intervalo. Si un importe se encuentra fuera de los intervalos definidos por los límites superior e inferior, se aplicará un índice de impuestos de cero.

## <a name="example-whole-amount-method-of-calculation"></a>Ejemplo: método de cálculo de importe completo
En la página Valores de código de impuestos, los índices de impuestos se configuran en los siguientes intervalos:

| Límite mínimo     | Límite máximo     | Índice de impuestos     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

Los impuestos se calculan sobre el importe gravable completo.

| Importe gravable (precio) | Cálculo    | Impuestos |
|------------------------|----------------|-----------|
| 35,00                  | 35,00 \* 0,30  | 10,50     |
| 50,00                  | 50,00 \* 0,30  | 15:00     |
| 85,00                  | 85,00 \* 0,20  | 17,00     |
| 305,00                 | 305,00 \* 0,10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a>Ejemplo: método de cálculo de intervalo
En la página Valores, los índices de impuestos se configuran en los siguientes intervalos:

| Límite mínimo     | Límite máximo     | Índice de impuestos     |
|-------------------|-------------------|--------------|
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

Los impuestos son la suma de los importes de impuestos que se calculan para cada importe de intervalo.

| Importe gravable (precio) | Cálculo                                                               | Impuestos |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35,00 \* 0,30                                                             | 10,50     |
| 50,00                  | 50,00 \* 0,30                                                             | 15:00     |
| 85,00                  | (50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)                          | 22,00     |
| 305,00                 | (50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50) | 45.50     |



Para obtener más información, consulte [Impuestos basados en los métodos de Base marginal y Cálculo](marginal-base-field.md)







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
