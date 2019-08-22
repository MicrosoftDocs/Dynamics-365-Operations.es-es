---
title: Previsión de puestos
description: Los gastos relacionados con los trabajadores componen a menudo una proporción grande de los costes de una organización. La previsión de puestos le permite planificar esos gastos y los incluye en la planificación de presupuestos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e2cee30bd32771931af9307ed041723d06f01b2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842722"
---
# <a name="position-forecasting"></a>Previsión de puestos

[!include [banner](../includes/banner.md)]

Los gastos relacionados con los trabajadores componen a menudo una proporción grande de los costes de una organización. La previsión de puestos le permite planificar esos gastos y los incluye en la planificación de presupuestos.

## <a name="position-forecasting-in-budget-planning"></a>Previsión de puestos en la planificación de presupuesto

[![Gráfico superior](./media/graphic-top.png)](./media/graphic-top.png) 

La previsión de puestos usa tres componentes principales para proporcionar los importes presupuestarios exactos para los gastos de los puestos. Estos importes se pueden introducir en un plan de presupuesto para los cálculos de presupuestos. 

El componente principal es la **previsión de puestos**, que representa todos los datos de coste asociados a un solo puesto. Puede crear varias versiones de un puesto de previsión asignando una situación diferente del plan de presupuesto a cada versión. Las versiones múltiples permiten un enfoque iterativo al presupuesto y le permiten comparar situaciones potenciales. Cada puesto de previsión tiene un puesto correspondiente en recursos humanos.

A **elemento de coste presupuestario** es un componente de configuración que representa un coste específico asociado con un puesto, como sueldo base, seguro médico pagado por el empleador, permisos de teléfono móvil, etc. Un elemento de coste presupuestario incluye la cuenta principal que se usa para el coste y opciones para el cálculo. Cada elemento de coste presupuestario se puede asignar a varios puestos de previsión. 

Un **grupo de compensación** es un componente opcional de la configuración que se usa para aplicar un conjunto de elementos de coste presupuestario y para pagar cálculos a los puestos que tienen características similares de sueldo. Un grupo de compensación puede incluir una cuadrícula de compensación de índices salariales. Cuando se asigna el grupo a un puesto de previsión, un nivel y un paso en la cuadrícula pueden asignar las ganancias del puesto de previsión. El conjunto de elementos de coste se agrega automáticamente.

### <a name="position-forecasting-processes"></a>Procesos de la previsión de puestos

[![graphic1b](./media/graphic1b.png)](./media/graphic1b.png) 

En un proceso típico para la previsión de puestos, primero se crean los componentes de configuración (los elementos de coste presupuestario y los grupos de compensación). Luego se generan los puestos de previsión, en función de puestos existentes. A continuación podrá realizar ajustes. Por ejemplo, puede agregar o finalizar puestos, cambiar índices salariales y costes de prestación, y agregar mejoras salariales. Puede crear varias versiones de un puesto de previsión para facilitar comparaciones entre diferentes escenarios de presupuestos. A continuación, puede incluir los puestos de previsión en los planes de presupuesto e incorporar los costes de los puestos de previsión como líneas de plan de presupuesto.

Puede crear versiones de puestos adicionales de previsión a medida que se revisan planes de presupuesto. Estas nuevas versiones proporcionan una base para las revisiones.

