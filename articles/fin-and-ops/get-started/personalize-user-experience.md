---
title: Personalizar la experiencia del usuario
description: "Este tema explica cómo puede personalizar Microsoft Dynamics 365 for Finance and Operations."
author: TLeforMicrosoft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7a828090fa34eb96d2b557eb06e48ad05b421ae8
ms.openlocfilehash: 3d969069dd5f447b449df84b097527d3814aa338
ms.contentlocale: es-es
ms.lasthandoff: 11/20/2017

---

# <a name="personalize-the-user-experience"></a>Personalizar la experiencia del usuario

[!INCLUDE [banner](../includes/banner.md)]

Este tema explica cómo puede personalizar Microsoft Dynamics 365 for Finance and Operations.

Hay muchos tipos de personalizaciones en Dynamics 365 for Finance and Operations. Algunas personalizaciones son las selecciones realizadas en una lista de opciones en una página de configuración. Algunas personalizaciones están predeterminadas, por ejemplo, Finance and Operations mantiene el ancho de las columnas de cuadrícula si las ajusta, y el estado de expandido/contraído de las Fichas desplegables. Otras personalizaciones son explícitas. Para las personalizaciones explícitas, tiene que especificar un modo interactivo de personalización y modificar el aspecto de una página gestionando directamente la forma en que los elementos aparecen o se comportan en la página. 

Todas las personalizaciones, de cualquier tipo, que un usuario haga en Finance and Operations son solo para dicho usuario, independientemente de la empresa con la que el usuario interactúa. Los cambios que un usuario hace a una página no afecta a otros usuarios en el sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opciones de sistema válidas para el usuario actual
En la barra de exploración se encontrará una imagen de engranaje que es el botón de menú **Configuración**. Al abrir el menú **Configuración** se mostrarán varias opciones. La selección de **Opciones** abrirá la página **Opciones** del usuario. Allí encontrará cuatro pestañas de opción: 

-   **Visual:** - Uee para elegir color de tema y el tamaño predeterminado de los elementos en las páginas.
-   **Preferencias:** - Aquí puede elegir los valores predeterminados para cada vez que abra Finance and Operations, incluida la empresa, página de inicio y modo de vista o edición predeterminados (que determina si una página está bloqueada para su visualización o se abre para editar cada vez que la abre). También encontrará idioma, zona horaria y las opciones de formato de fecha, hora y número. Por último, esta página contiene varias preferencias distintas que varían según el lanzamiento.
-   **Cuenta:** - Use para proporcionar el id. de usuario y otras opciones relacionadas con la cuenta.
-   **Flujo de trabajo:**- Aquí puede elegir opciones relacionadas con el flujo de trabajo.

## <a name="implicit-personalizations"></a>Personalizaciones implícitas
Las personalizaciones implícitas son las personalizaciones que realiza simplemente interactuando con determinados controles que recuerden su estado visible actual. 

- **Columnas de cuadrícula:** - Puede ajustar el ancho de una columna en una lista seleccionando la barra de tamaño a la izquierda o la derecha del encabezado de la columna y desplazándola hacia la izquierda o hacia la derecha hasta la anchura deseada. Finance and Operations almacenará la anchura que se le gustaría y mostrará esa columna con esa anchura cada vez que se abra la página con esa lista. 

- **Fichas Desplegables**: algunas páginas tienen secciones extensibles llamadas *Fichas Desplegables*. Finance and Operations guardará las Fichas Desplegables que ha expandido y las que ha contraído. Cada vez que vuelve a la página, esas mismas Fichas Desplegables se ampliarán o se contraerán según como las usó la última vez. En este artículo, explicaremos cómo cambiar el orden de las secciones de la ficah desplegable. En algunos casos, contraer una ficha Desplegable puede mejorar el rendimiento porque Finance and Operations no necesitará recuperar información para dicha ficha Desplegable hasta que se extienda la ficha Desplegable. 

- **Cuadros informativos**: algunas páginas tienen una sección llamada panel de *cuadro informativo*. Este panel contiene información solo de lectura relacionada con el tema actual de la página. Cada sección en el panel del cuadro informativo se denomina cuadro informativo. Puede expandir o contraer un cuadro informativo y Finance and Operations guardará su preferencia. En algunos casos, contraer un cuadro informativo puede mejorar el rendimiento porque Finance and Operations no necesitará recuperar la información para ese cuadro informativo hasta que se expanda el cuadro informativo.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personalizaciones explícitas que usan la barra de herramientas de personalización
Cada persona y empresa tiene una perspectiva distinta sobre qué datos son los más importantes para ellos o qué datos no son necesarios para llevar su negocio. La capacidad de adaptar la manera en que se pide su información, se interactúa con ella o se oculta es esencial para que Finance and Operations se convierta en una experiencia personal y productiva. 

