---
title: Planes de mantenimiento
description: En este tema se explican los planes de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4e9dca4b9b163e73c33ec2dc88b8aea2cecd9bef
ms.sourcegitcommit: 6476f27c8d3dced7c2e9a7344a4e378b51a1983e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "1922215"
---
# <a name="maintenance-plans"></a>Planes de mantenimiento

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Un plan de mantenimiento define cuándo debe llevarse a cabo un trabajo de mantenimiento previamente planificado en un activo. Los planes de mantenimiento pueden estar relacionadas con activos, tipos de activos, ubicaciones técnicas o tipos de ubicaciones técnicas, pero primero debe crear los planes de mantenimiento que se utilizarán en su empresa.

Un plan de mantenimiento puede tener varias líneas del plan de mantenimiento. En la línea del plan de mantenimiento se especifican un tipo y un intervalo de trabajo de mantenimiento. Existen dos tipos de líneas del plan de mantenimiento:

- Tiempo  
- Contador  

Las líneas del plan de mantenimiento de tipo "Hora" se usan para un mantenimiento planificado periódico basado en un intervalo de tiempo fijo. Las líneas del plan de mantenimiento de tipo "Contador" se usan para un mantenimiento planificado o un mantenimiento reactivo en función de los registros del contador del activo. Un plan de mantenimiento puede incluir varias líneas del plan de mantenimiento de ambos tipos.

>[!NOTE]
>Si no se ha registrado ningún valor del contador para un tipo de contador en un activo, se omiten las líneas del plan de mantenimiento.

En primer lugar, cree los planes de mantenimiento que necesita para sus trabajos de mantenimiento preventivo y seleccione los tipos de activos, los activos, los tipos de ubicación técnica y las ubicaciones técnicas que deben relacionarse con cada plan de mantenimiento. A continuación, si es necesario, también puede agregar planes de mantenimiento a un activo o a una ubicación técnica. Esto se hace en **Todos los activos** > seleccione el activo > ficha desplegable **Planes de mantenimiento del activo** o **Todas las ubicaciones técnicas** > seleccione la ubicación técnica > ficha desplegable **Planes de mantenimiento**.

Si agrega un plan de mantenimiento a tipos de activo o a tipos de ubicación técnica, significa que cuando cree nuevos activos o ubicaciones técnicas con esos tipos de activo o tipos de ubicación técnica, el activo o la ubicación técnica se agregará automáticamente al plan de mantenimiento. La fecha de inicio de la relación con un plan de mantenimiento será la fecha actual, que puede que sea necesario ajustar.

## <a name="set-up-maintenance-plans"></a>Configurar planes de mantenimiento

En esta sección se describe cómo configurar líneas del plan de mantenimiento y se proporcionan ejemplos de cómo se pueden usar.

1. Haga clic en **Administración de activos** > **Configuración** > **Mantenimiento preventivo** > **Planes de mantenimiento**.

2. Haga clic en **Nueva** para crear una nueva secuencia.

3. Inserte un identificador en el campo **Secuencia de mantenimiento** y un nombre en el campo **Nombre**.

4. En el campo **Fecha del plan**, inserte la fecha de inicio desde la que se puede hacer la planificación en el plan de mantenimiento. Tenga en cuenta que las líneas del plan de mantenimiento basado en la hora pueden tener otras fechas de plan.

5. Seleccione "Sí" en el botón de alternancia **Activar** para activar el plan de mantenimiento.

>[!NOTE]
>Si desactiva un plan de mantenimiento, no se creará ningún registro de programación en el programa de mantenimiento cuando ejecute un trabajo del plan de mantenimiento del programa.

6. Los campos **Días de tolerancia antes** y **Días de tolerancia después** se relacionan con las líneas del plan de mantenimiento en las que se seleccione la casilla **Suprimir trabajos de mantenimiento superpuestos** (consulte el paso 17). Los campos "Tolerancia" se usan para ampliar el intervalo en días en los que, si se superponen varios planes de mantenimiento, el trabajo más completo/grande se crea como una línea del programa de mantenimiento durante la programación del plan de mantenimiento, mientras que los trabajos más frecuentes y solapados se omiten durante la programación del plan de mantenimiento. Inserte el número de días en el campo **Días de tolerancia antes**, por ejemplo, "2".

