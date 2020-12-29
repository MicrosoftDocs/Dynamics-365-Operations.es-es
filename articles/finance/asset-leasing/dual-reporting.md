---
title: Informes duales
description: Este tema le guía a través de un ejemplo que muestra cómo puede cumplir con los requisitos para la presentación de informes de la Norma Internacional de Información Financiera (IFRS) y la presentación de informes legales en el arrendamiento de activos.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447791"
---
# <a name="dual-reporting"></a>Informes duales

[!include [banner](../includes/banner.md)]

Este tema le guía a través de un ejemplo que muestra cómo puede cumplir con los requisitos para la presentación de informes de la Norma Internacional de Información Financiera (IFRS) y la presentación de informes legales en el arrendamiento de activos. Es necesaria la familiaridad con las capas de registro en Microsoft Dynamics 365 Finance y facilitará la comprensión del ejemplo.

## <a name="example"></a>Ejemplo

El siguiente ejemplo contabiliza un arrendamiento según la información legal italiana utilizando tanto el método de base de efectivo como los métodos de informes IFRS. La empresa debe establecer tres libros para dar cuenta tanto de los requisitos legales italianos como de los requisitos del IFRS 16. Se requiere un libro para IFRS 16, un libro para los requisitos legales y un libro para revertir automáticamente las contabilizaciones legales. Los libros se configuran como se muestra en las siguientes tablas.

**Libro IFRS 16**

El libro IFRS 16 está configurado de manera que cumpla con el estándar contable IFRS 16. Todas las entradas que se publican en este libro se publicarán en una capa personalizada.

| Nombre                                    | Descripción    |
|-----------------------------------------|----------------|
| Tipo de libro                               | IFRS 16        |
| Descripción del libro                        | IFRS 16        |
| Capa de registro                           | Capa personalizada 1 |
| Tipo de arrendamiento                              | Finance        |
| Marco de contabilidad                    | IFRS 16        |
| Configuración del plazo del arrendamiento/vida útil         | 0,00           |
| Configuración del valor actual/valor razonable del activo | 0,00           |
| Umbral a corto plazo                    | 12             |
| Umbral de valor bajo                     | 5,000.00       |
| Pagar a proveedor                           | N.º             |

**Libro legal**

El libro legal es un libro de efectivo en el que la empresa contabilizará los gastos de arrendamiento como la cantidad de efectivo que se paga cada mes por el alquiler. Este libro no producirá un activo por derecho de uso (ROU) ni un pasivo por arrendamiento.

| Nombre                                    | Descripción |
|-----------------------------------------|-------------|
| Tipo de libro                               | Legal   |
| Descripción del libro                        | GAAP local  |
| Capa de registro                           | Actuales     |
| Tipo de arrendamiento                              | Automático   |
| Marco de contabilidad                    | Base en efectivo  |
| Configuración del plazo del arrendamiento/vida útil         | 0,00        |
| Configuración del valor actual/valor razonable del activo | 0,00        |
| Umbral a corto plazo                    | 0           |
| Umbral de valor bajo                     | 0           |
| Pagar a proveedor                           | N.º          |

**Libro de revocación legal**

El libro de revocación legal se configura de la misma manera que el libro legal.

| Nombre                                    | Descripción                    |
|-----------------------------------------|--------------------------------|
| Tipo de libro                               | Legal: revocación           |
| Descripción del libro                        | Libro para revocar el libro legal |
| Capa de registro                           | Capa personalizada 1                 |
| Tipo de arrendamiento                              | Automático                      |
| Marco de contabilidad                    | Base en efectivo                     |
| Configuración del plazo del arrendamiento/vida útil         | 0,00                           |
| Configuración del valor actual/valor razonable del activo | 0,00                           |
| Umbral a corto plazo                    | 0                              |
| Umbral de valor bajo                     | 0                              |
| Pagar a proveedor                           | N.º                             |

