---
title: "Estructuras de descomposición del trabajo"
description: "Una estructura de descomposición del trabajo (WBS) es una descripción del trabajo que se realizará para un proyecto. Es una jerarquía de tareas que representa la comprensión del equipo del proyecto de la composición del trabajo, y del tamaño, coste y duración de cada componente o tarea."
author: KimANelson
manager: AnnBe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 53f40b8988182312d753472af10b0752ee862bd2
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="work-breakdown-structures"></a>Estructuras de descomposición del trabajo

[!include[banner](../includes/banner.md)]

Una estructura de descomposición del trabajo (WBS) es una descripción del trabajo que se realizará para un proyecto. Es una jerarquía de tareas que representa la comprensión del equipo del proyecto de la composición del trabajo, y del tamaño, coste y duración de cada componente o tarea. Una WBS tiene tres propósitos principales:

-   Describir la descomposición o la composición del trabajo en tareas.
-   Programar el trabajo del proyecto.
-   Estimar el coste de cada tarea.

El nivel de detalle de una WBS depende del nivel de precisión que se requiere en las estimaciones y el nivel de seguimiento que se requiere frente a las estimaciones. Los proyectos que tienen muy baja tolerancia para los desvíos en la programación o el coste normalmente requieren una WBS más detallado y el seguimiento diligente del coste y del progreso del trabajo en relación con la WBS. Este tipo de proyecto es común en los sectores de la construcción y la ingeniería. 

Por el contrario, proyectos en sectores como los medios de comunicación y la publicidad, el software y la infraestructura de TI tienden a ser únicos, y la productividad es relativa a la experiencia y la competencia de la persona que está realizando la tarea. Por tanto, estos sectores usan una WBS para obtener una aproximación del tamaño de un proyecto, no para realizar un seguimiento del progreso de dicho proyecto detalladamente. 

La creación de una WBS es un proceso intensivo que se realiza normalmente durante un período largo, y que requiere la colaboración y la información de una amplia variedad de personas. Este tema describe cómo puede usar las mejoras de WBS en Microsoft Dynamics 365 for Finance and Operations para cumplir los requisitos de estimaciones y seguimiento.

## <a name="prerequisites-for-creating-a-wbs"></a>Requisitos previos para crear una WBS
Para crear una WBS, debe poder crear una programación del trabajo y estimar el coste del trabajo.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Requisitos previos para crear una programación de trabajos

Para usar las capacidades de programación completas de las características de WBS, complete la configuración siguiente:

1.  Configurar un calendario predeterminado y un calendario del proyecto:
    1.  Haga clic en **Gestión de proyectos y contabilidad** &gt; **Configurar** &gt; **Parámetros de gestión de proyectos y contabilidad** &gt; **Programación**. En el campo **Calendario de trabajo predeterminado**, especifique un calendario predeterminado. Este será el calendario laboral predeterminado para cualquier proyecto nuevo que se crea.
    2.  Puede modificar el calendario predeterminado para un proyecto concreto. Haga clic en la página de detalles del proyecto y, a continuación, en la ficha desplegable **Equipo del proyecto y programación**, actualice el campo **Calendario de programación** seleccionando otro calendario.

2.  Permite configurar los días laborables y las horas de trabajo estándar. El calendario que se establece como el calendario de trabajo para su proyecto se usará en la WBS para determinar la siguiente información:

-   Días laborables y vacaciones
-   El número de horarios de trabajo en un día

Para configurar los días laborables y las horas de trabajo para un calendario, o crear un calendario nuevo, haga clic en **Administración de la organización** &gt; **Común** &gt; **Calendarios**.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Requisitos previos para estimar el coste del trabajo

Para usar las capacidades completas de estimación de costes de la WBS, debe configurar los costes y los precios de ventas para trabajadores, categorías de mano de obra, gastos, cuotas y artículos.

-   Para configurar el coste y el precio de ventas de la mano de obra, los gastos y las categorías de cuotas, haga clic en **Gestión de proyectos y contabilidad** &gt; **Configuración** &gt; **Precios**.
-   Para configurar el coste y el precio de ventas de los artículos, use la página **Acuerdos comerciales** para cada artículo de la página de lista **Productos emitidos** de Gestión de información de productos.

## <a name="creating-a-wbs"></a>Creación de una WBS
La creación de una WBS conlleva tres actividades:

