---
title: Cómo los trabajadores usan la interfaz de ejecución de la planta de producción
description: Este tema describe cómo se utiliza la interfaz de ejecución de la planta de producción desde el punto de vista de un trabajador.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 02046da5e2487e203c9658c255f95a7c403d0b10
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814665"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Cómo los trabajadores usan la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]

La interfaz de ejecución de la planta de producción está optimizada para la interacción táctil. Su diseño proporciona un contraste visual que cumple con los requisitos de accesibilidad para entornos de planta. Ofrece las mismas capacidades funcionales que el dispositivo de tarjeta de trabajo. Sin embargo, también permite iniciar varios trabajos en paralelo desde una lista de trabajos. (Esta capacidad también se conoce como *agrupación de trabajos*). Además, desde una lista de trabajos, los trabajadores pueden abrir una guía que se creó en Microsoft Dynamics 365 Guide. De esta forma, pueden obtener instrucciones visuales en un HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Iniciar sesión en la interfaz de ejecución de la planta de producción como un trabajador

Antes de que los trabajadores puedan empezar a usar el dispositivo, un supervisor o personal técnico deben prepararlo y abrir la página correcta con el formato Dynamics 365 Supply Chain Management. Para obtener más información sobre cómo configurar el dispositivo, consulte [Configurar un dispositivo para ejecutar la interfaz de ejecución de la planta de producción](production-floor-execution-setup.md).

Una vez que se ha preparado el dispositivo, aparece la página de inicio de sesión. Esta página muestra información sobre el estado de los trabajos para la celda de trabajo local. Esta información se actualiza periódicamente. En la página, los trabajadores usan sus credenciales de identificación para firmar. Aunque los trabajadores no tienen que tener una cuenta de usuario para Supply Chain Management, sí deben tener una cuenta de *trabajador con tiempo registrado* que pueden usar cuando inician sesión.

![Página de inicio de sesión de la interfaz de ejecución de la planta de producción](media/pfei-sign-in-page.png "Página de inicio de sesión de la interfaz de ejecución de la planta de producción")

Las secciones restantes de este tema describen cómo interactúan los trabajadores con la interfaz.

## <a name="all-jobs-tab"></a>Pestaña Todos los trabajos

La pestaña **Todos los trabajos** proporciona una lista de trabajos que muestra todos los trabajos de producción que tienen un estado de *No empezado*, *Detenido* o *Empezado*. (El nombre de esta pestaña se puede personalizar y puede ser diferente para su sistema).

![Pestaña Todos los trabajos](media/pfei-all-jobs-tab.png "Pestaña Todos los trabajos")

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

![Pestaña Trabajos activos](media/pfei-active-jobs-tab.png "Pestaña Trabajos activos")

La lista de trabajos activos tiene las siguientes columnas:

- **Columna de selección**: la columna de la izquierda utiliza marcas de verificación para indicar los trabajos que ha seleccionado el trabajador. Los trabajadores pueden seleccionar varios trabajos de la lista al mismo tiempo. Para seleccionar todos los trabajos de la lista, active la marca de verificación en el encabezado de la columna. Cuando se selecciona un solo trabajo, los detalles sobre ese trabajo se muestran en la parte inferior de la página.
- **Orden**: esta columna muestra el número de pedido de producción de un trabajo.
- **Descripción**: esta columna muestra una descripción de la operación de la que forma parte un trabajo.
- **Solicitado**: esta columna muestra la cantidad que se planea producir con un trabajo.
- **Iniciado**: esta columna muestra la cantidad que ya se inició para un trabajo.
- **Completado**: esta columna muestra la cantidad que ya se completó para un trabajo.
- **Desechado**: esta columna muestra la cantidad que ya se desechó para un trabajo.
- **Restante**: esta columna muestra la cantidad que queda por completar de un trabajo.

## <a name="my-machine-tab"></a>Pestaña Mi máquina

