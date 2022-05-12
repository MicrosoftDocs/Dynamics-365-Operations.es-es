---
title: Cómo los trabajadores usan la interfaz de ejecución de la planta de producción
description: Este tema describe cómo se utiliza la interfaz de ejecución de la planta de producción desde el punto de vista de un trabajador.
author: johanhoffmann
ms.date: 01/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f163b8feb906470f31a648bf09abf5647c5f1bab
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645001"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Cómo los trabajadores usan la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]

La interfaz de ejecución de la planta de producción está optimizada para la interacción táctil. Su diseño proporciona un contraste visual que cumple con los requisitos de accesibilidad para entornos de planta. Ofrece las mismas capacidades funcionales que el dispositivo de tarjeta de trabajo. Sin embargo, también permite iniciar varios trabajos en paralelo desde una lista de trabajos. (Esta capacidad también se conoce como *agrupación de trabajos*). Además, desde una lista de trabajos, los trabajadores pueden abrir una guía que se creó en Microsoft Dynamics 365 Guide. De esta forma, pueden obtener instrucciones visuales en un HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Iniciar sesión en la interfaz de ejecución de la planta de producción como un trabajador

Antes de que los trabajadores puedan empezar a usar el dispositivo, un supervisor o personal técnico deben prepararlo y abrir la página correcta con el formato Dynamics 365 Supply Chain Management. Para obtener más información sobre cómo configurar el dispositivo, consulte [Configurar un dispositivo para ejecutar la interfaz de ejecución de la planta de producción](production-floor-execution-setup.md).

Una vez que se ha preparado el dispositivo, aparece la página de inicio de sesión. Esta página muestra información sobre el estado de los trabajos para la celda de trabajo local. Esta información se actualiza periódicamente. En la página, los trabajadores usan sus credenciales de identificación para firmar. Aunque los trabajadores no tienen que tener una cuenta de usuario para Supply Chain Management, sí deben tener una cuenta de *trabajador con tiempo registrado* que pueden usar cuando inician sesión.

![Página de inicio de sesión de la interfaz de ejecución de la planta de producción.](media/pfei-sign-in-page.png "Página de inicio de sesión de la interfaz de ejecución de la planta de producción")

Las secciones restantes de este tema describen cómo interactúan los trabajadores con la interfaz.

## <a name="all-jobs-tab"></a>Pestaña Todos los trabajos

La pestaña **Todos los trabajos** proporciona una lista de trabajos que muestra todos los trabajos de producción que tienen un estado de *No empezado*, *Detenido* o *Empezado*. (El nombre de esta pestaña se puede personalizar y puede ser diferente para su sistema).

![Pestaña Todos los trabajos.](media/pfei-all-jobs-tab.png "Pestaña Todos los trabajos")

La lista de trabajos tiene las siguientes columnas. Los números se corresponden con los números de la ilustración anterior.

1. **Columna de selección**: la columna de la izquierda utiliza marcas de verificación para indicar los trabajos que ha seleccionado el trabajador. Los trabajadores pueden seleccionar varios trabajos de la lista al mismo tiempo. Para seleccionar todos los trabajos de la lista, active la marca de verificación en el encabezado de la columna. Cuando se selecciona un solo trabajo, los detalles sobre ese trabajo se muestran en la parte inferior de la página.
1. **Columna de estado del trabajo**: esta columna utiliza símbolos para indicar el estado de cada trabajo. Los trabajos que no tienen símbolo en esta columna tienen el estado *No iniciado*. Un triángulo verde indica trabajos que tienen el estado *Iniciado*. Dos líneas verticales amarillas indican trabajos que tienen el estado *Detenido*.
1. **Columna de alta prioridad**: esta columna usa signos de exclamación para indicar trabajos que tienen alta prioridad.
1. **Orden**: esta columna muestra el número de pedido de producción de un trabajo.
1. **Descripción**: esta columna muestra una descripción de la operación de la que forma parte un trabajo.
1. **Solicitado**: esta columna muestra la cantidad que se planea producir con un trabajo.
1. **Iniciado**: esta columna muestra la cantidad que ya se inició para un trabajo.
1. **Completado**: esta columna muestra la cantidad que ya se completó para un trabajo.
1. **Desechado**: esta columna muestra la cantidad que ya se desechó para un trabajo.
1. **Restante**: esta columna muestra la cantidad que queda por completar de un trabajo.