Para este ejemplo, se ha creado un arrendamiento con la siguiente configuración en las pestañas **General** y **Líneas de programación de pagos**.

**Pestaña General**

| Campo                      | Valor            |
|----------------------------|------------------|
| Tipo de interés incremental del endeudamiento | 5%               |
| Fecha de inicio          | 1/1/2020         |
| Grupo de arrendamiento                | Edificios        |
| Proveedor                     | 1001             |
| Valor razonable del activo    | 245,000          |
| Vida útil del activo          | 120              |
| Tipo de anualidad               | Anualidad ordinaria |
| Intervalo de composición       | Mensual          |

**Pestaña Líneas de programación de pagos**

| Campo             | Valor      |
|-------------------|------------|
| Fecha inicial        | 1/1/2020   |
| Intervalo del período   | Meses     |
| Períodos           | 24         |
| Fecha final          | 31/12/2020 |
| Frecuencia de pago | Mensual    |
| Importe del pago    | 1.000      |

Para contabilizar este arrendamiento en dos marcos, use una capa de registro actual y una capa de registro personalizada. La siguiente tabla muestra un ejemplo de cada entrada de diario que requiere representar correctamente las finanzas bajo cada estándar de informes. Posteriormente se proporciona una descripción detallada de cada movimiento del diario correspondiente al primer mes del arrendamiento.

<table>
<thead>
<tr>
<th rowspan='3'>Número de cuenta</th>
<th rowspan='3'>Descripción</th>
<th colspan='3'>Libro legal (capa actual)</th>
<th rowspan='3'>Total de la capa actual</th>
<th>Libro de revocación (capa personalizada)</th>
<th colspan='4'>Libro IFRS 16 (capa personalizada)</th>
<th rowspan='3'>Capa actual + Total de capa personalizada</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
<th>JE-130</th>
<th>JE-140</th>
<th>JE-150</th>
<th>JE-160</th>
<th>JE-170</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Gasto de arrendamiento</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
<td>-1.000,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>2</td>
<td>Comisión bancaria</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Gasto de iVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Cuenta de compensación</td>
<td>-1.000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
<td>1,000.00</td>
<td></td>
<td>-1.000,00</td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Proveedores</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Activo por derecho de uso</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>22,794.00</td>
<td></td>
<td></td>
<td></td>
<td>22,793.90</td>
</tr>
<tr>
<td>7</td>
<td>Obligación de arrendamiento financiero</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td>-22.794,00</td>
<td>1,000.00</td>
<td>-94,97</td>
<td></td>
<td>-21.888,87</td>
</tr>
<tr>
<td>8</td>
<td>Gastos de intereses</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td>94.97</td>
<td></td>
<td>94.97</td>
</tr>
<tr>
<td>9</td>
<td>Efectivo</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Gasto de depreciación</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>949.75</td>
<td>949.75</td>
</tr>
<tr>
<td>11</td>
<td>Depreciación acumulada</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td>-949,75</td>
<td>-949,75</td>
</tr>
</tbody>
</table>

Como muestra la tabla anterior, se requieren tres libros para informar tanto según los informes legales como según los informes IFRS.

- El libro legal registra el pago del arrendamiento de acuerdo con las reglas para la contabilidad de efectivo en la capa actual.
- El libro de revocación legal revierte los asientos del diario legal.
- El libro IFRS 16 crea los asientos de diario que se requieren según IFRS 16.

Debe introducir cada arrendamiento solo una vez. A continuación, puede abrir la página **Libros** para ver todos los libros asociados con el arrendamiento.

> [!NOTE]
> Cuando crea los libros, los tres deben estar asociados con el mismo registro de arrendamiento.

La primera entrada de diario registra el gasto de arrendamiento en el libro legal. Puede crear los pagos en un lote o seleccionando la programación de pagos en el libro legal.

Para este ejemplo, se produce el siguiente movimiento de diario para el libro legal a partir de la programación de pagos.

