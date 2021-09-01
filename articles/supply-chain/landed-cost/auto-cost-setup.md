---
title: Configuración de costes automáticos
description: Este tema describe cómo configurar reglas de costos para varios niveles de viaje de entrada. Con base en estas reglas, el sistema calcula los costos y los agrega automáticamente. Por lo tanto, los usuarios no tienen que agregar los costos manualmente.
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e1db6c1da4ab311cc3e304d4f422004d5b8423d76f24c8bc8e528f742b1f42fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736776"
---
# <a name="auto-costs-setup"></a>Configuración de costes automáticos

[!include [banner](../../includes/banner.md)]

Puede usar la página **Costes automáticos** para configurar reglas de costos para diversas áreas de costos (como viajes, contenedores de envío, folios, órdenes de compra, artículos o líneas de órdenes de transferencia). Según las reglas y los campos que los usuarios seleccionan cuando crean registros para una de las áreas de costos, el sistema calcula los costos y los agrega automáticamente. Por lo tanto, los usuarios no tienen que agregar los costos manualmente.

Para trabajar con costes automáticoses, vaya a **Coste de aterrizaje \> Configuración de costos \> Costes automáticos**. Luego, configure sus reglas de costos automáticos como se describe en el resto de este tema.

## <a name="work-with-cost-areas"></a>Trabajar con áreas de costos

Los costes automáticos funcionan como acuerdos comerciales o cargos automáticos de diversa índole. Cada registro de costo automático pertenece a un nivel de costo específico. Utilice el campo **Área de costo** en el panel de lista de la página **Costes automáticos** para seleccionar el área de costos con la que desea trabajar. El panel de lista muestra solo los costes automáticos que pertenecen al área de costos actualmente seleccionada. Cualquier costo automático que cree pertenecerá al área de costos actualmente seleccionada.

Las áreas de costos permiten al sistema distribuir los costos entre las líneas de la orden de compra en un área de costos. Por ejemplo, el costo de un contenedor de envío distribuirá el valor entre todos los productos en ese contenedor de envío. Si hay dos o más contenedores de envío, se puede especificar el mismo tipo de costo para cada contenedor de envío. Por lo tanto, el tipo de contenedor se puede utilizar para encontrar el costo de auto correcto.

## <a name="buttons-on-the-action-pane"></a>Botones en el panel de acciones

La tabla siguiente describe los botones disponibles en el panel de acciones de la página **Costes automáticos**.

| Botón | Descripción |
|---|---|
| Editar | Edite un coste automático existente. |
| Crear nuevo | Cree un coste automático. |
| Borrar | Elimine un coste automático. |
| Copiar de | Cree un nuevo registro de coste automático basado en un registro existente. A continuación, puede editar libremente el nuevo registro. Este botón le ayuda a crear rápidamente nuevos costes automáticos. |
| Mostrar dimensiones | Abra un cuadro de diálogo donde puede seleccionar las dimensiones de inventario que se muestran para las transacciones de costos que ve. Si desactiva las casillas de verificación, se mostrarán menos dimensiones de inventario para las transacciones de costo. Por lo tanto, se mostrarán menos detalles para la transacción. Si se especifica una dimensión de inventario para un costo automático, el costo automático se aplicará solo cuando la dimensión de inventario especificada se utilice para el artículo en un viaje. |

## <a name="settings-on-the-header"></a>Configuración en el encabezado

La combinación de configuraciones en la sección de encabezado determina cuándo y cómo se agrega un coste automático específico a un viaje. Se aplicará un costo automático a un viaje, contenedor de envío o folio solo cuando los detalles del costo automático coincidan con los detalles del encabezado de esa área de costos. La suma de todos los costes automáticos coincidentes determina el costo de aterrizaje estimado de un viaje. Este costo se distribuye entre todos los artículos del barco o viaje.

En la tabla siguiente se describen todos los campos que pueden aparecer en la sección de encabezado. Sin embargo, los campos específicos que están disponibles varían, según el área de costo y las dimensiones de visualización que están seleccionadas actualmente.

