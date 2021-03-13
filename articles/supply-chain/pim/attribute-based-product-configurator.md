---
title: Precios de venta basados en atributos para la configuración de productos basada en restricciones
description: Este tema describe cómo crear modelos de precios de venta con precios de venta basados en componentes y atributos en lugar de en la lista de materiales física y la ruta.
author: sorenva
manager: tfehr
ms.date: 10/2/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2020-08-17
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: cba4b1eac33ae53e214297728c1cdf2710ebd9d9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007925"
---
# <a name="attribute-based-sales-prices-for-constraint-based-product-configuration"></a>Precios de venta basados en atributos para la configuración de productos basada en restricciones

Este tema describe cómo crear modelos de precios de venta con precios de venta basados en componentes y atributos en lugar de en la lista de materiales física y la ruta. Puede crear varios modelos de precios de venta para cada modelo de configuración de producto.

## <a name="set-relevant-product-information-management-parameters"></a>Establecer los parámetros de gestión de información de productos pertinentes

Antes de comenzar a crear sus modelos de precios, debe definir una moneda predeterminada, que se utiliza cuando crea sus modelos de precios de venta. También puede elegir si desea adjuntar un archivo de Microsoft Excel con un desglose de precios para todas las líneas de pedido o presupuesto. El desglose de precios le permitirá compartir detalles con los clientes sobre cómo llegó a un precio de venta específico para un producto configurado.

Para configurar su moneda predeterminada:

1. Vaya a **Gestión de la información del producto \> Configuración \> Parámetros de gestión de información del producto**.
1. Abra la pestaña **Modelos de configuración de productos basada en restricciones**.
1. Abra la lista desplegable **Moneda predeterminada** y seleccione su moneda.

    ![Establecer la moneda predeterminada para la configuración del producto basada en restricciones](media/prod-config-currency.png "Establecer la moneda predeterminada para la configuración del producto basada en restricciones")

1. Si desea adjuntar un archivo de Excel con un desglose de precios para todas las líneas de pedido o presupuesto, en la sección **Modelo de precio**, establezca **Adjuntar** en *Sí*.

## <a name="build-your-sales-price-models"></a><a name="build-price-model"></a>Crear sus modelos de precios de venta

Para crear un modelo de precios de venta:

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. Seleccione el modelo de configuración de productos de destino.
1. En el panel Acción, abra la pestaña **Modelo** y, desde el grupo **Preparar**, seleccione **Modelos de precios**.
1. Se abre la página **Modelos de precios**.
1. Seleccione un modelo de precios o agregue uno nuevo a la cuadrícula.
1. Seleccione **Editar** para abrir la página de edición para su modelo seleccionado, que proporciona las siguientes características:
    - El encabezado del formulario muestra la moneda predeterminada y le permite agregar nuevas monedas para la configuración de su precio.
    - El panel izquierdo muestra todos los componentes y requisitos de usuario del modelo de producto. Cada nodo del árbol del modelo de producto puede tener una expresión de precio base y un número opcional de reglas de expresión. Una regla de expresión consta de una condición y una expresión, y cada regla de expresión cubre una opción de producto que ayuda a controlar el precio del producto.
    - Cuando crea sus condiciones y expresiones, tiene los mismos operadores disponibles que para los cálculos en un modelo de producto. El editor de expresiones también admite condiciones y expresiones.
1. Seleccione un nodo en la columna de la izquierda y luego use las funciones descritas en el paso anterior para establecer reglas de precios para él (vea también el ejemplo proporcionado después de este procedimiento). Repita este paso para cada nodo según sea necesario.

El siguiente ejemplo muestra un precio base de un número estático de 899,95 EUR, que puede ser modificado por una o más de las siguientes cinco reglas de expresión, dependiendo de la configuración seleccionada por el cliente:

- Para el acabado del gabinete blanco, reste 59,95 EUR.
- Para la protección de las esquinas, agregue 35,95 EUR.
- Para una parrilla frontal de metal, agregue 89,95 EUR.
- Para el acabado del gabinete de palisandro, agregue 119,95 EUR.
- Añada 12,95 EUR por cada unidad de altura de altavoz.

![Modelo de precios de ejemplo](media/prod-config-rules-example.png "Modelo de precios de ejemplo")

## <a name="add-support-for-multiple-currencies"></a>Agregar soporte para múltiples monedas

Cuando se vende un producto configurable, el sistema verifica si los precios se han establecido explícitamente en la moneda del cliente. Si es así, se utilizan los valores explícitos. De lo contrario, el sistema utiliza los tipos de cambio de moneda establecidos para la empresa de ventas para convertir el valor de moneda predeterminado a la moneda del cliente.

Para agregar precios explícitos en una moneda adicional:

1. Abra la página de edición de su modelo de precio, como se describe en [Crear modelos de precios de venta](#build-price-model).
1. Seleccione el botón **Añadir** en el encabezado del modelo de precios para abrir el cuadro de diálogo desplegable **Monedas**, que enumera las monedas disponibles.
1. Seleccione la moneda que desea agregar en el cuadro de diálogo desplegable **Monedas** y luego seleccione **Aceptar**.
1. La lista desplegable **Moneda actual** ahora incluye la moneda que acaba de agregar, además de cualquier otra moneda que se haya agregado anteriormente. Seleccione su nueva moneda y observe que la cuadrícula en la sección **Reglas de expresión** ahora incluye dos campos de expresión:
    - **Expresión** - Muestra la expresión (o valor constante) para encontrar el precio usando la moneda actualmente seleccionada para **Moneda actual**.
    - **Expresiones predeterminadas** - Muestra la expresión (o valor constante) para encontrar el precio usando la moneda predterminada (mostrada en el campo **Moneda predeterminada**).

    > [!NOTE]
    > El campo **Condición** para las reglas de expresión es "propiedad" de la moneda predeterminada, lo que significa que no puede modificar la condición para otras monedas. Tampoco puede agregar nuevas reglas de expresión mientras se selecciona una moneda distinta a la predeterminada como **Moneda actual**.
1. Edite valores en la columna **Expresión** según sea necesario para la moneda actual.

En el siguiente ejemplo, _EUR_ es la moneda predeterminada y _Dólar estadounidense_ se ha añadido como moneda adicional.

![Ejemplo de un modelo con múltiples monedas](media/prod-config-rules-currency-example.png "Ejemplo de un modelo con múltiples monedas")

> [!NOTE]
> No puede agregar reglas de expresión que sean únicas para una moneda no predeterminada. Para crear reglas de expresión que sean relevantes solo para una moneda que no sea la moneda predeterminada, establezca la expresión de precio para la moneda predeterminada en cero. Luego, establezca la expresión adecuada para la moneda no predeterminada.

## <a name="test-your-price-model"></a>Pruebe su modelo de precio

Para probar cómo funcionan los precios de venta en una sesión de configuración, abra la página de edición para su modelo de precios, como se describe en [Crear sus modelos de precios de venta](#build-price-model) y luego seleccione **Prueba** en el Panel de acciones. Se abre el cuadro de diálogo **Modelo de producto de prueba**, donde puede hacer lo siguiente:

- Utilice los ajustes de configuración que se ofrecen aquí para seleccionar opciones de producto y luego ver cómo afectan el valor mostrado para **Precio y fecha de envío**.
- Seleccione **Ver desglose de precios** para descargar un documento de Excel que muestra todos los detalles sobre cómo se calculó el precio.

![Pruebe su modelo de producto](media/prod-config-test.png "Pruebe su modelo de producto")

La hoja de cálculo descargada muestra tanto el valor absoluto como la contribución como porcentaje para cada elemento de precio activo. Si ha configurado la opción de modelo de precio **Adjuntar** en la página **Parámetros de gestión de la información del producto**, esta hoja de Excel se adjunta a la línea de pedido o presupuesto.

![Hoja de cálculo de Excel que muestra el desglose de precios](media/prod-config-excel-example.png "Hoja de cálculo de Excel que muestra el desglose de precios")

## <a name="set-up-selection-criteria-for-price-models"></a>Configurar criterios de selección para modelos de precios

Cuando sus modelos de precios están en su lugar, debe establecer al menos un criterio de selección para elegir el modelo de precios cuando configura para cotizar o para ordenar. Lo hará configurando una o más consultas. En combinación con modelos de precios de venta coincidentes, las consultas brindan una gran flexibilidad a la hora de orientar los precios de venta a clientes, regiones, períodos y otros criterios específicos.

Para configurar criterios de selección para modelos de precios:

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. Seleccione el modelo de configuración de productos de destino.
1. En el panel Acción, abra la pestaña **Modelo** y, desde el grupo **Preparar**, seleccione **Criterios de modelos de precios**. Se abre la página **Criterios de modelos de precios**.
1. Si la fila de consulta que necesita aún no existe, seleccione **Nuevo** en el Panel de acciones para agregar una nueva fila a la cuadrícula y realizar la siguiente configuración:
    - **Nombre** - Escriba un nombre para esta fila.
    - **Descripción** - Describe brevemente la consulta y para qué sirve.
    - **Modelo de precio** - Seleccione un [modelo de precio](#build-price-model) (del modelo de configuración actual) que se aplicará la consulta cuando se active.
    - **Tipo de orden** - Seleccione el tipo de pedido donde se aplicará la consulta.
    - **Válida desde** - Especifique el primer día en que se aplicará la consulta.
    - **Caduca por** - Especifique la última fecha en la que se aplicará la consulta.

    ![Criterios de modelo de precio](media/prod-config-price-model-criteria.png "Criterios de modelo de precio")

1. Seleccione la fila de la consulta que desea definir y luego seleccione **Editar** en el **Panel de acciones**. El cuadro de diálogo del diseñador de consultas se abre. Funciona como la mayoría de los diseñadores de consultas en Supply Chain Management. Úselo para definir las condiciones bajo las cuales se debe aplicar el modelo de precios para la fila que seleccionó.

1. Repita los pasos 4-5 para cada consulta que necesite.
    > [!TIP]
    > Puede ahorrar tiempo copiando una fila existente que ya es similar a una nueva que necesita agregar. Para hacer esto, seleccione una fila de destino y luego seleccione **Duplicar** en el Panel de acciones.

1. Cuando haya terminado de configurar sus criterios, organícelos en el orden correcto en la lista **Criterios del modelo de precios**. Para reposicionar una fila, seleccione la fila y luego seleccione **Arriba** o **Abajo** en el Panel de acciones.

    > [!IMPORTANT]
    > En el momento de la configuración, el sistema comienza a buscar desde la parte superior de la lista y utiliza la primera consulta que coincide con los datos de la cotización o la línea de pedido. Por lo tanto, debe poner sus consultas más específicas en la parte superior. Si coloca una consulta general en la parte superior de la lista, esta es la que se utilizará aunque pueda haber una consulta más abajo en la lista que se dirija al cliente o prospecto exacto de la configuración.

## <a name="set-attribute-based-sales-prices-for-the-product-model-version"></a>Establecer precios de venta basados en atributos para la versión del modelo de producto

El paso final es especificar precios de venta basados en atributos para la versión del modelo de producto. Acción:

1. Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.
1. Seleccione el modelo de configuración de productos de destino.
1. En el panel Acción, abra la pestaña **Modelo** y, desde el grupo **Detalles de modelo de producto**, seleccione **Versiones**.
1. Se abrirá la página **Versiones**. Asegúrese de que **Método de fijación de precios** se establece en **Basado en atributos**.
    ![Establecer el método de fijación de precios en Basado en atributos](media/prod-config-versions.png "Establecer el método de fijación de precios en Basado en atributos")