### <a name="lease-payment--1312020--je-100"></a>Pago de arrendamiento - 31/1/2020 - JE 100

| Tipo de cuenta | Número de cuenta | Capa   | Descripción de cuenta | Débito    | Crédito   |
|--------------|----------------|---------|---------------------|----------|----------|
| Contabilidad       | 1              | Actuales | Gasto de arrendamiento       | 1,000.00 |          |
| Contabilidad       | 4              | Actuales | Cuenta de compensación    |          | 1,000.00 |

Un empleado de la sección de proveedores utiliza la funcionalidad estándar de Dynamics 365 para crear una factura para pagar el arrendamiento por fuera del arrendamiento de activos. Sin embargo, en lugar de seleccionar **Gastos de arrendamiento** como cuenta de débito, el empleado de la sección de proveedores selecciona una cuenta de compensación para generar la siguiente entrada.

### <a name="ap-process--1312020--je-110"></a>Proceso AP - 31/1/2020 - JE 110

| Tipo de cuenta | Número de cuenta | Capa   | Descripción de cuenta | Débito    | Crédito   |
|--------------|----------------|---------|---------------------|----------|----------|
| Contabilidad       | 4              | Actuales | Cuenta de compensación    | 1,000.00 |          |
| Contabilidad       | 2              | Actuales | Comisión bancaria            | 3.00     |          |
| Contabilidad       | 3              | Actuales | Gasto de iVA         | 5.00     |          |
| Proveedor       | 5              | Actuales | Proveedores    |          | 1,008.00 |

Cuando se envía el estado de cuenta al proveedor, se sigue el proceso de pago habitual. Durante este proceso, se genera la siguiente entrada de diario.

### <a name="cash-payment--1312020--je-120"></a>Pago en efectivo - 31/1/2020 - JE 120

| Tipo de cuenta | Número de cuenta | Capa   | Descripción de cuenta | Débito    | Crédito   |
|--------------|----------------|---------|---------------------|----------|----------|
| Proveedor       | 5              | Actuales | Proveedores    | 1,008.00 |          |
| Banco         | 9              | Actuales | Efectivo                |          | 1,008.00 |

En este punto, ha contabilizado completamente este contrato de arrendamiento según los requisitos de informes legales y puede generar un balance de prueba utilizando la capa actual. El sistema devuelve un saldo de comprobación que tiene las siguientes cifras.

<table>
<thead>
<tr>
<th rowspan='3'>Número de cuenta</th>
<th rowspan='3'>Descripción</th>
<th colspan='3'>Libro legal (capa actual)</th>
<th rowspan='3'>Total de la capa actual</th>
</tr>
<tr>
<th>JE-100</th>
<th>JE-110</th>
<th>JE-120</th>
</tr>
<tr>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
<th>Dr (Cr)</th>
</tr>
</thead>
<tbody>
<tr>
<td>1</td>
<td>Gasto de arrendamiento</td>
<td>1,000.00</td>
<td></td>
<td></td>
<td>1,000.00</td>
</tr>
<tr>
<td>2</td>
<td>Comisión bancaria</td>
<td></td>
<td>3.00</td>
<td></td>
<td>3.00</td>
</tr>
<tr>
<td>3</td>
<td>Gasto de iVA</td>
<td></td>
<td>5.00</td>
<td></td>
<td>5.00</td>
</tr>
<tr>
<td>4</td>
<td>Cuenta de compensación</td>
<td>-1.000,00</td>
<td>1,000.00</td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>5</td>
<td>Proveedores</td>
<td></td>
<td>-1.008,00</td>
<td>1,008.00</td>
<td>0,00</td>
</tr>
<tr>
<td>6</td>
<td>Activo por derecho de uso</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>7</td>
<td>Obligación de arrendamiento financiero</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>8</td>
<td>Gastos de intereses</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>9</td>
<td>Efectivo</td>
<td></td>
<td></td>
<td>-1.008,00</td>
<td>-1.008,00</td>
</tr>
<tr>
<td>10</td>
<td>Gasto de depreciación</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
<tr>
<td>11</td>
<td>Depreciación acumulada</td>
<td></td>
<td></td>
<td></td>
<td>0,00</td>
</tr>
</tbody>
</table>