1.  **Descomposición del trabajo**: permite crear una descomposición del trabajo en tareas o piezas manejables.
2.  **Programación de trabajos**: estime el tiempo necesario para completar una tarea, establecer interdependencias de tareas y seleccionar las fechas de inicio y fin para tareas.
3.  **Estimación de costes**: estime costes para cada tarea.

En las siguientes secciones se describe cómo capacidades de WBS pueden contribuir con cada una de estas actividades.

### <a name="work-decomposition"></a>Descomposición del trabajo

La creación de un desglose o una descomposición del trabajo suele ser el primer paso en el proceso de creación de una WBS. La funcionalidad de WBS admite las siguientes construcciones básicas para la descomposición o la descomposición del trabajo. 

**Tarea raíz del proyecto** La tarea raíz del proyecto es la tarea de resumen de nivel superior para un proyecto. Todas las demás tareas de proyecto se crean por debajo. El nombre de la tarea raíz se establece siempre al nombre del proyecto. El esfuerzo, las fechas y la duración del nodo raíz resumen los valores para las tareas por debajo de la tarea raíz. No puede modificar las propiedades del nodo raíz o eliminarlas.

**Tareas de contenedor o resumen** Una tarea de resumen es una tarea que tiene subtareas o tareas constitutivas por debajo. Una tarea de resumen no tiene ningún esfuerzo de trabajo o coste por sí misma. En su lugar, el coste y el esfuerzo de trabajo de una tarea de resumen son la suma del esfuerzo de trabajo y el coste de sus tareas constitutivas. La primera fecha inicial de las tareas constitutivas se usa como la fecha inicial de la tarea de resumen y la última fecha final de las tareas constitutivas se usa como la fecha final. Puede modificar el nombre de una tarea de resumen, pero no puede modificar las propiedades de programación para esfuerzo, fechas y duración. Si elimina una tarea de resumen, también eliminará todas sus tareas constitutivas. 

**Tareas del nodo hoja** Una tarea del nodo hoja representa el paquete de trabajo más granular del proyecto. Un nodo hoja tiene un esfuerzo estimado, un número previsto de recursos, una fecha inicial y una fecha final planificadas, y una duración. 

Puede completar las siguientes operaciones de jerarquía para habilitar la creación de una jerarquía de trabajo o la descomposición para un proyecto. 

**Nueva tarea** Cualquier tarea nueva que cree se agrega automáticamente en el nodo raíz y un número de WBS se asigna automáticamente a la tarea. El número de WBS representa el nivel de la tarea en la jerarquía. Para las tareas del primer nivel bajo la tarea raíz del proyecto, se usa un esquema de numeración de 1, 2, 3, etc. Para las tareas que se encuentran debajo del primer nivel, se usa un esquema de numeración de 1.1, 1.2, 1.3, etc. Para cada nivel que se agrega debajo de un nivel anterior, se agrega una nueva serie de puntos. 

Actualmente, no puede personalizar la numeración de WBS. 

**Tarea de sangría** Cuando se aplica sangría a una tarea, se convierte en un elemento secundario de la tarea que lo precede. El número de WBS de la nueva tarea secundaria se recalcula automáticamente en función del número de WBS de su nuevo elemento principal. La tarea principal es ahora una tarea de contenedor o resumen, y por tanto se convierte en una acumulación de sus tareas constitutivas. 

> [!NOTE] 
> Cuando se aplica sangría a tareas bajo una tarea que era un nodo hoja antes de la operación de sangría, la tarea de resumen recién creada pierde sus propias fechas, esfuerzo y número de recursos. Ahora usa un resumen de los valores de sus tareas nuevas constitutivas. 

**Anular la sangría de tarea** Cuando se anula la sangría de una tarea, ya no es una tarea constitutiva de su elemento principal. El número de WBS de esta tarea se recalcula automáticamente para reflejar el nuevo nivel de la tarea en la jerarquía. El esfuerzo, el coste y las fechas de la tarea principal anterior de la tarea se recalculan para excluir esa tarea. 

**Trasladar hacia arriba y Trasladar hacia abajo** Al hacer clic en **Trasladar hacia arriba** y **Trasladar hacia abajo**, cambie la posición de una tarea dentro de la jerarquía de su elemento principal. La posición de una tarea no afecta al esfuerzo, el coste, las fechas o la duración de la tarea. Sin embargo, el número de WBS de la tarea se recalcula automáticamente para reflejar la nueva posición de la tarea.