La pestaña **Mi maquina** permite a los trabajadores seleccionar un activo que está conectado a un recurso de máquina dentro del filtro establecido en la pestaña **Todos los trabajos**. Luego, el trabajador puede ver el estado y la salud del activo seleccionado leyendo los valores de hasta cuatro contadores seleccionados y listas de solicitudes de mantenimiento recientes y tiempos de inactividad registrados. El trabajador también puede solicitar mantenimiento para el activo seleccionado y registrar y editar el tiempo de inactividad de la máquina. (El nombre de esta pestaña se puede personalizar y puede ser diferente para su sistema).
 
![La pestaña Mi máquina](media/pfei-my-machine-tab.png "La pestaña Mi máquina")

La pestaña **Mi maquina** tiene las siguientes columnas. Los números se corresponden con los números de la ilustración anterior.

1. **Activo de la máquina** - Seleccione el activo de la máquina que desea rastrear. Empiece a escribir un nombre para seleccionar de una lista de activos coincidentes, o seleccione el icono de la lupa para seleccionar de una lista de todos los activos asociados con los recursos que están dentro del filtro de la lista de trabajos.

    > [!NOTE]
    > Los usuarios de Supply Chain Management pueden asignar un recurso a cada activo según sea necesario utilizando la página **Todos los activos** (en la pestaña **Activo fijo**, usando la lista desplegable **Recurso**). Para obtener más información, consulte [Crear un activo](../asset-management/objects/create-an-object.md).

1. **Configuraciones** - Seleccione el icono de engranaje para abrir un cuadro de diálogo donde puede elegir qué contadores ver para el activo de máquina seleccionado. Los valores de estos contadores se muestran en la parte superior de la pestaña **Gestión de activos**. El menú **Configuraciones** (que se muestra en la siguiente captura de pantalla) le permite habilitar hasta cuatro contadores. Para cada contador que desee habilitar, use el campo de búsqueda en la parte superior del icono para seleccionar un contador. Las listas del campo de búsqueda enumera todos los contadores asociados al activo seleccionado en la parte superior de la página **Gestión de activos**. Configure cada contador para supervisar el valor **Agregado** o el último valor **Real** para el contador. Por ejemplo, si configura un contador que rastrea cuántas horas ha estado funcionando la máquina, debe configurarlo en **Agregado**. Si configura un contador para medir la temperatura o presión actualizada más reciente, debe configurarlo en **Real**. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.

    ![Configuración de la pestaña Mi máquina](media/pfei-my-machine-tab-settings.png "Configuración de la pestaña Mi máquina")

1. **Solicitar mantenimiento** - Seleccione este botón para abrir un cuadro de diálogo donde puede crear una solicitud de mantenimiento. Podrá proporcionar una descripción y una nota. La solicitud se presentará a un usuario de Supply Chain Management, que luego podrá convertir la solicitud de mantenimiento en una orden de trabajo de mantenimiento.
1. **Registrar el tiempo de inactividad** - Seleccione este botón para abrir un cuadro de diálogo donde puede registrar el tiempo de inactividad de la máquina. Podrá seleccionar un código de motivo e ingresar un intervalo de fecha/hora para el tiempo de inactividad. El registro del tiempo de inactividad de la máquina se utiliza para calcular la eficiencia del activo de la máquina.
1. **Ver o editar** - Seleccione este botón para abrir un cuadro de diálogo donde puede editar o ver los registros de tiempo de inactividad existentes.


## <a name="starting-and-completing-production-jobs"></a>Iniciar y completar trabajos de producción

Para iniciar un trabajo de producción, los trabajadores seleccionan un trabajo en la pestaña **Todos los trabajos** y después seleccionan **Iniciar trabajo** para abrir el cuadro de diálogo **Iniciar trabajo**.

![Cuadro de diálogo Iniciar trabajo](media/pfei-start-job-dialog.png "Cuadro de diálogo Iniciar trabajo")

Los trabajadores utilizan el cuadro de diálogo **Iniciar trabajo** para confirmar la cantidad de producción y después iniciar el trabajo. Para ajustar la cantidad, los trabajadores pueden seleccionar el campo **Cantidad** y usar el teclado numérico que aparece. A continuación, los trabajadores seleccionan **Iniciar** para empezar a desarrollar el trabajo. El cuadro de diálogo **Iniciar trabajo** se cierra y el trabajo se agrega a la pestaña **Trabajos activos**.

