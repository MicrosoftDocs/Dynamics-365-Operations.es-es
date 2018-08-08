---
title: Definiciones de organigramas en informes financieros
description: "Este artículo proporciona información acerca de las definiciones de organigrama. Una definición de organigrama es un componente de informe, o bloque de creación, que ayuda a definir la estructura y jerarquía de la organización."
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ec1286f1f3fb75cefd40f3982ec62d5ed078299c
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="reporting-tree-definitions-in-financial-reports"></a>Definiciones de organigramas en informes financieros

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de las definiciones de organigrama. Una definición de organigrama es un componente de informe, o bloque de creación, que ayuda a definir la estructura y jerarquía de la organización.

Los informes financieros admiten los informes flexibles, de manera que pueda realizar con facilidad cambios a su estructura comercial. Los informes se generan a partir de diversos componentes o bloques de creación. Uno de estos bloques de creación es una definición de árbol de informes. Una definición de árbol de informes ayuda a definir la estructura y la jerarquía de la organización. Es una estructura jerárquica dimensional que se basa en las relaciones dimensionales de los datos financieros. Proporciona información en el nivel de la unidad de informes y en un nivel de resumen para todas las unidades del árbol. Las definiciones de organigramas se pueden combinar con las definiciones de columnas y las definiciones de informes para crear un grupo de bloques de creación que pueda ser usado por varias empresas. Se usa una unidad organizacional para cada organigrama. Una unidad organizacional puede ser un departamento individual de los datos financieros, o puede ser una unidad de resumen de nivel superior que combina la información de otras unidades organizacionales. Para obtener una definición del informe que incluya un organigrama, se genera un informe para cada unidad de notificación y para el nivel de resumen. Todos estos informes usan las definiciones de filas y de columnas especificadas en la definición del informe, a menos que la definición del informe especifique que se debe usar el organigrama de la definición de filas. Las definiciones de filas y columnas son componentes importantes en el diseño y la funcionalidad de informes financieros. Los organigramas aumentan el poder de los componentes y son compatibles con los informes flexible cuando la estructura comercial cambia. Los informes financieros que no se basan en organigramas usan solo algunas de las capacidades de los informes financieros. Puede usar varias definiciones de organigramas junto con las mismas definiciones de filas y de columnas para ver los datos de su organización de distintas maneras.

## <a name="reporting-tree-best-practices"></a>Prácticas recomendadas para organigramas
Antes de crear un organigrama, tenga en cuenta las siguientes prácticas recomendadas:

-   Primero determine qué informar dimensiones de informes requiere su entidad jurídica o empresa.
-   Tenga en cuenta cómo ha configurado la estructura y luego realice un organigrama de su empresa. El gráfico de la organización le ayudará a visualizar cómo agrupar las unidades organizacionales en uno o varios organigramas.
-   Comience con el nivel de detalle más bajo disponible, como los departamentos y los proyectos que se definen en los datos financieros. Agregue tantos cuadros al nivel de detalle como sea necesario, para mostrar divisiones o regiones de alto nivel. Cada cuadro representa una unidad de notificación potencial en cualquier organigrama que cree.
-   También debe considerar el mejor modo de crear sus organigramas. Puede usar un proceso automatizado de creación para generar un organigrama, o puede crear un organigrama manualmente. Es importante que comprenda ambos métodos antes de diseñar los organigramas.
-   Puede usar las unidades de notificación que se definen en su sistema de datos financieros para agregar unidades de notificación a la definición del organigrama.

## <a name="create-multiple-reporting-trees"></a> Crear varios organigramas
Puede crear un número ilimitado de organigramas para ver los datos de su organización de distintas maneras. Cada organigrama puede incluir cualquier combinación de departamentos y unidades. Una definición del informe solo puede contener un vínculo a un organigrama a la vez. Cambiando la estructura de las unidades de notificación, puede crear distintos organigramas. A continuación, puede utilizar las mismas definiciones de filas y de columnas para cada organigrama. De esta manera, puede crear rápidamente diferentes diseños de informes financieros. Si crea varios organigramas, puede imprimir una serie de informes financieros cada mes que analicen y presenten las operaciones de la empresa de diversas maneras. Para obtener más información, vea los ejemplos de estructuras de unidades organizacionales al final de este artículo.