## <a name="active-jobs-tab"></a>Pestaña Trabajos activos

Las pestañas **Trabajos activos** muestran una lista de todos los trabajos que el trabajador que inició sesión ya ha comenzado. (El nombre de esta pestaña se puede personalizar y puede ser diferente para su sistema).

![Pestaña Trabajos activos.](media/pfei-active-jobs-tab.png "Pestaña Trabajos activos")

La lista de trabajos activos tiene las siguientes columnas:

- **Columna de selección**: la columna de la izquierda utiliza marcas de verificación para indicar los trabajos que ha seleccionado el trabajador. Los trabajadores pueden seleccionar varios trabajos de la lista al mismo tiempo. Para seleccionar todos los trabajos de la lista, active la marca de verificación en el encabezado de la columna. Cuando se selecciona un solo trabajo, los detalles sobre ese trabajo se muestran en la parte inferior de la página.
- **Orden**: esta columna muestra el número de pedido de producción de un trabajo.
- **Descripción**: esta columna muestra una descripción de la operación de la que forma parte un trabajo.
- **Solicitado**: esta columna muestra la cantidad que se planea producir con un trabajo.
- **Iniciado**: esta columna muestra la cantidad que ya se inició para un trabajo.
- **Completado**: esta columna muestra la cantidad que ya se completó para un trabajo.
- **Desechado**: esta columna muestra la cantidad que ya se desechó para un trabajo.
- **Restante**: esta columna muestra la cantidad que queda por completar de un trabajo.

## <a name="my-jobs-tab"></a>Pestaña Mis trabajos

La pestaña **Mis trabajos** permite a los trabajadores ver fácilmente todos los trabajos no iniciados y sin terminar que se les asignan específicamente. Es útil en empresas donde los trabajos a veces o siempre se asignan a trabajadores específicos (recursos humanos) en lugar de otros tipos de recursos (como máquinas).

El sistema de programación asigna automáticamente cada trabajo de producción a un registro de recursos específico y cada registro de recursos tiene un tipo (como máquina o humano). Cuando configura a un empleado como trabajador de producción, puede asociar la cuenta del trabajador con un registro de recursos humanos único.

La pestaña **Mis trabajos** enumera todos los trabajos no iniciados y sin terminar que se han asignado al registro de recursos humanos del trabajador que inició sesión, si hay algún trabajador que haya iniciado sesión. Nunca enumera los trabajos que se han asignado a una máquina u otro tipo de recurso, incluso si el trabajador que inició sesión comenzó a trabajar en esos trabajos.

Para ver todos los trabajos iniciados por el trabajador que inició sesión, independientemente del tipo de recurso al que esté asignado cada trabajo, use la pestaña **trabajos activos**. Para ver todos los trabajos sin terminar que coinciden con la configuración del filtro de trabajo local, independientemente del trabajador o el estado de inicio, use la pestaña **Todos los trabajos**.

![Pestaña Mis trabajos.](media/pfei-my-jobs-tab.png "Pestaña Mis trabajos")

## <a name="my-machine-tab"></a>Pestaña Mi máquina

La pestaña **Mi maquina** permite a los trabajadores seleccionar un activo que está conectado a un recurso de máquina dentro del filtro establecido en la pestaña **Todos los trabajos**. Luego, el trabajador puede ver el estado y la salud del activo seleccionado leyendo los valores de hasta cuatro contadores seleccionados y listas de solicitudes de mantenimiento recientes y tiempos de inactividad registrados. El trabajador también puede solicitar mantenimiento para el activo seleccionado y registrar y editar el tiempo de inactividad de la máquina. (El nombre de esta pestaña se puede personalizar y puede ser diferente para su sistema).

![La pestaña Mi máquina.](media/pfei-my-machine-tab.png "La pestaña Mi máquina")

La pestaña **Mi maquina** tiene las siguientes columnas. Los números se corresponden con los números de la ilustración anterior.

1. **Activo de la máquina** - Seleccione el activo de la máquina que desea rastrear. Empiece a escribir un nombre para seleccionar de una lista de activos coincidentes, o seleccione el icono de la lupa para seleccionar de una lista de todos los activos asociados con los recursos que están dentro del filtro de la lista de trabajos.

    > [!NOTE]
    > Los usuarios de Supply Chain Management pueden asignar un recurso a cada activo según sea necesario utilizando la página **Todos los activos** (en la pestaña **Activo fijo**, usando la lista desplegable **Recurso**). Para obtener más información, consulte [Crear un activo](../asset-management/objects/create-an-object.md).

