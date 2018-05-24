---
title: "Depreciación con amortización degresiva del 175%"
description: "Este tema le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 175%."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8f78eb06930eab26d300fba6fd28333a5ce39cf8
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="175-percent-reducing-balance-depreciation"></a>Depreciación con amortización degresiva del 175%

[!include [banner](../includes/banner.md)]

Este tema le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 175%.

Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 175%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación. 

Para configurar una depreciación con amortización degresiva del 175%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**. Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.

## <a name="select-a-depreciation-year"></a>Selección de un año de depreciación
Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**. El valor predeterminado es **Calendario**. 

La selección determina las opciones disponibles en el campo **Frecuencia de períodos**. Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.

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

Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación decreciente del 175% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**. Los calendarios fiscales se configuran en la página **Calendarios fiscales**. Para obtener más información, consulte [Calendarios fiscales, ejercicios y períodos.](../budgeting/fiscal-calendars-fiscal-years-periods.md).

Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio. El ejercicio no puede ser superior ni inferior a los 12 meses. La depreciación se ajusta automáticamente para cada período y la extensión del siguiente ejercicio se determina mediante la configuración de los períodos de la página **Calendarios fiscales**. 

Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra el importe total de la depreciación calculada para el ejercicio en el último día del ejercicio.
-   **Período fiscal** calcula el importe total de depreciación para el ejercicio. Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.

## <a name="example-of-175-reducing-balance-depreciation"></a>Ejemplo de depreciación con amortización degresiva del 175%

|                                |        |
|--------------------------------|--------|
| Coste de adquisición               | 11.000 |
| Valor residual                  | 1.000  |
| Base de depreciación              | 10.000 |
| Años de tiempo de vida             | 5      |
| Porcentaje de depreciación anual | 35%    |

El método de depreciación degresiva del 175% divide el 175 por ciento entre los años de tiempo de vida. El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.

| Periodo | Cálculo del importe de depreciación anual | Valor neto                  | Valor neto en los libros al final del año |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| Año 1 | (11.000 - 1.000) × 35% = 3.500                | 11.000 - 3.500 = 7.500      | 11.000 - 1.000 - 3.500 = 6.500        |
| Año 2 | 6.500 × 35% = 2.275                           | 7.500 - 2.275 = 5.225       | 6.500 - 2.275 = 4.225                 |
| Año 3 | 4.225 × 35% = 1.478,75                        | 5.225 - 1.478,75 = 3.746,25 | 4.225 - 1.478,75 = 2.746,25           |

> [!NOTE] 
> Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 175% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.




