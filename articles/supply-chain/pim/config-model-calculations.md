---
title: Cálculos de modelo de configuración de producto
description: En este tema se describe cómo crear cálculos para los atributos en un modelo de configuración de producto
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 349fed3ca75b94db2f421a1ff3c3553c96c202c37d59857a3d973f3de8f995ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755260"
---
# <a name="product-configuration-model-calculations"></a>Cálculos de modelo de configuración de producto

[!include [banner](../includes/banner.md)]

En este tema se describe cómo crear cálculos para los atributos en un modelo de configuración de producto.

## <a name="prerequisites"></a>Requisitos previos

Los cálculos se usan en un modelo de configuración de productos para calcular los valores de configuración de un producto. Antes de que pueda comenzar a configurar los cálculos, debe existir el modelo de configuración del producto relacionado. Para obtener una descripción general del proceso de configuración de los modelos de configuración y las tareas relacionadas, consulte [Configurar un modelo de configuración de producto](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>Crear un cálculo

Un cálculo consta de una expresión y un atributo de destino. Para obtener más información, consulte [Preguntas frecuentes sobre los cálculos de modelos de configuración de productos](calculate-product-configuration-models.md).

Para crear un cálculo para un modelo de producto existente, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Común \> Modelos de configuración del producto**.
1. Abra un modelo de configuración de productos y seleccione **Editar**.
1. En la ficha desplegable **Cálculos**, seleccione **Agregar** para agregar un cálculo y luego establezca los siguientes campos:

    - **Nombre**: escriba un nombre para el cálculo.
    - **Descripción**: escriba una descripción del cálculo.
    - **Atributo de destino**: seleccione el atributo para el que está haciendo el cálculo.

1. Seleccione **Editar expresión**.
1. En el cuadro de diálogo **Ingrese un cálculo**, agregue los atributos, operadores y valores necesarios a la expresión. Para obtener más información sobre cómo trabajar con estos elementos, consulte [Restricciones de expresión o restricciones de tabla en modelos de configuración de producto](expression-constraints-table-constraints-product-configuration-models.md).
1. Cuando su expresión esté lista, seleccione **Aceptar**.

## <a name="calculation-examples"></a>Ejemplos de cálculo

Esta sección proporciona algunos ejemplos que muestran cómo funcionan los cálculos.

### <a name="example-1"></a>Ejemplo 1

El atributo objetivo es booleano y el cálculo usa la siguiente expresión condicional:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

Esta expresión devuelve un valor de *True* al atributo de destino si `decimalAttribute2` es mayor o igual que `decimalAttribute1`. De lo contrario, la expresión devuelve un valor *False*.

### <a name="example-2"></a>Ejemplo 2

Este ejemplo usa el atributo de texto `textFixedList` como atributo de destino. Este atributo contiene la siguiente lista fija.

| Valor | Valor del solucionador |
|---|---|
| C | 1a |
| mil millones | 2b |
| C | 2c |

La siguiente captura de pantalla muestra cómo podría verse la configuración de este atributo en su sistema.

![Configuración de tipo de atributo, por ejemplo 2.](media/model-calculations-example2.png "Configuración de tipo de atributo, por ejemplo 2")

El atributo se utiliza en la siguiente declaración condicional:

`If[integerAttribute < 150, 0, 2]`

Si `integerAttribute` es menor que 150, esta declaración devuelve el valor de texto del primer registro en la lista fija, *A*. De lo contrario, devuelve el valor de texto del tercer registro en la lista fija, *C*.

> [!NOTE]
> La lista fija es equivalente a una enumeración basada en cero (enum), y se accede a sus valores mediante el valor entero apropiado. Por lo tanto, el primer valor de lista fijo (*A*) coincide con *0*, el segundo valor (*B*) coincide con *1*, y el tercer valor (*C*) coincide con *2*.

### <a name="example-3"></a>Ejemplo 3

Este ejemplo usa el atributo de destino `textFixedList` del ejemplo anterior. También usa otro atributo de texto, `textAttribute`, que contiene la siguiente lista fija.

| Valor | Valor del solucionador |
|---|---|
| AA | 1aa |
| BB | 2bb |

La siguiente captura de pantalla muestra cómo podría verse la configuración de este atributo en su sistema.

![Configuración de tipo de atributo, por ejemplo 3.](media/model-calculations-example3.png "Configuración de tipo de atributo, por ejemplo 3")

El valor del atributo `textFixedList` se calcula utilizando la siguiente declaración condicional:

`If[textAttribute == "1aa", 0, 2]`

Si el valor `textAttribute` tiene un valor de resolución que es igual a *1aa*, esta expresión devuelve el valor de texto del primer registro en la lista fija, `textFixedList`, *A*. De lo contrario, devuelve el valor de texto del tercer registro en la lista fija `textFixedList`, *C*.

> [!NOTE]
> - La declaración condicional debe utilizar el valor solucionador del atributo.
> - En los cálculos solo se pueden utilizar atributos de texto de lista fija.

## <a name="see-also"></a>Consulte también

- [Preguntas más frecuentes sobre cálculos para modelos de configuración de productos](calculate-product-configuration-models.md)
- [Agregar una restricción de expresión a un modelo de configuración de producto](tasks/add-expression-constraint-product-configuration-model.md)
- [Visión general de los modelos de configuración de productos](product-configuration-models.md)