1. **Configuraciones** - Seleccione el icono de engranaje para abrir un cuadro de diálogo donde puede elegir qué contadores ver para el activo de máquina seleccionado. Los valores de estos contadores se muestran en la parte superior de la pestaña **Gestión de activos**. El menú **Configuraciones** (que se muestra en la siguiente captura de pantalla) le permite habilitar hasta cuatro contadores. Para cada contador que desee habilitar, use el campo de búsqueda en la parte superior del icono para seleccionar un contador. Las listas del campo de búsqueda enumera todos los contadores asociados al activo seleccionado en la parte superior de la página **Gestión de activos**. Configure cada contador para supervisar el valor **Agregado** o el último valor **Real** para el contador. Por ejemplo, si configura un contador que rastrea cuántas horas ha estado funcionando la máquina, debe configurarlo en **Agregado**. Si configura un contador para medir la temperatura o presión actualizada más reciente, debe configurarlo en **Real**. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.

    ![Configuración de la pestaña Mi máquina.](media/pfei-my-machine-tab-settings.png "Configuración de la pestaña Mi máquina")

1. **Solicitar mantenimiento** - Seleccione este botón para abrir un cuadro de diálogo donde puede crear una solicitud de mantenimiento. Podrá proporcionar una descripción y una nota. La solicitud se presentará a un usuario de Supply Chain Management, que luego podrá convertir la solicitud de mantenimiento en una orden de trabajo de mantenimiento.
1. **Registrar el tiempo de inactividad** - Seleccione este botón para abrir un cuadro de diálogo donde puede registrar el tiempo de inactividad de la máquina. Podrá seleccionar un código de motivo e ingresar un intervalo de fecha/hora para el tiempo de inactividad. El registro del tiempo de inactividad de la máquina se utiliza para calcular la eficiencia del activo de la máquina.
1. **Ver o editar** - Seleccione este botón para abrir un cuadro de diálogo donde puede editar o ver los registros de tiempo de inactividad existentes.

## <a name="starting-and-completing-production-jobs"></a>Iniciar y completar trabajos de producción

Para iniciar un trabajo de producción, los trabajadores seleccionan un trabajo en la pestaña **Todos los trabajos** y después seleccionan **Iniciar trabajo** para abrir el cuadro de diálogo **Iniciar trabajo**.

![Cuadro de diálogo Iniciar trabajo.](media/pfei-start-job-dialog.png "Cuadro de diálogo Iniciar trabajo")

Los trabajadores utilizan el cuadro de diálogo **Iniciar trabajo** para confirmar la cantidad de producción y después iniciar el trabajo. Para ajustar la cantidad, los trabajadores pueden seleccionar el campo **Cantidad** y usar el teclado numérico que aparece. A continuación, los trabajadores seleccionan **Iniciar** para empezar a desarrollar el trabajo. El cuadro de diálogo **Iniciar trabajo** se cierra y el trabajo se agrega a la pestaña **Trabajos activos**.

Los trabajadores pueden iniciar un trabajo que se encuentra en cualquier estado. Cuando un trabajador inicia un trabajo que tiene el estado *No iniciado*, el campo **Cantidad** del cuadro de diálogo **Iniciar trabajo** muestra inicialmente la cantidad completa. Cuando un trabajador inicia un trabajo que tiene el estado *No iniciado* o *Detenido*, el campo **Cantidad** muestra inicialmente la cantidad restante.

## <a name="reporting-good-quantities"></a>Notificar buenas cantidades

Cuando un trabajador completa (o completa parcialmente) un trabajo, puede notificar buenas cantidades que se produjeron seleccionando un trabajo en la pestaña **Trabajos activos** y seleccionando a continuación **Notificar progreso**. En el cuadro de diálogo **Notificar progreso**, el trabajador introduce la cantidad buena a través del teclado numérico. La cantidad está en blanco de forma predeterminada. Después de especificar una cantidad, el trabajador puede actualizar el estado del trabajo a *En curso*, *Detenido* o *Terminado*.