## <a name="position-forecasting-setup"></a>Configuración de la previsión de puestos
[![graphic2](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Elementos de coste presupuestario

Los elementos de coste presupuestario se usan para definir los detalles de coste para un puesto de previsión. Estos detalles incluyen el tipo de coste, cómo se calcula el coste, y si el coste se asignará a las fechas varias en que el puesto de previsión se incluye en un plan de presupuesto. 

Los campos específicos definen el comportamiento del elemento de coste presupuestario. Cada elemento de coste presupuestario se asignará un tipo de coste del presupuesto de **Ganancia**, **Prestación**, **Impuestos** o **Otro**. Se usan los tipos de coste presupuestario principalmente para calcular totales. El valor **Anulación del puesto de previsión** especifica si los importes del elemento se pueden modificar en el puesto de previsión. El campo **Método de asignación** se utiliza cuando un puesto de previsión se agrega a un plan de presupuesto. Puede dividir el importe de coste en líneas independientes del plan de presupuesto que tienen diferentes fechas, de forma mensual, trimestral, semanal o quincenal. Al seleccionar una fecha de inicio, se asigna el coste como un solo importe en la fecha de inicio que se establece en la posición de previsión. 

El cálculo del importe de coste del elemento del presupuesto de coste usa las fechas de vigencia para que el mismo elemento de coste se pueda usar en distintos períodos. Una sola cuenta principal se asigna en cada período, junto con un porcentaje o un importe anual que indique el importe de coste. Un elemento de coste presupuestario puede usar un porcentaje de otros elementos de coste o de un importe anual, pero no ambos. También puede especificar un límite anual. 

Si el elemento de coste se basa en un porcentaje, debe especificar los elementos de coste presupuestario que se usan como base para el cálculo.

**Ejemplo** 

La organización de Jorge proporciona un permiso de formación del 5 por ciento del sueldo base de un empleado. Jorge desea crear un elemento de coste presupuestario para este coste. Él crea un nuevo elemento de coste presupuestario y asigna el tipo de coste presupuestario **Prestación**.

Jorge no quiere que los directores cambien el importe de la prestación. Por lo tanto, selecciona **No permitir cambios de coste** en el campo **Anulación del puesto de previsión**. La organización desea que este coste se asigne uniformemente a cada mes. Por lo tanto, Jorge selecciona **Trimestral** en el campo **Método de asignación**. 

A continuación, Jorge agrega una línea de cálculo de costes, establece las fechas y una cuenta principal, y especifica **5.00** como porcentaje. Su organización tiene un límite de $5.000 por ejercicio para esta prestación. Por lo tanto, Jorge especifica dicho importe como el límite anual. 

Finalmente, Jorge agrega todos los elementos de coste de la ganancia que se usan para el sueldo base como bases de cálculo. Su elemento de coste presupuestario está ahora listo para usar.

### <a name="compensation-groups"></a>Grupos de compensación

Los grupos de compensación se pueden usar para agrupar puestos de previsión que tienen atributos similares de compensación. También se puede usar para definir las ganancias de un puesto de previsión y los aumentos anuales, y para asignar un conjunto de elementos comunes de coste presupuestario. 

Una función básica de los grupos de compensación es asignar un conjunto de elementos de coste presupuestario a un puesto de previsión. Por lo tanto, los grupos de compensación se pueden usar para agregar costes comunes, como planes de prestaciones y impuestos. Un director que está creando un puesto de previsión no tiene que conocer todos los elementos de coste que deben agregarse. Los elementos de coste pueden agregarse al seleccionar el grupo de compensación. Los elementos se agregan al grupo de compensación configurado en la ficha **Elementos de coste presupuestario**. 

Los grupos de compensación también pueden determinar los índices de ganancia para un puesto de previsión. Puede configurar un grupo para usar por hora o como sueldo anual para calcular las ganancias del puesto de previsión. En la ficha **Tablas del índice de compensación**, una cuadrícula de compensación de índices salariales determina las ganancias que se agregan a un puesto de previsión, en función de un nivel y un paso asignados. Estas cuadrículas se pueden basar en cuadrículas existentes de compensación en recursos humanos. También puede crear nuevas cuadrículas de compensación para la planificación de presupuesto. 

Las fechas de vigencia y de vencimiento de las tablas del índice de compensación le permiten cambiar índices salariales en cualquier fecha. Esta función resulta útil cuando una unidad de negociación ha negociado un aumento global en el medio de un ciclo de presupuesto. En este caso, puede cambiar la fecha de vencimiento de la tabla existente el día antes de la fecha de cambio del índice y agregar una nueva tabla de índice que comience en la nueva fecha. Cuando se crea una nueva tabla de índice, si selecciona **Crear una nueva cuadrícula de compensación de una cuadrícula existente**, puede seleccionar una tabla existente del índice de recursos humanos. En la tabla del índice creada, la opción **Cambio total** permite aplicar un porcentaje o un aumento o descuento del importe fijo a todas las tarifas de la cuadrícula. 

Los campos **Aumentar programación** y **Fecha del aumento** del grupo de compensación se usan cuando debe crear mejoras de sueldo ya que los puestos van de un paso al siguiente. Un aumento de pago anual es un escenario típico. La programación de aumento determina si la fecha de aniversario del puesto o una sola fecha común se usa para el incremento del paso. La programación de aumento se aplica a todas las posiciones de previsión en el grupo de compensación. 

Se usa el elemento de coste de la ganancia que se seleccionó en el grupo de compensación al crear las ganancias para los puestos de previsión en el grupo, incluido el sueldo base y cualquier aumento de etapa. El campo **Plan fijo de compensación** vincula el grupo de compensación a un plan de compensación fija en recursos humanos. Este vínculo puede asignar la información de compensación fija de un trabajador a un puesto de previsión, y puede por lo tanto realizar una planificación de presupuesto más precisa. Recuerde que la estructura de la cuadrícula de compensación (niveles y pasos) para el grupo de compensación debe coincidir con la estructura del plan de compensación fija. De lo contrario, el sistema no puede vincular correctamente el grupo de compensación y el plan de compensación fija.

## <a name="creating-forecast-positions"></a>Crear puestos de previsión
[![graphic3](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Crear puestos de previsión para puestos existentes

Para la planificación de manera más precisa del presupuesto, puede crear puestos de previsión con los detalles de puestos existentes en Microsoft Dynamics 365 for Finance and Operations, independientemente de si el puesto existe o no actualmente. 

La función **Agregar puestos existentes** muestra todas las posiciones para una organización. Al configurar la fecha **A partir de**, puede cambiar la lista de puestos de modo que contenga los puestos que existían en una fecha en el pasado o, normalmente, en el futuro (por ejemplo, el inicio del ciclo presupuestario siguiente). Seleccione una situación del proceso de planificación presupuestaria y el plan de presupuesto, seleccione puestos en la lista, y haga clic en **Aceptar** para crear los puestos de previsión para los puestos seleccionados. Tenga en cuenta que puede crear un puesto de previsión para cada puesto existente en un proceso y una situación de planificación presupuestaria. Sin embargo, puede crear versiones adicionales asignando distintas situaciones del plan de presupuesto. 

Si los elementos de coste presupuestario se han asignado a la posición en recursos humanos, estos elementos de coste presupuestario también se asignan a la posición de previsión y utilizan los importes predeterminados. El campo **Trabajador asignado** del puesto de previsión se establece con el nombre del trabajador asignado al puesto, si un trabajador está asignado. Este campo es un campo simple de texto. No se crea ningún vínculo directo. 

Si se selecciona un elemento de coste presupuestario, el importe anual de compensación fija se asigna al puesto de previsión mediante el elemento seleccionado de coste, siempre que el trabajador tenga asignado un plan de compensación fija. Si el trabajador no tiene un plan de compensación fija, o si no se asigna ningún trabajador, el importe predeterminado se usa para el elemento de coste presupuestario. 

Cuando la opción **Asignar un grupo de compensación** está establecida en **Sí**, si el trabajador asignado al puesto tiene un plan de compensación fija basado en pasos que está vinculado a un grupo de compensación (según lo descrito anteriormente), el nivel y el paso del trabajador se asignan al puesto de previsión, junto con el grupo de compensación. El elemento de coste presupuestario de ganancias del grupo de compensación se agrega al puesto de previsión, y se usan el índice salarial en el nivel y el paso del grupo de compensación. 

El ajuste de la opción **Asignar un grupo de compensación** tiene prioridad sobre e ajuste **Asignación del elemento de coste presupuestario**. Se pueden utilizar las dos configuraciones al mismo tiempo. 

[![graphic4](./media/graphic4.png)](./media/graphic4.png) 

Otra opción es asignar una fecha de aniversario. La fecha seleccionada (fecha inicial, fecha inicial del trabajador, fecha de inicio del empleo o fecha de antigüedad ajustadas) del trabajador asignado se establece como la fecha de aniversario del puesto de previsión, y se usa para información y cuando se generan los aumentos de sueldo.

### <a name="creating-new-forecast-positions"></a>Crear nuevos puestos de previsión

Puede crear nuevos puestos de previsión de dos formas: copiando una previsión de puesto existente o creando una nueva previsión de puesto. 

Si se ha seleccionado un puesto de previsión, seleccione **Copiar el puesto de previsión seleccionado** para crear un nuevo puesto de previsión que tenga un estado de previsión **Propuesto**. Este puesto de previsión tiene todos los mismos datos que la posición de previsión que se copió, excepto el trabajador asignado y las notas sobre los elementos de coste presupuestario. Tenga en cuenta que una nueva posición correspondiente también se creó en recursos humanos. Este puesto tiene una descripción de **Creado por previsión**. 

También puede crear un puesto de previsión totalmente nuevo. Seleccione un trabajo existente, y también seleccione la situación del proceso de planificación presupuestaria y el plan de presupuesto. Puede agregar cualquier otro detalle que desee agregar. De nuevo, un puesto nuevo se crea en recursos humanos al mismo tiempo.

## <a name="working-with-forecast-positions"></a>Trabajar con puestos de previsión
[![graphic5](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Varias versiones de un puesto de previsión

Puede modificar puestos de previsión para aplicar los cambios conocidos para el ciclo presupuestario o los cambios modelo propuestos. Una práctica común es crear un conjunto de línea base de puestos de previsión, crear copias de dichos puestos de previsión, y después usar las copias para modelar los distintos conjuntos de cambios. Las copias se asignan a otra situación del plan de presupuesto, pero al menos hasta que se realizan los cambios, son idénticas a los puestos de previsión de los que se han copiado. Los originales y las copias comparten el mismo puesto en recursos humanos. 

La función **Copiar al escenario** proporciona esta característica. Tenga en cuenta que cada puesto de recursos humanos sólo puede tener un puesto de previsión en cada escenario del plan de presupuesto.

### <a name="modifying-forecast-positions"></a>Modificar puestos de previsión

Los cambios realizados en los puestos de previsión se limitan a dichos puestos de previsión. Los cambios no afectan a los registros de puestos en recursos humanos. La mayoría de los cambios también se limita al puesto de previsión que se está editando. Es decir, los cambios son específicos al proceso de planificación presupuestaria y al escenario del plan de presupuesto que tienen asignados. Las excepciones son los cambios en los campos que se comparten para el puesto en los procesos y las situaciones. Estos campos incluyen los campos en la pestaña **General** y la pestaña **Dimensiones financieras**. Cuando se cambian estos campos, los nuevos valores se aplican a la posición en todos los escenarios de planificación de presupuesto. Por lo tanto, estos campos permiten rápidamente actualizar todas sus versiones.

#### <a name="budget-cost-elements"></a>Elementos de coste presupuestario

Los elementos de coste presupuestario proporcionan la información principal para los planes de presupuesto: el importe presupuestario y la cuenta principal. El importe de presupuesto es el importe que se envía al plan de presupuesto cuando un puesto de previsión se incluye en un plan. El importe presupuestario se calcula y no se puede modificar directamente. Este importe es el importe anual o un cálculo del porcentaje de los elementos de la base del importe anual (como se define en la configuración del elemento de coste presupuestario). El importe luego se descompone en factores por el número de días en el intervalo de fechas del elemento (fecha inicial hasta la fecha final) y también por el valor **Equivalente a jornada completa** para el puesto de previsión. 

Por ejemplo, una línea del elemento de coste presupuestario del 1 de enero de 2017 al 30 de junio de 2017, que tiene un importe anual de 100.000 y un valor de FTE de **0,50** se calcula como 100.000 × (181 días ÷ 365 días) × 0,50 = 24.794,52. 

Las líneas del elemento de coste presupuestario se deben recalcular cuando el valor de FTE se modifica en el puesto de previsión. Las líneas también deben ser recalculadas cuando se modifican las fechas de activación o las fechas de retirada. Las modificaciones de estas fechas pueden provocar una actualización las fechas de inicio y de fin del elemento de coste del presupuesto, que deben estar dentro de las fechas del puesto de previsión. Cuando se requiera recalcular, el botón **Volver a calcular** estará disponible y aparece el mensaje "Requiere cálculo". También es necesario volver a calcular si agrega o quita un elemento de coste presupuestario.

**Ejemplo** 

La organización está considerando dos opciones para reducir el coste de un puesto de contable. Una opción es terminar el puesto parte del año. Otra opción es cambiar el puesto a tiempo parcial para todo el año. Alberto ha creado un puesto de previsión para el puesto existente de contable en una situación de línea base. Copia este puesto de previsión de línea base en la situación A, establece la fecha de jubilación al 31 de mayo, y vuelve a calcular. Alberto después copia el puesto de previsión de la línea base en la situación B, cambia el valor de FTE a **0,50**, y recalcula. Alberto ahora tiene tres versiones, cada una con totales de coste que se alinean con sus opciones.

#### <a name="assigning-a-compensation-group"></a>Asignar un grupo de compensación

Cuando se asigna un grupo de compensación a un puesto de previsión, los elementos de coste presupuestario predeterminados del grupo de compensación se agregan. Si los elementos de coste ya están asignados al puesto de previsión, esos elementos de coste permanecen. Si a un grupo de compensación ya ha sido asignado y se está modificando, los elementos existentes del coste de presupuesto se quitarán y sse ustituirán por el conjunto del grupo de compensación. 

Cuando selecciona un nivel de compensación y un paso, se agrega un elemento de coste presupuestario de ganancias (tal como se define en el grupo de compensación). El importe anual se calcula usando el índice en el nivel y el paso seleccionados, y las horas anuales en el grupo de compensación (o, para un salario anual, el importe completo en el nivel y el paso). De nuevo, este importe se descompone en factores por el intervalo de fechas de la línea del elemento de coste y el valor de FTE del puesto de previsión.

#### <a name="generating-increases"></a>Generar incrementos

Los aumentos anuales (uno por año natural) se pueden crear automáticamente para puestos de previsión que tienen un grupo de compensación basado en pasos asignado. Haga clic en **Generar aumentos** para agregar un elemento de coste presupuestario de ganancias en el paso más alto siguiente. La fecha inicial del nuevo elemento de coste presupuestario de ganancias es la fecha programada del aumento que se muestra en el puesto de previsión. Esta fecha se establece en el grupo de compensación de una de estas dos formas. Si la programación del aumento del grupo de compensación se establece en **Fecha común**, la fecha del aumento se especifica en el grupo de compensación. Si la programación del aumento se establece en **Fecha de aniversario**, se usa el campo de la fecha de aniversario en el puesto de previsión, y el ciclo presupuestario proporciona el año. Si hay años varios naturales dentro de un ciclo de presupuesto, se agregan varios aumentos. 

La fecha final del elemento actual de coste presupuestario de ganancias se actualiza con el día anterior a la fecha del aumento. El proceso de recálculo se usa automáticamente cuando se generan los aumentos. Por lo tanto, no es necesario volver a calcular manualmente. 

Si hace clic en **Generar aumentos** una segunda vez, el proceso se ejecuta otra vez pero no agrega más registros. Solo se crea un aumento por año natural.

#### <a name="changes-from-other-pages"></a>Modificaciones de otras páginas

Las actualizaciones a los puestos de previsión también pueden provenir de otras áreas, como el elemento de coste presupuestario y las páginas de la configuración del grupo de compensación. También puede modificar puestos de previsión a través del procesamiento de actualización masivo. 

Hay dos opciones disponibles en la página de configuración de **Elemento del coste presupuestario**: **Agregar a puestos** y **Actualizar puestos**. La opción **Agregar a puestos** agrega el elemento de coste presupuestario a puestos de previsión seleccionados. Si el elemento ya está asignado a un puesto de previsión, se omite dicho puesto de previsión. La opción **Puestos de actualización** aplica los valores actuales (la cuenta principal, el porcentaje, el importe anual, etc.) a los puestos seleccionados de previsión. 

Cada proceso tiene una página similar donde puede seleccionar los puestos de previsión. La página **Agregar a puestos** muestra todos os puestos de previsión que estén disponibles para la selección, mientras que la página **Actualizar puestos** muestra solo los puestos de previsión que tengan ya el elemento de coste presupuestario asignado. (Por lo tanto, la página **Actualizar puestos** ofrece una manera de averiguar qué puestos de previsión ya tienen asociado el elemento de coste). Puede mover puestos de previsión desde una cuadrícula superior a una cuadrícula inferior para incluirlos en la actualización. 

Tenga en cuenta que la funcionalidad **Cambiar fechas** en la pestaña **Cálculo de costes** cambia inmediatamente las fechas de inicio y fin del elemento de coste del presupuesto en los puestos de previsión. No hay opciones de selección disponibles. 

En la página **Grupo de compensación**, la función **Actualizar índices de puestos** aplica los índices actuales de la tabla del índice de compensación a los puestos de previsión que se asignan al grupo. Los índices se actualizan, y las líneas adicionales del elemento de coste se agregan para cualquier línea nueva de la tabla del índice (basado en fechas). Sin embargo, los elementos de coste presupuestario y las fechas del incremento no se actualizan. Puede seleccionar qué proceso de planificación presupuestaria y qué escenario del plan de presupuesto desea actualizar. Por lo tanto, puede actualizar un escenario pero dejar otros escenarios sin cambios para la comparación. 

Seleccionando puestos de previsión y haciendo clic en **Actualización masiva**, podrá agregar o cambiar más de un puesto de previsión en ese mismo tiempo. Hay muchas opciones disponibles. Una opción en la pestaña **Dimensiones financieras** es ligeramente diferente a las otras y está relacionada con los elementos de coste presupuestario. Puede agregar elementos de coste presupuestario estableciendo la opción **Presupuestos predeterminados** a **Sí**. Si no se selecciona ningún elemento de coste del presupuesto, pero **Presupuestos predeterminados** está establecido en **SíYes**, se eliminan todos los elementos de coste presupuestario que tiene asignados actualmente. 

El proceso de recálculo se usa automáticamente en cualquier puesto de previsión que haya cambiado.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Incorporar puestos de previsión en los planes de presupuesto

[![graphic6](./media/graphic6-1024x327.png)](./media/graphic6.png)

El propósito de crear y modificar puestos de la previsión es agregarlos a los planes de presupuesto, de modo que los planes de presupuesto incluyan los importes presupuestarios más precisos. Existen dos métodos para agregar puestos de previsión a planes de presupuesto. Puede usar un proceso de generación o un proceso de selección en el plan de presupuesto.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Generar plan presupuestario a partir de posiciones de previsión

La función **Generación del plan de presupuesto desde puestos de previsión** crea o actualiza planes de presupuesto de modo que tengan los importes de presupuesto y recuentos de FTE de los puestos de previsión. Los importes presupuestarios del puesto de previsión se convierten en los importes de la línea del plan de presupuesto y se agregan para valores de la dimensión financiera y fecha de vigencia. El proceso de generación asigna la posición de previsión de origen a la línea del plan presupuestario. Para ver el puesto, puede agregar el puesto de previsión como una fila en el diseño del plan presupuestario o usar la consulta **Líneas del plan presupuestario**. Para omitir esta asignación, defina la opción a **Incluir puesto en la línea del plan presupuestario** en **No**. 

Puede seleccionar un escenario de FTE del plan presupuestario para incluir el número de FTE en el plan presupuestario. Solo puede seleccionar los escenarios de tipo de cantidad que se incluyen en el diseño del plan presupuestario de destino. Cuando selecciona un escenario de FTE, también debe especificar una cuenta principal de FTE. Esta cuenta se usa para crear las líneas del plan presupuestario de la cantidad. 

El proceso de planificación presupuestaria y el escenario de del plan presupuestario seleccionados en el origen determinarn el proceso y el escenario de planificación presupuestaria del escenario de destino. Dado que estos atributos se asignan a posiciones de previsión, deben estar sincronizador con el plan presupuestario. Por tanto, los atributos no se pueden editar en el destino. 

Para otros procesos de generación, hay tres opciones disponibles:

-   **Crear un nuevo plan presupuestario**: crear un nuevo plan con los atributos que están seleccionados en la sección **Destino**.
-   **Sustituir el escenario del plan presupuestario existente**: eliminar todos los datos en el plan presupuestario de destino en el escenario seleccionado del plan presupuestario y crear nuevas líneas que tengan los datos del puesto de previsión.
-   **Actualizar el escenario del plan presupuestario existente y anexar nuevos datos**: actualizar las líneas existentes en el plan de destino que coinciden con las líneas de origen y también agregar nuevas líneas para los nuevos datos. La conciliación se basa en la cuenta contable, la fecha, la clase de presupuesto y otros valores, como el puesto de previsión. Todas las líneas con un número de posición que coincida con el número de posición de origen se sustituyen por las nuevas líneas de origen.

### <a name="selecting-forecast-positions"></a>Seleccionar puestos de previsión

También puede agregar importes presupuestarios del puesto de previsión directamente a un plan de presupuesto. Use la función **Agregar puestos** encima de las líneas del plan de presupuesto para seleccionar los puestos de previsión que desea incluir. 

Las situaciones del plan de presupuesto que puede seleccionar como origen se limitan a las situaciones que se incluyen en la configuración del plan. Una opción en la pestaña **Destino** permite especificar que la situación y la cuenta principal de FTE están disponibles para incluir recuentos de FTE, pero no son necesarios. 

Este proceso de selección actúa como la opción **Actualizar la situación existente del plan de presupuest y agregar los nuevos datos** para un proceso de generación. Todas las líneas del plan existente de presupuesto donde se va a agregar el puesto de previsión se eliminarán y se sustituirán por nuevas líneas que se basan en el estado actual del puesto de previsión.

#### <a name="date-options"></a>Opciones de fecha

Tanto para el proceso de generación como para el proceso de selección, la fecha inicial de la línea del elemento de coste presupuestario determina la fecha de vigencia de la línea correspondiente del plan de presupuesto. El campo **Método de asignación** de la página de configuración del elemento de coste presupuestario especifica el método de asignación:

-   **Fecha inicial**: la fecha inicial del elemento de coste del presupuesto se usa como la fecha de vigencia de la línea del plan de presupuesto.
-   **Mensual**: el importe presupuestario se divide uniformemente por el número de meses en el intervalo de fechas para producir un importe mensual normal que se asigne el primer día de cada mes. Si el primer período es un mes incompleto, el importe para ese mes se descompone en factores por el número de días que el coste estará activo en ese mes, y el resultado se asigna a la fecha inicial. El importe del último mes es la diferencia entre el importe total del presupuesto y la suma del resto de los meses. Por lo tanto, el redondeo puede afectar al importe del último mes.
-   **Trimestral**: este método es igual que el **Mensual**, pero los cálculos se realizan para períodos de tres meses.
-   **Semanal** la lógica es similar a la lógica de los métodos **Mensual** y **Trimestral**. El importe presupuestario se divide uniformemente por el número de semanas en el intervalo de fechas para producir un importe semanal normal que se asigne el primer día de cada semana. Si el primer período es una semana incompleta, el importe para esa semana se descompone en factores por el número de días que el coste estará activo en esa semana, y el resultado se asigna a la fecha inicial. El importe de la última semana es la diferencia entre el importe total del presupuesto y la suma del resto de las semanas. Por lo tanto, el redondeo puede afectar al importe de la última semana.
-   **Quincenal**: este método es igual que el **Semanal**, pero los cálculos se realizan para períodos de dos semanas.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Modificar línas de planes presupuestarios que tienen puestos de previsión

Las líneas del plan de presupuesto muestran el origen de los importes de presupuesto (el número del puesto de previsión) pero no están vinculados. Por lo tanto, las modificaciones al puesto de previsión no se muestran en la línea del plan de presupuesto, y las modificaciones a la línea del plan de presupuesto se muestran en el puesto de previsión. Si cambia un puesto de previsión y desea que las actualizaciones se incluyan en un plan de presupuesto, debe incorporar el puesto de previsión en el plan de nuevo. Sin embargo, recuerde que este proceso elimina todas las líneas que se asignan al puesto de previsión. Por tanto, se eliminan los cambios realizados a estas líneas. 

Para ver en qué planes de presupuesto se ha incluido un puesto de previsión, puede generar el informe **Puestos de previsión por plan de presupuesto**. Como alternativa, en el puesto de previsión, puede abrir el cuadro informativo **Planes asociados de presupuesto** para ver los planes.