### <a name="schedule-estimation"></a>Estimación de la programación

La estimación de la programación es normalmente el segundo paso en la creación de una WBS. Como práctica recomendada, debe completar la estimación de la programación después de crear las tareas. La página **Estructura de descomposición del trabajo** en Finance and Operations tiene dos secciones. El panel superior está pensado para la estimación de la programación y el panel inferior incluye una pestaña **Costes e ingresos estimados** que puede usar para la estimación de costes. 
**Dependencias de tareas** En una WBS, puede crear una relación predecesora entre tareas. Al asignar tareas predecesoras a una tarea, esa tarea solo se puede iniciar después de completarse todas sus tareas predecesoras. La fecha inicial planificada de la tarea se establece automáticamente a la última fecha de todas sus predecesoras. 

**Programación de tareas en Microsoft Dynamics 365 for Finance and Operations** Los siguientes factores determinan la programación de las tareas de nodo hoja:

-   Predecesores
-   Esfuerzo
-   El número de recursos
-   Fechas inicial y final

La fecha inicial de una tarea de nodo hoja que no tenga predecesores se establece automáticamente en la fecha inicial de programación del proyecto. La duración de una tarea de nodo hoja se calcula siempre como el número de días laborables entre sus fechas de inicio y finales. 

****Reglas de programación**** Cuando la ayuda de previsión automática está activada, se aplican las siguientes reglas a la programación de tareas para tareas de nodo hoja:

-   Las fechas de inicio y final de una tarea deben ser días laborables, de acuerdo con el calendario de programación del proyecto.
-   La fecha inicial de una tarea que tiene predecesoras se establece automáticamente a la última fecha final de todas sus predecesoras.
-   El esfuerzo de una tarea se calcula automáticamente de la siguiente manera:

Número de personas × Duración × Número de horas en un día de trabajo estándar en el calendario del proyecto. 

En algunos casos, es posible que desee desviarse de estas reglas. Puede desactivar la programación automática para evitar que Finance and Operations establezca o corrija automáticamente las propiedades de las tareas de nodo hoja. Al especificar la información para una tarea que provoca una infracción de cualquier regla de programación, se muestra un icono de error de programación para la tarea. Si no desea que se muestren los errores de programación, haga clic en **Se muestra los errores de programación** para desactivar la característica. 

> [!NOTE] 
> Los valores para una tarea de contenedor o resumen continúan calculándose como la suma de los valores de las tareas constitutivas, independientemente de si la ayuda de programación automática está activada o desactivada. 

**Corrección de errores de programación** Cuando la ayuda de programación automática está activada, no es probable que se produzcan errores de programación. Sin embargo, si desactiva la ayuda de programación automática y la vuelve a activar más tarde, los iconos de errores de programación pueden aparecer en la WBS. 

**Corrección de errores de previsión por tarea** Al hacer doble clic en el icono del error de programación para una tarea específica, un cuadro de diálogo muestra todos los errores de programación para esa tarea. Puede decidir qué errores de programación corregir para la tarea. 

**Corrección de todos los errores de programación** Si desea que Finance and Operations corrija todos los errores de programación en la WBS, en el Panel de acciones, haga clic en **Corregir todas las discrepancias de programación**. 

> [!NOTE] 
> Esta característica puede provocar modificaciones significativas a la WBS. Los errores se corrigen en el siguiente orden:

1.  El esfuerzo estimado en todas las tareas se modifica para que sea igual a la capacidad que se define en el calendario del proyecto.
2.  La fecha inicial de cada tarea se modifica de modo que la tarea empieza una vez que se completan todas sus tareas predecesoras.
3.  La fecha inicial de cada tarea se modifica para eliminar espacios en las fechas iniciales de las tareas predecesoras.

### <a name="cost-estimation"></a>Estimación de coste

Como se mencionó anteriormente en este documento, especifica la estimación de costes para cada tarea de nodo hoja usando la pestaña **Costes e ingresos estimados** del panel inferior de la página **Estructura de descomposición del trabajo**. 

> [!NOTE] 
> No puede modificar la estimación de costes para una tarea de contenedor o resumen. La estimación de costes para una tarea de resumen es igual a la suma de la estimación de costes de sus tareas del nodo hoja. El coste total estimado para cada tarea se calcula como la suma de los importes de coste estimado para los siguientes tipos de transacción:

