---
title: "Tiempo de vida restante de depreciación lineal"
description: "Este artículo le ofrece una visión general del método de depreciación Tiempo de vida restante de depreciación lineal."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13851
ms.assetid: 0fa2f71a-596c-414c-a6e6-8f7405a0bf81
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 765825ba43cad44b076ea6628d2787011e97fc57
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="straight-line-life-remaining-depreciation"></a>Tiempo de vida restante de depreciación lineal

[!include[banner](../includes/banner.md)]


Este artículo le ofrece una visión general del método de depreciación Tiempo de vida restante de depreciación lineal.

Al configurar un perfil de amortización de activo fijo y seleccionar **Tiempo de vida restante de depreciación lineal** en el campo **Método** de la página **Perfiles de depreciación**, la depreciación de los activos fijos que se asigna al perfil de depreciación se basará en el tiempo de vida restante del activo. El importe de depreciación generalmente es el mismo en cada período de depreciación. Para configurar una depreciación lineal restante, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**. Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.

## <a name="select-a-depreciation-year"></a>Selección de un año de depreciación
Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**. El valor predeterminado es **Calendario**. La selección determina las opciones disponibles en el campo **Frecuencia de períodos**. Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.

### <a name="calendar"></a>Calendario

Si selecciona **Calendario** en el campo ***Año de depreciación***, se asume un año comprendido entre el 1 de enero y el 31 de diciembre, aun cuando haya definido el calendario fiscal diferente. La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año. Normalmente, la base de depreciación es el valor neto en los libros menos el valor residual. En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos. Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra un importe el 31 de diciembre.
-   **Mensual** registra un importe mensual al final de cada mes del calendario.
-   **Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).
-   **Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).
-   **Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.

Por ejemplo, si selecciona **Anual**, la depreciación anual se registra una sola vez al año, el 31 de diciembre de cada año. Si selecciona **Mensual**, la depreciación se registra mensualmente como una doceava parte del importe de depreciación anual.

### <a name="fiscal"></a>Fiscal

Si selecciona **Fiscal** en el campo **Año de depreciación**, se utiliza el tiempo de vida restante de depreciación lineal. La depreciación se calcula en función de los años fiscales restantes. Por ejemplo, para el ejercicio del 1 de julio del 2015 al 30 de junio de 2016, el cálculo de la depreciación comienza el 1 de julio. El ejercicio no puede ser superior ni inferior a los 12 meses. La depreciación se ajusta para cada período fiscal. La extensión del siguiente ejercicio se determina por los períodos fiscales configurados en la página **Calendarios fiscales**. Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

-   **Anual** registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.
-   **El período fiscal**calcula el importe total de depreciación para el ejercicio. Este importe se acumula entonces en los períodos fiscales definidos en la página **Calendarios fiscales** del calendario fiscal especificado en el libro.

## <a name="example-of-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Ejemplo de depreciación lineal de un activo fijo sin modificar
Un activo fijo tiene las siguientes características:

|                     |        |
|---------------------|--------|
| Coste de adquisición    | 11.000 |
| Valor residual       | 1.000  |
| Base de depreciación   | 10.000 |
| Años de tiempo de vida  | 5      |
| Depreciación anual | 2.000  |

El importe de depreciación es el mismo cada año: (Coste de adquisición - Valor residual) ÷ Años de tiempo de vida

| Periodo | Cálculo del importe de depreciación anual | Valor neto en los libros al final del año |
|--------|-----------------------------------------------|---------------------------------------|
| Año 1 | (11.000 - 1.000) ÷ 5 = 2.000                  | 9.000                                 |
| Año 2 | (9.000 - 1.000) ÷ 4 = 2.000                   | 7.000                                 |
| Año 3 | (7.000 - 1.000) ÷ 3 = 2.000                   | 5.000                                 |
| Año 4 | (5.000 - 1.000) ÷ 2 = 2.000                   | 3.000                                 |
| Año 5 | (3.000 - 1.000) ÷ 1 = 2.000                   | 1.000                                 |