![Cuadro de diálogo Notificar progreso.](media/pfei-report-progress-dialog.png "Cuadro de diálogo Notificar progreso")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Informar buenas cantidades en pedidos de lotes que tienen coproductos y subproductos

Los trabajadores pueden utilizar la interfaz de ejecución de la planta de producción para informar el progreso de los pedidos por lotes. Estos informes incluyen coproductos y productos derivados.

Algunos fabricantes, especialmente en las industrias de procesos, utilizan pedidos por lotes para gestionar sus procesos de producción. Los pedidos por lotes se crean a partir de fórmulas, y esas fórmulas se pueden definir para que tengan coproductos y subproductos como salida. Cuando se informa sobre los comentarios sobre esos pedidos por lotes, la cantidad de salida debe registrarse en el artículo de fórmula y también en los coproductos y subproductos.

Cuando un trabajador completa o completa parcialmente un trabajo en un pedido por lotes, puede informar las cantidades buenas o de desecho para cada producto que se define como salida para el pedido. Los productos que se definen como salida para un pedido de lote pueden ser del tipo *Fórmula*, *Coproducto* o *Subproducto*.

Para informar buenas cantidades de los productos, un trabajador selecciona un trabajo en la pestaña **Trabajos activos** y luego selecciona **Informe el progreso**.

Entonces, en el cuadro de diálogo **Informe el progreso**, el trabajador puede seleccionar entre los productos que se definen como salida para la orden de lote para informar. El trabajador puede seleccionar uno o varios productos de la lista y luego seleccionar **Informe el progreso**. Para cada producto, la cantidad está en blanco por defecto y el trabajador puede usar el teclado numérico para ingresar la cantidad. El trabajador puede utilizar los botones **Anterior** y **Siguiente** para moverse entre los productos seleccionados. Después de especificar la cantidad para cada producto, el trabajador puede actualizar el estado del trabajo a *En curso*, *Detenido* o *Terminado*.

![Informar sobre coproductos y productos derivados](media/report-co-by-products.png "Informar sobre coproductos y productos derivados")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Elaboración de informes sobre pedidos de lote para artículos de planificación

Cuando un trabajador completa un trabajo en un pedido de lote para un artículo de planificación, informará las cantidades solo de coproductos y subproductos, porque los artículos de planificación no contienen un artículo del tipo *Fórmula*.

### <a name="reporting-co-product-variation"></a>Informar la variación del coproducto

Si un pedido de lote se crea a partir de una versión de fórmula donde la opción **Variaciones de coproductos** está configurada en *Sí*, el trabajador puede informar sobre coproductos que no forman parte de la definición de los pedidos por lotes. Esta funcionalidad se utiliza en escenarios en los que puede producirse una salida de producto inesperada en el proceso de producción.

En este caso, el trabajador puede especificar el coproducto y la cantidad a reportar seleccionando **Variaciones de coproductos** en el cuadro de diálogo de progreso del informe. A continuación, el trabajador puede seleccionar entre todos los productos emitidos que se definen como coproductos.

### <a name="reporting-catch-weight-items"></a>Informar artículos con peso capturado

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Los trabajadores pueden utilizar la interfaz de ejecución de la planta de producción para informar el progreso de los pedidos por lotes que se crean para artículos de peso capturado. Los pedidos por lotes se crean a partir de fórmulas, que se pueden definir para que tengan productos de peso capturado y productos de fórmula, coproductos y subproductos. También se puede definir una fórmula para que tenga líneas de fórmula para los ingredientes definidos para el peso capturado. Los artículos con peso capturado utilizan dos unidades de medida para realizar un seguimiento del inventario: cantidad de peso capturado y cantidad de inventario. Por ejemplo, en la industria alimentaria, la carne en caja se puede definir como un artículo con peso capturado, en el que la cantidad de peso capturado se usa para rastrear el número de cajas y la cantidad de inventario se usa para rastrear el peso de las cajas.

## <a name="reporting-scrap"></a>Notificar residuo

Cuando un trabajador completa (o completa parcialmente) un trabajo, puede notificar residuos seleccionando un trabajo en la pestaña **Trabajos activos** y seleccionando a continuación **Notificar residuo**. En el cuadro de diálogo **Notificar residuo**, el trabajador introduce la cantidad de residuo a través del teclado numérico. El trabajador también selecciona un motivo (*Ninguno*, *Máquina*, *Operador* o *Material*).