-   Mano de obra
-   Artículo o material
-   Gastos

Se usa un tipo de transacción **Cuota** para estimar el ingreso basado en cuotas. Este tipo de transacción no tiene un componente de coste y por tanto no se considera si se estiman los costes. 

Se usa un tipo de transacción **A cuenta** para registrar el valor de las ventas contratadas en un tipo de valor fijo de proyecto. Tampoco se considera este tipo de transacción cuando se estiman los costes. 

Cuando estima los costes para mano de obra, material y gastos para cada tarea, debe asignar una categoría de proyecto al coste estimado. 

**Cálculo de costes de mano de obra** Para cada tarea de nodo hoja, asigna un esfuerzo de trabajo en horas y una categoría predeterminada. Por tanto, al configura una programación para una tarea, la estimación del coste de mano de obra para esa tarea se agrega automáticamente en la categoría predeterminada para la mano de obra. Esta estimación de coste se muestra en la pestaña **Costes e ingresos estimados** de la cuadrícula **Detalles de línea** para esa tarea. Si necesita más estimaciones del coste de la mano de obra, puede agregarlas en esta pestaña. Si aumenta o disminuye las horas de la estimación de la mano de obra, la programación de la tarea se actualiza automáticamente. 

**Cálculo de costes de gastos y material** La pestaña **Costes e ingresos estimados** también le permite estimar los costes de gastos y material para una tarea, si necesita estimaciones. 

El coste y el precio de venta para cada línea de estimación de gasto o de mano de obra se basan en la configuración que se define para cada categoría de las tablas de precios en **Gestión de proyectos y contabilidad** &gt; **Configuración** &gt; **Precios**. Para artículos, se añaden el coste y el precio de venta de manera predeterminada desde el artículo o los acuerdos comerciales en la página de lista **Productos emitidos** de Gestión de información de productos.

## <a name="tracking-progress-on-the-wbs"></a>Seguimiento del progreso en la WBS
Algunos sectores realizan un seguimiento del progreso de un proyecto con una WBS en un nivel muy granular, mientras que los demás realizan un seguimiento del progreso en un nivel superior de la WBS. En esta sección se describe cómo puede usar el seguimiento de la WBS para sus requisitos de proyecto. 

Finance and Operations tiene tres vistas para la WBS de un proyecto: la vista Planificación, la vista Seguimiento de esfuerzos y la vista Seguimiento de costes.

### <a name="planning-view"></a>Vista de planificación

La vista Planificación muestra la estimación planeada o de línea base de la información de programación y de coste. Aunque no haya ninguna característica para realizar un seguimiento de la versión y la línea base para una WBS de proyecto, los valores de esta vista están pensados para representar la versión de línea base. Las secciones Estimación de la programación y Estimación de coste de este tema describen esta vista y cómo se usa para crear una WBS.

### <a name="effort-tracking-view"></a>Vista de seguimiento de esfuerzos

La vista Seguimiento de esfuerzos muestra el seguimiento del progreso para las tareas en la WBS. Compara las horas de esfuerzo reales acumuladas para una tarea con las horas de esfuerzo planificadas. Las fórmulas siguientes proporcionan los valores en la vista Seguimiento de esfuerzos:

-   Porcentaje de progreso = Esfuerzo real hasta la fecha ÷ Esfuerzo planificado para la tarea
-   Esfuerzo restante (también conocido como Estimación hasta completar \[ETC\]) = Esfuerzo planificado – Esfuerzo real hasta la fecha
-   Estimación al completar (EAC) = Esfuerzo restante + Esfuerzo real hasta la fecha
-   Desviación de esfuerzo proyectada = Esfuerzo planificado – EAC

La vista Seguimiento de esfuerzos muestra una proyección de la desviación del esfuerzo para la tarea, en función de si EAC es superior o inferior al esfuerzo planificado:

-   Si EAC es mayor que el esfuerzo planificado, la tarea se proyecta para tardar más tiempo que el planificado originalmente y va retrasada respecto a lo programado.
-   Si EAC es menor que el esfuerzo planificado, la tarea se proyecta para tardar menos tiempo que el planificado originalmente y va por delante de lo programado.