Las personalizaciones explícitas son aquellas personalizaciones que se realizan explícitamente con la intención de cambiar el aspecto o el comportamiento de un elemento o de una página, seleccionando un menú de personalización. El tipo más básico de personalización explícita es cuando se hace clic con el botón secundario en un elemento y se selecciona **Personalizar**. (Tenga en cuenta que no todos los elementos en su página se pueden personalizar.) Si selecciona este método de personalización, verá la ventana de la propiedad del elemento. 

[![Personalización de las propiedades de un elemento](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg) 

Personalizará un elemento en la página de esta manera si desea simplemente cambiar la etiqueta del elemento, ocultar el elemento para que no aparezca en la página (esto no cambia ningún dato, simplemente no muestra la información), incluir la información de la sección de resumen de la ficha desplegable (si el elemento no se encuentra en una ficha Desplegable), omitir el campo al tabular o hacer que los datos no se puedan cambiar marcándolo como “No editar”. 

Cuando desee mover u ocultar elementos o realizar varios cambios, puede usar la barra de herramientas de personalización, disponible en la ventana de propiedad de los elementos seleccionando **Personalizar este formulario**. La barra de herramientas de personalización también está disponible en el panel de acciones del formulario, en el grupo de **personalización** de la pestaña **Opciones**. Seleccione **Personalizar este formulario** y verá la barra de herramientas de personalización. 

[![Barra de herramientas de la personalización](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

La barra de herramientas de personalización tiene varias acciones para la personalización. 

- Elija la herramienta **Seleccionar** si desea seleccionar y cambiar las propiedades de muchos elementos, de uno en uno. Primero, haga clic en la herramienta Seleccionar y, a continuación, haga clic en el elemento cuyas propiedades desea modificar. Cuando selecciona un elemento, la ventana de la propiedad del elemento se abrirá y podrá modificar las propiedades para dicho elemento. Es posible repetir el proceso para otros elementos en el formulario que sean personalizables. En algunos casos, seleccionará un elemento y verá que algunas de las propiedades no son modificables. Esto significa que según la forma en que se usa el elemento actual, Finance and Operations no puede permitirle cambiar dicha propiedad. Por ejemplo, no puede ocultar un campo que se necesario. 

- Elija la herramienta **Mover** si desea seleccionar y mover un elemento a otra ubicación dentro del grupo actual de elementos. (No puede mover un elemento fuera del grupo principal). Primero, haga clic en la herramienta Mover y, a continuación, haga clic en el elemento que desea mover. Al hacer clic en el elemento que desee mover, Finance and Operations explorará el formulario para determinar a dónde se puede mover este elemento y crear una serie de “áreas de colocación” que se muestran como una línea coloreada y en negrita, junto al área donde se puede colocar el elemento cuando se desplaza el elemento dentro del grupo actual. 

- Elija la herramienta **Ocultar** para seleccionar y ocultar un elemento. Para ocultar un elemento, elija simplemente la herramienta Ocultar y haga clic en el elemento que desea ocultar. Cuando elija la herramienta Ocultar, todos los elementos actualmente ocultos se harán visibles y se mostrarán en un contenedor sombreado de manera que pueda elegir el elemento para mostrarlo. 

- Elija la herramienta **Seleccionar** para ver qué aspecto tendrá la página con los elementos seleccionados ocultos. 

- Elija la herramienta **Resumen** cuándo desea que un campo numérico o de cadena se muestra en el área de resumen de la ficha desplegable. La herramienta Resumen se aplicará solo a los campos que están dentro de una sección de la ficha desplegable. Cuando elija la herramienta de resumen, Finance and Operations mostrará todos los campos que hayan sido seleccionados como campos de resumen incluyéndolos en un contenedor sombreado. Puede agregar y eliminar de forma interactiva campos de un resumen de ficha desplegable si hace clic en el campo. 

- Elija la herramienta **Omitir** para quitar un elemento de la secuencia del tabulador del teclado de la página. Cuando elija la herramienta Omitir, todos los elementos actualmente omitidos se mostrarán en un contenedor sombreado de manera que pueda elegirlos nuevo para hacerlos parte de la secuencia de tabulación seleccionando u omitiendo un elemento. 

- Elija la herramienta **Editar** cuando desee marcar un elemento como *editable* o *no es editable*. Cuando elija la herramienta Editar, todos los elementos actualmente no editables se harán visibles y se mostrarán en un contenedor sombreado de manera que pueda elegirlos para hacerlos editables. Tenga en cuenta que algunos campos son necesarios y no se pueden editar. Dichos campos aparecerán con un icono de candado junto a ellos. 

- Elija la herramienta **Agregar** para agregar un campo en la página. Con la herramienta Agregar, no puede crear un nuevo campo, pero puede agregar los campos que forman parte de la definición de la página actual, pero que no se muestran en la página. Cuando elija la herramienta Agregar, primero deberá seleccionar el grupo o el área en el que desea agregar un campo. Un cuadro de diálogo mostrará la lista de campos relacionados a la sección que ha seleccionado. En ese cuadro de diálogo, puede seleccionar uno o más campos para agregar y hacer clic en **Insertar**. Si después desea elimina un campo que ha agregado anteriormente, repita el proceso, pero simplemente desactive el campo que ha agregado anteriormente. 

- Elija el botón **Administrar** para ver una lista de las opciones de administración relacionadas con todas las personalizaciones de la página actual. 

- Elija **Desactivar** para restablecer la página a su valor predeterminado, estado instalado. Todas las personalizaciones en la página actual se desactivarán. No existe la acción de deshacer, de modo que use esta opción solo cuando está seguro que desea restablecer la página. 

- Elija **Importación** para usar una personalización de un archivo de la personalización que usted o otro usuario creó anteriormente para esta página. La importación de una personalización desactivará cualquier personalización que haya realizado en la página completa y use todas las personalizaciones del archivo seleccionado. Si desea guardar o compartir una personalización, seleccionará la opción **Exportar** para guardar las personalizaciones a un archivo. 

- Elija el botón **Cerrar** para cerrar la barra de herramientas y devolver la página a su anterior estado interactivo. 

Con la barra de herramientas de la personalización, guardar es implícito. Sus personalizaciones surtirán efecto inmediatamente a medida que las hace y no hay necesidad de hacer clic en el botón **Guardar**. En algunos casos, verá un icono de candado junto a un elemento cuando selecciona una herramienta. Esto quiere decir que para que la página funcione correctamente, no puede modificar las propiedades relacionadas con la herramienta seleccionada. Cuando se abre la barra de herramientas de la personalización, la página pasará a ser no interactiva. No puede escribir datos o expandir y contraer secciones.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personalización explícita: agregar un mosaico o lista a un espacio de trabajo
Algunas páginas con listas tendrán una característica adicional de personalización disponible dentro del panel de acciones, en el grupo de **personalización** de la pestaña **Opciones**. Seleccione **Agregar al área de trabajo** para abrir la lista desplegable que le proporcionará la capacidad de mostrar información en la lista actual (filtrada y clasificada o predeterminada) en un área de trabajo, como una lista o icono de resumen (que se puede usar para mostrar el número de artículos en la lista). 

[![Agregar al espacio de trabajo](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Para agregar una lista a un espacio de trabajo, primero clasifique o filtre la lista con la información como desee verla en el espacio de trabajo, después seleccione el cuadro de diálogo **Agregar a espacio de trabajo**. A continuación, seleccione el espacio de trabajo deseado y seleccione **Lista** en la lista desplegable de **Presentación**. Cuando seleccione **Lista** un cuadro de diálogo se abrirá y le permitirá seleccionar las columnas que desea ver en la lista y la etiqueta para la lista tal y como aparecerá en el espacio de trabajo. 

Para agregar un mosaico a un espacio de trabajo, primero debe filtrar la lista para representar los datos que quiere resumir (o a los que quiere tener acceso rápido). Luego, abra el menú del cuadro de diálogo desplegable **Agregar a espacio de trabajo**. A continuación, seleccione el espacio de trabajo deseado y seleccione **Mosaico** en el menú desplegable **Presentación**. Cuando seleccione **Mosaico**, un cuadro de diálogo se abrirá permitiendo que proporcione una etiqueta de mosaico y que decida si el mosaico mostrará un recuento. Cuando se pone en un espacio de trabajo, el mosaico le permitirá abrir la página actual del espacio de trabajo y mostrar la lista de información relacionada con el mosaico. 

Cuando la lista o mosico se agrega a un espacio de trabajo, puede elegir abrir el espacio de trabajo y reordenar la lista o el mosaico dentro del grupo en que se ha colocado.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personalización explícita: Agreagar un resumen de un espacio de trabajo a un panel de información
Algunos espacios de trabajo contienen los mosaicos de la cuenta (mosaicos con números en ellos) que también quisiera ver en el panel de información. En un espacio de trabajo, haga clic con el botón secundario en un mosaico de recuento, seleccione **Personalizar**y, a continuación, seleccione **Anclar al panel de información**. La próxima vez que navegue (y actualice) el panel de información seleccionado, verá ese recuento debajo de ese mosaico de navegación del área de trabajo en el panel de navegación.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personalización explícita: Personalización del panel de información
El panel de información suele ser la primera página que verá al abrir Finance and Operations. Puede personalizar el panel de información para cambiar sus mosaicos de navegación del espacio de trabajo, para mostrar solo los mosaicos que desea ver, para cambiar de nombre a los mosaicos o para organizar los mosaicos en el orden en que se preferiría verlos. 

Para personalizar el panel de información, seleccione cualquier mosaico y haga clic con el botón secundario para abrir un menú contextual. En el menú de contexto, seleccione **Personalizar**. Si el mosaico seleccionado es uno que desea ocultar, renombrar o saltarse, puede realizar ese cambio directamente en la ventana de la propiedad que ha aparecido. Si desea organizar los mosaicos, seleccione **Personalizar este formulario** en la ventana de propiedad para abrir la barra de herramientas de la personalización. Puede usar la herramienta para **Mover** para organizar los mosaicos.

## <a name="administration-of-personalization"></a>Administración de la personalización
Tras personalizar una página, puede compartir sus personalizaciones con otros usuarios exportando la página personalizada. A continuación puede pedir que los demás usuarios naveguen a la página personalizada e importen el archivo de personalización que ha creado, o puede dar su personalización a un usuario que tenga privilegios de administración y que pueda aplicar el archivo de personalización a muchos usuarios al mismo tiempo.

Los usuarios con privilegios de administración también pueden gestionar las personalizaciones para otros usuarios en la página **Personalización**. Esta página tiene cuatro fichas: 

- **Aplicar**: puede importar o seleccionar una personalización para uno o varios usuarios. Para aplicar una personalización a uno o varios usuarios, seleccione un rol y usuarios dentro de ese rol. A continuación, seleccione una personalización existente o importe un archivo de personalización para aplicarlo a los usuarios seleccionados. La personalización se validará y aplicará a todos los usuarios seleccionado la próxima vez que abra la página seleccionada.

- **Borrar**: puede borrar las personalizaciones de la página o del espacio de trabajo para uno o varios usuarios. Seleccione una página para ver la lista de usuarios que han personalizado la página. A continuación, seleccione los usuarios que deberían tener borradas las personalizaciones de esa página y seleccione **Borrar**. Se borran todas las personalizaciones que los usuarios seleccionados han aplicado a la página o al espacio de trabajo seleccionado. Esta acción no se puede deshacer. Sin embargo, si la página o el espacio de trabajo tiene una personalización guardada, esa personalización se puede reimportar.

- **Administrador por usuario** Permite seleccionar un usuario para ver la lista de páginas que esta persona ha personalizado.  Puede seleccionar habilitar o deshabilitar su capacidad para utilizar la personalización para páginas determinadas o el sistema completo.  También puede importar, exportar o borrar la personalización de este usuario.

- **Sistema:** – Puede desactivar temporalmente todas las personalizaciones para todos los usuarios del sistema. Si lo hace, no eliminará las personalizaciones pero restablecerá simplemente todas las páginas a su estado predeterminado para todos los usuarios. Si vuelve a habilitar más tarde la personalización, todas las personalizaciones se volverán a aplicar. También puede desactivar permanentemente todas las personalizaciones para todos los usuarios del sistema. Asegúrese de exportar las personalizaciones que es posible que desee más adelante antes de realizar este paso, ya que no podrá recuperar más tarde las personalizaciones eliminadas. 

## <a name="personalization-of-inventory-dimensions"></a>Personalización de dimensiones de inventario

Al personalizar la configuración de dimensiones de inventario en una página, tenga en cuenta los valores que se han creado usando la opción **Dimensión de visualización**. Por ejemplo, si usa la personalización para ocultar una columna para la dimensión de inventario de número de lote y aparece la columna la siguiente vez que abre la página, podría ser porque los ajustes de visualización de la dimensión controlan qué columnas de la dimensión de inventario se muestran. 

Los ajustes de visualización de la dimensión se aplican a todas las páginas y estos valores anulan cualquier configuración personalizada de campos de dimensión de inventario en las páginas individuales. 

Para el ejemplo con la dimensión de inventario de número de lote, esta dimensión tendría estar desactivada como parte de la opción de **Dimensiones de visualización** para que la tabla no muestre esta columna. Este cambio aplicaría finalmente no sólo a una página determinada, sino en todas las páginas.

