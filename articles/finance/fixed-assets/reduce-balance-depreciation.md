---
title: Reducción de depreciación de saldo
description: Este tema le ofrece una visión general del método de depreciación Depreciación degresiva.
author: moaamer
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f734a0cedf6d9ee7967c3bbed0dfcf95cf33f1cd
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674634"
---
# <a name="reduce-balance-depreciation"></a>Reducción de depreciación de saldo

[!include [banner](../includes/banner.md)]

Este tema le ofrece una visión general del método de depreciación Depreciación degresiva.

Cuando se configura un método de depreciación de activos fijos y se selecciona Depreciación degresiva en el campo **Método** de la página **Perfiles de depreciación**, los activos a los que se ha asignado este método de depreciación se deprecian con el mismo porcentaje en cada período de depreciación.

Para configurar la depreciación degresiva, también debe realizar sus selecciones en los campos de la ficha desplegable **General** y la página **Perfiles de depreciación**. En primer lugar, seleccione un año en el campo **Año de depreciación**. En función de la selección, aparecerán distintas opciones en el campo **Frecuencia de períodos**, tal como se explica en las siguientes secciones. 

También debe especificar un valor en el campo **Porcentaje** para el método o perfil de depreciación. Si selecciona la opción **Depreciación total**, la base de depreciación restante se toma del último período de depreciación y se podría tratar de un importe considerable. Algunos países/regiones no utilizan el cambio a un método de depreciación lineal. El cambio se realiza cuando el importe del método de depreciación alternativo es mayor o igual que el importe del perfil de depreciación principal y el importe de depreciación utilizado es el del método alternativo. 

Puesto que un activo nunca se va a depreciar completamente en base a un cálculo de porcentaje, debe seleccionar la opción **Depreciación total** para depreciar un activo por completo.

## <a name="select-a-depreciation-year"></a>Seleccionar un año de depreciación
Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**. La selección define las opciones disponibles en el campo **Frecuencia de períodos**. La opción predeterminada es **Calendario**.

### <a name="calendar"></a>Calendario

La **opción Calendario** actualiza la base de depreciación, que normalmente el valor neto menos el valor residual, el 1 de enero de cada año. En el posterior ejemplo de reducción de depreciación del saldo, la base de depreciación es el numerador en la primera expresión en la columna de cálculos. 

Si selecciona **Calendario**, tiene las siguientes opciones disponibles en el campo **Frecuencia de períodos**, que define las fechas de registro de acumulación de depreciación a lo largo del año de calendario:

- Anual registra el 31 de diciembre.
- Mensual registra un importe mensual al final de cada mes del calendario.
- Trimestral registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).
- Semestral registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).
- Diariamente registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.

Por ejemplo, si selecciona **Anual**, la depreciación anual se registra una sola vez al año, el 31 de diciembre de cada año. Si selecciona **Mensual**, la depreciación se registra mensualmente como una doceava parte del importe de depreciación anual.

### <a name="fiscal"></a>Fiscal

Si selecciona **Fiscal** en el campo **Año de depreciación**, se utiliza el método de depreciación lineal. Se calcula en base al ejercicio, que se configura en la página **Calendarios fiscales** para el calendario fiscal seleccionado en la página **Libro mayor**. Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio. El ejercicio no puede ser superior ni inferior a los 12 meses. La depreciación se ajusta para cada período fiscal. La duración del siguiente ejercicio se basa en los períodos fiscales que configura al crear un nuevo ejercicio en la página **Calendarios fiscales**.


Si selecciona **Fiscal**, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:

- Anual registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.
- El periodo fiscal registra el importe total de la depreciación calculada para el ejercicio, que se acumula en los períodos fiscales definidos para el calendario fiscal seleccionado en la página del **Libro mayor** o el calendario fiscal seleccionado para el libro de un activo fijo.

## <a name="example-of-reducing-balance-depreciation"></a>Ejemplo de depreciación degresiva

Suponga que el precio de adquisición de activos fijos es de 11.000, el valor residual de 1.000 y el factor del porcentaje de depreciación es 30. 

A través del método de Saldo decreciente, el 30 por ciento de la base de depreciación (valor neto del libro menos el valor residual) se calcula al final del período de depreciación anterior. En la siguiente tabla se muestra la depreciación para los tres primeros años.

| Período | Cálculo del importe de depreciación anual | Valor neto en los libros al final del año |
|--------|-------------------------------------------|---------------------------------------|
| Año 1 | (11.000 - 1.000) \* 30% = 3.000           | (11.000 - 1.000) - 3.000 = 7.000      |
| Año 2 | (7.000 - 1.000) \* 30% = 1.800            | (7.000 -1.800) = 5.200                |
| Año 3 | (5.200 - 1.000) \* 30% = 1.260            | (5.200 - 1.260) = 3.940               |










[!INCLUDE[footer-include](../../includes/footer-banner.md)]