**Reproyección del esfuerzo del director del proyecto** Ocasionalmente, el director del proyecto u otra persona que está realizando el seguimiento del progreso de un proyecto deberá revisar las estimaciones originales en una tarea. La tarea puede moverse con mayor rapidez o con más lentitud de lo que se anticipó originariamente por varios motivos. Por ejemplo, el ámbito se ha reducido, o los trabajadores tienen menos experiencia de lo que se planificó originalmente. Las proyecciones son la percepción de las estimaciones de un director de proyecto, según el estado actual en un proyecto. En general, no debe cambiar los números de línea base, porque una línea base del proyecto representa un documento bien publicado para la estimación del coste y la programación del proyecto que han acordado todas las partes interesadas del proyecto. 

Hay dos maneras en que los directores de proyectos pueden modificar el esfuerzo en las tareas:

-   Modificar el esfuerzo restante que se establece automáticamente para actualizar el esfuerzo restante real de la tarea.
-   Modificar el porcentaje del progreso que se establece automáticamente para actualizar el progreso verdadero de la tarea.

Ambos métodos causan un cálculo del ETC, EAC de la tarea, el porcentaje del progreso y la desviación proyectada del esfuerzo de la tarea. El EAC, ETC y el porcentaje del progreso en las tareas de resumen también se recalculan, y se actualiza su desviación del esfuerzo proyectada. 

**Esfuerzo modificado en tareas de resumen** Puede modificar el esfuerzo en las tareas de contenedor o resumen. Independientemente de si modifica estos valores con el esfuerzo restante o el porcentaje del progreso en las tareas de resumen, los cálculos se producen automáticamente en el siguiente orden:

1.  Se calculan el EAC, el ETC y el porcentaje del progreso en la tarea.
2.  El nuevo EAC se distribuye a las tareas secundarias en la misma proporción que el importe de EAC original.
3.  Se calcula el nuevo EAC en cada tarea del nodo hoja.
4.  Se recalculan el porcentaje del progreso y el esfuerzo restante para todas las tareas secundarias afectadas, en función del nuevo valor de EAC. También se recalcula la desviación del esfuerzo de las tareas.
5.  También se recalcula El EAC de las tareas de resumen de los nodos hoja.

Haga clic en **Expandir a nivel** en la vista Seguimiento de esfuerzos para establecer el nivel en el que realizar el seguimiento y mantener la WBS. La WBS se expande automáticamente a ese nivel en la vista Seguimiento de esfuerzos siempre que la abre.

### <a name="cost-tracking-view"></a>Vista de seguimiento de costes

La vista Seguimiento de costes muestra el seguimiento del consumo de coste para una tarea. En esta vista, el coste real que se ha gastado con una tarea hasta la fecha se compara con el coste planificado para la tarea. Las fórmulas siguientes proporcionan los valores en la vista Seguimiento de costes:

-   Porcentaje de coste consumido = Coste real hasta la fecha ÷ Coste planificado para la tarea
-   Coste para completar (CTC) = Coste planificado – Coste real hasta la fecha
-   Estimación al completar (EAC) = CTC + Coste real hasta la fecha
-   Desviación del coste proyectado = Coste planificado – EAC

La vista Seguimiento de costes muestra una proyección de la desviación de coste para la tarea, en función de si EAC es superior o inferior al coste planificado:

-   Si EAC es mayor que el coste planificado, la tarea se proyecta para usar más dinero que el planificado originalmente y supera el presupuesto.
-   Si EAC es menor que el coste planificado, la tarea se proyecta para usar menos dinero que el planificado originalmente y está por debajo del presupuesto.

**Reproyección del coste del director del proyecto** Los directores de proyecto deben usar CTC para revisar la estimación de coste original en una tarea. El director de proyecto puede modificar el valor de CTC al coste que se requiere para completar la tarea. Si modifica el valor de CTC, se recalculan el CTC de la tarea, EAC, el porcentaje del coste consumido y la desviación de coste proyectada en una tarea. El EAC, ETC y el porcentaje del coste consumido en las tareas de resumen también se recalculan, y se actualiza su desviación de coste proyectada. 

> [!NOTE] 
> Cuando revise el esfuerzo para una tarea de WBS en la vista Seguimiento de esfuerzos, el CTC de la tarea, EAC, el porcentaje del coste consumido y la desviación de coste proyectada se recalculan en la vista Seguimiento de costes. Sin embargo, las revisiones de coste no afectan a los valores de la vista Seguimiento de esfuerzos, ya que el coste por tipo de transacción (mano de obra, material o gastos) o la categoría de proyecto no se revisa. 

