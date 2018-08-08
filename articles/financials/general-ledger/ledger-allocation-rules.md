---
title: "Reglas de asignación contable"
description: "Este artículo ofrece información general relativa a las reglas de asignación contable. Describe los diversos componentes de estas reglas de asignación y los métodos de asignación que se pueden usar para ellos."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAllocation, LedgerAllocationBasisRule, LedgerAllocationRequest, LedgerAllocationRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15402
ms.assetid: 8147e148-7c11-45ef-95c6-f9889a875b54
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 63562cde3f2813fdcfc9df7ccbfc623aa2fbe9b1
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="ledger-allocation-rules"></a>Reglas de asignación contable

[!include [banner](../includes/banner.md)]

Este artículo ofrece información general relativa a las reglas de asignación contable. Describe los diversos componentes de estas reglas de asignación y los métodos de asignación que se pueden usar para ellos.

Las reglas de asignación de contabilidad se usan para calcular y para generar automáticamente diarios y asientos contables para asignar saldos contables o importes fijos. Los métodos de asignación pueden ser variables o fijos. Se pueden usar los siguientes métodos de asignación para las reglas de asignación de contabilidad:

-   **Base**: este método variable se usa cuando la asignación depende de los saldos contables reales, en función de los criterios de filtro. Por ejemplo, los costes de publicidad se pueden asignar según las ventas de cada departamento en proporción con el total de ventas departamentales.
-   **Porcentaje fijo** y **Peso fijo**: para estos métodos, el porcentaje de asignación o el peso se define directamente para la regla. Por ejemplo, se pueden asignar gastos de publicidad de modo que el departamento A reciba el 70 por ciento de los gastos de publicidad y el departamento B reciba el 30 por ciento.
-   **Equitativamente**: este método distribuye el importe de manera equitativa a cada destino definido. Por ejemplo, si se definen destinos para el departamento A y el departamento B, los gastos de publicidad se pueden asignar de modo que el departamento A y el departamento B reciban el 50 por ciento de los gastos de publicidad.

Si se usa Base como método de asignación para una regla de asignación, entonces también deberá definir una regla de base de asignación contable independiente. El proceso "Solicitud de asignación de proceso" permite a los usuarios procesar la regla de asignación de contabilidad y ver las entradas de asignación del diario resultantes antes de que se registren o eliminen las asignaciones calculadas.

## <a name="components-of-ledger-allocation-rules"></a>Componentes de reglas de asignación contable
Cada regla de asignación tiene cuatro componentes: general, origen, destino y contrapartida. Se requiere un componente adicional, reglas de bases de asignación contable, si se usa Base como método de asignación. Cada componente proporciona una parte crítica de la información necesaria para procesar asignaciones.

-   **General**: el componente general es donde el usuario especifica opciones como el método de asignación, la configuración de las reglas de empresas vinculadas y si la regla está activa.
-   **Origen**: este componente es donde el usuario especifica los datos de origen para la asignación. La asignación se puede basar en saldos contables (**Origen de datos** = **Libro mayor**) o importes fijos (**Origen de datos** = **Valor fijo**). Cuando **Origen de datos** se establece en **Libro mayor**, se deben definir criterios de filtro de suministro para la regla de asignación de contabilidad (por ejemplo, para los gastos de publicidad).
-   **Destino**: este componente define cómo se debe distribuir y contabilizar el resultado del cálculo de asignación. Por ejemplo, puede haber una línea de destino para cada departamento.
-   **Compensación**: este componente define cómo se deben determinar las cuentas principales y las dimensiones para las entradas de contrapartida que equilibran las entradas de destino. Normalmente se usan opciones definidas por el usuario en lugar de cuentas o dimensiones basadas en el origen. Cuando **Origen de datos** se establece en **Valor fijo**, **Origen** no se puede utilizar como opción.
-   **Reglas de la base de asignación contable**: estas reglas usan sus propios criterios de filtro de origen para determinar qué saldos contables se deben usar para la asignación (por ejemplo, los ingresos por departamento). Cada regla base de asignación se puede usar con varias reglas de asignación.