![Cuadro de diálogo Notificar residuo.](media/pfei-report-scrap-dialog.png "Cuadro de diálogo Notificar residuo")

## <a name="adjust-material-consumption-and-make-material-reservations"></a>Ajustar el consumo de material y hacer reservas de material.

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Los trabajadores pueden ajustar el consumo de material para cada trabajo de producción. Esta funcionalidad se usa en escenarios donde la cantidad real de materiales consumidos por un trabajo de producción fue mayor o menor que la cantidad planificada. Por lo tanto, debe ajustarse para mantener los niveles de inventario actualizados.

Los trabajadores también pueden hacer reservas sobre el lote y los números de serie de los materiales. Esta funcionalidad se usa en escenarios en los que un trabajador debe especificar manualmente qué lote de material o números de serie se consumieron para cumplir con los requisitos de trazabilidad del material.

Los trabajadores pueden especificar la cantidad a ajustar seleccionando **Ajustar material**. Este botón no se encuentra disponible en las ubicaciones siguientes:

- En el cuadro de diálogo **Notificar residuo**
- En el cuadro de diálogo **Notificar progreso**
- En la barra de herramientas de la derecha

### <a name="adjust-material-consumption-from-the-report-scrap-and-report-progress-dialog-boxes"></a>Ajuste el consumo de material desde los cuadros de diálogo Informar de desecho e Informar de progreso

Después de que un trabajador ingresa la cantidad a informar en el cuadro de diálogo **Informar sobre el progreso** o **Informar de rechazo**, el botón **Ajustar material** pasa a estar disponible. Cuando el usuario selecciona este botón, aparece el cuadro de diálogo **Ajustar material**. Este cuadro de diálogo enumera los artículos que se planean consumir cuando se informa la cantidad buena o desechada para el trabajo.

La lista del cuadro de diálogo muestra la siguiente información:

- **Número de producto**: el producto maestro y las variantes del producto.
- **Nombre de producto** – El nombre del producto.
- **Propuesta**: la cantidad estimada de material que se consumirá cuando se notifique el progreso o el rechazo de la cantidad especificada para el trabajo.
- **Consumo**: la cantidad real de material que se consumirá cuando se notifique el progreso o el rechazo de la cantidad especificada para el trabajo.
- **Reservado** – La cantidad de material que se ha reservado físicamente en el inventario.
- **Unidad**: la unidad de la lista de materiales (L. MAT).

El lado derecho del cuadro de diálogo muestra la siguiente información:

- **Número de producto**: el producto maestro y las variantes del producto.
- **Estimada**: la cantidad estimada que se va a consumir.
- **Empezado** – La cantidad que se ha iniciado en el trabajo de producción.
- **Cantidad restante** – De la cantidad estimada, la cantidad que queda por consumir.
- **Cantidad liberada**: la cantidad que se ha consumido.

Se pueden realizar las siguientes acciones:

- El trabajador puede especificar la cantidad a ajustar de un material seleccionando **Ajustar consumo**. Después de confirmar la cantidad, la cantidad en la columna **Consumo** se actualiza con la cantidad ajustada.
- Cuando el trabajador selecciona **Ajustar material**, se crea un diario de lista de selección de producción. Este diario contiene los mismos artículos y cantidades que la lista **Ajustar material**.
- Cuando el trabajador ajusta una cantidad en el cuadro de diálogo **Ajustar material**, el campo **Propuesta** en la línea de diario correspondiente se actualiza con la misma cantidad. Si el trabajador selecciona **Cancelar** en el cuadro de diálogo **Ajustar material**, la lista de selección se elimina.
- Si el trabajador selecciona **OK**, la lista de selección no se elimina. Se publicará cuando el trabajo se informe en el cuadro de diálogo **Informar de rechazo** o **Informar sobre el progreso**.
- Si el trabajador selecciona **Cancelar** en el cuadro de diálogo **Informar del progreso** o **Notificar residuo**, la lista de selección se elimina.

### <a name="adjust-material-from-the-primary-or-secondary-toolbar"></a>Ajuste el material desde la barra de herramientas principal o secundaria