Si desea utilizar las cifras IFRS 16 para ejecutar el mismo saldo de comprobación, los asientos del diario contable legal deben revertirse y los asientos del diario de IFRS 16 deben contabilizarse. Para revertir las entradas de diario legales, este ejemplo incluye un libro de revocación legal que tiene la misma configuración que el libro legal pero un perfil de contabilización opuesto. Por ejemplo, el libro legal *adeuda* una cuenta de gastos de arrendamiento, pero el libro de revocación *abona* esta cuenta. Estas relaciones se definen fácilmente en las cuentas de contabilización de arrendamiento de activos en la página **Parámetros de arrendamiento de activos** (**Arrendamiento de activos \> Configurar \> Parámetros de arrendamiento de activos**).

Cuando se utiliza el mismo proceso que se utilizó para el libro legal para el libro de revocación, se produce el siguiente asiento de diario. La diferencia es que el libro de revocación registra las entradas de revocación del libro legal. Las entradas de revocación también se realizan en la capa personalizada. Cuando se ejecuta un saldo de comprobación en la capa actual, las entradas del diario de revocación no se incluyen.

### <a name="lease-payment--1312020--je-130"></a>Pago de arrendamiento - 31/1/2020 - JE 130

| Tipo de cuenta | Número de cuenta | Capa  | Descripción de cuenta | Débito    | Crédito   |
|--------------|----------------|--------|---------------------|----------|----------|
| Contabilidad       | 4              | Personalizado | Cuenta de compensación    | 1,000.00 |          |
| Contabilidad       | 1              | Personalizado | Gasto de arrendamiento       |          | 1,000.00 |

Ahora que ha eliminado las entradas del diario legal, registrará todas las entradas de diario que requiere IFRS 16 en el libro de IFRS 16. Estas entradas incluyen el reconocimiento inicial del activo por derecho de uso y el pasivo de ROU, y el registro de intereses y depreciación.

### <a name="initial-recognition--112020--je-140"></a>Reconocimiento inicial - 1/1/2020 - JE 140

| Tipo de cuenta | Número de cuenta | Capa  | Descripción de cuenta      | Débito     | Crédito    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| Contabilidad       | 6              | Personalizado | Activo por derecho de uso                | 22,793.90 |           |
| Contabilidad       | 7              | Personalizado | Obligación de arrendamiento financiero |           | 22,793.90 |

El pago del arrendamiento se contabiliza como los demás pagos de arrendamiento. La razón para utilizar la cuenta de compensación es garantizar que el efectivo se abone solo una vez.

### <a name="lease-payment--1312020--je-150"></a>Pago de arrendamiento - 31/1/2020 - JE 150

| Tipo de cuenta | Número de cuenta | Capa  | Descripción de cuenta      | Débito    | Crédito   |
|--------------|----------------|--------|--------------------------|----------|----------|
| Contabilidad       | 7              | Personalizado | Obligación de arrendamiento financiero | 1,000.00 |          |
| Contabilidad       | 4              | Personalizado | Cuenta de compensación         |          | 1,000.00 |

El asiento de diario de gasto por intereses se genera a partir de la programación de amortización del pasivo.

### <a name="interest-expense--1312020--je-160"></a>Gastos de intereses - 31/1/2020 - JE 160

| Tipo de cuenta | Número de cuenta | Capa  | Descripción de cuenta      | Débito | Crédito |
|--------------|----------------|--------|--------------------------|-------|--------|
| Contabilidad       | 8              | Personalizado | Gastos de intereses         | 94.97 |        |
| Contabilidad       | 7              | Personalizado | Obligación de arrendamiento financiero |       | 94.97  |