7. Si ha insertado un valor en **Días de tolerancia antes**, inserte también el número de días en el campo **Días de tolerancia después**, por ejemplo, "2".

>[!NOTE]
>El ejemplo descrito en este paso y el anterior significa que si se superponen varias líneas del plan de mantenimiento y se selecciona **Suprimir trabajos de mantenimiento superpuestos** para una o más líneas, el período de omisión de líneas del programa de mantenimiento se amplía a un total de cinco días (la fecha de inicio prevista en la línea del programa de mantenimiento *y* dos días antes *y* dos días después de esa fecha).

8. Los campos del grupo **Detalles** en la ficha desplegable **Detalles** muestra, el número de líneas del plan de mantenimiento configuradas en el plan de mantenimiento, así como el número de activos y de ubicaciones técnicas relacionados con el plan de mantenimiento.

9. En la ficha desplegable **Líneas**, haga clic en **Agregar línea de tiempo** o **Agregar línea de contador del activo** para crear una nueva línea del plan de mantenimiento.

10. Inserte una descripción para la línea en el campo **Descripción de la orden de trabajo**. La descripción se transfiere a las órdenes de trabajo relacionadas.

11. En el campo **Tipo de trabajo de mantenimiento**, seleccione el tipo de trabajo para el que se relaciona la línea del plan de mantenimiento.

12. En los campos **Variante del tipo de trabajo de mantenimiento** y **Comercio**, seleccione la variante y el comercio relacionados con el tipo de trabajo de mantenimiento.

13. En los campos **Finalizar en días** y **Finalizar en horas**, puede insertar la fecha de finalización prevista en días u horas. La fecha de finalización prevista se inserta en relación con la fecha de inicio prevista, que se calcula cuando se crean las líneas del programa de mantenimiento. Por ejemplo, puede insertar "7" en el campo **Finalizar en días** para indicar que el trabajo relacionado debe completarse en una semana desde la fecha de inicio prevista.

