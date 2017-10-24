---
title: "Definiciones de filas en el diseñador de informes financieros"
description: "Una definición de fila es un componente de informe, o bloque de creación, que especifica el contenido de cada fila de un informe financiero. Una definición de fila se puede combinar con las definiciones de columnas, definiciones de organigramas y definiciones de informes para crear un grupo de bloques de creación que puedan usar varias empresas."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 06a75889e62cbba6e47a8543cf663868df5ae2e3
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="row-definitions-in-financial-report-designer"></a>Definiciones de filas en el diseñador de informes financieros

[!include[banner](../includes/banner.md)]


Una definición de fila es un componente de informe, o bloque de creación, que especifica el contenido de cada fila de un informe financiero. Una definición de fila se puede combinar con las definiciones de columnas, definiciones de organigramas y definiciones de informes para crear un grupo de bloques de creación que puedan usar varias empresas.

<a name="create-a-row-definition"></a>Crear una definición de fila
-----------------------

1.  En el diseñador de informes, en el panel de navegación, haga clic en **Definiciones de las filas**.
2.  En el menú **Archivo**, haga clic en **Nueva** y, a continuación, haga clic en **Definición de filas**. Para obtener más información sobre el contenido de cada celda, vea [Modificar las celdas de la definición de filas](modify-row-definition-cells-financial-reporting.md).

## <a name="open-a-row-definition"></a>Abrir una definición de fila
1.  En el diseñador de informes, en el panel de navegación, haga clic en **Definiciones de las filas**.
2.  Haga doble clic en el nombre de la definición de la fila para abrirla.
3.  Para ver los bloques de creación asociados con la definición de filas, haga clic con el botón secundario en la definición de filas y seleccione **Asociaciones**.

## <a name="contents-of-a-row-definition"></a> Contenido de una definición de filas
Una definición de fila puede contener hasta 20.000 filas de la dimensión financiera e incluir la siguiente información:

-   Texto descriptivo que agrega significado al informe creando títulos de sección, líneas y espacios, como **Efectivo** o **Ingresos totales**
-   Vínculos a los datos financieros, que pueden incluir valores de dimensión en Microsoft Dynamics 365 for Finance and Operations **Nota:** Puede configurar una definición de filas para extraer datos del sistema de dimensiones financieras cada vez que se genera el informe.
-   Los totales de filas y las fórmulas que se basan en los datos financieros vinculados

Normalmente, cada fila en una definición de fila contiene uno de los siguientes tipos de información:

-   Referencias al sistema de las dimensiones financieras
-   Totales o cálculos que se basan en los datos
-   Formato

Hay dos métodos para escribir información en una definición de fila:

-   Especifique manualmente la información de fila en una nueva definición de fila. Para obtener más información, consulte [Modificar las celdas de la definición de filas](modify-row-definition-cells-financial-reporting.md).
-   Utilice el diseñador de informes para extraer información de la fila directamente de las dimensiones financieras. Para obtener más información, consulte la sección "Fórmulas/filas/unidades relacionadas" en [Modificar las celdas de la definición de filas](modify-row-definition-cells-financial-reporting.md).

## <a name="add-dimensions-in-a-row-definition"></a> Agregar dimensiones en una definición de filas
Una dimensión es una intersección de datos y de valores. Puede agrupar datos y valores en el diseñador de informes. A continuación, puede clasificar y analizar transacciones con más detalle. Puede usar el cuadro de diálogo **Insertar filas desde dimensiones** para agregar varias filas a una definición de fila al mismo tiempo. El cuadro de diálogo muestra una columna para cada dimensión. En la tabla siguiente se describe la información que puede especificar para cada dimensión.