El asiento de diario de gasto por depreciación se genera a partir de la programación de depreciación de activos.

### <a name="depreciation-expense--1312020--je-170"></a>Gasto de depreciación - 31/1/2020 - JE 170

| Tipo de cuenta | Número de cuenta | Capa  | Descripción de cuenta      | Débito  | Crédito |
|--------------|----------------|--------|--------------------------|--------|--------|
| Contabilidad       | 10             | Personalizado | Gasto de depreciación     | 949.75 |        |
| Contabilidad       | 11             | Personalizado | Depreciación acumulada |        | 949.75 |

Después de crear y publicar todas estas entradas del diario, verá los siguientes valores de "capa personaliada 1". Tenga en cuenta que la última columna incluye la comisión bancaria, el gasto del impuesto sobre el valor añadido (IVA) y la reducción de efectivo de la capa anterior, pero no incluye los asientos del diario de informes legales. Por lo tanto, logrará verdaderas capacidades de informes dobles. En este momento, la empresa solo tiene que ejecutar su saldo de comprobación y combinar la capa actual y la capa personalizada para crear un saldo de comprobación IFRS.

| Número de cuenta | Descripción              | Libro legal\-Capa actual\-JE\-100\-Dr \(Cr\) | Libro legal\-Capa actual\-JE\-110\-Dr \(Cr\) | Libro legal\-Capa actual\-JE\-120\-Dr \(Cr\) | Capa actual \- Totales | - | Libro de revocación\-Capa personalizada\-JE\-130\-Dr \(Cr\) | Libro IFRS 16\-Capa personalizada\-JE\-140\-Dr \(Cr\) | Libro IFRS 16\-Capa personalizada\-JE\-150\-Dr \(Cr\) | Libro IFRS 16\-Capa personalizada\-JE\-160\-Dr \(Cr\) | Libro IFRS 16\-Capa personalizada\-JE\-170\-Dr \(Cr\) | Capa actual \+ Capa personalizada \- Totales |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| 1          | Gasto de arrendamiento            | 1,000\.00                                         |                                                   |                                                   | 1,000\.00               |   | \-1.000                                         |                                                |                                                |                                                |                                                | 0\.00                                   |
| 2          | Comisión bancaria                 |                                                   | 3\.00                                             |                                                   | 3\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 3\.00                                   |
| 3          | Gasto de iVA              |                                                   | 5\.00                                             |                                                   | 5\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 5\.00                                   |
| 4          | Cuenta de compensación         | \-1.000\.00                                       | 1,000\.00                                         |                                                   | 0\.00                   |   | 1.000                                           |                                                | \-1.000                                        |                                                |                                                | 0\.00                                   |
| 5          | Proveedores         |                                                   | \-1.008\.00                                       | 1,008\.00                                         | 0\.00                   |   |                                                 |                                                |                                                |                                                |                                                | 0\.00                                   |
| 6          | Activo por derecho de uso                |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | 22,794                                         |                                                |                                                |                                                | 22,793\.90                              |
| 7          | Obligación de arrendamiento financiero |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 | \-22.794                                       | 1.000                                          | \-94\.97                                       |                                                | \-21.888\.87                            |
| 8          | Gastos de intereses         |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                | 94\.97                                         |                                                | 94\.97                                  |
| 9          | Efectivo                     |                                                   |                                                   | \-1.008\.00                                       | \-1.008\.00             |   |                                                 |                                                |                                                |                                                |                                                | \-1.008\.00                             |
| 10         | Gasto de depreciación     |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | 949\.75                                        | 949\.75                                 |
| 11         | Depreciación acumulada |                                                   |                                                   |                                                   | 0\.00                   |   |                                                 |                                                |                                                |                                                | \-949\.75                                      | \-949\.75                               |