14. En el campo **Tipo de intervalo**, seleccione el tipo de intervalo que se usará en la línea del plan de mantenimiento, por ejemplo, "Repetido..." o "Una vez…". Consulte la tabla [Visión general de tipos de intervalo](## Interval types overview) más abajo para ver una descripción de la relación entre los tipos de intervalo y los tipos de línea.

15. El campo **Período** se relaciona únicamente con los tipos de línea basados en la hora. Seleccione el tipo de período relacionado con la frecuencia del período.

16. En el campo **Frecuencia del período**, inserte el número de veces que debe usarse la línea para trabajos de mantenimiento preventivo planificados. Ejemplo: si ha creado una línea de tipo "Contador", su contador es cantidad de producción e inserta el número "20 000" en este campo, se crean nuevas líneas de secuencias de mantenimiento durante la programación de mantenimiento preventivo cada vez que se espere que produzca 20 000 artículos más.

17. La casilla **Suprimir trabajos de mantenimiento superpuestos** se relaciona con los tipos de línea basada en la hora y basada en contador. Seleccione la casilla para eliminar las entradas del programa de mantenimiento que se crean en la misma fecha. Esto es relevante si, por ejemplo, ha creado una línea de inspección de 1 mes, una línea de inspección de 6 meses y una línea de inspección de 1 año. Para la inspección de 1 año solo desea que se realice esa inspección, no las otras dos inspecciones, que también cabrían en el intervalo de tiempo. Para configurar este ejemplo correctamente, configure la línea de inspección de 1 año como la primera línea, la línea de 6 meses como la segunda línea y la línea de 1 mes como la tercera línea. A continuación, seleccione la casilla **Suprimir trabajos de mantenimiento superpuestos** para las líneas de 1 mes y de 6 meses. De esta forma, se asegura de que cuando alcance la marca de 1 año se omitan las inspecciones para un mes y seis meses, y se crea únicamente una línea del programa de mantenimiento para la línea de inspección de 1 año.

>[!NOTE]
>El ejemplo descrito en este paso muestra que el trabajo más completo, que contiene el mayor número de tareas y que no se hace con tanta frecuencia, debe insertarse siempre como la primera línea. Los trabajos más frecuentes se insertan como líneas independientes en el orden de frecuencia, colocando el trabajo más frecuente en la parte inferior de la lista.

18. El campo **Contador** se relaciona únicamente con los tipos de línea basada en contador. Seleccione el tipo de contador que se usará en la línea. Si un tipo de contador no está activo en un activo relacionado, se omite la línea del plan de mantenimiento.

19. El campo **Límite de tiempo de contador de activo en días** se relaciona únicamente con los tipos de línea basada en contador. Inserte un número que defina cuántos registros de contador de días atrasados se comprueban cuando se realiza la planificación del plan de mantenimiento. Esto significa hasta qué punto se usan los datos (registros de contador existentes) como base para calcular la tendencia que determina cuántas líneas del programa de mantenimiento se crean.

>*Ejemplo:* si se espera que los registros de contador se hagan una vez al mes, puede insertar el número "365" en este campo porque la programación del plan de mantenimiento siempre se basará en los últimos 12 meses. De este modo, creará líneas del programa de mantenimiento basadas en la tendencia del último año. Por otro lado, si inserta el número "10" en este campo, se espera que los registros de contador se hagan con más frecuencia, por ejemplo, a diario. Esto significa que cuando programa un plan de mantenimiento, los registros de contador para los últimos 10 días se utilizan como base para la programación de líneas del programa de mantenimiento.

20. El campo **Fecha del plan** se relaciona únicamente con los tipos de línea basados en la hora. Si la línea del plan de mantenimiento tiene otra fecha de planificación que el plan de mantenimiento completo, seleccione una fecha en el campo **Fecha del plan** de la línea.

21. En el campo **Nivel de servicio**, puede seleccionar un nivel de servicio de la orden de trabajo como delimitación adicional en la línea del plan de mantenimiento para que se utilice como un nivel de servicio en órdenes de trabajo.

22. Seleccione la casilla **Crear automáticamente** si desea que una orden de trabajo se cree automáticamente según la línea del plan de mantenimiento seleccionada al programar planes de mantenimiento.

23. Si ha seleccionado la casilla **Crear automáticamente**, puede seleccionar un tipo de orden de trabajo para la orden de trabajo creada automáticamente en el campo **Tipo de orden de trabajo**. Si ha seleccionado la casilla **Crear automáticamente** y no selecciona un tipo de orden de trabajo en este campo, se usará el tipo de orden de trabajo seleccionado en el vínculo **Administración de activos** > **Configuración** > **Parámetros de administración de activos** > **Órdenes de trabajo** > campo **Tipo de orden de trabajo preventivo**.

24. Use los campos **Desde estación** y **Hasta estación** para crear una línea del plan de mantenimiento basada en la hora dentro de un periodo de 12 meses. *Ejemplo:* el equipo que se usa para mantener zonas verdes requiere servicio cada primavera dentro de un período predefinido. Inserte la fecha de inicio del período que se repetirá en el campo **Desde estación**.

25. Inserte la fecha de finalización del período que se repetirá en el campo **Hasta estación**.

26. En el campo **Período resultante**, se muestra el período actual que se repetirá. Cuando el período actual haya pasado y comience un nuevo año, el período que se muestra en este campo se actualizará para reflejar el siguiente período en la secuencia de repetición.

27. En la ficha desplegable **Activos**, seleccione los activos que deben relacionarse con el plan de mantenimiento.

28. En la ficha desplegable **Tipos de activos**, seleccione los tipos de activos que deben relacionarse con el plan de mantenimiento.

29. En la ficha desplegable **Ubicaciones técnicas**, seleccione las ubicaciones técnicas que deben relacionarse con el plan de mantenimiento. Si es necesario, puede realizar una configuración más específica seleccionando un tipo de activo, un fabricante y un modelo relacionados.

30. En la ficha desplegable **Tipos de ubicación técnica**, seleccione los tipos de ubicación técnica que deben relacionarse con el plan de mantenimiento.

>[!NOTE]
>Cuando se crean órdenes de trabajo manualmente en activos que son cubiertos por la garantía de un proveedor, se muestra un cuadro de diálogo para que el usuario reconozca la garantía. La creación de la orden de trabajo se puede cancelar. La comprobación de una relación de garantía se omite para órdenes de trabajo que se crean automáticamente.

## <a name="interval-types-overview"></a>Visión general de tipos de intervalo

| Tipo y descripción del intervalo                                                                                                                                                                                                                                                                                                                                                                                                       | Tipo de línea: Hora                                                                                                                                                                                                                                                                                                                                                           | Tipo de línea: Contador                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo de intervalo: repetido a partir de la fecha del plan** Comienza el recuento a partir de la fecha del plan utilizada. Cuando programe planes de mantenimiento, se crean líneas del programa de mantenimiento cuando se alcanza el intervalo.                                                                                                                                                                                                                | Se usa la **Fecha del plan** en la línea del plan de mantenimiento. Si no se selecciona ninguna fecha del plan en la línea, se usa la **Fecha del plan** para el plan de mantenimiento. Ejemplo: si se inserta el número "3" en el campo **Frecuencia de períodos** y se selecciona "Año" en el campo **Período**, se creará una nueva línea del programa de mantenimiento una vez cada 3 años.                             | Se usa la **Fecha del plan** para el plan de mantenimiento. Si ha sustituido el contador, se usa la última fecha de sustitución como la fecha del plan.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Tipo de intervalo: Repetido desde la fecha de inicio** El recuento comienza desde la fecha de inicio en la relación del activo. La fecha se selecciona en la vista de detalles **Todos los activos** > ficha desplegable **Planes de mantenimiento del activo** > campo **Fecha de inicio**, o en la vista de detalles **Todas las ubicaciones técnicas** > ficha desplegable **Planes de mantenimiento** > campo **Fecha de inicio**. Cuando programe planes de mantenimiento, se crea una línea del programa de mantenimiento cuando se alcanza el intervalo. | Se usa la fecha de inicio de la línea del plan de mantenimiento en el activo o la ubicación técnica. Si ese campo está en blanco, se usa la **Fecha del plan** para el plan de mantenimiento.                                                                                                                                                                                                 | Se usa la fecha de inicio de la línea del plan de mantenimiento en el activo o la ubicación técnica. Si ese campo está en blanco, se usa la **Fecha del plan** para el plan de mantenimiento.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **Tipo de intervalo: Repetido desde la última orden de trabajo** El recuento comienza desde la fecha y hora reales de finalización de la última orden de trabajo que se completó en el activo con este tipo de trabajo de mantenimiento específico y la combinación de variante de tipo de trabajo de mantenimiento y comercio. Esa fecha y hora se muestran en el campo **Finalización real** en la vista de detalles **Todas las órdenes de trabajo**.                                                                                                                                 | Se usa la fecha y hora real de finalización de la orden de trabajo completada en el activo con esa combinación de tipo de trabajo de mantenimiento, variante de tipo de trabajo de mantenimiento y comercio. Si no se encuentra ninguna orden de trabajo completada, se usa una de las fechas empleadas en el tipo de intervalo "Repetido desde la fecha de inicio" que se describe anteriormente.                                                                                             | Se usa la fecha y hora real de finalización de la orden de trabajo completada en el activo *y* la combinación de tipo de trabajo de mantenimiento / variante de tipo de trabajo de mantenimiento / comercio . Si la fecha y hora de inicio se dejó en blanco en la orden de trabajo, se usa una de las fechas empleadas en el tipo de intervalo "Repetido desde la fecha de inicio" que se describe anteriormente.                                                                                                                                                                                                                                                                                                                                                                           |
| **Tipo de intervalo: Una vez desde la fecha del plan** Consulte la descripción del tipo de intervalo anterior "Repetido desde la fecha del plan". La única diferencia es que este tipo de intervalo solo debe usarse una vez.                                                                                                                                                                                                                                                   | Consulte la descripción del tipo de intervalo anterior "Repetido desde la fecha del plan". Este intervalo suele usarse para un mantenimiento o trabajo de servicio único.                                                                                                                                                                                                                             | Consulte la descripción del tipo de intervalo anterior "Repetido desde la fecha del plan". Este intervalo suele usarse para un mantenimiento o trabajo de servicio único. **Nota 1:** este tipo de intervalo solo es pertinente si el contador se sustituye cada vez que lleva a cabo un mantenimiento o un trabajo de servicio. Si, por algún motivo, se ha sustituido un contador antes de final del intervalo planificado, se calcula un nuevo intervalo de tiempo para el trabajo desde el momento en que se sustituye el contador. **Nota 2:** si el contador se sustituye al completar el mantenimiento o el trabajo de servicio, este tipo de intervalo funciona como el tipo de intervalo anterior "Repetido desde la fecha del plan".                                             |
| **Tipo de intervalo: Una vez desde la fecha de inicio** Consulte la descripción del tipo de intervalo anterior "Repetido desde la fecha de inicio". La única diferencia es que este tipo de intervalo solo debe usarse una vez.                                                                                                                                                                                                                                                 | Consulte la descripción del tipo de intervalo anterior "Repetido desde la fecha de inicio". Este intervalo suele usarse para un mantenimiento o trabajo de servicio único.                                                                                                                                                                                                                            | Consulte la descripción del tipo de intervalo anterior "Repetido desde la fecha de inicio". Este intervalo suele usarse para un mantenimiento o trabajo de servicio único. La **Nota 1** anterior también se aplica a este tipo de intervalo. **Nota 3:** si el contador se sustituye al completar el mantenimiento o el trabajo de servicio, este tipo de intervalo funciona como el tipo de intervalo anterior "Repetido desde la fecha de inicio".                                                                                                                                                                                                                                                                                                |
| **Tipo de intervalo: Una vez alcanzado por encima** Este tipo intervalo se relaciona únicamente con intervalos y se usa para indicar una configuración del límite superior en la línea del plan de mantenimiento. Las entradas del programa de mantenimiento tendrán la fecha y hora de inicio prevista del registro del contador, lo que significa que estas entradas se crearán con una fecha de inicio prevista igual o anterior a la fecha del sistema.                                                | N/A                                                                                                                                                                                                                                                                                                                                                                       | El intervalo de contador indica un límite superior. Si se excede dicho límite al crear un registro de contador, se crea una línea del programa de mantenimiento cuando programe un mantenimiento preventivo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Tipo de intervalo: Una vez alcanzado por debajo** Este tipo intervalo se relaciona únicamente con intervalos y se usa para indicar una configuración del límite inferior en la línea del plan de mantenimiento. Las entradas del programa de mantenimiento tendrán la fecha y hora de inicio prevista del registro del contador, lo que significa que estas entradas se crearán con una fecha de inicio prevista igual o anterior a la fecha del sistema.                                                 | N/A                                                                                                                                                                                                                                                                                                                                                                       | El intervalo de contador indica un límite inferior. Si se sobrepasa dicho límite al crear un registro de contador, se crea una línea del programa de mantenimiento cuando programe un mantenimiento preventivo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Tipo de intervalo: vinculado a partir de la fecha de inicio** Este tipo de intervalo creará solo una línea de mantenimiento una vez. Un plan de mantenimiento puede contener más líneas de plan de mantenimiento que usan este tipo de intervalo, y esas líneas se vinculan. Normalmente, creará un plan de mantenimiento que contenga únicamente líneas de este tipo de intervalo. Las líneas del programa de mantenimiento se crean identificando la línea del plan de mantenimiento que tiene la primera fecha y hora de inicio prevista.                                                                                                                                                                                                                                                                                                                                                                                           | Consulte la descripción anterior para "Una vez desde la fecha de inicio". Ejemplo: crea dos líneas en un plan de mantenimiento para un trabajo de servicio en un vehículo: una línea basada en la hora con un periodo de 1 año y una línea basada en contador con una límite de 25000 km. Se crea una línea del programa de mantenimiento para el límite que se alcance primero. Para este tipo de línea, crea la línea con el período de 1 año.                                                                                                                                                                                   | Consulte la descripción anterior para "Una vez desde la fecha de inicio". Ejemplo: crea dos líneas en un plan de mantenimiento para un trabajo de servicio en un vehículo: una línea basada en la hora con un periodo de 1 año y una línea basada en contador con una límite de 25000 km. Se crea una línea del programa de mantenimiento para el límite que se alcance primero. Para este tipo de línea, crea la línea con el límite de 25000 km. Ejemplo de creación de dos líneas de contador: también puede configurar un plan de mantenimiento con dos líneas vinculadas basadas en contador. La primera línea tiene un límite de 10 000 artículos producidos, mientras que la segunda línea se relaciona con la máquina o el centro de trabajo que requiere el servicio después de funcionar 3000 horas.                                                                                                                                                           |
| **Tipo de intervalo: vinculado desde la última orden de trabajo** Este tipo de intervalo crea nuevas líneas de programación de mantenimiento después de cada orden de trabajo completada. Un plan de mantenimiento puede contener más líneas que usan este tipo de intervalo, y esas líneas se vinculan. Normalmente, creará un plan de mantenimiento que contiene líneas del plan de mantenimiento de solo este tipo de intervalo. Las líneas del programa de mantenimiento se crean identificando la línea del plan de mantenimiento que tiene la primera fecha y hora de inicio prevista.                                                                                                                                                                                                                                                                        | Este tipo de intervalo funciona básicamente igual que "Vinculado desde la fecha de inicio" que se describe anteriormente. La única diferencia es la fecha en la que se basa el tipo de intervalo. La fecha usada es la fecha y hora real de la última orden de trabajo completada en el activo *y* la combinación de tipo de trabajo de mantenimiento / variante de tipo de trabajo de mantenimiento / comercio.                                                                                                                                                                                                                                                           | Este tipo de intervalo funciona básicamente igual que "Vinculado desde la fecha de inicio" que se describe anteriormente. La única diferencia es la fecha en la que se basa el tipo de intervalo. La fecha usada es la fecha y hora real de la última orden de trabajo completada en el activo *y* la combinación de tipo de trabajo de mantenimiento / variante de tipo de trabajo de mantenimiento / comercio.                                                                                                                   |


>[!NOTE]
>Cuando se crean líneas del programa de mantenimiento para líneas del plan de mantenimiento basadas en la hora, la hora prevista es siempre al principio del día. Para las líneas del plan de mantenimiento basadas en contador, la hora prevista puede ser cualquiera durante el día.

A continuación encontrará ejemplos de la configuración de líneas del plan de mantenimiento basadas en la hora y basadas en contador:

**Ejemplo 1 - Línea del plan de mantenimiento basada en la hora:** un trabajo de lubricación se puede configurar en un intervalo fijo que se produzca una vez a la semana. Para ello, seleccione "Repetido desde la fecha del plan" en el campo **Tipo de intervalo**. Consulte un ejemplo en la siguiente ilustración.

![Figura 1](media/02-preventive-maintenance.png)

**Ejemplo 2 - Línea del plan de mantenimiento basada en la hora:** un trabajo de inspección se puede configurar para que se lleve a cabo aproximadamente una vez a la semana. Para ello, seleccione "Repetido desde la última orden de pedido" en el campo **Tipo de intervalo**. Consulte un ejemplo en la siguiente ilustración.

![Figura 2](media/03-preventive-maintenance.png)

**Ejemplo 3 - Línea del plan de mantenimiento basada en contador:** la siguiente ilustración gráfica muestra un contador de horas para el que se crea una nueva línea del programa de mantenimiento cada vez que han pasado 250 horas. El tipo de intervalo para esta línea basada en contador es "Repetido desde la fecha de inicio". La fecha de inicio es la fecha de inicio de los activos relacionados en la vista de detalles **Todos los activos** > ficha desplegable **Planes de mantenimiento del activo** > campo **Fecha de inicio**, o en la vista de detalles **Ubicación técnica** > ficha desplegable **Planes de mantenimiento** > campo **Fecha de inicio**. Este es un ejemplo de un plan de mantenimiento *preventivo* porque el programa de mantenimiento se crea automáticamente cada vez que se alcanza el umbral (+ 250).

![Figura 3](media/04-preventive-maintenance.png)


**Ejemplo 4 - Línea del plan de mantenimiento basada en contador:** la siguiente ilustración gráfica muestra una disminución en un valor de contador, que mide el desgaste de la zapata de freno. Se crea una línea del programa de mantenimiento cuando se crea un registro de contador por debajo de 20 mm en la zapata de freno. El tipo de intervalo para esta línea basada en contador es "Una vez alcanzado por debajo" o "Una vez desde la última fecha de inicio". Este es un ejemplo de un plan de mantenimiento *reactivo* porque el programa de mantenimiento no se crea hasta que se registre una medida por debajo de 20 mm.

![Figura 4](media/05-preventive-maintenance.png)


**Ejemplo 5 - Línea del plan de mantenimiento basada en contador:** la siguiente ilustración gráfica muestra un contador con un umbral de -18° Celsius. Se crea una línea del programa de mantenimiento cuando se realiza un registro de contador por encima de -18° Celsius. El tipo de intervalo para esta línea basada en contador es "Una vez alcanzado por encima". Este es un ejemplo de un plan de mantenimiento *reactivo* porque el programa de mantenimiento no se crea hasta que se registre una medida por encima de -18° Celsius.

![Figura 5](media/06-preventive-maintenance.png)

- Cuando cree un nuevo activo y ese activo use un tipo de activo relacionado con un plan de mantenimiento, el plan de mantenimiento se inserta automáticamente en la ficha desplegable **Todos los objetos** > **Planes de mantenimiento del activo**. Además, en **Valores predeterminados de tipo de activo**, en la ficha desplegable **Planes de mantenimiento**, se insertarán automáticamente los planes de mantenimiento relacionados.  
- Si agrega o elimina tipos de activo o tipos de ubicación técnica en **Planes de mantenimiento**, ese cambio solo se reflejará en los nuevos activos creados después de hacer el cambio.  
- Si agrega o elimina activos o ubicaciones técnicas en **Planes de mantenimiento**, ese cambio se actualizará automáticamente en la ficha desplegable **Todos los activos** > **Planes de mantenimiento del activo** o en la ficha desplegable **Todas las ubicaciones técnicas** > **Planes de mantenimiento**.  

La siguiente ilustración muestra un ejemplo de un plan de mantenimiento de "servicio de camión” en la página **Planes de mantenimiento**.

![Figura 6](media/07-preventive-maintenance.png)


## <a name="add-a-maintenance-plan-to-an-asset"></a>Agregar un plan de mantenimiento a un activo

1. Haga clic en **Administración de activos** > **Común** > **Activos** > **Todos los activos** o **Activos activos**.

2. Seleccione el activo sobre el que desee configurar un plan de mantenimiento y haga clic en **Editar**.

3. En la ficha desplegable **Planes de mantenimiento del activo**, haga clic en **Agregar línea** para agregar un plan de mantenimiento al activo.

4. En el campo **Plan de mantenimiento**, seleccione el plan de mantenimiento pertinente.

5. En el campo **Fecha de inicio**, seleccione la fecha a partir de la cual se puede hacer la planificación de trabajos de mantenimiento preventivo. 

6. Haga clic en **Guardar**. El campo **Activar** se actualiza automáticamente.

La siguiente ilustración muestra un ejemplo de planes de mantenimiento configurados en un activo en la página **Todos los activos**.

![Figura 7](media/08-preventive-maintenance.png)