| Campo | Descripción |
|---|---|
| **Código de cuenta** | <p>Seleccione uno de los siguientes valores:</p><ul><li>**Tabla** - La regla de coste se aplica solo a un proveedor específico.</li><li>**Grupo** - La regla de coste se aplica a un grupo de proveedores específico. El sistema buscará el [grupo de tipo de costes de proveedor](costing-parameters-setup.md) asociado con el registro de proveedor.</li><li>**Todos** - La regla de coste se aplica a todos los proveedores. |
| **Empresa de transporte** | Seleccione el proveedor o grupo de proveedores al que se aplica la regla de coste. Este campo solo está disponible si selecciona *Tabla* o *Grupo* en el campo **Código de cuenta**. |
| **Agente de aduanas** | Seleccione el proveedor o grupo de proveedores al que se aplica la regla de coste. Este campo solo está disponible si selecciona *Tabla* o *Grupo* en el campo **Código de cuenta**. |
| **Código de artículo** | <p>Seleccione uno de los siguientes valores:</p><ul><li>**Tabla** - La regla de coste se aplica solo a un artículo específico.</li><li>**Grupo** - La regla de coste se aplica a un grupo de artículos específico. El sistema buscará el [grupo de tipo de costes de artículo](costing-parameters-setup.md) asociado con el registro de artículo.</li><li>**Todos** - La regla de coste se aplica a todos los artículos.|
| **Relación de artículos** | Seleccione el artículo o grupo de artículos al que se aplica la regla de coste. Este campo solo está disponible si selecciona *Tabla* o *Grupo* en el campo **Código de artículo**. |
| **Modo de entrega** | Seleccione el modo de entrega (por ejemplo, aéreo o marítimo) al que se aplica la regla de costo. |
| **Tipo de contenedor** | El tipo de contenedor de envío en el que se enviarán las mercancías. Se puede aplicar un costo automático a un viaje solo si el tipo de contenedor de la configuración del costo automático coincide con el tipo de contenedor del viaje. |
| **Desde el puerto** y **Hasta el puerto** | El puerto de origen ("desde") y el puerto de destino ("hasta") del viaje. (Algunos contenedores de envío pueden tener diferentes puertos "a", porque el viaje puede detenerse en varios puertos). Se puede aplicar un costo automático a un viaje solo si los puertos "desde" y "hasta" en la configuración del costo automático coinciden con " desde "y" hasta "los puertos del viaje. |
| **Número de coste automático** | Identificador exclusivo de la regla de coste automático. El valor de este campo se genera automáticamente en función de la secuencia numérica que se configura en la página **Parámetros de costo descargado**. |
| **Dimensiones de inventario** | Algunas áreas de costos le permiten incluir una o más dimensiones del artículo en el encabezado (como tamaño, color, almacén y número de lote). Seleccione **Dimensiones de la pantalla** en el Panel de acciones para seleccionar las dimensiones que deben incluirse. |

## <a name="settings-on-the-lines-fasttab"></a>Configuración en la ficha desplegable Líneas

En la ficha desplegable **Líneas**, agregue una fila para cada moneda que se puede usar cuando se aplica un costo a una línea de orden de compra en un viaje. 

Para artículos y órdenes de compra, el sistema comparará la moneda de cada línea de orden de compra con las monedas que se especifican en la ficha desplegable **Líneas**. Se aplicará solo el valor de costo establecido para la línea o el artículo coincidente. Si no se configura ninguna línea para la moneda de la línea o el artículo, el costo automático no se aplicará a esa línea o artículo.

Para otros tipos de áreas de costos, todas las líneas de la ficha desplegable **Líneas** se aplicarán a cada viaje, contenedor de envío, folio o línea de orden de transferencia que coincida con los valores establecidos en el encabezado.

En la tabla siguiente se describen todos los campos que pueden aparecer en cada línea. Sin embargo, los campos específicos que están disponibles varían, según el área de costo que está seleccionada actualmente.