## <a name="create-a-reporting-tree-definition"></a> Crear una definiciones del organigrama
Una definición del organigrama contiene las columnas que se describen en la tabla siguiente.


| Columna del organigrama |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        Compañía        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          El nombre de la empresa para el organigrama. El valor <strong>@ANY</strong>, que normalmente se asigna solo al nivel de resumen, permite que el organigrama se use para todas las empresas. Todas las ramas secundarias tienen una compañía asignada.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|       Nombre de la unidad       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   El código que identifica esta unidad de notificación en el organigrama gráfico. Asegúrese de establecer un sistema de codificación único que sea coherente y que vaya a ser fácil de comprender para los usuarios.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|   Descripción de la unidad    |                                                                                                                                                                                                                                                                                                                                                                                                                                                        El título de la unidad de notificación aparece en el encabezado o el pie de página del informe si especifica <strong>UnitDesc</strong> como código en la pestaña <strong>Encabezados y pies de página</strong> de la definición del informe. El título aparece en la descripción de la fila del informe si especifica <strong>UnitDesc</strong> en la celda <strong>Descripción</strong> de la definición de la fila                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|      Dimensiones       |                                                                                                                                                                                                                                                                                                                                                                      Una unidad de notificación que recaba información directamente de los datos financieros. Define la colocación y las longitudes lógicas para la cuenta y los segmentos relacionados. Cada fila de unidad organizacional debe tener una dimensión en esta columna. También puede colocar una dimensión en una fila de unidad de resumen (por ejemplo, para los gastos que están relacionados directamente con esa unidad). Si especifica una dimensión en una fila de resumen de unidad, las cuentas que se usan en unidades principales no se deben usar en unidades secundarias. De lo contrario, se pueden duplicar los importes.                                                                                                                                                                                                                                                                                                                                                                      |
|    Definiciones de las filas    |                                                                                                                                                                                                                                                                                                                                                                                        El nombre de la definición de filas para la unidad de notificación. Se usa la misma definición de fila para todas las unidades del organigrama. Cuando se genera un informe, esta definición de fila se usa para todas las unidades organizacionales. La definición de fila puede incluir varios vínculos de dimensiones financieras. Si se especifica una definición de fila en el organigrama, active la casilla <strong>Usar definición de fila del organigrama</strong> de la pestaña <strong>Informe</strong> de la definición del informe.                                                                                                                                                                                                                                                                                                                                                                                        |
|       Vínculo de fila        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            Vínculo de fila que se va a usar para la unidad organizacional. Los vínculos de fila se especifican para la definición de fila para identificar las dimensiones financieras con las que se crearán vínculos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|     Vínculo externo     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   Vínculo de fila que se va a usar para esta unidad organizacional. Los vínculos de fila se definen para que la definición de filas identifique el informe al que vincularla.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|     Archivo externo     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              La ruta de acceso al archivo de la hoja de cálculo de informes financieros del que extraer datos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|     Opciones de página      |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Esta columna controla si se suprimen los detalles de la unidad organizacional cuando se ve o se imprime el informe.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|       % de distribución        | El porcentaje de la unidad organizacional que se debe asignar a la unidad principal. El porcentaje especificado en esta columna solo se aplica a cada fila de la definición de filas antes de que el valor de la fila se agregue al informe principal. Por ejemplo, si se debe dividir una unidad secundaria uniformemente entre dos departamentos, los importes en cada fila se multiplican por el 50 por ciento antes de que el valor se agregue al informe del departamento. Una unidad organizacional no puede tener dos unidades principales. Para asignar los importes de una unidad organizacional a las unidades biparentales, cree otra unidad organizacional que tenga la misma dimensión para distribuir el 50 por ciento adicional. Especifique porcentajes enteros sin una coma decimal. Por ejemplo, <strong>25</strong> representa la asignación del 25 por ciento al elemento primario. Si incluye una coma decimal (<strong>,25</strong>), se asigna el porcentaje del 0,25% al elemento primario. Para usar un porcentaje inferior al 1 por ciento, use la opción <strong>Permitir distribución de &lt;1%</strong> en la definición del importe. Esta opción está en la pestaña <strong>Opciones adicionales</strong> en el cuadro de diálogo <strong>Configuración de informes</strong>. A este cuadro de diálogo se obtiene acceso desde el botón <strong>Otra</strong> en la pestaña <strong>Configuración</strong> de la definición del informe. |
|     Seguridad de la unidad     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   Restricciones en los usuarios y grupos que pueden tener acceso a la información de la unidad organizacional.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|    Texto adicional    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               El texto incluido en el informe.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |

Para crear una definición de organigrama, siga estos siguientes pasos.

1.  Abrir el diseñador de informes.
2.  Haga clic en **Archivo** &gt; **Nuevo** &gt; **Definición del organigrama**.
3.  Haga clic en **Editar** &gt; **Insertar unidades organizacionales de dimensiones**.
4.  En el cuadro de diálogo **Insertar unidades de notificaciones de dimensiones**, active la casilla para cada dimensión que desee incluir en la definición del organigrama. El cuadro de diálogo **Insertar unidades de notificaciones de dimensiones** contiene las siguientes secciones.

    | Sección                          | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
    |----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | Segmentación de la dimensión de los informes | Utilice los botones **Dividir segmentos** y **Combinar segmentos** para cambiar el número y la longitud de los segmentos. **Nota:** Solo puede combinar los segmentos que ha dividido. Para combinar varias dimensiones, use los caracteres comodín en sus valores de dimensión.                                                                                                                                                                                                          |
    | Incluir/posición de carácter       | En esta sección se muestran las dimensiones que se definen en los datos financieros y muestra el número de caracteres del valor más largo que se define para cada dimensión. Active la casilla para una dimensión para incluir esa dimensión en la jerarquía del organigrama.                                                                                                                                                                                           |
    | Jerarquía e intervalos de segmentación     | En esta sección se muestra la jerarquía de la dimensión. Puede mover las dimensiones en la lista para cambiar el orden de las notificaciones. En los cuadros **Desde la dimensión** y **Hasta la dimensión**, puede especificar un intervalo de valores en cada dimensión. Si no se especifica un intervalo, se insertan todos los valores de dimensión en el organigrama. **Nota:** Si utiliza más de una dimensión, solo se devuelven en los resultados combinaciones de dimensiones que se han registrado. |

    Para una captura de pantalla que muestre un ejemplo del cuadro de diálogo **Insertar unidades de informe de dimensiones**, consulte la sección "Ejemplo del cuadro de diálogo Insertar las unidades de informe de dimensiones" más adelante en este artículo.
5.  Para crear segmentos adicionales (por ejemplo, como la división de un segmento en dos segmentos más cortos), haga clic en la ubicación correcta en un campo de **Posición del carácter**, y luego haga clic en **Dividir segmentos**.
6.  Para combinar dos segmentos en un segmento, haga clic en cualquiera de los cuadros de segmento para combinar y, a continuación, en **Combinar segmentos**.
7.  La jerarquía define cómo las dimensiones se notifican unas a otras y el intervalo para cada dimensión. Para modificar la jerarquía de las dimensiones en el área **Jerarquía y intervalos de segmentos**, seleccione la dimensión que desee mover y, a continuación, haga clic en **Mover hacia arriba** o **Mover hacia abajo**.
8.  Para especificar un intervalo de valores de dimensión para agregar al organigrama, en el área **Jerarquía e intervalos de segmentos**, siga estos pasos:
    1.  En el campo **Desde la dimensión** para esa dimensión, escriba el primer valor del intervalo.
    2.  En el campo **Hasta la dimensión**, escriba el último valor del rango.