| Opción                | Descripción                                                                                                                                                                                                                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dimensión             | El modelo que identifica la dimensión que se agrega a la definición de filas. Este modelo contiene una Y comercial (&) o el signo de número (\#) para cada puesto de las dimensiones. Normalmente, use todos los signos & para la dimensión de la cuenta principal y todos los signos de número para otras dimensiones. |
| Inicio de intervalo de dimensión | El primer valor de esta dimensión que se va a agregar a la definición de fila.                                                                                                                                                                                                                 |
| Fin de intervalo de dimensión   | El último valor que agregará esta dimensión a la definición de filas.                                                                                                                                                                                                                  |

Para agregar dimensiones a una definición de fila, siga estos pasos.

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  En el menú **Editar** , haga clic en **Insertar filas de dimensiones**.
3.  En el cuadro de diálogo **Insertar filas desde dimensiones**, en la fila **Dimensiones**, seleccione la celda en la que la dimensión se transferirá a la definición de filas y, a continuación, haga clic en **Todas &&&**.
4.  Para limitar la definición de filas a un intervalo específico de valores de dimensión, especifique el valor de dimensión de inicio en la celda **Inicio del intervalo de la dimensión** y después especifique el valor de dimensión final en la celda **Fin del intervalo de la dimensión**. Para incluir todos los valores de la dimensión seleccionada, deje estas celdas vacías. **Nota:** los caracteres comodín (\* o ?) en los intervalos de la dimensión pueden no devolver todos los resultados que desea, en función de cómo la base de datos ERP intercala los datos.
5.  En el campo **Código de la fila de inicio**, especifique el código de la fila del primer valor de dimensión que se agregará a la definición de filas.
6.  En el campo **Incrementar cada fila en**, especifique el hueco entre los códigos de fila consecutivas. Por ejemplo, si el código de la primera fila es 100 y el valor de incremento es 30, las primeras nuevas filas tienen los códigos 100, 130, 160, 190 y 220. Use un valor de incremento que proporcione espacio para insertar nuevas filas de formato y de fórmula.
7.  Haga clic en **Aceptar**. Para cada uno de los valores de dimensión seleccionados, se agrega una línea a la definición de filas.

## <a name="adjust-rounding-in-a-row-definition"></a> Ajuste de redondeo en una definición de filas
Si tiene un balance de situación donde se redondean los importes, los totales pueden estar desequilibrados. Este problema puede producirse si, por ejemplo, utiliza la opción de redondeo en un informe de balance de situación y la definición del informe también especifica el redondeo. Puede utilizar la opción **Ajuste de redondeo** en la definición de filas para equilibrar los importes de los balances de situación. Puede desactivar el redondeo o modificarlo en la pestaña **Configuración** de la definición del informe. En la siguiente tabla se muestra cómo se redondean los importes. En esta tabla, los totales de las filas 100 y 200 difieren cuando se activa el redondeo.

| Código de la fila | Importes sin redondeo | Importe con redondeo a millares enteros |
|----------|--------------------------|-----------------------------------------|
| 100      | 3,600                    | 4                                       |
| 200      | 3,700                    | 4                                       |
| Total    | 7,300                    | 8                                       |

Para ajustar el redondeo en un balance de situación, siga estos pasos.

1.  En el diseñador del informes, haga clic en **Definiciones de filas** y después abra la definición de fila para modificarla.
2.  En el menú **Editar**, haga clic en **Ajuste de redondeo**.
3.  En el cuadro **Ajustes de redondeo**, especifique los siguientes valores:
    -   **Fila de ajuste de redondeo:** el código de fila para la fila que se debe ajustar para equilibrar el balance de situación.
    -   **Fila de activos totales:** el código de fila para la fila en el balance de situación que contiene los activos totales.
    -   **Fila de pasivos totales:** el código de fila para la fila en el balance de situación que contiene los pasivos totales.
    -   **Límite de ajuste del importe**: un número entero positivo que especifica el límite en ajustes automáticos. Este importe se compara con el valor absoluto de diferencias de redondeo real.

    **Nota:** estos códigos de fila se deben vincular a los datos financieros. Es decir, la fila debe tener un valor de dimensión en la celda **Vincular a dimensiones financieras**. No **haga** referenceia a una fila de descripción (**DESC**), calculada (**CALC**) o de totales (**TOT**).

Los importes en el balance de situación se equilibrarán ahora cuando se activa el redondeo. **Nota:** el límite de ajuste se aplica según la opción **Precisión del redondeo** que se especifica para la definición del informe. Por ejemplo, si redondea el informe en millares y especifica **2** en el cuadro **Límite del ajuste de importe**, recibirá un mensaje de advertencia cuando el valor del campo **Fila de ajuste de redondeo** aumenta o disminuye por más de 2.000.

## <a name="format-row-and-column-text"></a>Dar formato al texto de la columna y la fila
Puede personalizar el aspecto de sus informes cambiando fuentes y dando formato al texto. En las secciones siguientes se explica cómo dar formato al aspecto de filas y columnas en los informes.

### <a name="manage-font-styles"></a>Gestionar estilos de fuentes

Puede crear y modificar estilos de fuente para el informe. A continuación, puede aplicar esos estilos al documento o a una fila o columna concreta de un informe.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Crear un estilo de fuente</td>
<td><ol>
<li>En el diseñador de informes, en el menú <strong>Formato </strong>, haga clic en <strong>Estilos y formato</strong>.</li>
<li>En el cuadro de diálogo <strong>Estilos y formato</strong>, haga clic en <strong>Nuevo</strong> y especifique un nombre único para el estilo nuevo.</li>
<li>Seleccione las fuentes y haga clic en <strong>Aceptar</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Modificar un estilo de fuente</td>
<td><ol>
<li>En el diseñador de informes, en el menú <strong>Formato </strong>, haga clic en <strong>Estilos y formato</strong>.</li>
<li>En el cuadro de diálogo <strong>Estilos y formato</strong>, seleccione un estilo para modificar y haga clic en <strong>Modificar</strong>.</li>
<li>Seleccione las fuentes y haga clic en <strong>Aceptar</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Aplicar un estilo de fuente</td>
<td><ol>
<li>En el diseñador de informes, e una definición o definición de columna, o en encabezados y pies de página, seleccione una o más celdas.</li>
<li>En la lista <strong>Estilo</strong> de la barra de herramientas, seleccione un estilo de fuente.</li>
</ol></td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a>Dar formato al texto de la fila

El formato que se especifica en la definición de la fila anula el formato que se especifica en la definición de la columna y la definición del informe. Puede modificar el formato de texto mediante los controles de la barra de herramientas de formato. Estos controles son controles estándar de Microsoft Windows.

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  Seleccione las celdas a las que desea dar formato. Para seleccionar varias celdas, mantenga presionada la tecla Ctrl mientras selecciona la celda.
3.  Haga clic en el botón de la barra de herramientas del formato que desea aplicar. Por ejemplo, para aplicar sangría a una fila, seleccione la fila y luego haga clic en **Aumentar sangría** ![Aumentar sangría](https://i-technet.sec.s-msft.com/dynimg/IC679497.gif "Aumentar sangría") en la barra de herramientas.

### <a name="adjust-columns-while-you-design-reports"></a>Ajustar columnas mientras se diseñan informes

Para facilitar ver las columnas en las que está trabajando en la definición de filas, puede ajustar la anchura de una columna y ocultar además (minimizar) o mostrar columnas en el panel de vista. Las modificaciones que realice afectan solo al aspecto en pantalla de las columnas. No afectan al formato de las columnas en los informes.

### <a name="change-the-width-of-a-column-in-the-view-pane"></a>Cambiar la anchura de una columna en el panel de vista

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  En el menú **Formato**, seleccione **Anchura de columna**.
3.  En el cuadro de diálogo **Ancho de columna**, escriba un valor y, a continuación, haga clic en **Aceptar**. De forma alternativa, también puede arrastrar el límite derecho de una celda del encabezado de columna para cambiar el ancho de la columna.

### <a name="hide-columns-in-the-view-pane"></a>Ocultar columnas en el panel de vista

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  Seleccione las columnas que desea minimizar.
3.  Haga clic con el botón secundario y, a continuación, haga clic en **Ocultar**.

### <a name="show-all-hidden-columns-in-the-view-pane"></a>Mostrar todas las columnas ocultas en el panel de vista

1.  En el diseñador de informes, abra la definición de filas para modificarla.
2.  Haga clic con el botón secundario en la columna minimizada que desee mostrar y, a continuación, haga clic en **No ocultar**.


<a name="see-also"></a>Consulte también
--------

[Informes financieros](financial-reporting-intro.md)