**Revisión de proyección para costes en tareas de resumen** Puede revisar costes en tareas de resumen y los cálculos se producen automáticamente en el siguiente orden:

1.  Se recalculan el EAC, CTC y el porcentaje del coste consumido en la tarea.
2.  El nuevo EAC se distribuye a las tareas secundarias en la misma proporción que el importe de EAC original en las tareas.
3.  Se calcula el nuevo EAC para cada tarea.
4.  El CTS y el porcentaje de coste consumido se recalculan para las tareas secundarias afectadas, según el valor de EAC. También se recalcula la desviación del coste de las tareas.
5.  El EAC para todas las tareas de resumen se vuelve a calcular en función de este cambio.

Haga clic en **Expandir a nivel** en la vista Seguimiento de costes para establecer el nivel en el que realizar el seguimiento y mantener la WBS. La WBS se expande a ese nivel en la vista Seguimiento de costes siempre que la abre.

### <a name="earned-value-management"></a>Administración del valor obtenido

Puede usar el método del valor acumulado (EVM) para realizar un seguimiento del progreso de un proyecto. Puede ver la métrica del valor acumulado en el área de trabajo del director del proyecto. El componente del gráfico de valor acumulado muestra los valores con fases temporales de valor planeado y coste real. El valor acumulado a partir de la fecha actual se muestra como un punto. Los datos con fases temporales para el valor acumulado no se encuentran disponibles actualmente. 

La fase de tiempo en el gráfico de valor acumulado se muestra por semana o por mes. Esta sección describe los tres pilares de EVM: valor planeado, valor acumulado y coste real. 

**Valor planificado** La teoría de EVM indica que el diagrama del valor esperado representa el índice en el que el equipo del proyecto planificó obtener valor en el proyecto. 

Finance and Operations usa la regla de obtención 0:100 cuando representa el valor planificado. En esta regla, el valor de la tarea se registra en la tarea como su fecha final. No se registra ningún valor hasta que la tarea se completa al 100 por cien. 

En Gestión de proyectos y contabilidad, especifique la fecha final de los nodos hoja y el coste planificado para el mismo. Cuando el gráfico del valor planificado se muestra por semana, el valor planificado se describe por semana para todas las tareas de nodo hoja para la duración del proyecto. 

**Valor acumulado** La teoría de EVM indica que el diagrama del valor obtenido representa el índice en el que el equipo del obtiene realmente el valor en el proyecto. 

Finance and Operations usa la regla de obtención 0:100 cuando representa el valor acumulado. En esta regla, el valor de la tarea se registra en la tarea como su fecha final. No se registra ningún valor hasta que la tarea se completa al 100 por cien. 

Cuando se calcula el valor acumulado, se considera el porcentaje del progreso de cada tarea. Según la regla de obtención 0:100, solo las tareas que se completen en un período determinado se consideran para el cálculo del valor acumulado a partir del fin de ese período. El valor acumulado en el proyecto se calcula para todas las tareas que se hayan completado cuando se crea el gráfico. 

> [!NOTE] 
> Actualmente, el sistema para el seguimiento de WBS no tiene estructuras de datos para almacenar porcentajes de progreso históricos en cada tarea. Por lo tanto, el valor acumulado solo se puede notificar a partir del momento en que se procesa el cubo. Procese el cubo con regularidad para actualizar los datos del valor acumulado que se muestran en el área de trabajo. 

**Coste real** La teoría de EVM indica que el diagrama de coste real representa el índice en el que se gasta el dinero en el proyecto. 

Las transacciones que se registran en un proyecto se usan para representar la línea de coste real. Los costes se resumen por fecha. Estos datos se usan a continuación para representar los costes reales por semana o por mes en el gráfico de valor acumulado.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Cómo usar los conceptos de valor planificado, de valor acumulado y de coste real

**Desviación de la programación** Durante la planificación, crea una previsión por el trabajo en una línea de tiempo. Por lo tanto, el valor planificado es el índice en el que los planificadores del proyecto pensaron que se completaría el trabajo en el proyecto. Después de que un proyecto esté en curso, el trabajo se completa y el proyecto acumula valor. Al comparar el valor planificado con el valor acumulado, puede ver cómo progresa el trabajo en un proyecto. El resultado de esta comparación se denomina desviación de programación. 

