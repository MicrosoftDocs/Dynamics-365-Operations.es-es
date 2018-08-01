---
title: Mejoras para el registro de extractos
description: "En este tema se describen mejoras que se han realizado en la función de registro de extractos."
author: josaw1
manager: AnnBe
ms.date: 04/26/2016
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 4961ee7fcc56af0646e421c9e040e2129cc322c4
ms.openlocfilehash: e6d6ede65764c0b35c9ce0985af0d9f2cd6653c0
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2018

---

# <a name="improvements-to-statement-posting"></a>Mejoras para el registro de extractos

[!include[banner](includes/banner.md)]

En este tema se describe el primer conjunto de mejoras que se han realizado en la función de registro de extractos. Estas mejoras están disponibles en Microsoft Dynamics 365 for Finance and Operations 7.3.2.

## <a name="activation"></a>Activación

De forma predeterminada, durante la implementación de Finance and Operations 7.3.2 se configura el programa para usar la antigua función de registro de extractos. Para habilitar la función mejorada de registro de extractos, debe activar su clave de configuración.

- Vaya **Administración del sistema** \> **Configuración** \> **Configuración de licencia** y, a continuación, en el nodo **Ventas al por menor** , desactive la casilla de verificación **Extractos comerciales (herencia)** , y seleccione la casilla de verificación **Extractos comerciales** .

Cuando la nueva clave de configuración de **Extractos comerciales** se haya activado, estará disponible un nuevo elemento de menú llamado **Extractos comerciales**. Este elemento de menú permite crear, calcular y enviar extractos manualmente. Cualquier extracto que produzca un error cuando se usa el proceso de registro de lotes también estará disponible a través de este elemento de menú. (Si está activada la clave de configuración **Extractos comerciales (herencia)**, el elemento de menú se llamará **Extractos abiertos**).

Finance and Operations incluye las siguientes validaciones relacionadas con estas claves de configuración:

- Las dos claves de configuración no pueden estar activadas a la vez.
- Se deben usar las mismas claves de configuración para todas las operaciones que se realizan en un extracto determinado durante su ciclo de vida (Crear, Calcular, Borrar, Registrar, etc.). Por ejemplo, no puede crear y calcular un extracto mientras está activada la clave de configuración **Extracto comercial (herencia)** y, a continuación intentar registrar el mismo extracto con la clave de configuración **Extracto comercial** activada.

> [!NOTE]
> Recomendamos que utilice la clave de configuración **Extractos comerciales** para la función mejorada de registro de extractos, a menos que tenga motivos de peso para utilizar la clave de configuración **Extractos comerciales (herencia)** en su lugar. Microsoft seguirá invirtiendo en la nueva función mejorada de registro de extractos, y es importante que empiece a utilizarla lo antes posible para beneficiarse de ella. La función de registro de extractos heredada quedará obsoleta en una versión futura.

## <a name="setup"></a>Configuración

Como parte de las mejoras de la función de registro de extractos, se han incluido tres nuevos parámetros en la ficha desplegable **Extracto** en la ficha **Registro** de la página **Parámetros comerciales**:

- **Deshabilitar borrado de extracto**: esta opción sólo es aplicable para la función de registro de extractos heredada. Recomendamos establecer esta opción en **No** para evitar que los usuarios borren extractos que están en estado semiregistrado. Si se desactivan los extractos que están en estado semiregistrado, los datos resultarán dañados. Solo debe establecer esta opción en **Sí** en circunstancias excepcionales.
- **Reservar inventario durante el cálculo**: se recomienda usar el trabajo por lotes **Registrar inventario** para la reserva de inventario, y establecer esta opción en **No**. Si esta opción se establece en **No**, la función mejorada del registro de extractos no intenta crear entradas de la reserva de inventario a la hora de calcular (si las entradas no se crearon a través del trabajo por lotes **Registrar inventario** ). En lugar de ello, la función solo crea entradas de reserva de inventario en el momento del registro. Esta implementación fue una elección de diseño basada en el hecho de que el intervalo de tiempo entre el proceso de cálculo y el proceso de registro suele ser pequeño. Sin embargo, si desea realizar la reserva de inventario en el momento del cálculo, puede establecer esta opción en **Sí**.

    La función heredada de registro de extractos siempre reserva el inventario durante el proceso de cálculo de extracto (si la reserva no se ha realizado ya con el trabajo por lotes **Registrar inventario** ), independientemente del valor de esta opción.

- **Deshabilitar recuento obligatorio**: si esta opción está establecida en **Sí**, el proceso de registro de un extracto continua, incluso si la diferencia entre el importe contado y el importe de transacción en el extracto está fuera del umbral definido en la ficha desplegable **Extracto** para tiendas.

