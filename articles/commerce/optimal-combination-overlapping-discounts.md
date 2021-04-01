---
title: Determinar la combinación óptima de descuentos superpuestos
description: Cuando los descuentos se superponen, debe determinar la combinación de descuentos superpuestos que generará el total más bajo de la transacción o el descuento total más alto. Cuando el importe de descuento varía en función del precio de los productos que se han comprado, por ejemplo en el descuento comercial habitual “Compre 1 y llévese otro con X por ciento de descuento” (BOGO), este proceso se convierte en un problema de optimización combinatoria.
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailParameters, RetailPeriodicDiscount,
audience: Application User, IT Pro
ms.reviewer: josaw
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: fee9289820d3df821036412147994e227d68d1dc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257180"
---
# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a>Determinar la combinación óptima de descuentos superpuestos

[!include [banner](includes/banner.md)]

Cuando los descuentos se superponen, debe determinar la combinación de descuentos superpuestos que generará el total más bajo de la transacción o el descuento total más alto. Cuando el importe de descuento varía en función del precio de los productos que se han comprado, por ejemplo en el descuento comercial habitual “Compre 1 y llévese otro con X por ciento de descuento” (BOGO), este proceso se convierte en un problema de optimización combinatoria.

Este artículo se aplica a Microsoft Dynamics AX 2012 R3 con 3105973 KB (liberado el 2 de noviembre de 2015) o posterior, y Dynamics 365 Commerce. Para determinar la combinación de descuentos superpuestos para aplicarlos de manera oportuna, hemos introducido un método de aplicación descuentos superpuestos. A este nuevo método lo llamamos **clasificación de valor marginal**. La clasificación de valor marginal se usa cuando el tiempo necesario para evaluar las combinaciones posibles de descuentos superpuestos supera un umbral que se puede configurar en la página **Parámetros de Commerce**. En el método de la clasificación de valor marginal, se calcula un valor para cada descuento superpuesto usando el valor del descuento en los productos compartidos. Los descuentos superpuestos se aplican desde el valor relativo más alto hasta el más bajo. Para obtener más información sobre el nuevo método, consulte la sección “Valor marginal”, más adelante en este artículo. La clasificación de valor marginal no se usa cuando los importes de descuento de un producto no se ven afectados por otro producto de la transacción. Por ejemplo, este método no se usa para dos descuentos simples o para un descuento simple y un descuento por cantidad de un producto individual.

## <a name="discount-examples"></a>Ejemplos de descuentos

Puede crear un número ilimitado de descuentos en un conjunto habitual de productos. Sin embargo, dado que no hay límite, pueden producirse problemas de rendimiento si intenta calcular los descuentos que se deben usar en diversos productos. Los ejemplos siguientes muestran este problema con más detalle. En el ejemplo 1, comenzamos con dos productos y dos descuentos superpuestos. A continuación, en el ejemplo 2, mostramos cómo el problema aumenta a medida que se agregan más productos.

### <a name="example-1-two-products-and-two-discounts"></a>Ejemplo 1: Dos productos y dos descuentos

En este ejemplo, se requieren dos productos para poder obtener cada descuento y los descuentos no se pueden combinar. Los descuentos en este ejemplo son descuentos **Mejor precio**. Ambos productos pueden obtener ambos descuentos. Aquí están los dos descuentos.

![Ejemplo de dos mejores precios/descuentos](./media/overlapping-discount-combo-01.jpg)

En dos productos cualquiera, el mejor de estos dos descuentos depende de los precios de los dos productos. Si el precio de ambos productos es igual o casi igual, el descuento 1 es mejor. Si el precio de un producto es significativamente inferior al precio del otro producto, el descuento 2 es mejor. A continuación se indica la regla matemática para evaluar estos dos descuentos entre sí.

![Regla para evaluar los descuentos](./media/overlapping-discount-combo-02.jpg)

> [!NOTE]
> Cuando el precio del producto 1 es igual a dos tercios del precio del producto 2, los dos descuentos son iguales. En este ejemplo, el porcentaje de descuento efectivo del descuento 1 varía entre un pequeño porcentaje (cuando los precios de los dos productos son muy diferentes) y un máximo de 25 por ciento (cuando los dos productos tienen el mismo precio). El porcentaje de descuento efectivo del descuento 2 es fijo. Siempre es el 20 por ciento. Dado que el porcentaje de descuento efectivo del descuento 1 tiene un intervalo que puede ser superior o inferior al descuento 2, el mejor descuento depende de los precios de los dos productos que se deben descontar. En este ejemplo, el cálculo se completa rápidamente, ya que solo se aplican dos descuentos a solo dos productos. Solo hay dos combinaciones posibles: una aplicación del descuento 1 o una aplicación del descuento 2. No hay permutas que calcular. El valor de cada descuento se calcula usando ambos productos, y se emplea el mejor descuento.

### <a name="example-2-four-products-and-two-discounts"></a>Ejemplo 2: Cuatro productos y dos descuentos

A continuación, utilizaremos cuatro productos y los mismos dos descuentos. Los cuatro productos pueden obtener ambos descuentos. Existen doce combinaciones posibles. Al final, dos descuentos se aplicarán a la transacción con una de tres combinaciones posibles: dos aplicaciones del descuento 1, dos aplicaciones del descuento 2 o una aplicación del descuento 1 y una del descuento 2. Para mostrar las combinaciones posibles, echaremos un vistazo a dos conjuntos diferentes de cuatro productos que tienen precios diferentes:

- Los cuatro productos tienen el mismo precio, 15,00 $. En este caso, la mejor combinación del descuento es dos aplicaciones del descuento 1. Dos productos se venderán al precio completo y dos con un 50 por ciento de descuento. El total descontado de la transacción es 45 $ (15 + 15 + 7,50 + 7,50), que es 15 $ (el 25 por ciento) de descuento del total de 60 $ sin descuento. El descuento 2 es solo de 12 $(20 por ciento).
- Los dos productos cuestan 20 $ cada uno, un producto cuesta 15 $ y un producto cuesta 5 $. En este caso, la mejor combinación de descuento es una aplicación del descuento 2 y una aplicación del descuento 1. En las siguientes tablas se muestran los descuentos.

Para leer las tablas, utilice un producto de una fila y un producto de una columna. Por ejemplo, en la tabla del descuento 1, si combina los dos productos de 20 $, recibe un 10 $ de descuento. En la tabla del descuento 2, si combina el producto de 15 $ y el de 5 $, recibe un descuento de 4 $.

![Ejemplo que utiliza cuatro productos para los mismos dos descuentos](./media/overlapping-discount-combo-03.jpg)

Primero, encontramos el descuento más alto disponible de dos productos con cualquiera de los descuentos. Las dos tablas muestran el importe de descuento de todas las combinaciones de los dos productos. Las partes sombreadas de las tablas representan los casos en los que un producto se empareja consigo mismo (algo imposible) o un emparejamiento inverso de dos productos que genere el mismo importe de descuento y que se puede ignorar. Al mirar las tablas, puede ver que el descuento 1 para los dos artículos de 20 $ es el descuento más alto disponible para cualquiera de los descuentos en los cuatro productos. (Este descuento se resalta en verde en la primera tabla.) Nos queda solo el producto de 15 $ y el de 5 $. Al mirar las dos tablas de nuevo, puede ver que, en estos dos productos, el descuento 1 otorga 2,50 $ de descuento, mientras que el descuento 2 otorga 4 $ de descuento. Por lo tanto, seleccionamos el descuento 2. El descuento total es 14 $. Para poder visualizar esta discusión más fácilmente, aquí tenemos dos tablas adicionales que muestran el porcentaje de descuento efectivo para todas las combinaciones posibles de dos productos tanto para el descuento 1 como para el descuento 2. Solo se incluye la mitad de la lista de combinaciones para estos dos descuentos y el orden en el que se colocan los dos productos en el descuento no importa. El descuento efectivo más alto (25 por ciento) está resaltado en verde y el descuento efectivo más bajo (10 por ciento) está resaltado en rojo.

![Porcentaje de descuento efectivo para todas las combinaciones de dos producto para ambos descuentos](./media/overlapping-discount-combo-04.jpg)

> [!NOTE]
> Si los precios varían y compiten dos o más descuentos, la única forma de garantizar la mejor combinación de descuentos consiste en evaluar ambos descuentos y compararlos.

## <a name="total-possible-combinations"></a>Total de combinaciones posibles

Esta sección continúa el ejemplo de la sección anterior. Agregaremos más productos y otro descuento y veremos cuántas combinaciones deben calcularse y compararse. En la tabla siguiente muestra el número de combinaciones posibles de descuentos a medida que aumenta la cantidad de producto. En la siguiente tabla se muestra lo que ocurre cuando hay dos descuentos superpuestos, como en el ejemplo anterior, y cuando hay tres descuentos superpuestos. El número de combinaciones posibles de descuentos que se deben evaluar supera rápidamente lo que incluso un ordenador rápido puede calcular y comparar con una velocidad aceptable para las transacciones comerciales.

![Número de combinaciones posibles de descuentos a medida que aumenta la cantidad de producto.](./media/overlapping-discount-combo-05.jpg)

Si se aplican cantidades incluso superiores o más descuentos superpuestos, el número total de combinaciones posibles de descuentos llega rápidamente a varios millones y el tiempo necesario para evaluar y seleccionar la mejor combinación posible comienza a notarse. Se han realizado algunas optimizaciones en el motor de precio para reducir el número total de combinaciones que se deben evaluar. Sin embargo, dado que el número de descuentos superpuestos y las cantidades en una transacción no están restringidos, se tendrá que evaluar siempre un gran número de combinaciones cuando haya descuentos superpuestos. Este problema es al que se enfrenta la clasificación de valor marginal.

## <a name="marginal-value-method"></a>Método de valor marginal

Para resolver el problema de un número de combinaciones que aumenta exponencialmente, existe una optimización que calcula el valor por producto compartido de cada descuento en el conjunto de productos al que se pueden aplicar dos o más descuentos. A este valor lo denominamos **valor marginal** del descuento de los productos compartidos. El valor marginal es el aumento medio por producto del importe de descuento total cuando se incluyen productos compartidos en cada descuento. El valor marginal se calcula tomando el importe de descuento total (DTotal), restando el importe de descuento sin los productos compartidos (DMinus\\ Compartido) y dividiendo esa diferencia por el número de productos (ProductosCompartidos).

![Fórmula para calcular el valor marginal](./media/overlapping-discount-combo-06.jpg)

Después de calcular el valor marginal de cada descuento en un conjunto de productos compartidos, se aplican los descuentos a los productos compartidos en orden y exhaustivamente desde el valor marginal más alto hasta el más bajo. En este método todas las posibilidades restantes de descuentos no se comparan cada vez que se aplica una instancia única de un descuento. En su lugar, los descuentos superpuestos se comparan una vez y después se aplican en orden. No se realiza ninguna comparación adicional. Puede configurar el umbral para cambiar al método de valor marginal en la ficha **Descuento** de la página **Parámetros de Commerce**. El tiempo aceptable para calcular el descuento total varía en los diferentes sectores minoristas. Sin embargo, este tiempo normalmente va de milésimas de segundo a un segundo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]