9.  Repita los pasos del 7 al 8 para cada dimensión en el área **Jerarquía y intervalos de segmento**.
10. Una vez que haya terminado de definir cómo se deben traer las unidades organizacionales al nuevo organigrama, haga clic en **Aceptar**.
11. Haga clic en **Archivo** &gt; **Guardar** para guardar el organigrama. Escriba un nombre exclusivo y una descripción para el organigrama y, a continuación, haga clic en **Aceptar**.

### <a name="open-an-existing-reporting-tree-definition"></a>Abra una definición existente del organigrama

1.  En el diseñador de informes, haga clic en **Definiciones de organigramas** en el panel de navegación.
2.  Haga doble clic en un nombre en el organigrama para abrirlo.
3.  Para ver los bloques de creación asociados con la definición del organigrama, haga clic con el botón secundario en la definición del organigrama y seleccione **Asociaciones**.

### <a name="roll-up-data-in-a-reporting-tree"></a>Distribuir los datos en un organigrama

Al usar un organigrama, puede agregar importes desde unidades organizacionales secundarias en el nivel de la unidad organizacional principal. Esta agregación se conoce como distribución de los datos. Se usan las reglas siguientes para distribuir importes en las unidades principales de un organigrama:

-   En un organigrama, las unidades secundarias deben contener dimensiones, a menos que sea el organigrama sea de nivel único. Las unidades principales no contienen normalmente dimensiones en un organigrama. **Nota:** Si especifica las dimensiones para las unidades tanto secundarias como principales, puede provocar la duplicación de datos en el informe.
-   Las unidades de notificación que contienen dimensiones en el organigrama se corresponden con las dimensiones que se usan en las definiciones de fila y de columna. La combinación de dimensiones determina los importes que se devuelven para esa unidad. Por ejemplo, en el ejemplo 2 que aparece más adelante en este artículo, las líneas 6 y 7 devuelven solo valores para los departamento 00 y 01, respectivamente.
-   Los importes para las unidades organizacionales principales que no contienen dimensiones en el organigrama se determinan desde el informe de la unidad secundaria y se distribuye el importe en la unidad principal especificada. Por ejemplo, si la unidad principal (consulte Contoso EE. UU. en el ejemplo 2 de los ejemplos de distribución de datos) tiene dos unidades secundarias (022 y 023) y no contiene dimensiones, se genera un informe para la unidad secundaria y la principal. El total principal es la suma de los dos importes secundarios.

### <a name="manage-reporting-units"></a>Gestionar unidades de notificación

Cada definición de organigrama se muestra en vistas únicas. Hay una vista gráfica para que muestra la jerarquía principal o secundaria y una vista de la hoja de cálculo que muestra información específica para cada unidad organizacional. La vista gráfica y la vista de la hoja de cálculo están vinculadas. Cuando selecciona una unidad organizacional en una visualización, también se selecciona en la otra visualización. Puede crear jerarquías entre dimensiones que se basan en las relaciones dimensionales de los datos financieros. Cuando crea una definición del organigrama, puede usar las mismas definiciones de filas varias veces, con independencia de si va a generar un extracto de ingresos de un departamento como un extracto de resumen de ingresos consolidado. Las dimensiones que se definen en la definición de filas se pueden combinar con dimensiones en la definición del organigrama para proporcionar varias visualizaciones del rendimiento de su organización.

### <a name="reporting-unit-structure"></a> Estructura de la unidad de notificación

Se usan los siguientes tipos de unidades organizacionales en los informes financieros:

-   Una unidad detallada recaba información directamente de los datos financieros, de una hoja de cálculo de Excel o de otra hoja de cálculo de informes financieros.
-   Una unidad de resumen resume datos de las unidades de nivel inferior.