El botón **Ajustar material** se puede configurar para que aparezca en la barra de herramientas principal o secundaria. (Para más información, vea [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md)). Un trabajador puede seleccionar **Ajustar material** para un trabajo de producción que está en curso. En este caso, aparece el cuadro de diálogo **Ajustar material**, donde el trabajador puede hacer los ajustes deseados. Cuando se abre el cuadro de diálogo, se crea una lista de selección de producción que contiene líneas para las cantidades ajustadas para la orden de producción. Si el trabajador selecciona **Publicar ahora**, se confirma el ajuste y se contabiliza la lista de selección. Si el trabajador selecciona **Cancelar**, se elimina la lista de selección y no se hace ningún ajuste.

### <a name="adjust-material-consumption-for-catch-weight-items"></a>Ajustar el consumo de material para artículos con peso capturado

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Los trabajadores pueden ajustar el consumo de material para artículos con peso capturado. Esta funcionalidad se usa en escenarios donde la cantidad real de material de peso capturado consumido por un trabajo de producción fue mayor o menor que la cantidad planificada. Por lo tanto, debe ajustarse para mantener los niveles de inventario actualizados. Cuando un trabajador ajusta el consumo de un artículo de peso capturado, puede ajustar tanto la cantidad de peso capturado como la cantidad de inventario. Por ejemplo, si se planea que un trabajo de producción consuma cinco cajas que tienen un peso estimado de 2 kilogramos por caja, el trabajador puede ajustar tanto la cantidad de cajas a consumir como el peso de las cajas. El sistema validará que el peso especificado de las cajas esté dentro del umbral mínimo y máximo definido en el producto liberado.

### <a name="reserve-materials"></a>Reserva de materiales

En el cuadro de diálogo **Ajustar material**, un trabajador puede hacer y ajustar reservas de material seleccionando **Material de reserva**. El cuadro de diálogo **Material de reserva** que aparece muestra el inventario disponible físicamente para el artículo para cada dimensión de almacenamiento y seguimiento.

Si el material está habilitado para los procesos de almacén avanzados, la lista muestra solo el inventario físicamente disponible para la ubicación de entrada de producción del material. La ubicación de entrada de producción se define en el recurso donde se planifica el trabajo de producción. Si el número de artículo está controlado por lote o número de serie, se muestra la lista completa de números de lote y serie físicamente disponibles. Para especificar una cantidad a reservar, el trabajador puede seleccionar **Material de reserva**. Para eliminar una reserva existente, el trabajador puede seleccionar **Eliminar reserva**.

Para obtener más información sobre cómo configurar la ubicación de entrada de producción, consulte la siguiente publicación de blog: [Configuración de la ubicación de entrada de producción](/archive/blogs/axmfg/deliver-picked-materials-to-the-locations-where-the-materials-are-consumed-by-operations-in-production).

> [!NOTE]
> Las reservas que hace un trabajador en el cuadro de diálogo **Material de reserva** permanecerá cuando el trabajador seleccione **Cancelar** en el cuadro de diálogo **Informar sobre el progreso** o **Informar de rechazo**.
>
> No es posible ajustar reservas para artículos con peso capturado.

## <a name="completing-a-job-and-starting-a-new-job"></a>Completar un trabajo e iniciar un trabajo nuevo

Por lo general, los trabajadores completan un trabajo seleccionando uno o más trabajos actuales en la pestaña **Trabajos activos** y seleccionando a continuación **Notificar progreso**. A continuación, especifican la cantidad producida (la cantidad buena) y establecen el estado *Completado*. Si se seleccionó más de un trabajo, un trabajador puede usar los botones **Anterior** y **Siguiente** botones para moverse entre ellos. Para iniciar un nuevo trabajo, el trabajador lo selecciona en la pestaña **Todos los trabajos** y después selecciona **Iniciar trabajo**.

Un trabajador también puede iniciar un nuevo trabajo mientras su trabajo anterior sigue abierto. De nuevo, el trabajador selecciona el trabajo nuevo en la pestaña **Todos los trabajos** y después selecciona **Iniciar trabajo**. Sin embargo, en este caso, el cuadro de diálogo **Iniciar trabajo** informa al trabajador de que está trabajando actualmente en un trabajo y que, por lo tanto, debe detener o completar ese trabajo antes de comenzar el nuevo.

## <a name="working-on-multiple-jobs-in-parallel"></a>Trabajar en varios trabajos en paralelo

