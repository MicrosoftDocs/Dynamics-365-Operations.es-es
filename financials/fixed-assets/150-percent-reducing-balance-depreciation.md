---
title: "Depreciación con amortización degresiva del 150%"
description: "Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 150%."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 0ec99c4bb0c86b1097a22fdc9785928267b80ade
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="150-percent-reducing-balance-depreciation"></a>Depreciación con amortización degresiva del 150%

[!include[banner](../includes/banner.md)]


Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 150%.

Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 150%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación. Este porcentaje se calcula en función del tiempo de vida del activo. Por ejemplo, si un activo tiene un tiempo de vida de cinco años, el porcentaje se calcula como 30 por ciento (150% ÷ 5). 

Para configurar una depreciación con amortización degresiva del 150%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**. Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.

## <a name="selection-of-depreciation-year"></a>Selección del año de depreciación
Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**. 

El valor predeterminado es **Calendario**. La selección determina las opciones disponibles en el campo **Frecuencia de períodos**. Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.

### <a name="calendar"></a>Calendario

Puede elegir mantener el valor predeterminado en el campo **Año de depreciación**, **Calendario**. 

La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año. Normalmente, la base de depreciación es el valor neto en los libros menos el valor residual. En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos. 

Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra un importe el 31 de diciembre.
-   **Mensual** registra un importe mensual al final de cada mes del calendario.
-   **Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).
-   **Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).
-   **Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.

### <a name="fiscal"></a>Fiscal

Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación decreciente del 150% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**. Los calendarios fiscales se configuran en la página **Calendarios fiscales**. 

Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio. El ejercicio no puede ser superior ni inferior a los 12 meses. La depreciación se ajusta para cada período. La extensión del siguiente ejercicio se determina por los períodos fiscales configurados en la página **Calendarios fiscales**. 

Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra el importe total de la depreciación calculada para el ejercicio en el último día del ejercicio.
-   **Período fiscal** registra el importe total de depreciación calculado para el ejercicio. Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.

## <a name="example-of-150-reducing-balance-depreciation"></a>Ejemplo de depreciación degresiva del 150%
|                                |        |
|--------------------------------|--------|
| Coste de adquisición               | 11.000 |
| Valor residual                  | 1.000  |
| Base de depreciación              | 10.000 |
| Años de tiempo de vida             | 5      |
| Porcentaje de depreciación anual | 30%    |

El método de depreciación degresiva del 150% divide el 150 por ciento entre los años de tiempo de vida. El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.

| Periodo | Cálculo del importe de depreciación anual | Valor neto             | Valor neto en los libros al final del año |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| Año 1 | (11.000 - 1.000) × 30% = 3.000                | 11.000 - 3.000 = 8.000 | 11.000 - 1.000 - 3.000 = 7.000        |
| Año 2 | 7.000 × 30% = 2.100                           | 8.000 – 2.100 = 5.900  | 7.000 – 2.100 = 4.900                 |
| Año 3 | 4.900 × 30% = 1.470                           | 5.900 - 1.470 = 4.430  | 4.900 - 1.470 = 3.430                 |

> [!NOTE]
> Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 150% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.




