---
title: Previsiones del inventario
description: Este tema describe la funcionalidad de previsión de suministro y demanda que se puede usar para crear previsiones de inventario en Microsoft Dynamics 365 Supply Chain Management.
author: crytt
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0919706ddcc70fecd15df6bf1cbdd58fe9a8e337b2d45cd61a4fb9d821e4114
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757815"
---
# <a name="inventory-forecasts"></a>Previsiones del inventario

[!include [banner](../includes/banner.md)]

Este tema describe cómo ver y crear previsiones de inventario. Puede crear y ver líneas de previsión de oferta y demanda para artículos, grupos de artículos, claves de asignación de artículos, cuentas de clientes, grupos de clientes, cuentas de proveedores y grupos de proveedores.

Para cada línea de previsión, puede seleccionar el modelo de previsión que se utiliza. Luego puede especificar el artículo o grupo de artículos, más la cantidad o el importe de la transacción. También puede configurar una programación de hora para asignar la cantidad de previsión.

Las líneas de previsión de suministro y demanda producen una previsión de inventario para la misma combinación de un artículo y un modelo. Esta previsión de inventario representa un equilibrio entre el suministro y la demanda que se ingresaron para el mismo artículo. Este valor se puede editar. La previsión de inventario ayuda al equipo de administración de inventario a revisar los cambios esperados en el inventario disponible de un artículo durante el próximo período que se ha previsto.

Después de introducir el suministro o la demanda, podrá ejecutar la planificación de previsión para calcular los requisitos brutos de los materiales y capacidad y para generar los pedidos planificados.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Ver e ingresar manualmente las líneas de previsión

Use este procedimiento para crear manualmente líneas de previsión para los productos.

También hay otras formas de crear líneas de previsión:

- [Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md).
- [Importar datos históricos para previsión de la demanda](import-historical-data.md).
- [Generar la previsión mediante un servicio web de Aprendizaje automático de Microsoft Azure](demand-forecasting-setup.md).
- [Importar líneas de previsión de suministro o demanda mediante el marco de administración de datos (entidades de datos ForecastDemandForecastEntryStaging y ForecastSupplyForecastEntryStaging)](../../dev-itpro/data-entities/data-entities-data-packages.md).

Como muestra la tabla del paso 1, hay diferentes formas de acceder a las páginas que se utilizan.

1. Según el tipo de entidad para la que desee crear una previsión y el tipo de previsión que desee crear, abra una página de previsión de suministro, demanda o inventario como se describe en la siguiente tabla.

    | Entidad | Instrucciones |
    |---|---|
    | Productos emitidos | <ol><li>Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</li><li>Seleccione el producto para el que desea crear una previsión.</li><li>En el panel de acciones, en la pestaña **Plan**, en el grupo **Previsión**, seleccione **Previsión de demanda**, **Previsión de suministro** o **Previsión de inventario**, dependiendo del tipo de previsión con el que desee trabajar</li></ol> |
    | Variantes de productos emitidos | <ol><li>Vaya a **Gestión de información de productos \> Productos \> Variantes de productos despachados**.</li><li>Seleccione la variante para la que desea crear una previsión.</li><li>En el panel de acciones, en la pestaña **Plan**, en el grupo **Previsión**, seleccione **Previsión de demanda**, **Previsión de suministro** o **Previsión de inventario**, dependiendo del tipo de previsión con el que desee trabajar</li></ol> |
    | Grupos de artículos | <ol><li>Vaya a **Gestión del inventario \> Configurar \> Inventario \> Grupos de artículos**.</li><li>Seleccione el grupo de artículo para el que desea crear una previsión.</li><li>En el panel de acciones, seleccione **Previsión \> Demanda**, **Previsión \> Suministro** o **Previsión \> Previsión de inventario**, según el tipo de previsión con el que desee trabajar.</li></ol> |
    | Claves de asignación por artículos | <ol><li>Vaya a **Gestión del inventario \> Configuración \> Previsión**.</li><li>Seleccione la clave de asignación de artículos para la que se creará la previsión.</li><li>En el panel de acciones, seleccione **Previsión de la demanda**.</li></ol> |
    | Empresas cliente | <ol><li>Vaya a **Planificación maestra \> Previsión \> Previsión de demanda manual \> Clientes**.</li><li>Seleccione el cliente para el que desea crear una previsión.</li><li>En el panel de acciones, seleccione **Definir previsión de la demanda**.</li></ol> |
    | Grupos de clientes | <ol><li>Vaya a **Planificación maestra \> Previsión \> Previsión de demanda manual \> Grupos de clientes**.</li><li>Seleccione el grupo de clientes para el que desea crear una previsión.</li><li>En el panel de acciones, seleccione **Definir previsión de la demanda**.</li></ol> |
    | Empresas proveedoras | <ol><li>Vaya a **Planificación maestra \> Previsión \> Previsión de demanda manual \> Proveedores**.</li><li>Seleccione el proveedor para el que desea crear una previsión.</li><li>En el panel de acción, seleccione **Entrada** para abrir la página **Previsión de suministro**.</li></ol> |
    | Grupos de proveedores | <ol><li>Vaya a **Planificación maestra \> Previsión \> Previsión de demanda manual \> Grupos de proveedores**.</li><li>Seleccione el grupo de proveedores para el que desea crear una previsión.</li><li>En el panel de acción, seleccione **Entrada** para abrir la página **Previsión de suministro**.</li></ol> | 
    | Todas las líneas | <ul><li>Vaya a **Planificacion maestra \> Previsión \> Líneas de previsión de demanda** o **Planificacion maestra \> Previsión \> Líneas de previsión de suministro**, dependiendo del tipo de previsión con el que desee trabajar.</li></ul> |

    Dependiendo de su selección, aparecerá la página de **Previsión de suministro** o de **Previsión de la demanda**. Muestra las líneas de previsión existentes para el registro que seleccionó antes de abrir la página.

