---
title: "Depreciación de consumo"
description: "Este artículo le ofrece una visión general del método de depreciación Consumo."
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
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f48eabb3c07f53e8a086be4e0d1597b8ea4d401b
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="consumption-depreciation"></a>Depreciación de consumo

[!include [banner](../includes/banner.md)]

Este artículo le ofrece una visión general del método de depreciación Consumo.

Si configura un perfil de depreciación para activos fijos y selecciona **Consumo** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos se asignan a este perfil de depreciación según su uso. No tiene que configurar porcentajes e intervalos en la página **Métodos de depreciación**. Una vez creado el perfil de depreciación que utiliza el método Consumo, puede configurar el método de varias formas.

## <a name="set-up-and-use-consumption-depreciation"></a>Configuración y uso de la depreciación de consumo
1.  En la página **Métodos de depreciación**, cree el perfil de depreciación. Para los cálculos de consumo, el perfil de depreciación debe tener un identificador y un nombre, y **Consumo** debe estar seleccionado en el campo **Método**.
2.  En la página **Factores de consumo**, configure factores de consumo. Cada factor de consumo debe tener un identificador y un nombre, y un factor de consumo que se especifique como una cantidad o un porcentaje.
3.  En la página **Unidades de consumo**, configure unidades de consumo. Cada unidad de consumo debe tener un identificador y un nombre. Las unidades de depreciación se usan para calcular la depreciación del consumo en la página **Depreciación de consumo**. Algunos ejemplos de unidades son kilómetro (km), kilogramo (kg) y hora.
4.  En la página **Activos fijos**, configure activos fijos individuales. Para cada activo fijo, seleccione los modelos de valor y los libros amortización que tengan perfiles de depreciación. Debe configurar modelos de valor o libros de amortización para la depreciación de consumo, si cualquiera de sus activos fijos usan perfiles de depreciación que se basan en el método Consumo. Esta configuración se realiza en la ficha **Depreciación** de la página **Modelos de valor** o la ficha desplegable **General** de la página **Perfil de depreciación**. Puede utilizar el mismo modelo de valor para varios activos fijos. Los perfiles de depreciación son parte del modelo de valor o libro amortización que seleccione para cada activo fijo. No puede agregar ni modificar perfiles de depreciación directamente en la página **Activos fijos**. Puede modificar perfiles de depreciación solo en la página **Libros de amortización**.
5.  En la página **Modelos de valor** de la página **Libros de amortización**, en el grupo de campos **Depreciación de consumo**, especifique información en los siguientes campos:
    -   Factor de consumo
    -   Unidad
    -   Depreciación de unidad
    -   Consumo estimado

    El campo**Consumo registrado** muestra la depreciación de consumo, en unidades, que ya se ha registrado para la combinación del activo fijo y del modelo de valor, o para el libro de depreciación. No es posible actualizar manualmente el valor en este campo.

## <a name="examples"></a>Ejemplo
### <a name="example-1"></a>Ejemplo 1

El siguiente factor de consumo se configura para el 31 de enero:

-   La cantidad es 1.000.
-   El precio de depreciación de la unidad se especifica para el activo fijo es 1,5.

La propuesta de depreciación el 31 de enero es la siguiente: Cantidad × Depreciación de unidad 1.000 x 1,5 = 1.500 Si el factor especificado para el activo fijo es un factor de porcentaje, la cantidad que se estima en el campo **Consumo estimado** para el modelo de valor del activo fijo se multiplica por el porcentaje que se configura para la fecha final seleccionada. La cantidad resultante se sugiere entonces como cantidad de depreciación para el período.

### <a name="example-2"></a>Ejemplo 2

El siguiente factor de depreciación de consumo se configura para el 31 de enero.

-   El porcentaje es del 10%.
-   El precio de depreciación de la unidad se especifica para el activo fijo es 1,5.
-   La cantidad estimada del activo fijo es 2.000.

La propuesta de depreciación el 31 de enero es la siguiente: Cantidad estimada × Porcentaje x Unidad de depreciación 2.000 x ,10 × de 1,5 = 300