Un trabajador puede trabajar en varios trabajos al mismo tiempo (es decir, en paralelo). En este caso, el conjunto de trabajos en los que está trabajando el trabajador se denomina *agrupación de trabajos*. El trabajador puede agregar nuevos trabajos a la agrupación o completar uno o más trabajos de la agrupación. Los dos escenarios siguientes muestran cómo un trabajador puede trabajar en paralelo en varios trabajos.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Escenario 1: un trabajador que no tiene trabajos activos quiere iniciar dos trabajos y trabajar en ellos en paralelo

El trabajador selecciona los dos trabajos en la pestaña **Todos los trabajos** y después selecciona **Iniciar trabajo**. El cuadro de diálogo **Iniciar trabajo** muestra los dos trabajos seleccionados y el trabajador puede ajustar la cantidad de inicio para cada trabajo. A continuación, el trabajador confirma el cuadro de diálogo y puede iniciar los dos trabajos.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Escenario 2: un trabajador que tiene dos trabajos activos en curso quiere iniciar un tercer trabajo y trabajar en él en paralelo con los otros dos

El trabajador selecciona el tercer trabajo en la pestaña **Todos los trabajos** y después selecciona **Agrupación**. En el cuadro de diálogo **Agrupación**, el trabajador puede ajustar la cantidad inicial. A continuación, el trabajador confirma el cuadro de diálogo seleccionando **Agrupación**.

## <a name="working-on-indirect-activities"></a>Trabajar en actividades indirectas

