---
title: "Depreciación con amortización degresiva del 200%"
description: "Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 200%."
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 24f677cd3b416c6301a664629cb73e3cbae9f457
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="200-percent-reducing-balance-depreciation"></a>Depreciación con amortización degresiva del 200%

[!include[banner](../includes/banner.md)]


Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 200%.

Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 200%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación. El porcentaje se calcula en función del tiempo de vida del activo. Por ejemplo, si un activo tiene un tiempo de vida de cinco años, el porcentaje se calcula como 40 por ciento (200% ÷ 5). 

Este método se conoce también como doble saldo decreciente.

Para configurar una depreciación con amortización degresiva del 200%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**. Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.

## <a name="select-a-depreciation-year"></a>Selección de un año de depreciación
Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**. El valor predeterminado es **Calendario**. 

La selección determina las opciones disponibles en el campo **Frecuencia de períodos**. Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.

### <a name="calendar"></a>Calendario

Puede elegir mantener el valor predeterminado en el campo **Año de depreciación**, **Calendario**. 

La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año. Normalmente, la depreciación es el valor neto en los libros menos el valor residual. En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos. 

Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra un importe el 31 de diciembre.
-   **Mensual** registra un importe mensual al final de cada mes del calendario.
-   **Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).
-   **Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).
-   **Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.

### <a name="fiscal"></a>Fiscal

Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación degresiva del 200% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**. Los calendarios fiscales se configuran en la página **Calendarios fiscales**. 

Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio. El ejercicio no puede ser superior ni inferior a los 12 meses. La depreciación se ajusta para cada período. La extensión del siguiente ejercicio se determina por los períodos fiscales configurados en la página **Calendarios fiscales**. 

Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.
-   **Período fiscal** registra el importe total de depreciación calculado para el ejercicio. Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.

## <a name="example-of-200-reducing-balance-depreciation"></a>Ejemplo de depreciación degresiva del 200%
|                                |        |
|--------------------------------|--------|
| Coste de adquisición               | 11.000 |
| Valor residual                  | 1.000 |
| Base de depreciación              | 10.000 |
| Años de tiempo de vida             | 5      |
| Porcentaje de depreciación anual | 40%    |

El método de depreciación degresiva del 200% divide el 200 por ciento entre los años de tiempo de vida. El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.

| Periodo | Cálculo del importe de depreciación anual | Valor neto             | Valor neto en los libros al final del año |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| Año 1 | (11.000 – 1.000) × 40% = 4.000                | 11.000 - 4.000 = 7.000 | 11.000 - 1.000 – 4.000 = 6.000        |
| Año 2 | 6.000 × 40% = 2.400                           | 7.000 - 2.400 = 4.600  | 6.000 - 2.400 = 3.600                 |
| Año 3 | 3.600 × 40% = 1.440                           | 4.600 - 1.440 = 3.160  | 3.600 - 1.440 = 2.160                 |

> [!NOTE] 
> Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 200% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.