Una unidad de notificación principal es una unidad de resumen que agrega información resumida de una unidad de detalle. Una unidad de resumen puede ser tanto una unidad de detalle y una unidad de resumen. Por tanto, una unidad de resumen recabar la información de una unidad de nivel inferior, de los datos financieros o de una hoja de cálculo de Excel. Una unidad principal puede ser la unidad secundaria de una unidad de nivel superior principal. Una unidad organizacional secundaria puede ser una unidad de detalle que tira información directamente de los datos financieros o de una hoja de cálculo Excel. Una unidad organizacional secundaria también puede ser una unidad de resumen intermedia. En otras palabras, puede ser la unidad principal de una unidad de nivel inferior y también la unidad secundaria de una unidad de resumen de nivel superior. En la situación más común de las unidades organizacionales, las unidades principales tienen una celda en blanco en la columna **Dimensiones** y las unidades secundarias tienen vínculos a combinaciones de dimensiones específicas o de comodín.

### <a name="organize-reporting-units"></a> Organizar unidades de notificación

Puede cambiar la estructura de organización de un organigrama moviendo las unidades de notificación en la visualización gráfica. También puede promover las unidades organizacionales a un nivel superior en el organigrama y bajarlas a un nivel inferior.

1.  En el diseñador de informes, abra la definición del organigrama para modificarla.
2.  En la vista gráfica de la definición del organigrama, seleccione una unidad de notificación.
3.  Arrastre la unidad a una nueva posición. De forma alternativa, haga clic con el botón secundario en la unidad y, a continuación, seleccione **Aumentar nivel de la unidad organizacional** o **Disminuir nivel de la unidad organizacional**.
4.  Haga clic en **Archivo** &gt; **Guardar** para guardar los cambios.

### <a name="add-text-about-a-reporting-unit"></a> Agregar texto sobre una unidad de notificación

Una entrada de texto adicional es una cadena de texto estática de hasta 255 caracteres, que agrega información en la definición del organigrama. Por ejemplo, el texto adicional puede ser una descripción breve de la compañía. Puede crear hasta diez entradas de texto adicionales para cada unidad de notificación en una definición del organigrama. El texto adicional aparece en el informe para la unidad organizacional a la que se asigna el texto. Puede agregar entradas de texto de la columna **Descripción** de la definición de filas y de la pestaña **Encabezados y pies de página** en la definición del informe.

1.  En el diseñador de informes, abra la definición del organigrama para modificarla.
2.  Haga doble clic en la celda de **Texto adicional** para la fila de la unidad organizacional.
3.  En el cuadro de texto **Texto adicional**, en la primera fila vacía, escriba el texto. La primera fila que contiene texto aparece como UnitText1, independientemente de su posición en el cuadro de diálogo de **Texto adicional**.
4.  Para agregar más entradas de texto para esta unidad de notificación, escriba el texto en una fila vacía.
5.  Haga clic en **Aceptar**.

### <a name="remove-additional-text-from-a-reporting-unit"></a>Quitar el texto adicional de una unidad de notificación

1.  En el Diseñador de informes, abra la definición de organigrama que desee modificar.
2.  Haga doble clic en la celda **Texto adicional** de la fila de la unidad organizacional.
3.  En el cuadro de diálogo **Texto adicional**, seleccione la entrada que quiere quitar y, a continuación, haga clic en **Borrar**. De forma alternativa, haga clic con el botón secundario en la entrada y, a continuación, seleccione **Cortar**.
4.  Haga clic en **Aceptar**.

### <a name="restrict-access-to-a-reporting-unit"></a>Restringir el acceso a una unidad de notificación

Puede evitar que determinados usuarios y grupos tengan acceso a una unidad de notificación. También puede definir restricciones para que se aplique a unidades organizacionales secundarias de la unidad organizacional.

1.  En el diseñador de informes, abra la definición del organigrama para modificarla.
2.  Haga doble clic en la celda **Seguridad de unidad** de la fila de la unidad organizacional de la que desee restringir el acceso.
3.  En el cuadro de diálogo **Seguridad de la unidad**, haga clic en **Usuarios y grupos**.
4.  Seleccione los usuarios o grupos que deberían tener acceso a la unidad organizacional y, a continuación, haga clic en **Aceptar**.
5.  Para restringir el acceso a unidades de notificación secundarias, active la casilla **Agregar seguridad a unidades organizacionales secundarias**.
6.  Haga clic en **Aceptar**.

