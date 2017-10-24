---
title: "Tiempo de vida de depreciación lineal"
description: "Este artículo le ofrece una visión general del método de depreciación Tiempo de vida de depreciación lineal."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2b8c078841ca2e4bd994bbfbbe2abb130a4cf6fa
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="straight-line-service-life-depreciation"></a>Tiempo de vida de depreciación lineal

[!include[banner](../includes/banner.md)]


Este artículo le ofrece una visión general del método de depreciación Tiempo de vida de depreciación lineal.

Al configurar un método de depreciación de activos fijos y seleccionar Tiempo de vida de depreciación lineal en el campo Método en la página Perfiles de depreciación, la depreciación de los activos fijos que se asigna a este método de depreciación se basa en el tiempo de vida total del activo. Generalmente, éste es el mismo importe de depreciación en cada período de depreciación. 

La única diferencia en el importe de depreciación calculado entre el tiempo de vida lineal restante y el tiempo de vida lineal es cuando hay un ajuste registrado en el activo. 

Para configurar una depreciación con amortización lineal de vida de servicio, también debe seleccionar opciones en los campos Año de depreciación y Frecuencia de períodos en la página Métodos de depreciación.

## <a name="select-a-depreciation-year"></a>Seleccionar un año de depreciación
Puede seleccionar Calendario o Fiscal en el campo Año de depreciación de la página Métodos de depreciación. La selección define las opciones disponibles en el campo Frecuencia de períodos. La opción predeterminada es Calendario.

### <a name="calendar"></a>Calendario

Al seleccionar Calendario, se asume un año comprendido entre el 1 de enero y el 31 de diciembre, aun cuando haya definido el calendario fiscal de forma diferente. 

La opción Calendario actualiza la base de depreciación, que normalmente es el valor neto menos el valor residual, el 1 de enero de cada año. En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos. 

Si selecciona Calendario, tiene las siguientes opciones disponibles en el campo Frecuencia de períodos, que define las fechas de registro de acumulación de depreciación a lo largo del año de calendario:
-   Anual registra un importe el 31 de diciembre.
-   Mensual registra un importe mensual al final de cada mes del calendario.
-   Trimestral registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).
-   Semestral registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).
-   Diariamente registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.

Por ejemplo, si selecciona Anual, la depreciación anual se registra una sola vez al año, el 31 de diciembre de cada año. Si selecciona Mensual, la depreciación se registra mensualmente como una doceava parte del importe de depreciación anual.

### <a name="fiscal"></a>Fiscal

Si selecciona Fiscal en el campo Año de depreciación, se utiliza la depreciación con amortización lineal de vida de servicio. Se calcula en función del ejercicio, que se define mediante el calendario fiscal especificado para el libro o mediante el calendario fiscal seleccionado en la página del libro mayor. Los calendarios fiscales se configuran en la página Calendarios fiscales.

Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio. El ejercicio no puede ser superior ni inferior a los 12 meses. La depreciación se ajusta automáticamente para cada período fiscal. La duración del siguiente ejercicio se basa en los períodos fiscales que configura al crear un nuevo ejercicio en el formulario Calendarios fiscales. 

Si selecciona Fiscal, aparecen las siguientes opciones disponibles en el campo Frecuencia de períodos:
-   Anual registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.
-   Periodo fiscal calcula el importe total de la depreciación para el ejercicio, que se acumula en los períodos fiscales definidos en el formulario Calendarios fiscales para el calendario fiscal.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>Ejemplo: depreciación lineal de un activo fijo sin modificar
Suponga que el activo fijo tiene las siguientes características.

|                     |        |
|---------------------|--------|
| Coste de adquisición    | 11.000 |
| Valor residual       | 1.000  |
| Base de depreciación   | 10.000 |
| Años de tiempo de vida  | 5      |
| Depreciación anual | 2.000  |

Obtiene el mismo importe de depreciación cada año. (Coste de adquisición - Valor residual) / Años de tiempo de vida

| Período | Cálculo del importe de depreciación anual | Valor neto en los libros al final del año |
|--------|-------------------------------------------|---------------------------------------|
| Año 1 | (11.000 - 1.000) / 5 = 2.000              | 9.000                                 |
| Año 2 | (11.000 - 1.000) / 5 = 2.000              | 7.000                                 |
| Año 3 | (11.000 - 1.000) / 5 = 2.000              | 5.000                                 |
| Año 4 | (11.000 - 1.000) / 5 = 2.000              | 3.000                                 |
| Año 5 | (11.000 - 1.000) / 5 = 2.000              | 1.000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>Ejemplo: depreciación lineal de un activo fijo modificado

Suponga que agrega un ajuste de adquisición de 4.000 en el año 2 para el mismo activo fijo. 

El tiempo de vida del ajuste de adquisición es el mismo que el del activo fijo y empieza en el momento de su adquisición. Un valor neto en los libros permanece al final del año 5, correspondiente al valor neto en los libros del ajuste de adquisición. La depreciación por período se calcula tal y como se muestra en la siguiente tabla.

| Período | Cálculo del importe de depreciación anual | Valor neto en los libros al final del año |
|--------|-------------------------------------------|---------------------------------------|
| Año 1 | 10.000 / 5 = 2.000                        | 11.000 - 2.000 = 9.000                |
| Año 2 | 4.000 (ajuste de adquisición)            | 9.000 + 4.000 =13.000                 |
| Año 2 | 14.000 / 5 = 2.800                        | 13.000 - 2.800 = 10.200               |
| Año 3 | 14.000 / 5 = 2.800                        | 10.200 - 2.800 = 7.400                |
| Año 4 | 14.000 / 5 = 2.800                        | 7.400 - 2.800 = 4.600                 |
| Año 5 | 14.000 / 5 = 2.800                        | 4.600 - 2.800 = 1.800                 |
| Año 6 | 800 restantes\*                           | 1.800 – 800 = 1.000                   |

\*Debido a que el importe restante es inferior al importe de depreciación, sólo se toma el importe restante menos el valor residual.