| Campo | Descripción |
|---|---|
| **Divisa** | Seleccione la moneda a la que se aplica la línea. Esta moneda está relacionada con la orden de compra. Cuando el sistema está tratando de encontrar los costos automáticos que deben aplicarse a un viaje y sus líneas de viaje, seleccionará la línea que tenga la misma moneda que la orden de compra. Este campo está disponible solo cuando el campo **Área de costo** está configurado en *Orden de compra* o *Artículo*. |
| **Código de tipo de coste** | El tipo de coste. |
| **Método de reparto** | <p>El método que se utiliza para distribuir los costos a las líneas. Las siguientes opciones están disponibles:</p><ul><li><p>**Por ciento** - El valor del campo **Valor de coste** es un porcentaje que se aplica al valor total de los bienes.</p><p>Por ejemplo, si el campo **Valor de coste** está configurado en *10* y el valor total de los bienes es $800, el valor del costo es $80 (= $800 × 10 por ciento).</p></li><li>**Cantidad** - El costo se distribuirá en función de la cantidad de mercancías.</li><li>**Importe** - El costo se distribuirá en función del valor de las mercancías.</li><li>**Volumen** - El costo se distribuirá en función del volumen de las mercancías. El volumen se especifica en el maestro del artículo.</li><li>**Peso** - El costo se distribuirá en función del peso de las mercancías. El peso se especifica en el maestro del artículo.</li><li>**Volumétrica** - El costo se distribuirá en función de la medida volumétrica de las mercancías.</li><li><p>**Medición** - Esta opción permite especificar una medida en el módulo **Coste descargado**. Suele ser utilizada por organizaciones que no conocen el volumen o el peso individual de los productos, pero que requieren una distribución más precisa que la que permiten las opciones **Importe** o **Cantidad**. El transportista o agente proporcionará a la organización el peso o la medida cúbica, en el nivel de artículo o de la orden de compra.</p><p>Por ejemplo, el transporte marítimo es igual a $900. El artículo A tiene un peso de 800 kilogramos (kg) y un volumen de 2 metros cúbicos (m³). El artículo B tiene un peso de 100 kg y un volumen de 1 m³. Estos son los resultados cuando los costos se distribuyen por peso:</p><ul><li>Elemento A = $800</li><li>Elemento B = $100</li></ul><p>Estos son los resultados cuando los costos se distribuyen por volumen:</p><ul><li>Elemento A = $600</li><li>Elemento B = $300</li></ul><p>**Nota:** Cuando el campo **Método de reparto** está configurado en *Medición*, el sistema utiliza las medidas que se ingresan tanto para el área de costo (el contenedor de envío) como para las líneas. Estas medidas no necesariamente tienen que sumar el total esperado. Sin embargo, si necesita que se sumen al total esperado, puede hacer una verificación utilizando las estadísticas para revisar la medición total. La configuración del mensaje de medición y la actualización automática de la medición a nivel de envío o contenedor se establecen en el encabezado del viaje.</p></li></ul> |
| **Fecha de inicio** | Especifique el inicio del rango de fechas para el cálculo de costos, si hay un rango de fechas. Esta fecha es la primera fecha en la que se aplicará el coste automático. |
| **Hasta fecha** | Especifique el final del rango de fechas para el cálculo de costos, si hay un rango de fechas. Esta fecha es la última fecha en la que se aplicará el costo automático. |
| **Categoría** | <p>Seleccione el método que se debe utilizar para calcular el coste. Las siguientes opciones están disponibles:</p><ul><li>**Fijo** - El costo se distribuirá en función del método de reparto.</li><li>**Piezas** - El costo se asignará por pieza. Por lo tanto, no se utilizará el método de prorrateo.</li><li>**Por ciento** - Se agregará un porcentaje del valor de la mercancía. Por lo tanto, no se utilizará el método de prorrateo.</li><li>**Velocidad** - Seleccione esta opción si hay desgloses por cantidad. El campo **Método de reparto** de la línea debe establecerse en *Medición*.</li><ul> |
| **Con desglose por cantidad** | <p>Seleccione esta casilla de verificación para hacer que el botón **Roturas de cantidad** esté disponible en la ficha desplegable **Líneas**. Los desgloses de cantidad permiten desglosar el costo y variar los diferentes costos, dependiendo de la cantidad en la línea de orden de compra del viaje. Esta funcionalidad se utiliza a menudo cuando el modo de suministro es el aire. El campo **Categoría** de la línea debe establecerse en *Tasa*.</p><p>La cantidad pertenece a la opción seleccionada en el campo **Método de reparto**. El valor del costo será igual a la cantidad que se ingrese en el campo **Valor de coste**.<p>Por ejemplo, cantidades de 45 a 100 kg producen una carga de $ 6,00 por medición (como kg / m³). Las cantidades qeu superen los 100 kg producen una carga de $ 5,50 por medición (como kg/m³).</p> |
| **Valor de coste** | Escriba el valor del coste. |
| **Código de divisa de coste** | Seleccione la divisa del coste. |
| **Grupo de impuestos de artículos** | Permite seleccionar el código de impuestos para el coste. |
| **Coste mínimo** | <p>Este campo se aplica solo si la casilla **Desglose por cantidad** está seleccionada. Si la medida no alcanza este valor, se selecciona el valor mínimo, independientemente de los costos que se especifiquen en la página **Roturas de cantidad**.<p>Por ejemplo, cantidades de 0 a 45 kg producen una carga de $6 por medición (kg/m³). Las cantidades de 46 a 100 kg producen una carga de $ 5,50 por medición (kg/m³). Si se envían 2 kg, el corte de cantidad creará un valor de costo de $12. Sin embargo, si el campo **Costo mínimo** está configurado en *$100*, el costo final será $100.</p> |
| **Agregado** | Seleccione esta casilla de verificación para permitir que los usuarios muevan este costo del nivel del contenedor de envío al nivel del viaje. En este caso, los costos se pueden calcular automáticamente a nivel de contenedor de envío. Sin embargo, también se pueden combinar y distribuir entre todos los artículos de todos los contenedores de un viaje, en lugar de todos los artículos de los contenedores de envío individuales. |
| **Tipo de coste vinculado** | <p>Vincule la línea actual a otra línea en el mismo registro de costo automático especificando el valor **Código de tipo de costo** de la línea que desea vincular. Esta funcionalidad está disponible solo cuando el campo **Categoría** de la línea actual se establece en *Porcentaje*. Cuando la línea actual está vinculada a otra línea, el costo de la línea actual se basará en el costo de la otra línea.</p><p>Por ejemplo, el flete es $ 1000 y desea que el recargo por combustible sea el 10 por ciento del costo del flete. En este caso, la línea debe tener un valor de **Categoría** de *Porcentaje*, un **Valor de coste** del *10 %* y un **Tipo de costo vinculado** de *Transporte*.</p> |
| **Ajuste de valor** e **Importe de ajuste** | <p>Utilice estos campos para ajustar el valor y la cantidad de varios valores porcentuales. Están disponibles solo cuando el campo **Área de costo** está configurado en *Artículo*.</p><p>Se pueden configurar diferentes costos para diferentes componentes de un artículo. Un componente de un artículo puede tener un porcentaje de costo diferente al de los otros componentes de ese artículo. En ocasiones, se requiere este enfoque para valorar una parte específica de los bienes a diferentes tasas.</p><p>Por ejemplo, el derecho de un reloj se calcula en dos tipos: un componente del reloj tiene un tipo de derecho del 10 por ciento y un segundo componente tiene un tipo de derecho del 2 por ciento. En este caso, el cálculo de costos se dividirá entre los dos componentes.</p><p>El costo se calcula para el artículo, pero el valor del costo se ajusta por el valor de los componentes que tienen la categoría de costo diferente. El costo de los componentes restantes se puede calcular utilizando la cantidad por la que se ajustó el cálculo anterior.</p><p>Por ejemplo, el componente A del reloj tiene un costo de $ 9,50 y un arancel del 10 por ciento, y el componente B tiene un costo de $ 0,50 y un arancel del 2 por ciento. Por lo tanto, el coste total es de 10,00. La primera entrada es para la línea del 10 por ciento. Usa los siguientes valores:</p><ul><li>**Categoría:** *Porcentaje*</li><li>**Valor de coste:** *10*</li><li>**Valor ajustado:** *Ajustar por*</li><li>**Valor ajustado:** *-0,50*</li></ul><p>Esta configuración especifica que el costo del artículo ($ 10) debe reducirse en $ 0,50 (el precio del componente B) antes de que se calcule un cargo de derecho del 10 por ciento. Por lo tanto, el 10 por ciento se aplicará a $ 9,50.</p><p>La segunda entrada es para la línea del 2 por ciento (los $ 0,50 por los que se ajustó la entrada anterior). Usa los siguientes valores:</p><ul><li>**Categoría:** *Porcentaje*</li><li>**Valor de coste:** *2*</li><li>**Valor ajustado:** *Uso*</li><li>**Ajuste:** *0,50*</li></ul><p>Esta configuración calcula el derecho restante que se paga sobre el componente B.</p> |
