---
title: "Preguntas más frecuentes sobre cálculos para modelos de configuración de productos"
description: "En este artículo se describen los cálculos para los modelos de configuración de productos y se explica cómo utilizar los cálculos junto con las restricciones."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f13d03e5d1a26a5c87d71732b692537be94bdfb8
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="calculations-for-product-configuration-models-faq"></a>Preguntas más frecuentes sobre cálculos para modelos de configuración de productos

[!include[banner](../includes/banner.md)]


En este artículo se describen los cálculos para los modelos de configuración de productos y se explica cómo utilizar los cálculos junto con las restricciones.

Se pueden usar cálculos para operaciones aritméticas o lógicas. Complementan restricciones de expresión en modelos de configuración de productos. Puede definir cálculos en la página **Detalles del modelo de configuración de productos basados en restricciones** y después crear expresiones para los cálculos en el editor de expresiones. Para obtener más información, consulte Crear cálculos.

## <a name="what-is-a-calculation"></a>¿Cuál es un cálculo?
Un cálculo es un elemento utilizable en un modelo de configuración de productos. Los cálculos complementan las restricciones dejándole usar decimales para calcular valores mediante al configurar un producto. Además, los cálculos disponen de conjunto mayor de operadores disponibles que las restricciones.  

Al igual que una restricción, un cálculo se asocia a un componente específico en un modelo de configuración de productos y no se puede volver a utilizar con otro componente y compartirse con él. Una diferencia importante entre los cálculos y restricciones es que los cálculos son obligatorios (unidireccionales), mientras que las restricciones se declarativas (bidireccionales). Para obtener más información sobre restricciones, consulte [Restricciones de expresión o restricciones de tabla](expression-constraints-table-constraints-product-configuration-models.md).  

Un cálculo consta de un atributo de destino y una expresión de cálculo.

## <a name="what-is-a-target-attribute"></a>¿Cuál es un atributo de destino?
Un atributo de destino es un atributo que recibe el resultado de la expresión de cálculo.  

En la siguiente expresión, el atributo de destino es una medida de mantel:  

**Expresión:** If\[(atributoDecimal1 &lt;= atributoDecimal2, True, False\]  

**atributoDecimal1** es la longitud de la mesa y **atributoDecimal2** es la longitud del mantel. La expresión devuelve el valor **True** al atributo de destino si **decimalAttribute2** es mayor o igual que **decimalAttribute1**. De lo contrario, la expresión devuelve un valor **False**. Por lo tanto, la medida de mantel es aceptable si la longitud del mantel es igual o mayor que la longitud de la mesa.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>¿Qué tipos de atributo pueden establecerse en atributos de destino?
Todos los tipos de atributo que se admiten para el configurador de productos pueden establecerse en el atributo de destino, a excepción de texto sin lista fija.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>¿Puede el valor de un atributo de destino restringir los valores de los atributos de entrada en un cálculo?
No, el valor de un atributo de destino no puede restringir los valores de los atributos de entrada, ya que los cálculos son unidireccionales. Por lo tanto, el valor del atributo de destino se determina según los cambios en el valor de los atributos de entrada, pero un cambio en el valor del destino no afecta al valor de los atributos de entrada. Este comportamiento varía con respecto al comportamiento en las restricciones. Las restricciones se producen en ambas direcciones.

### <a name="example"></a>Ejemplo

En la siguiente expresión, el destino para el cálculo es la longitud de un cable eléctrico y el valor de entrada es un color:  

**Expresión:** \[If Color == "Verde", 1.5, 1.0\]  

Al configurar el artículo, el cálculo generará **1,5** como la longitud del cable eléctrico si especifica **Verde** como el atributo de color. Si especifica cualquier otro color, la longitud se define en **1,0**. Sin embargo, dado que los cálculos son unidireccionales, el cálculo no establece el valor del atributo de color en **verde** cuando se especifica una longitud de **1,5**.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>¿Qué sucede si un cálculo tiene un atributo de destino del tipo número entero pero un cálculo genera un número decimal?
Si un atributo de destino es del tipo entero, pero un cálculo genera un número decimal, solo se devuelve la parte entera del resultado calculado. Se elimina la parte decimal y el resultado no se redondea. Por ejemplo, un resultado 12,70 se muestra como 12.

## <a name="when-do-calculations-occur"></a>¿Cuándo se produce los cálculos?
Los cálculos se producen cuando un valor se ha proporcionado para todos los atributos de entrada.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>¿Se puede sobrescribir el valor que se calcula para el atributo de destino?
Puede sobrescribir el valor que se calcula para el atributo de destino, a menos que el atributo de destino se establezca como oculto o de solo lectura.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a>¿Cómo se establece un atributo de destino como oculto o de solo lectura?
Para establecer un atributo como oculto o de solo lectura, siga estos pasos.

1.  Haga clic en **Gestión de información de productos** &gt; **Común** &gt; **Modelos de configuración del producto**.
2.  Seleccione un modelo de configuración de producto y haga clic en **Editar** en el panel de acciones.
3.  En la página **Detalles del modelo de configuración de productos basados en restricciones**, seleccione el atributo que desea usar como atributo de destino.
4.  En la ficha desplegable **Atributos**, seleccione **Oculto** o **Solo lectura**.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>¿Puede un cálculo sobrescribir los valores que yo establezca?
N. º Los valores que establece al configurar un producto son los valores que se usan. El cálculo que se produce cuando cambian los valores de entrada de un cálculo no puede sobrescribir los valores que proporcione para un atributo específico.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>¿Qué sucede si se quita un valor de entrada de un cálculo?
Si quita un valor de entrada de un cálculo, el valor del atributo de destino también se quita.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>¿Por qué recibo un mensaje de error que indica que el modelo contiene una contradicción?
Este mensaje se muestra cuando un cálculo incluye un error o existe una contradicción en una o varias restricciones. Para obtener más información sobre contradicciones en restricciones, consulte [Restricciones de expresión o restricciones de tabla](expression-constraints-table-constraints-product-configuration-models.md). Estos son algunos casos en los que se pueden producir errores en los cálculos:

-   Un valor se divide por 0 (cero).
-   Existe un conflicto entre los siguientes dos elementos:
    -   Los valores disponibles para un atributo y que están limitados por una restricción.
    -   Un valor generado por un cálculo.
-   Los valores que devuelve el cálculo se encuentran fuera del dominio del atributo. Un ejemplo es un número entero de \[1..10\] que se calculan en 0.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>¿Por qué se produce un mensaje de error aunque haya validado correctamente el modelo de producto?
Los cálculos no se incluyen en la validación. Debe probar el modelo de configuración de productos para buscar errores en los cálculos. Siga estos pasos para probar un modelo de configuración de productos.

1.  Haga clic en **Gestión de información de productos** &gt; **Común** &gt; **Modelos de configuración del producto**.
2.  Seleccione un modelo de configuración de producto y, en el panel de acciones, haga clic en **Ejecutar** y luego en **Probar**.