Además, se ha introducido el campo **Número máximo de extractos registrados en paralelo** en la ficha desplegable **Procesamiento por lotes** . Este campo define el número de tareas por lotes que se deben ejecutar al mismo tiempo. Actualmente hay que establecer manualmente el valor de este campo.

Asimismo, con el nuevo proceso de registro, es necesario definir un **Producto de tarjeta regalo** en la ficha desplegable **Tarjeta regalo** de la pestaña **Registrar** de la página **Parámetros comerciales**. Esto ocurre incluso si la organización no utiliza tarjetas regalo. 

Tenga en cuenta que todos los valores y parámetros asociados a los registros de extracto, y que se definen en las tiendas y en la página **Parámetros comerciales**, son aplicables a la función mejorada del registro de extractos.

## <a name="processing"></a>En procesamiento
Los extractos se pueden calcular y registrar por lotes mediante los elementos de menú **Calcular extractos por lotes** y **Registrar extractos por lotes**. Como alternativa, se pueden calcular y registrar manualmente mediante el elemento de menú **Extractos comerciales** que proporciona la función mejorada de registro de extractos.

El proceso y los pasos para calcular y registrar extractos por lotes son iguales que en la antigua función de registro de extractos. Sin embargo, se han realizado mejoras significativas en el procesamiento básico en el back-end de los extractos. Estas mejoras hacen que el proceso sea más flexible, y ofrece mayor visibilidad de los estados y la información de errores. Esto permite a los usuarios localizar la causa original de los errores y continuar con el proceso de registro sin provocar daños en los datos y sin requerir correcciones de datos.

En las secciones siguientes se describen algunas de las mejoras importantes de la función de registro de extractos que aparecen en la interfaz de usuario para extractos comerciales y extractos registrados.

### <a name="status-details"></a>Detalles de estado
Se ha incluido un nuevo modelo de estado en la rutina de registro de extractos para los procesos de cálculo y registro.

En la siguiente tabla se describen los distintos estados y su orden durante el proceso de cálculo.

| Orden de estados | Comunidad autónoma      | Descripción |
|-------------|------------|-------------|
| 1           | Iniciado    | El extracto se ha creado y está listo para ser calculado. |
| 2           | Marcado     | Se identifican las transacciones que se encuentran en el ámbito del extracto a partir de los parámetros del extracto y se marcan con el identificador del extracto. |
| 3           | Calculado | Las líneas del extracto se han calculado y se han mostrado. |

En la siguiente tabla se describen los distintos estados y su orden durante el proceso de registro.

| Orden de estados | Estado                   | Descripción |
|-------------|-------------------------|-------------|
| 1           | Comprobado                 | Se han realizado varias validaciones relacionadas con los parámetros (por ejemplo, el gasto de disposición), y en el extracto y las líneas de extracto (por ejemplo, la diferencia entre el importe contado y el importe de transacción). |
| 2           | Agregado              | Las transacciones de ventas para clientes con nombre y sin nombre se han agregado según la configuración. Cada transacción agregada acaba por convertirse en un pedido de ventas. |
| 3           | Pedido de cliente creado  | Se han creado pedidos de ventas en el sistema a partir de la transacción agregada. |
| 4           | Pedido de cliente facturado | Los pedidos de ventas se han facturado. |
| 5           | Descuentos registrados        | Se han registrado los diarios de descuento periódico según la configuración. |
| 6           | Ingresos/gastos registrados   | Se han registrado las transacciones de ingresos/gastos como asientos. |
| 7           | Asientos vinculados         | Se han creado los diarios de pagos y se han vinculado a la factura correspondiente. |
| 8           | Pagos registrados         | Se han registrado los diarios de pago. |
| 9           | Tarjetas regalo registradas       | Se han registrado las transacciones de tarjetas regalo como asientos. |
| 10          | Registrada                  | El extracto se ha marcado como registrado. |

Cada estado de las tablas anterior es independiente por naturaleza, y se crea una dependencia jerárquica entre los estados. Esta dependencia fluye de arriba a abajo. Si el sistema detecta errores mientras procesa un estado, el estado del extracto se revierte al estado anterior. Cualquier reintento posterior del proceso se reanuda desde el estado en el que se produjo el error. Este enfoque tiene las siguientes ventajas:

- El usuario tiene plena visibilidad del estado en el que se produjo el error.
- Se evita que los datos resulten dañados. Por ejemplo, en la función antigua de registro de extractos había casos en los que se facturaban algunos pedidos de ventas y otros se dejaban abiertos. También había casos en los que algunos diarios de pago no tenían una factura correspondiente que liquidar a causa de un error en el registro de la factura.
- Los usuarios pueden ver el estado actual de un extracto mediante el botón **Detalles de estado** en el grupo **Detalles de ejecución** del extracto. La página de detalles de estado tiene tres secciones:

    - En la primera sección se muestra el estado actual del extracto, junto con el código de error y un mensaje de error detallado, en caso de error.
    - En la segunda sección se muestran los distintos estados del proceso de cálculo. Las pistas visuales indican los estados que se han ejecutado correctamente, los estados que no se han podido ejecutar a causa de errores y los estados que aún no se han ejecutado.
    - En la tercera sección se muestran los distintos estados del proceso de registro. Las pistas visuales indican los estados que se han ejecutado correctamente, los estados que no se han podido ejecutar a causa de errores y los estados que aún no se han ejecutado.

Además, el encabezado de las secciones segunda y tercera muestra el estado general del proceso relevante.

### <a name="event-logs"></a>Registros de evento
Un extracto pasa por distintas operaciones (por ejemplo, Crear, Calcular, Desactivar y Registrar), y se puede llamar a varias instancias de la misma operación durante el ciclo de vida del extracto. Por ejemplo, después de crear y calcular un extracto, un usuario puede borrarlo y calcularlo de nuevo. El botón **Registros de eventos** en el grupo **Detalles de ejecución** del extracto proporciona una traza de auditoría completa de las distintas operaciones aplicadas a un extracto, así como información acerca de cuándo se llamó a estas operaciones.

### <a name="aggregated-transactions"></a>Transacciones agregadas
Durante el proceso de registro se agregan las transacciones de ventas según la configuración. Estas transacciones agregadas se almacenan en el sistema y se usan para crear pedidos de ventas. Cada transacción agregada crea un pedido de ventas correspondiente en el sistema. Puede ver las transacciones agregadas utilizando el botón **Transacciones agregadas** en el grupo **Detalles de ejecución** del extracto.

La ficha **Detalles del pedido de ventas** de una transacción agregada muestra la siguiente información:

- **Identificador de registro**: el identificador de la transacción agregada.
- **Número de extracto**: el extracto al que pertenece la transacción agregada.
- **Fecha**: la fecha en la que se creó la transacción agregada.
- **Id. de ventas**: el identificador del pedido de ventas asignado cuando se crea un pedido de ventas a partir de la transacción agregada. Si este campo está en blanco, el pedido de ventas correspondiente no se ha creado.
- **Número de líneas agregadas**: el número total de líneas para la transacción agregada y el pedido de ventas.
- **Estado**: el último estado de la transacción agregada.
- **Id. de factura**: el identificador del pedido de ventas asignado cuando se factura el pedido de ventas de la transacción agregada. Si este campo está en blanco, la factura del pedido de ventas no se ha registrado.

La ficha **Detalles de transacción** de una transacción agregada muestra todas las transacciones comerciales que se han insertado en la transacción agregada. Las líneas agregadas en la transacción agregada muestran todos los registros agregados de las transacciones comerciales. Las líneas agregadas también muestra detalles como el artículo, la variante, cantidad, precio, el importe neto, la unidad, y el almacén. Básicamente, cada línea agregada corresponde a una línea de pedido de ventas.

En la página **Transacciones agregadas**, puede descargar los datos XML de una transacción agregada específica mediante el botón **Exportar XML del pedido de ventas** . Puede usar XML para depurar problemas que implican la creación y el registro de pedidos de ventas. Solo tiene que descargar los datos XML, cárgarlos en un entorno de pruebas y depurar el problema en el entorno de pruebas. La funcionalidad de descarga de datos XML para transacciones agregadas no está disponible para los extractos registrados.

La vista de transacciones agregadas proporciona las siguientes ventajas:

- El usuario tiene visibilidad de las transacciones agregadas con error durante la creación del pedido de ventas y pedidos de ventas con error durante la facturación.
- El usuario tiene visibilidad de cómo se agregan las transacciones.
- El usuario tiene una traza de auditoría completa, desde las transacciones comerciales hasta los pedidos de ventas y las facturas de ventas. Esta traza de auditoría no estaba disponible en la antigua función de registro de extractos.
- El archivo de datos XML agregados facilita la identificación de problemas durante la creación y facturación de pedidos de ventas.

### <a name="journal-vouchers"></a>Asientos del diario
El botón **Asientos del diario** del grupo **Detalles de ejecución** del extracto muestra las distintas transacciones de asiento que se crean para un extracto, y que están relacionadas con descuentos, cuentas de ingresos/gastos, tarjetas regalo, etc.

Actualmente, el programa solo muestra estos datos para los extractos registrados.