Los trabajadores pueden iniciar un trabajo que se encuentra en cualquier estado. Cuando un trabajador inicia un trabajo que tiene el estado *No iniciado*, el campo **Cantidad** del cuadro de diálogo **Iniciar trabajo** muestra inicialmente la cantidad completa. Cuando un trabajador inicia un trabajo que tiene el estado *No iniciado* o *Detenido*, el campo **Cantidad** muestra inicialmente la cantidad restante.

## <a name="reporting-good-quantities"></a>Notificar buenas cantidades

Cuando un trabajador completa (o completa parcialmente) un trabajo, puede notificar buenas cantidades que se produjeron seleccionando un trabajo en la pestaña **Trabajos activos** y seleccionando a continuación **Notificar progreso**. En el cuadro de diálogo **Notificar progreso**, el trabajador introduce la cantidad buena a través del teclado numérico. La cantidad está en blanco de forma predeterminada. Después de especificar una cantidad, el trabajador puede actualizar el estado del trabajo a *En curso*, *Detenido* o *Terminado*.

![Cuadro de diálogo Notificar progreso](media/pfei-report-progress-dialog.png "Cuadro de diálogo Notificar progreso")

## <a name="reporting-scrap"></a>Notificar residuo

Cuando un trabajador completa (o completa parcialmente) un trabajo, puede notificar residuos seleccionando un trabajo en la pestaña **Trabajos activos** y seleccionando a continuación **Notificar residuo**. En el cuadro de diálogo **Notificar residuo**, el trabajador introduce la cantidad de residuo a través del teclado numérico. El trabajador también selecciona un motivo (*Ninguno*, *Máquina*, *Operador* o *Material*).

![Cuadro de diálogo Notificar residuo](media/pfei-report-scrap-dialog.png "Cuadro de diálogo Notificar residuo")

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

Las actividades indirectas son actividades que no están directamente relacionadas con un pedido de producción. Las actividades indirectas se pueden definir de manera flexible, como se describe en [Configurar actividades indirectas para el tiempo y la asistencia](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Por ejemplo, Shannon, un trabajador de planta en Contoso, desea asistir a una reunión de la empresa y las reuniones se consideran una actividad indirecta. Se aplica uno de los dos escenarios siguientes:

- **Shannon trabaja en uno o más trabajos activos.** Shannon selecciona **Actividad**, identifica la actividad (reunión) y confirma su selección. Aparece un mensaje que le informa de que tiene trabajos en curso. A partir del mensaje, Shannon puede optar por completar o detener los trabajos en los que está trabajando antes de ir a la reunión.
- **Shannon no tiene ningún trabajo activo.** Shannon selecciona **Actividad**, identifica la actividad (reunión) y confirma su selección. Ahora está registrada como participante de la reunión.

En ambos escenarios, después de que Shannon confirme su selección, va a la página de inicio de sesión o a una página que esperará su confirmación de que ha regresado de la actividad indirecta. La página que aparece depende de la configuración de la interfaz de ejecución de la planta de producción. (Para obtener más información, vea [Configurar la interfaz de ejecución de la planta de producción](production-floor-execution-configure.md).)

## <a name="registering-breaks"></a>Registro de descansos

Los trabajadores pueden registrar descansos. Los descansos se pueden definir de manera flexible, como se describe en [Pago basado en registros](pay-based-on-registrations.md).

Un trabajador registra una pausa seleccionando **Descanso** y seleccionando a continuación la tarjeta que representa el tipo de descanso (por ejemplo, almuerzo). Una vez que el trabajador ha confirmado la selección, el dispositivo muestra la página de inicio de sesión o una página que esperará a que el trabajador confirme que ha regresado del descanso. La página que aparece depende de la configuración de la interfaz de ejecución de la planta de producción. (Para obtener más información, vea [Configurar la interfaz de ejecución de la planta de producción](production-floor-execution-configure.md).)

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