Si el valor planificado para un período es superior al valor acumulado, la cantidad de trabajo que se ha realizado en un proyecto es menor que lo que se planificó. Por lo tanto, el proyecto está retrasado respecto a lo programado. Dado que el valor planificado y el valor acumulado se expresan en términos monetarios, al tiempo de retardo en el proyecto también se le asigna un valor monetario. 

Si el valor planificado para un período es menor que el valor acumulado, la cantidad de trabajo que se ha realizado en un proyecto es mayor que lo que se planificó. Por lo tanto, el proyecto está adelantado respecto a lo programado. A este plazo también se le asigna un valor monetario.

**Desviación de coste** Dado que el valor acumulado usa el precio de coste como el multiplicador, el valor acumulado indica el coste del trabajo que se realiza en un proyecto. Conforme progresa un proyecto, el registro de transacciones proporciona un registro de dinero que se gasta realmente en dicho proyecto. Al comparar el valor acumulado con el coste real, puede ver el importe de dinero que se está gastando con el valor que se acumula. El resultado de esta comparación se denomina desviación de coste. 

Si el coste real que se gasta para un período es superior al valor acumulado, se gastó más dinero que el que se acumuló. Por lo tanto, el proyecto supera el presupuesto. 

Si el coste real que se gasta para un período es inferior al valor acumulado, se acumuló más dinero que el que se gastó. Por lo tanto, el proyecto está por debajo del presupuesto.

## <a name="wbs-templates"></a>Plantillas de WBS
Puede usar la característica de plantillas de WBS para crear plantillas estándar para proyectos. Si los proyectos que su empresa ofrece implican mucho trabajo repetible, debe pensar en crear una plantilla de WBS. 

Puede crear una plantilla de WBS desde la WBS de un proyecto existente, para que el conocimiento y las prácticas recomendadas que recopiló durante la planificación de ese proyecto se puedan reutilizar en proyectos similares en el futuro. Sin embargo, en ocasiones, es posible que no tenga sentido guardar la WBS completa como plantilla. Por tanto, también puede crear plantillas de las partes de la WBS para un proyecto.

### <a name="saving-a-projects-wbs-as-a-template"></a>Guardar la WBS de un proyecto como plantilla

Tras crear una plantilla, puede importarla en la WBS de un proyecto nuevo bajo el nodo raíz o en cualquier tarea en la WBS del proyecto.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>Importación de una plantilla de WBS en la WBS de un proyecto

Al importar tareas, las tareas de la plantilla se organizan según la fecha inicial de la tarea en la que se importan. Durante la importación, las relaciones predecesoras en las tareas de plantillas se usan para calcular las fechas iniciales para las tareas importadas. El calendario de trabajo estándar del proyecto de destino se aplica para computar las fechas finales de las tareas importadas, de manera que se conserven los días laborables y las horas laborables estándar que se definen en el calendario de trabajo del proyecto actual. 

Los importes de coste y los precios de ventas en las líneas de estimación se aplican para garantizar que los precios específicos del proyecto o del contrato de proyecto tienen fechas válidas.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>Diferencias entre la WBS de un proyecto y una plantilla de WBS

-   Las tareas de plantillas de WBS no tienen fechas de inicio y fechas finales.

Los días laborables y no laborables no se establecen para las plantillas de WBS.

-   Las plantillas de WBS siempre usan el calendario de programación que se configura como el calendario predeterminado para todos los proyectos.

El calendario de programación predeterminado se usa solo para averiguar horas en un día laborable estándar.

-   Las relaciones predecesoras no se copian en una plantilla de WBS.

Dado que las plantillas de WBS no tienen fechas, no se requiere la lógica de la fecha de inicio que se basa en la fecha final de un predecesor.

-   Una línea de estimación de coste de mano de obra se crea automáticamente cuando se crea una tarea en una plantilla de WBS. El precio de venta y el importe del coste se copian del trabajador seleccionado.

Los costes de gasto y artículo se pueden crear manualmente, tal y como pueden en la WBS de un proyecto.

-   Se muestran errores de programación cuando hay desviaciones de la fórmula siguiente:

Esfuerzo = Número de recursos × Duración × Número de horas en un día laborable estándar 

Puede corregir todos los errores de programación al mismo tiempo haciendo clic en **Corregir todos los errores de programación**. 

Como alternativa, puede corregir los errores de programación individualmente haciendo clic en el icono de advertencia para cada tarea.