### <a name="payment-journals"></a>Diarios de pagos
El botón **Diarios de pagos** del grupo **Detalles de ejecución** del extracto muestra los distintos diarios de pagos creados para un extracto.

Actualmente, el programa solo muestra estos datos para los extractos registrados.

## <a name="other-improvements"></a>Otras mejoras

Se han realizado otras mejoras de backend en la función de registro de extractos que son visibles para el usuario. A continuación se incluyen algunos ejemplos:

- La agregación no tiene en cuenta las entidades de personal, terminal o turno. Como hay menos parámetros de agregación, también hay que procesar menos líneas de pedido de ventas.
- Los bloqueos en las tablas de transacciones comerciales se reducen introduciendo tablas de extensión adicionales y realizando operaciones de inserción en lugar de operaciones de actualización en las tablas de transacciones comerciales.
- El número de tareas por lotes en ejecución se ha parametrizado y restringindo. Por lo tanto, este número se puede adaptar específicamente al entorno de un cliente. En la antigua función del registro de extractos se creaba simultáneamente un número ilimitado de tareas por lotes. Los resultados eran cargas imposibles de gestionar, sobrecarga y cuellos de botella en el servidor de proceso por lotes.
- Los extractos se ponen en cola de forma eficaz mediante la priorización de los extractos que tienen el mayor número de transacciones.
- Los procesos por lotes como **Calcular extractos por lotes** y **Registrar extractos por lotes** se ejecutan sólo en modo de lotes. En la antigua función de registro de extractos, los usuarios podían elegir trabajar con estos procesos por lotes en un modo interactivo, que es una operación de un solo subproceso, a diferencia de los proceso por lotes, que son operaciones de múltiples subprocesos.
- En la antigua función de registro de extractos, cualquier error de una tarea por lotes ponía a todo el trabajo por lotes en estado de error. En la función mejorada, los errores de una tarea por lotes no ponen al trabajo por lotes en estado de error si las demás tareas por lotes se completaron correctamente. Debe evaluar el estado de registro de una ejecución por lotes en la página **Extractos comerciales**, donde puede ver los extractos que no se han registrado a causa de errores.
- En la antigua función de registro de extractos, la primera aparición de un error de extracto provoca el error de todo el lote. Los demás extractos no se procesan. En la función mejorada, el proceso por lotes sigue procesando todos extractos, incluso si se produce un error en alguno de ellos. Una ventaja es que los usuarios obtienen visibilidad del número exacto de extractos con error. Por lo tanto, los usuarios no tienen que verse atascados en un bucle continuo de corrección de errores y ejecución del proceso de registrar de extractos hasta que se hayan registrado todos los extractos.

## <a name="general-guidance-about-the-statement-posting-process"></a>Norma general sobre el proceso de registro de extractos

- Es recomendable ejecutar el proceso de registro de extractos en un lote, ya que la ejecución por lotes se beneficia de la potencia del marco de procesamiento de lotes basada en su capacidad de usar múltiples subprocesos. Es necesario utilizar múltiples subprocesos para gestionar los grandes volúmenes de transacciones típicos del registro de extractos.
- Es recomendable activar el inventario físico negativo en el grupo de modelos de artículos para poder disfrutar de una experiencia de registro sin problemas. En algunos casos es posible que no se puedan registrar extractos negativos a menos que haya un inventario físico negativo. Por ejemplo, en teoría, si sólo hay una unidad de un artículo en el inventario, y se ha realizado una transacción de ventas y una transacción de devolución para el artículo, debería ser posible registrar la transacción incluso si el inventario negativo no está activado. Sin embargo, dado que el proceso de registro de extracto utiliza tanto la transacción de ventas como la transacción de devolución en un único pedido de cliente, no hay garantía de que la línea de ventas se registre primero, seguida de la línea de devolución. Por lo tanto, pueden producirse errores. Si se activa el inventario negativo en este escenario, el registro de transacción no se verá afectado negativamente, y el sistema reflejará correctamente el inventario.
- Es recomendable usar la agregación al calcular y registrar extractos. Por lo tanto, se recomiendan los valores siguientes para algunos parámetros de agregación:

    - Vaya a **Comercio** \> **Configuración de sede central** \> **Parámetros** \> **Parámetros comerciales**. A continuación, en la ficha **Registro** , en la ficha desplegable **Actualización de inventario**, en el campo **Nivel de detalle** , seleccione **Resumen**.
    - Vaya a **Comercio** \> **Configuración de sede central** \> **Parámetros** \> **Parámetros comerciales**. A continuación, en la ficha **Registro**, en la ficha desplegable **Agregación**, establezca la opción **Transacciones de asiento** en **Sí**.