Las actividades indirectas son actividades que no están directamente relacionadas con un pedido de producción. Las actividades indirectas se pueden definir de manera flexible, como se describe en [Configurar actividades indirectas para el tiempo y la asistencia](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Por ejemplo, Shannon, un trabajador de planta en Contoso, desea asistir a una reunión de la empresa y las reuniones se consideran una actividad indirecta. Se aplica uno de los dos escenarios siguientes:

- **Shannon trabaja en uno o más trabajos activos.** Shannon selecciona **Actividad**, identifica la actividad (reunión) y confirma su selección. Aparece un mensaje que le informa de que tiene trabajos en curso. A partir del mensaje, Shannon puede optar por completar o detener los trabajos en los que está trabajando antes de ir a la reunión.
- **Shannon no tiene ningún trabajo activo.** Shannon selecciona **Actividad**, identifica la actividad (reunión) y confirma su selección. Ahora está registrada como participante de la reunión.

En ambos escenarios, después de que Shannon confirme su selección, va a la página de inicio de sesión o a una página que esperará su confirmación de que ha regresado de la actividad indirecta. La página que aparece depende de la configuración de la interfaz de ejecución de la planta de producción. (Para obtener más información, vea [Configurar la interfaz de ejecución de la planta de producción](production-floor-execution-configure.md).)

## <a name="registering-breaks"></a>Registro de descansos

Los trabajadores pueden registrar descansos. Los descansos se pueden definir de manera flexible, como se describe en [Pago basado en registros](pay-based-on-registrations.md).

Un trabajador registra una pausa seleccionando **Descanso** y seleccionando a continuación la tarjeta que representa el tipo de descanso (por ejemplo, almuerzo). Una vez que el trabajador ha confirmado la selección, el dispositivo muestra la página de inicio de sesión o una página que esperará a que el trabajador confirme que ha regresado del descanso. La página que aparece depende de la configuración de la interfaz de ejecución de la planta de producción. (Para obtener más información, vea [Configurar la interfaz de ejecución de la planta de producción](production-floor-execution-configure.md).)

## <a name="view-the-my-day-dialog"></a>Ver el cuadro de diálogo "Mi día"

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

El diálogo **Mi día** proporciona a los trabajadores una visión general de sus registros y saldos. El diálogo se divide en las siguientes tres secciones:

- La sección principal enumera los registros que el trabajador actual realizó en una fecha seleccionada. Se abre mostrando los registros para el día actual y proporciona un selector de fechas que permite al trabajador ver otros días.
- La sección **Último saldo diario calculado** muestra los saldos actuales del trabajador por tiempo pagado, horas extra pagadas, ausencia y ausencia pagada. Estos valores se basan en los registros que se han calculado durante el proceso de aprobación.
- La sección **Saldos** proporciona una descripción general de los saldos en un período definido para categorías seleccionadas de registros (como vacaciones, tiempo estándar y horas extra). Estos saldos se basan en la forma en que se configuran los saldos estadísticos en el módulo **Tiempo y asistencia**. Para obtener más información sobre cómo configurar esto, consulte [Mostrar saldos de vacaciones en la interfaz de ejecución de la planta de producción](production-floor-execution-payroll-stats.md).

Los administradores pueden agregar esta característica a la interfaz colocando el botón **Mi día** en una barra de herramientas para cada pestaña relevante como se describe en [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md).

## <a name="working-in-teams"></a>Trabajar en equipos

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

Cuando se asigna a varios trabajadores al mismo trabajo de producción, pueden formar un equipo. El equipo puede designar a un trabajador como piloto. Los trabajadores restantes se convierten automáticamente en asistentes de ese piloto. Para el equipo resultante, solo el piloto debe registrar el estado del trabajo. Los registros de tiempo se aplican a todos los miembros del equipo.

### <a name="prerequisites"></a>Requisitos previos

Para usar equipos, un administrador debe habilitar la acción **Asistente** para la barra de herramientas principal en la pestaña **Todos los trabajos** de la interfaz de ejecución de la planta de producción. Para instrucciones, vea [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md).

### <a name="form-a-new-team-that-has-a-pilot-and-an-assistant"></a>Formar un nuevo equipo que tenga un piloto y un asistente

Un trabajador puede registrarse como asistente seleccionando **Asistente** en la pestaña **Todos los trabajos**. A continuación, en el cuadro de diálogo **Seleccionar empleado al cual asistir** que aparece, el trabajador puede seleccionar un piloto en una lista de trabajadores que están trabajando activamente en un trabajo. Una vez que el trabajador confirma su selección, se convierte en asistente del trabajador seleccionado, quien se convierte en el piloto del nuevo equipo.

### <a name="assign-a-new-pilot-to-an-existing-team"></a>Asignar un nuevo piloto a un equipo existente

Cuando un equipo quiere seleccionar un nuevo piloto, el piloto actual debe designar a otro trabajador del equipo como nuevo piloto. Para designar a un nuevo piloto, el piloto actual selecciona **Asistente** en la pestaña **Todos los trabajos**. A continuación, en el cuadro de diálogo **Cambiar piloto** que aparece, el piloto puede seleccionar un nuevo piloto en una lista de trabajadores que ya están en el equipo. Después de que el piloto actual confirme su selección, se elimina del equipo por completo. Sin embargo, puede reincorporarse al equipo cuando lo requiera.

### <a name="assistant-clocks-out"></a>Un asistente ficha la salida

Cuando un empleado que trabaja como asistente ficha la salida, deja el equipo. Si las opciones **Equipos permanentes** y **Reiniciar a la hora de entrada** están configuradas como *Sí*, un trabajador que ficha la salida se reincorporará automáticamente al equipo la próxima vez que fiche la entrada. Puede encontrar estas opciones en la pestaña **General** de la página **Parámetros de Tiempo y asistencia**.

## <a name="opening-instructions"></a>Instrucciones de apertura

Para abrir un documento adjunto a un trabajo, los trabajadores pueden seleccionar **Instrucciones**. El botón **Instrucciones** solo está disponible si un documento está asociado al trabajo en los datos maestros. Por ejemplo, un documento adjunto a un producto en la página **Productos lanzados** de Supply Chain Management estará disponible para que los trabajadores la abran en la interfaz de ejecución de la planta.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Abrir guías de realidad mixta para HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) puede ayudar a capacitar a los trabajadores proporcionando un aprendizaje práctico que utiliza la realidad mixta. Puede definir procesos estandarizados con instrucciones paso a paso que guíen a sus empleados hacia las herramientas y piezas que necesitan, y les muestren cómo utilizar estas herramientas en situaciones de trabajo reales. Esta es una visión general del proceso.

1. Cada vez que un trabajador abra una lista de trabajos en la interfaz de ejecución de la planta, la interfaz buscará todas las guías relevantes para los trabajos que se muestran.
1. El trabajador selecciona **Guías** para ver la lista de guías.
1. El trabajador selecciona una guía relevante de la lista.
1. La interfaz de ejecución de la planta muestra un código QR para la guía seleccionada.
1. El trabajador se pone un dispositivo HoloLens y mira el código QR para iniciar la guía.
1. El trabajador trabaja con la guía para aprender la tarea.

Para obtener más información sobre cómo crear, asignar y usar guías para HoloLens, consulte [Proporcionar guías de realidad mixta para trabajadores en producción](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