1. En el panel de acciones, seleccione **Nuevo** para agregar una línea de previsión a la cuadrícula en la parte superior de la página.
1. En la nueva línea, en el campo **Modelo**, seleccione el modelo de previsión a utilizar. Luego introduzca otros detalles según sea necesario, como el artículo, el grupo de artículos, la cuenta o el grupo de cliente o proveedor, la cantidad del artículo o el importe total de la transacción. Para obtener detalles completos sobre los campos que están disponibles en las páginas de **Previsión de suministro** y **Previsión de la demanda**, consulte las secciones posteriores de este tema.
1. Para distribuir la previsión durante el período, en la pestaña **Descripción general**, seleccione **Asignar previsión** en la barra de herramientas.
1. En la cuadrícula **Asignación**, revise el horizonte de tiempo y los intervalos de tiempo que se usan para distribuir las cantidades de previsión.

## <a name="supply-forecast-lines"></a>Líneas de previsión de suministro

La previsión de suministro le permite crear un plan para los artículos que se deben comprar. Informa a los empleados de adquisiciones y abastecimiento lo que se espera que pidan.

Puede ingresar una previsión de suministro por artículo, grupo de artículos, clave de asignación de artículos, proveedor y grupo de proveedores. Para obtener información sobre todas las formas de abrir la página de **Previsión de suministro** para varias entidades y registros, consulte la sección [Ver e ingresar manualmente las líneas de previsión](#manual-entry) anterior en este tema.

La parte superior de la página **Previsión de suministro** proporciona una cuadrícula de líneas de previsión de suministro y un conjunto de pestañas que puede usar para ver y establecer más información sobre una línea de previsión seleccionada. La parte inferior de la página proporciona una cuadrícula de **Asignación**.

Las siguientes subsecciones describen todos los campos que están disponibles en cada pestaña y todos los comandos que están disponibles en el Panel de acciones de la página y en la barra de herramientas en la pestaña **Descripción general**.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>Comandos del panel de acciones en la página de previsión de suministro

La tabla siguiente describe los comandos disponibles en el panel de acciones de la página **Previsión de suministro**.

| Comando | Descripción |
|---|---|
| Guardar | Guarde su configuración actual. |
| Editar | Habilite la configuración en la página que se va a editar. |
| Crear nuevo | Agregue una nueva línea de previsión a la cuadrícula superior. |
| Suprimir | Elimine la línea de previsión seleccionada de la cuadrícula superior. |
| Saldos de previsión | Vea los saldos de previsión que se han calculado para la id. de modelo de la línea seleccionada para el año fiscal actual. Los saldos se dividen por período (mes). |
| Previsiones de flujo de efectivo | Vea las transacciones de previsión que se han asignado a la contabilidad general. Para obtener más información consulte [Previsión de flujo de efectivo](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Inventario \> Mostrar dimensiones | Seleccione las dimensiones del inventario que deben mostrarse en la cuadrícula de la pestaña **Descripción general**. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>Comandos de la barra de herramientas en la pestaña Descripción general de la página de previsión de suministro

La tabla siguiente describe los comandos disponibles en el panel de acciones de la pestaña **Descripción general** de la página **Previsión de suministro**.

| Comando | Descripción |
|---|---|
| Asignar previsión | Si está utilizando un método de asignación, genere las líneas de programación individuales para la transacción de previsión. Luego, la cantidad de la línea se distribuye por fecha (de acuerdo con los intervalos de tiempo seleccionados), cantidad e importe para todo el horizonte de tiempo. |
| Actualización masiva | Abre la página **Editar transacciones de previsión**. (Ver la sección [Transacciones de previsión de actualización masiva](#bulk-update) más adelante en este tema.) |
| Previsión del inventario | Abra una vista de la página **Previsión de inventario** que se filtra para la combinación de artículo/modelo seleccionado. (Consulte la sección Previsión [de inventario](#inventory-forecast) más adelante en este tema.) |
| Crear requisito de artículo | Abra un cuadro de diálogo donde puede crear requisitos de artículos y pedidos de ventas o líneas de diario de artículos para transacciones de previsión relacionadas con el proyecto. Aunque este comando está disponible tanto para las líneas de previsión de suministro como para las líneas de previsión de la demanda, no se puede utilizar en la página **Previsión de suministro**. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>La pestaña Descripción general en la página Previsión de suministro

La siguiente tabla describe los campos en la pestaña **Descripción general** de la página **Previsión de suministro**.

| Campo | Descripción |
|---|---|
| **Modelo** | El modelo de previsión al que está asociada la transacción. |
| **Fecha** | La fecha de inicio de la transacción. |
| **Cuenta del proveedor** | La cuenta del proveedor con la que está asociada la transacción. |
| **Grupo de proveedores** | El grupo del proveedor con la que está asociada la transacción. |
| **Número de artículo** | El identificador del artículo. |
| **Grupo de artículos** | El grupo de artículos con el que está asociada la transacción. |
| **Clave de asignación de artículos** | La clave de asignación de artículos que se asocia con la previsión. |
| **Cantidad PC** | La cantidad prevista en la unidad de peso capturado especificada. |
| **Unidad de PC** | La unidad de peso capturado en la que se ha adquirido el artículo. El valor se recupera automáticamente de la configuración del artículo. |
| **Cantidad** | La cantidad de previsión en la unidad de compras especificada. |
| **Unidad** | La unidad en la que se compra el artículo. El valor se recupera automáticamente de la configuración del artículo. Sin embargo, puede modificarla si se configuran las conversiones de unidades. |
| **Importe** | El importe bruto, menos descuentos, con la transacción de previsión contribuye a la previsión. |
| **Divisa** | Divisa usada para la transacción de previsión. La divisa predeterminada se introduce automáticamente, pero usted puede seleccionar otra divisa. |
| (Otras dimensiones) | Las dimensiones adicionales se pueden mostrar como columnas en la cuadrícula. Para seleccionar las dimensiones adicionales que se muestran, seleccione **Dimensiones de la pantalla** en el Panel de acciones. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>La pestaña General en la página Previsión de suministro

La pestaña **General** muestra más información acerca de la línea que está actualmente seleccionada en la pestaña **Descripción general**. Parte de esta información se repite en la pestaña **Descripción general**. La siguiente tabla describe los campos que son exclusivos de la pestaña **General**.

| Campo | Descripción |
|---|---|
| Informe | Ajuste esta opción en *Sí* para incluir la transacción en los informes. |
| Comentarios | Escriba cualquier comentario que pueda tener sobre la transacción de previsión. |
| Activa | Seleccione esta casilla de verificación para incluir la transacción en los informes presupuestarios. |
| Incluir en previsiones de flujo de efectivo | Seleccione esta castilla de verificación para asignar la transacción de previsión a la contabilidad general. La configuración de esta casilla de verificación no se puede modificar para transacciones de informes. |
| Grupo de impuestos | El grupo impositivo que se usa para especificar los impuestos para la transacción de previsión. |
| Grupo de impuestos de artículos | El grupo impositivo del artículo que se usa para especificar los impuestos para la transacción de previsión. |
| Método | <p>Seleccione el método que se utiliza para asignar la transacción de previsión:</p><ul><li>**Ninguna**: ninguna asignación tiene lugar.</li><li>**Período**: pronostique la misma cantidad para cada período. Si selecciona este valor, especifique una cantidad en el campo **Por** y una unidad de tiempo en el campo **Unidad**.</li><li>**Clave**: asigne la cantidad de previsión de acuerdo con la clave de asignación de períodos que se especifica en el campo **Clave de período**. Puede usar este método cuando desee tener en cuenta la variación estacional.</li></ol>|
| Por | <p>Especifique el número de intervalos de tiempo que la previsión se extiende en el futuro. Este campo está disponible únicamente si selecciona *Período* en el campo **Método**.</p><p>Por ejemplo, seleccione *Período* en el campo **Método**, especifique *1* en el campo **Por** y seleccione *Meses* en el campo **Unidad**. Especifique una fecha final en el campo **Final** que se extiende un año en el futuro. En este caso, se creará una línea de previsión por cada mes del año próximo, basándose en el artículo y la cantidad indicados en la línea de encabezado.</p> |
| Unidad | Seleccione la unidad del intervalo de tiempo: *Dias*, *Meses*, o *Años*. La asignación corresponde, pues, al número de días, meses o años especificado en el campo **Por**.|
| Clave de período | Especifique la clave de asignación de períodos. |
| Fin | Especifique la fecha de finalización cuando se usan los campos **Por** y **Unidad**. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>La pestaña Artículo en la página Previsión de suministro

Seleccione la pestaña **Artículo** para mostrar más información de artículo sobre la línea que está actualmente seleccionada en la pestaña **Visión general**.

La cuadrícula en la parte superior de la pestaña **Artículo** repite la información del elemento que también se muestra en la pestaña **Descripción general**. Además, incluye el campo **Precio unitario**, que muestra el precio de compra para el número de unidades que se especifica en el campo **Unidad**. El precio por unidad se recupera automáticamente de la configuración del artículo, pero se puede modificar.

Los campos debajo de la cuadrícula proporcionan más detalles del artículo. Parte de esta información se repite de la pestaña **Descripción general**. La siguiente tabla describe los campos que son exclusivos de la pestaña **Artículo**.

| Campo | Descripción |
|---|---|
| Unidad de precio | El número de unidades a las que se aplica el precio de compra. El valor se recupera automáticamente de la tabla de artículos, pero puede modificarse. |
| Gastos en compras | Gastos fijos en el precio de compra. Los gastos no dependen de la cantidad. |
| Porcentaje de descuento | El descuento expresado en forma porcentual. |
| Importe de descuento | El descuento expresado en un importe por unidad de ventas. |
| Importe bruto | El importe cuando no se aplican descuentos. |
| Cantidad | La cantidad de la transacción expresada en unidad de inventario del artículo. |
| Sub L. MAT | El número de lista de materiales (L. MAT) de una sublista de materiales específica. |
| Subruta | El número de ruta de una subruta específica. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>La pestaña Dimensión financiera en la página Previsión de suministro

La pestaña **Dimensión financiera** muestra todos los valores de la dimensión financiera para la línea que está actualmente seleccionada en la pestaña **Descripción general**.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>La pestaña Dimensión de inventario en la página Previsión de suministro

La pestaña **Dimensión de inventario** muestra todos los valores de la dimensión de inventario para la línea que está actualmente seleccionada en la pestaña **Descripción general**.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>La cuadrícula Asignación en la página Previsión de suministro

Si está utilizando una clave de asignación de artículos, o si ha ingresado una previsión de artículo para uno o más períodos futuros, puede asignar la previsión seleccionando **Asignar previsión** en la barra de herramientas de la pestaña **Descripción general**. Luego, la cantidad se distribuye de la manera indicada por las líneas en la cuadrícula **Asignación**.

## <a name="demand-forecast-lines"></a>Líneas de previsión de la demanda

La previsión de la demanda le permite ingresar o generar demanda para un cliente. Ayuda a los empleados de ventas y marketing a informar a los empleados de planificación maestra sobre la demanda esperada durante el próximo período de previsión.

Puede ingresar una previsión de la demanda por artículo, grupo de artículos, clave de asignación de artículos, cliente y grupo de clientes. Para obtener información sobre todas las formas de abrir la página de **Previsión de la demanda** para varias entidades y registros, consulte la sección [Ver e ingresar manualmente las líneas de previsión](#manual-entry) anterior en este tema.

La parte superior de la página **Previsión de la demanda** proporciona una cuadrícula de líneas de previsión de la demanda y un conjunto de pestañas que puede usar para ver y establecer más información sobre una línea de previsión seleccionada. La parte inferior de la página proporciona una cuadrícula de **Asignación**.

Las siguientes subsecciones describen todos los campos que están disponibles en cada pestaña y todos los comandos que están disponibles en el Panel de acciones de la página y en la barra de herramientas en la pestaña **Descripción general**.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>Comandos del panel de acciones en la página de previsión de la demanda

La tabla siguiente describe los comandos disponibles en el panel de acciones de la página **Previsión de la demanda**.

| Comando | Descripción |
|---|---|
| Guardar | Guarde su configuración actual. |
| Editar | Habilite la configuración en la página que se va a editar. |
| Crear nuevo | Agregue una nueva línea de previsión a la cuadrícula superior. |
| Suprimir | Elimine la línea de previsión seleccionada de la cuadrícula superior. |
| Saldos de previsión | Vea los saldos de previsión que se han calculado para la id. de modelo de la línea seleccionada para el año fiscal actual. Los saldos se dividen por período (mes). |
| Previsión de flujo de efectivo | Vea las transacciones de previsión que se deben asignar a la contabilidad general. Para obtener más información consulte [Previsión de flujo de efectivo](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Mostrar dimensiones | Seleccione las dimensiones de seguimiento, almacenamiento y producto que deben mostrarse en la cuadrícula de la pestaña **Descripción general**. |
| Vista previa de contabilidad general | Vea las entradas de la contabilidad general para la transacción seleccionada. |
| Transferir líneas de presupuesto | Transferir líneas de presupuesto al proyecto seleccionado. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Comandos de la barra de herramientas en la pestaña Descripción general de la página de previsión de la demanda

La tabla siguiente describe los comandos disponibles en el panel de acciones de la pestaña **Descripción general** de la página **Previsión de la demanda**.

| Comando | Descripción |
|---|---|
| Asignar previsión | Si está utilizando un método de asignación, genere las líneas de programación individuales para la transacción de previsión. Luego, la cantidad de la línea se distribuye por fecha (de acuerdo con los intervalos de tiempo seleccionados), cantidad e importe para todo el horizonte de tiempo. |
| Actualización masiva | Abre la página **Editar transacciones de previsión**. (Ver la sección [Transacciones de previsión de actualización masiva](#bulk-update) más adelante en este tema.) |
| Previsión del inventario | Abra una vista de la página **Previsión de inventario** que se filtra para la combinación de artículo/modelo seleccionado. (Consulte la sección Previsión [de inventario](#inventory-forecast) más adelante en este tema.) |
| Crear requisito de artículo | Abra un cuadro de diálogo donde puede crear requisitos de artículos y pedidos de ventas o líneas de diario de artículos para transacciones de previsión relacionadas con el proyecto. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>La pestaña Descripción general en la página Previsión de la demanda

La siguiente tabla describe los campos en la pestaña **Descripción general** de la página **Previsión de la demanda**.

| Campo | Descripción |
|---|---|
| **Nombre de la tarea** | El nombre de la tarea por lotes usado para crear la linea de previsión. |
| **Modelo** | El modelo de previsión al que está asociada la transacción. |
| **Fecha** | La fecha de inicio de la transacción. |
| **Cuenta de cliente** | La cuenta de cliente con la que está asociada la transacción. |
| **Grupo de clientes** | El grupo de cliente con el que está asociada la transacción. |
| **Número de artículo** | El identificador del artículo. |
| **Nombre del producto** | Descripción del artículo. |
| **Clave de asignación de artículos** | La clave de asignación de artículos utilizada durante la asignación de previsión del inventario. |
| **Cantidad de ventas** | La cantidad de transacción en la unidad de ventas especificada. |
| **Unidad** | La unidad en la que se vende el artículo. |
| **Importe** | El importe bruto, excluyendo descuentos, con la transacción de previsión contribuye a la previsión. |
| **Precio de venta** | El precio de venta para el número de unidades que se especifica en el campo **Precio unitario**. El valor se recupera automáticamente de la configuración del artículo, pero se puede modificar. |
| **Divisa de ventas** | Divisa usada para la transacción de previsión. La divisa predeterminada se introduce automáticamente, pero usted puede seleccionar otra divisa. |
| **Cantidad PC** | La cantidad prevista en la unidad de peso capturado especificada. |
| **Unidad de PC** | La unidad de peso capturado en la que se vende el artículo. El valor se recupera automáticamente de la configuración del artículo. |
| (Otras dimensiones) | Las dimensiones de seguimiento, almacenamiento y producto se pueden mostrar como columnas en la cuadrícula. Para seleccionar las dimensiones adicionales que se muestran, seleccione **Dimensiones de la pantalla** en el Panel de acciones. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>La pestaña General en la página Previsión de la demanda

La pestaña **General** muestra más información acerca de la línea que está actualmente seleccionada en la pestaña **Descripción general**. Parte de esta información se repite en la pestaña **Descripción general**. La siguiente tabla describe los campos que son exclusivos de la pestaña **General**.

| Campo | Descripción |
|---|---|
| Número de secuencia de previsión de la demanda | El número único de la línea de previsión de la demanda. Este número se genera mediante el uso de la secuencia numérica que se selecciona para las previsiones de la demanda en la página **Parámetros de planificación maestra**. |
| Grupo de artículos | El grupo de artículos con el que está asociada la transacción. |
| Informe | Ajuste esta opción en *Sí* para incluir la transacción en los informes. |
| Comentarios | Escriba cualquier comentario que pueda tener sobre la transacción de previsión. |
| Activa | Seleccione esta casilla de verificación para incluir la transacción en los informes presupuestarios. La configuración de esta casilla de verificación no se puede modificar para transacciones de informes. |
| Incluir en previsiones de flujo de efectivo | Seleccione esta castilla de verificación para asignar la transacción de previsión a la contabilidad general. La configuración de esta casilla de verificación no se puede modificar para transacciones de informes. Para obtener más información consulte [Previsión de flujo de efectivo](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Grupo de impuestos | El grupo impositivo que se usa para especificar los impuestos para la transacción de previsión. |
| Grupo de impuestos de artículos | El grupo impositivo del artículo que se usa para especificar los impuestos para la transacción de previsión. |
| Método | <p>Seleccione el método que se utiliza para asignar la transacción de previsión:</p><ul><li>**Ninguna**: ninguna asignación tiene lugar.</li><li>**Período**: pronostique la misma cantidad para cada período. Si selecciona este valor, especifique una cantidad en el campo **Por** y una unidad de tiempo en el campo **Unidad**.</li><li>**Clave**: asigne la cantidad de previsión de acuerdo con la clave de asignación de períodos que se especifica en el campo **Clave de período**. Puede usar este método cuando desee tener en cuenta la variación estacional.</li><ul>|
| Por | <p>Especifique el número de intervalos de tiempo que la previsión se extiende en el futuro. Este campo está disponible únicamente si selecciona *Período* en el campo **Método**.</p><p>Por ejemplo, seleccione *Período* en el campo **Método**, especifique *1* en el campo **Por** y seleccione *Meses* en el campo **Unidad**. Especifique una fecha final en el campo **Final** que se extiende un año en el futuro. En este caso, se creará una línea de previsión por cada mes del año próximo, basándose en el artículo y la cantidad indicados en la línea de encabezado. |
| Unidad | Seleccione la unidad del intervalo de tiempo: *Dias*, *Meses*, o *Años*. La asignación corresponde, pues, al número de días, meses o años especificado en el campo **Por**.|
| Clave de período | Especifique la clave de asignación de período que se utiliza para asignar la previsión. Para obtener más información, consulte [Asignación de datos de la planificación presupuestaria](../../finance/budgeting/budget-planning-data-allocation.md). |
| Fin | Especifique la fecha de finalización cuando se usan los campos **Por** y **Unidad**. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>La pestaña Artículo en la página Previsión de la demanda

La pestaña **Artículo** muestra más información de artículo acerca de la línea que está actualmente seleccionada en la pestaña **Descripción general**. Parte de esta información se repite en la pestaña **Descripción general**. La siguiente tabla describe los campos que son exclusivos de la pestaña **Artículo**.

| Campo | Descripción |
|---|---|
| Unidad de precio | El número de unidades de ventas al que se aplica el precio de ventas. El valor se recupera automáticamente de la tabla de artículos, pero puede modificarse. |
| Gastos de ventas | Gastos fijos en el precio de venta. Los gastos no dependen de la cantidad. |
| Precio de coste | El coste de la transacción de previsión actual por unidad de inventario. El valor se recupera de la tabla Artículos, pero puede modificarse. |
| Porcentaje de descuento | El descuento expresado en forma porcentual. |
| Importe de descuento | El descuento expresado en un importe por unidad de ventas. |
| Importe bruto | El importe cuando no se aplican descuentos. |
| Cantidad del inventario | La cantidad de la transacción expresada en unidad de inventario del artículo. |
| Usar L. MAT específica | El número de L. MAT de una sub-L. MAT. |
| Usar ruta específica | El número de ruta de una subruta específica. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>La pestaña Proyecto en la página Previsión de la demanda

La pestaña **Proyecto** muestra más información de proyecto acerca de la línea que está actualmente seleccionada en la pestaña **Descripción general**. Parte de esta información se repite en las pestañas **Descripción general**, **General** o **Artículo**. La siguiente tabla describe los campos que son exclusivos de la pestaña **Proyecto**.

| Campo | Descripción |
|---|---|
| Fecha del proyecto | La fecha de la transacción de la previsión de la demanda. |
| Id. de proyecto | Identificador del proyecto al que hace referencia la transacción actual. |
| Fuente de financiación | La fuente de financiación que está asociada con la previsión de la demanda. |
| Número de actividad | La actividad que está asociada con la transacción de la previsión de la demanda. |
| Categoría | La categoría de coste de la transacción actual. |
| Propiedad de la línea | El estado al que está vinculada la transacción. |
| Id. de transacción | El identificador del sistema para la transacción de previsión de demanda. |
| Importe de coste | El importe de la transacción de la previsión de la demanda. |
| Precio unitario | Precio por unidad. |
| Autor de la modificación | El identificador del último trabajador que modificó la transacción seleccionada. |
| Fecha de la factura | Introduzca la fecha de pago esperada. |
| Fecha de eliminación | Visualice o modifique la fecha de eliminación. Cuando se crea la previsión, la fecha de eliminación se establece en la fecha final del proyecto. Si el proyecto no tiene fecha final, se aplica la fecha del proyecto. Este campo solo se aplica a proyectos de precio fijo y de inversión. |
| Fecha de pago del coste | Escriba la fecha prevista del pago de la compra. |
| Fecha de pago de ventas | Escriba la fecha prevista del pago de las ventas. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>La pestaña Dimensión financiera en la página Previsión de la demanda

La pestaña **Dimensión financiera** muestra todos los valores de la dimensión financiera para la línea que está actualmente seleccionada en la pestaña **Descripción general**.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>La pestaña Dimensión de inventario en la página Previsión de la demanda

La pestaña **Dimensión de inventario** muestra todos los valores de la dimensión de inventario para la línea que está actualmente seleccionada en la pestaña **Descripción general**.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>La cuadrícula Asignación en la página Previsión de la demanda

Si está utilizando una clave de asignación de artículos, o si ha ingresado una previsión de artículo para uno o más períodos futuros, puede asignar la previsión seleccionando **Asignar previsión** en la barra de herramientas de la pestaña **Descripción general**. Luego, la cantidad se distribuye de la manera indicada por las líneas en la cuadrícula **Asignación**.

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Previsión del inventario

Las páginas de líneas de previsión de suministro y demanda tienen un botón de **Previsión de inventario** que abre una vista de la página **Previsión de inventario** que se filtra para la misma combinación de artículo/modelo. La previsión de inventario representa un equilibrio entre el suministro y la demanda que se ingresaron para el mismo artículo. Este valor se puede editar. La previsión de inventario ayuda al equipo de administración de inventario a revisar los cambios esperados en el inventario disponible de un artículo durante el próximo período que se ha previsto.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>El panel de acciones en la página de previsión de inventario

La tabla siguiente describe los comandos disponibles en el panel de acciones de la página **Previsión de inventario**.

| Acción | Descripción |
|---|---|
| Previsión del suministro | Abra una vista de la página **Previsión de sumnistro** que se filtra para la misma combinación de artículo/modelo/fecha. |
| Previsión de la demanda | Abra una vista de la página **Previsión de la demanda** que se filtra para la misma combinación de artículo/modelo/fecha. |
| Inventario \> Mostrar dimensiones | Seleccione las dimensiones de seguimiento, almacenamiento y producto que deben mostrarse en la cuadrícula **Descripción general**. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>La cuadrícula en la página de previsión de inventario

La siguiente tabla describe los campos en la cuadrícula en la página **Previsión de inventario**.

| Campo | Descripción |
|---|---|
| **Modelo** | El modelo de previsión al que está asociada la transacción. |
| **Número de artículo** | El identificador del artículo. |
| **Fecha del presupuesto** | La fecha de la transacción de previsión. |
| **Tipo de previsión** | La fuente de la transacción (*Previsión de la demanda* o *Previsión de suministro*). |
| **Cantidad PC** | La cantidad prevista en la unidad de peso capturado. |
| **Cantidad** | La cantidad prevista en la unidad de inventario. |
| **PC acumulado** | La cantidad de previsión acumulada en la unidad de peso capturado cuando se han acumulado varias líneas de previsión para el mismo artículo. |
| **Sub L. MAT** | El número de L. MAT de una sub L. MAT. |
| **Subruta** | El número de ruta de una subruta específica. |
| (Otras dimensiones) | Las dimensiones adicionales se pueden mostrar como columnas en la cuadrícula. Para seleccionar las dimensiones adicionales que se muestran, seleccione **Inventario \> Dimensiones de la pantalla** en el Panel de acciones. |

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Transacciones de previsión de actualización masiva

Use este procedimiento para procesar líneas de transacción de previsión existentes. Puede copiar, editar y eliminar las líneas de transacción de previsión.

1. En la página de líneas de previsión de suministro o demanda, seleccione **Actualización masiva**.
1. En el cuadro de diálogo, seleccione **Filtro**.
1. En la pestaña **Rango**, seleccione los criterios que identifican los datos de previsión de origen que desea copiar, editar o eliminar. Estos datos podrían incluir el modelo de previsión, el número de artículo y la cuenta de cliente.
1. Seleccione **Aceptar** para confirmar su selección.

    Una vez seleccionados los datos, puede utilizar el cuadro de diálogo **Editar transacciones de previsión** para definir cómo desea copiarlo, editarlo o eliminarlo.

    > [!NOTE]
    > El paso de filtrado es un requisito previo para utilizar la funcionalidad de **Edición masiva**. Si lo omite, el programa selecciona y actualiza **todas** las líneas de previsión. Por lo tanto, podría causar involuntariamente la duplicación o eliminación de transacciones.

1. En la sección **Gestión**, seleccione si desea copiar, actualizar o eliminar las transacciones de previsión seleccionadas.
1. Use la sección **Modificaciones en el campo** para modificar los parámetros de la previsión. Seleccione la casilla del parámetro y, a continuación, seleccione de entre las opciones disponibles. Por ejemplo, seleccione la casilla de verificación **Modelo** y luego seleccione un número de modelo de previsión. Las líneas de previsión existentes se copian al modelo de previsión seleccionado.
1. Utilizar la sección **Cambio de periodo** para adelantar o atrasar las fechas de inicio y finalización de la previsión. Seleccione la casilla de verificación y luego use los campos de cantidad y periodo para definir cómo se debe modificar el periodo de tiempo para las fechas de la previsión. Puede ingresar una cantidad negativa para adelantar la fecha de inicio (es decir, hacerlo antes).

    Por ejemplo, para atrasar la fecha de inicio de la transacción prevista en seis meses, seleccione la casilla de verificación, introduzca *6* como la cantidad, y seleccione *Meses* como período.

1. Use la sección **Corregir campo** para actualizar los datos de previsión reales. En el campo **Campo**, seleccione el criterio que desea modificar. En el campo **Factor**, indique un factor multiplicador para aplicar al criterio seleccionado, o especifique una constante para añadir o restar. Por ejemplo, seleccione *Cantidad* como criterio, e ingrese un factor de *1,5* para multiplicar la cantidad del artículo por 1,5. También puede indicar una constante de *-25* para reducir la cantidad de artículos en 25 unidades.
1. Utilice la sección **Dimensiones financieras** para actualizar las dimensiones financieras de las líneas de previsión. Seleccione las dimensiones financieras que desea cambiar y luego ingrese un valor para aplicar a las dimensiones seleccionadas.
1. Seleccione **OK** para aplicar sus cambios.

## <a name="use-forecasts-with-master-planning"></a>Usar previsiones con planificación maestra

Después de ingresar su pronóstico de demanda y / o pronóstico de suministro, puede incluir los pronósticos durante la planificación maestra para contabilizar la demanda y / o suministro esperados en su ejecución de planificación maestra. Cuando se incluyen previsiones en la planificación maestra, se calculan las necesidades brutas de materiales y capacidad, y se generan los pedidos planificados.

### <a name="set-up-a-master-plan-to-include-an-inventory-forecast"></a>Configurar un plan maestro para incluir un pronóstico de inventario

Para configurar un plan maestro de modo que incluya un pronóstico de inventario, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un plan existente o cree uno nuevo.
1. En la ficha rápida **General**, establezca los siguientes campos:

    - **Modelo de previsión** - Seleccione el modelo de previsión para aplicar. Este modelo se considerará cuando se genere una sugerencia de suministro para el plan maestro actual.
    - **Incluir previsión de suministro** - Establezca esta opción en *Sí* para incluir la previsión de suministro en el plan maestro actual. Si se configura en *No*, las transacciones de previsión de suministro no se incluirán en el plan maestro.
    - **Incluir previsión de la demanda** - Establezca esta opción en *Sí* para incluir la previsión de demanda en el plan maestro actual. Si se configura en *No*, las transacciones de previsión de demanda no se incluirán en el plan maestro.
    - **Método utilizado para reducir los requisitos de pronóstico** - Seleccione el método que se debe utilizar para reducir los requisitos de pronóstico. Para más información, vea [Claves de reducción de previsión](planning-optimization/demand-forecast.md#reduction-keys).

1. En la ficha desplegable **Vallas de tiempo en días**, puede establecer los siguientes campos para especificar el período durante el cual se incluye el pronóstico:

    - **Plan de previsión** - Establezca esta opción en *Sí* para anular el límite de tiempo del plan de pronóstico que se origina en los grupos de cobertura individuales. Establézcalo en *No* para utilizar los valores de los grupos de cobertura individuales para el plan maestro actual.
    - **Período de tiempo de pronóstico** - Si configura la opción **Plan de previsión** como *Sí*, especifique el número de días (a partir de la fecha de hoy) que se debe aplicar el pronóstico de demanda.

    > [!IMPORTANT]
    > La opción **Plan de previsión** aún no es compatible con la Optimización de la planificación.

### <a name="run-a-master-plan-that-includes-an-inventory-forecast"></a>Ejecutar un plan maestro que incluya un pronóstico de inventario

Para ejecutar un plan maestro de modo que incluya un pronóstico de inventario, siga estos pasos.

1. Vaya a **Planificacion maestra \> Espacios de trabajo \> Planificacion maestra**.
1. En el campo **Plan maestro**, ingrese o seleccione el plan maestro que configuró en el procedimiento anterior.
1. En el icono **Planificación maestra**, seleccione **Ejecutar**.
1. En el cuadro de diálogo **Planificacion maestra**, establezca la opción **Seguimiento del tiempo de procesamiento** en *Sí*.
1. En el campo **Número de subprocesos**, especifique un número.
1. En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.
1. Aparece un cuadro de diálogo de editor de consultas estándar. En la pestaña **Rango**, seleccione la fila donde el campo **Campo** está establecido en *Número de artículo*.
1. En el campo **Criterios**, seleccione el número de artículo para incluir en el plan.
1. Seleccione **Aceptar**.

Para ver los requisitos que se calculan, abra la página **Requisitos brutos**. Por ejemplo, en la página **Productos emitidos**, en el panel Acción, en la pestaña **Plan**, en el grupo **Requisitos**, seleccione **Requisito bruto**.

Para ver los pedidos planificados que se generan, vaya a **Planificacion maestra \> Común \> Pedidos planificados** y seleccione el plan de previsión adecuado.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la previsión de la demanda](introduction-demand-forecasting.md)
- [Configuración de previsión de demanda](demand-forecasting-setup.md)
- [Generar previsión estadística de línea base](generate-statistical-baseline-forecast.md)
- [Realización de ajustes manuales en la previsión de línea base](manual-adjustments-baseline-forecast.md)
- [Planificación maestra con previsiones de demanda](planning-optimization/demand-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