### <a name="remove-access-to-a-reporting-unit"></a>Quitar acceso a una unidad de notificación

1.  En el diseñador de informes, abra la definición del organigrama para modificarla.
2.  Haga doble clic en la celda **Seguridad de la unidad** para la fila de unidad organizacional a la que quitar acceso.
3.  En el cuadro de diálogo **Seguridad de la unidad**, seleccione un nombre y haga clic en **Quitar**.
4.  Haga clic en **Aceptar**.

### <a name="link-to-reports"></a>Vínculo para informes

Una vez que haya creado una columna **informe** en la definición de filas y haya especificado el informe que desee incluir en el informe, debe actualizar el organigrama con la columna vinculada y la información acerca del informe. Un informe se puede importar en cualquier unidad del organigrama.

### <a name="identify-the-report-in-a-reporting-tree"></a>Identificar el informe en un organigrama

1.  En el diseñador de informes, abra la definición del organigrama para modificarla.
2.  En la columna **Definiciones de filas**, la información de las celdas se basa en la información para la fila seleccionada, porque la misma definición de la fila se debe usar en todas las unidades del organigrama. Haga doble clic en la celda **Definiciones de filas** y seleccione la definición de fila que contiene información acerca del informe.
3.  En la celda **Vínculo de la hoja de cálculo** para una unidad organizacional, seleccione el nombre del vínculo que corresponde al informe.
4.  En la celda **Ruta del informe o del libro** para la unidad de notificación, escriba el nombre del informe o explore para seleccionar el informe.
5.  Para especificar una hoja de cálculo en un informe, escriba el nombre de la hoja de cálculo en la celda **Nombre de a hoja de cálculo**.
6.  Repita los pasos 3 a 5 para cada unidad organizacional que debería recibir datos de un informe. Para evitar que los datos incorrectos aparezcan en su informe, asegúrese de que los nombres correctos del informe aparecen en la unidad correspondiente del organigrama.

## <a name="examples"></a>Ejemplo
### <a name="reporting-unit-structure--example-1"></a>Estructura de la unidad organizacional – Ejemplo 1

Consulte la estructura de las unidades organizacionales en el siguiente organigrama:

-   La unidad organizacional de Contoso Japón es una unidad principal de las unidades secundarias de Contoso Japón Ventas y Contoso Japón Consultoría.
-   La unidad de la división de Contoso Japón Ventas es una unidad secundaria de la unidad de Contoso Japón Ventas y una unidad principal de las unidades de ventas para el hogar y de automóviles.
-   Las unidades de notificación de detalle más bajo (ventas para el hogar, ventas de automóviles, servicios al cliente y operaciones) representan departamentos en los datos financieros. Estas unidades de notificación se encuentran en el área sombreada del diagrama.
-   Las unidades de resumen de alto nivel resumen la información de las unidades de detalle.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Estructura de la unidad organizacional – Ejemplo 2

En el diagrama siguiente, el organigrama tiene una estructura de organización que está dividida por la función de negocio. [![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Ejemplo del cuadro de diálogo Insertar unidades organizacionales de dimensiones

En la siguiente ilustración se muestra un ejemplo del cuadro de diálogo **Insertar unidades de notificaciones de dimensiones**. Para este ejemplo, los resultados devolverán la combinación de unidades de negocio, centros de costes y departamentos. [![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png) La definición del organigrama resultante se clasifica por unidad de negocio, a continuación, por centro de coste y, por último, por departamento. La dimensión para la quinta unidad organizacional es **Unidad de negocio = \[001\], Centro de coste =\[\], Departamento = \[022\]** e identifica una unidad organizacional para las cuentas que son específicas de la unidad de negocio 001 y el departamento 022. [![ReportingTree](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Ejemplos de distribución de datos

Los ejemplos siguientes muestran información que se puede usar en una definición del organigrama para los datos que se distribuyen.

#### <a name="example-1"></a>Ejemplo 1

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>Ejemplo 2

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

# <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)




