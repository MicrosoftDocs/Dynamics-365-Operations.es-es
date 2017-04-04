---
title: Personalizar la experiencia del usuario
description: "Este artículo se explica cómo puede personalizar el Microsoft Dynamics 365 para las operaciones."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserSetup
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 8965c193839002776b3c61036b23b54625c974a4
ms.lasthandoff: 03/31/2017


---

# <a name="personalize-the-user-experience"></a>Personalizar la experiencia del usuario

Este artículo se explica cómo puede personalizar el Microsoft Dynamics 365 para las operaciones.

Hay muchos tipos de personalizaciones en Microsoft Dynamics 365 para las operaciones. Algunas personalizaciones son las selecciones realizadas en una lista de opciones en una página de configuración. Algunas personalizaciones se implícitas, por ejemplo, Dynamics 365 para las operaciones efectúa un seguimiento de los anchos de columnas de la cuadrícula si se las ajusta, y al estado expandido/contraida de fichas desplegables. Otras personalizaciones son explícitas. Para las personalizaciones explícitas, tiene que especificar un modo interactivo de personalización y modificar el aspecto de una página gestionando directamente la forma en que los elementos aparecen o se comportan en la página. 

Todas las personalizaciones, de cualquier tipo, que un usuario cree en Dynamics 365 para las operaciones son para dicho usuario únicamente, independientemente de la empresa que el usuario interactúa. Los cambios que un usuario hace a una página no afecta a otros usuarios en el sistema.

## <a name="systemwide-options-for-the-current-user"></a>Systemwide opciones para el usuario actual
En la barra de exploración se encontrará una imagen de engranaje que es el botón de menú **Configuración**. Al abrir el menú **Configuración** se mostrarán varias opciones. La selección de **Opciones** abrirá la página **Opciones** del usuario. Allí encontrará cuatro pestañas de opción: **Visual****Preferencias****Cuenta** y **Flujo de trabajo**.

-   **Visual: **para elegir un tema de color y el tamaño predeterminado de los elementos en las páginas.
-   ** Preferencias: ** Aquí puede elegir los valores predeterminados para cada vez que se abre Dynamics 365 para las operaciones, incluyendo la empresa, la página de la inicial, y ver predeterminada/el modo de edición (que determina si una página está bloqueada para ver o abierto para cada vez editarle abre). También encontrará idioma, zona horaria y las opciones de formato de fecha, hora y número. Por último, esta página contiene varias preferencias distintas que varían según el lanzamiento.
-   **Cuenta: **para proporcionar el id. de usuario y otras opciones relacionadas con la cuenta.
-   **Flujo de trabajo: **aquí puede elegir opciones relacionadas con el flujo de trabajo.

## <a name="implicit-personalizations"></a>Personalizaciones implícitas
Las personalizaciones implícitas son las personalizaciones que realiza simplemente interactuando con determinados controles que recuerden su estado visible actual. 

**Columnas de cuadrícula:** puede ajustar la anchura de una columna en una lista seleccionando la barra de tamaño a la izquierda o la derecha del encabezado de la columna y desplazándola hacia la izquierda o hacia la derecha hasta la anchura deseada. La Dynamics 365 para las operaciones almacenará el ancho que desea mostrarle y a esa columna con ese ancho cada vez abra la página con esta lista. 

**Fichas Desplegables:** algunas páginas tienen secciones extensibles llamadas Fichas Desplegables. La Dynamics 365 para las operaciones almacenará que ha expandido fichas desplegables se, y que ha incurrido fichas desplegables usted. Cada vez que vuelve a la página, esas mismas Fichas Desplegables se ampliarán o se contraerán según como las usó la última vez. En este artículo, explicaremos cómo cambiar el orden de las secciones de la ficah desplegable. En algunos casos, contraer una ficha desplegable puede mejorar el rendimiento porque Dynamics 365 para las operaciones no necesitará recuperar información para dicho ficha desplegable hasta que se expanda la ficha desplegable. 

**Cuadros informativos:** algunas páginas tienen una sección llamada panel de cuadro informativo. Este panel contiene información solo de lectura relacionada con el tema actual de la página. Cada sección en el panel del cuadro informativo se denomina cuadro informativo. Puede ampliar o contraer el cuadro y una Dynamics 365 el hecho para las operaciones almacenará su preferencia. En algunos casos, contraer el cuadro el hecho puede mejorar el rendimiento porque Dynamics 365 para las operaciones no necesitará recuperar información para el cuadro el hecho hasta que se expanda el cuadro el hecho.

## <a name="explicit-personalizations-using-the-personalization-toolbar"></a>Personalizaciones explícitas que usan la barra de herramientas de personalización
Cada persona y empresa tiene una perspectiva distinta sobre qué datos son los más importantes para ellos o qué datos no son necesarios para llevar su negocio. Se pide la capacidad de la manera ajustar su información, interactuado, con o incluso ocultado es clave a crear Dynamics 365 para las operaciones una experiencia personal y productiva. 

Las personalizaciones explícitas son aquellas personalizaciones que realice explícitamente con el intenta cambiar su aspecto o el comportamiento de un artículo o de una página, elige un menú de personalización. El tipo más básico de personalización explícita es donde el hacer clic con el botón secundario en un artículo y seleccione ** personalizar **. Nota (que no todos los artículos de la página se pueden personalizar.) Si selecciona este método de personalización, verá la ventana de la propiedad del artículo. 

[![que personalizar las propiedades de un artículo (]. /media/personalization-element-properties.jpg])(. /media/personalization-element-properties.jpg) 

Personalizará un elemento en la página de esta manera si desea simplemente cambiar la etiqueta del elemento, ocultar el elemento para que no aparezca en la página (esto no cambia ningún dato, simplemente no muestra la información), incluir la información de la sección de resumen de la ficha desplegable (si el elemento no se encuentra en una ficha Desplegable), omitir el campo al tabular o hacer que los datos no se puedan cambiar marcándolo como “No editar”. 

Cuando desee mover u ocultar elementos o realizar varios cambios, puede usar la barra de herramientas de personalización, disponible en la ventana de propiedad de los elementos seleccionando **Personalizar este formulario**. La barra de herramientas de personalización también está disponible en el panel de acciones del formulario, en el grupo de la personalización de la pestaña **Opciones**. Seleccione **Personaliar este formulario** y verá la barra de herramientas de la personalización. 

[barra de herramientas de personalización![] (. /media/personalization-personalizationtoolbar.jpg])(. /media/personalization-personalizationtoolbar.jpg)

La barra de herramientas de personalización tiene varios acciones de personalización. Elija la herramienta **Seleccionar** si desea seleccionar y cambiar las propiedades de muchos elementos, de uno en uno. Primero, haga clic en la herramienta Seleccionar y, a continuación, haga clic en el elemento cuyas propiedades desea modificar. Cuando selecciona un elemento, la ventana de la propiedad del elemento se abrirá y podrá modificar las propiedades para dicho elemento. Es posible repetir el proceso para otros elementos en el formulario que sean personalizables. En algunos casos, seleccionará un elemento y verá que algunas de las propiedades no son modificables. Esto significa que basado en el camino el artículo actual se utiliza, Dynamics 365 para las operaciones no puede cambiar permitirle dicha propiedad. Por ejemplo, no puede ocultar un campo que se necesario. 

Elija la herramienta **Mover** si desea seleccionar y mover un elemento a otra ubicación dentro del grupo actual de elementos. (No puede mover un elemento fuera del grupo principal). Primero, haga clic en la herramienta Mover y, a continuación, haga clic en el elemento que desea mover. Al hacer clic en el artículo que desee mover, Dynamics 365 para las operaciones digitalizará el formulario para comprender si este artículo se puede mover y crear una serie de “zonas de esa otoño” presentación como haber coloreado, gruesa línea junto al área donde el artículo se puede quitar como el arrastrar el artículo acerca dentro del grupo actual. 

Elija la herramienta **Ocultar** para seleccionar y ocultar un elemento. Para ocultar un elemento, elija simplemente la herramienta Ocultar y haga clic en el elemento que desea ocultar. Cuando elija la herramienta Ocultar, todos los elementos actualmente ocultos se harán visibles y se mostrarán en un contenedor sombreado de manera que pueda elegir el elemento para mostrarlo. Elija la herramienta Seleccionar para ver qué aspecto tendrá la página con los elementos seleccionados ocultos. Elija la herramienta **Resumen** cuándo desea que un campo numérico o de cadena se muestra en el área de resumen de la ficha desplegable. La herramienta Resumen se aplicará solo a los campos que están dentro de una sección de la ficha desplegable. Si elige la herramienta de resumen, Dynamics 365 para las operaciones mostrará todos los campos que se han campos seleccionados como añadiéndolos resumen de contenedor en un sombreado. Puede agregar y eliminar de forma interactiva campos de un resumen de ficha desplegable si hace clic en el campo. 

Elija ** salto ** la herramienta para quitar un artículo de la secuencia de la ficha del teclado de la página. Si elige la herramienta de salto, todos los artículos saltados actualmente se mostrarán en un contenedor sombreado de modo que pueda elegirlos de nuevo para crearles la parte de la secuencia de la ficha seleccionando un artículo omitido. 

Elija la herramienta **Editar** cuando desee marcar un elemento como editable o no es editable. Cuando elija la herramienta Editar, todos los elementos actualmente no editables se harán visibles y se mostrarán en un contenedor sombreado de manera que pueda elegirlos para hacerlos editables. Tenga en cuenta que algunos campos son necesarios y no se pueden editar. Dichos campos aparecerán con un icono de candado junto a ellos. 

Elija la herramienta **Agregar** para agregar un campo en la página. Con la herramienta Agregar, no puede crear un nuevo campo, pero puede agregar los campos que forman parte de la definición de la página actual, pero que no se muestran en la página. Cuando elija la herramienta Agregar, primero deberá seleccionar el grupo o el área en el que desea agregar un campo. Un cuadro de diálogo mostrará la lista de campos relacionados a la sección que ha seleccionado. En ese cuadro de diálogo, puede seleccionar uno o más campos para agregar y hacer clic en insertar. Si después desea elimina un campo que ha agregado anteriormente, repita el proceso, pero simplemente desactive el campo que ha agregado anteriormente. 

Elija ** gestionar ** botón para ver una lista de opciones de administración relacionadas con todas las personalizaciones para la página actual. 

Elija ** Borrar ** para restablecer la página a su valor predeterminado, instalado. Todas las personalizaciones en la página actual se borradas. Existen ningún deshacer la acción, tan sólo utiliza esta opción cuando tenga esta manera que desea restablecer la página. 

Elija **Importación** para usar una personalización de un archivo de la personalización que usted o otro usuario creó anteriormente para esta página. La importación de una personalización desactivará cualquier personalización que haya realizado en la página completa y use todas las personalizaciones del archivo seleccionado. Si desea guardar o compartir una personalización, seleccionará la opción **Exportar** para guardar las personalizaciones a un archivo. 

Elija el botón **Cerrar** para cerrar la barra de herramientas y devolver la página a su anterior estado interactivo. 

Con la barra de herramientas de la personalización, guardar es implícito. Sus personalizaciones surtirán efecto inmediatamente a medida que las hace y no hay necesidad de hacer clic en el botón **Guardar**. En algunos casos, aparecerá un icono de candado junto a un artículo cuando selecciona una herramienta. Esto significa que para que la página como funcione correctamente, no podrá modificar las propiedades relacionadas con la herramienta seleccionado. Cuando se abre la barra de herramientas de la personalización, la página pasará a ser no interactiva. No puede escribir datos o expandir y contraer secciones.

## <a name="explicit-personalization-adding-a-tile-or-list-to-a-workspace"></a>Personalización explícita: agregar un mosaico o lista a un espacio de trabajo
Algunas páginas con listas tendrán una característica adicional de personalización disponible dentro de su Panel de acciones, en el grupo de la personalización de la pestaña opciones. Seleccione **Agregar al espacio de trabajo** para abrir la lista desplegable que proporciona la capacidad de mostrar la información de la lista actual (filtrada y clasificada o predeterminado) en un espacio de trabajo como una lista o mosaico de resumen (que se pueda usar para mostrar el número de elementos de la lista). 

[![Add to workspace](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png) 

Para agregar una lista a un espacio de trabajo, primero clasifique o filtre la lista con la información como desee verla en el espacio de trabajo, después seleccione el cuadro de diálogo del espacio de trabajo. A continuación, seleccione el espacio de trabajo deseado y seleccione **Lista** de la lista desplegable de la presentación. Cuando selecciona **Lista** un diálogo se abrirá permitiendo que se seleccionen las columnas que desea ver en la lista, y la etiqueta para la lista como aparecerá en el espacio de trabajo. 

Para agregar un mosaico a un espacio de trabajo, primero debe filtrar la lista para representar los datos que quiere resumir (o a los que quiere tener acceso rápido). Luego, abra el cuadro desplegable Agregar a espacio de trabajo. A continuación, seleccione el espacio de trabajo deseado y seleccione **Mosaico** de la lista desplegable de la presentación. Cuando selecciona **Mosaico**, un diálogo se abrirá permitiendo que proporcione una ficha de mosaico y que decida si el mosaico muestra una cuenta. Cuando se pone en un espacio de trabajo, el mosaico le permitirá abrir la página actual del espacio de trabajo y mostrar la lista de información relacionada con el mosaico. 

Cuando la lista o mosico se agrega a un espacio de trabajo, puede elegir abrir el espacio de trabajo y reordenar la lista o el mosaico dentro del grupo en que se ha colocado.

## <a name="explicit-personalization-adding-a-summary-from-a-workspace-to-a-dashboard"></a>Personalización explícita: Agreagar un resumen de un espacio de trabajo a un panel de información
Algunas áreas de trabajo contienen los mosaicos de recuento (mosaicos con números en ellos) que también quisieran ver en el panel. En un área de trabajo, haga clic con el botón secundario en un recuento colocar y seleccione ** personalizar **. Seleccione **Anlar al panel de información**. La próxima vez que navegue (y actualice) el panel de información seleccionado, verá ese recuento debajo de ese mosaico de navegación del área de trabajo en el panel de navegación.

## <a name="explicit-personalization-personalizing-your-dashboard"></a>Personalización explícita: Personalización del panel de información
El panel suele ser la primera página que verá al abrir Dynamics 365 para las operaciones. Puede personalizar el panel de información para cambiar sus mosaicos de navegación del espacio de trabajo, para mostrar solo los mosaicos que desea ver, para cambiar de nombre a los mosaicos o para organizar los mosaicos en el orden en que se preferiría verlos. Para personalizar el panel de información, seleccione cualquier mosaico y haga clic con el botón secundario para abrir un menú contextual. En el menú de contexto, seleccione **Personalizar**. Si el mosaico seleccionado es uno que desea ocultar, renombrar o saltarse, puede realizar ese cambio directamente en la ventana de la propiedad que ha aparecido. Si desea organizar los mosaicos, seleccione **Personalizar este formulario** en la ventana de propiedad para abrir la barra de herramientas de la personalización. Puede usar la herramienta de movimientos para organizar los mosaicos.

## <a name="administration-of-personalization"></a>Administración de la personalización
Es posible personalizar una página y compartirla con otros usuarios simplemente exportando la página personalizada y solicitando que los otros usuarios naveguen a la página personalizada e importen el archivo de personalización que ha creado. Si un usuario tiene privilegios de administración, también puede gestionar las personalizaciones para otros usuarios en la página **Configuración de la personalización**. Desplácese a la página b. En la página **Personalización**, encontrará dos fichas, una etiquetada **Sistema** y una etiquetada** Usuarios**. 

**Sistema:** Aquí es donde puede desactivar temporalmente o “apagar” todas las personalizaciones en el sistema. Esto no elimina personalizaciones, pero restablece todos los formularios a su estado predeterminado. Puede volver a habilitar más tarde la personalización para tener todas las personalizaciones aplicadas de nuevo a todos los formularios de los usuarios. También puede eliminar todas las personalizaciones de todos los usuarios. Tenga en cuenta que si elimina personalizaciones, no hay manera de volver a habilitar automáticamente personalizaciones del sistema. Asegúrese de haber exportado las personalizaciones que puede querer importar más tarde antes de realizar este paso. 

**Usuarios:** aquí es donde puede decidir para cada usuario si puede realizar la personalización implícita o explícita. También puede decidir si cada usuario puede realizar la personalización implícita o explícita en un formulario específico. Por último, puede importar o exportar o eliminar una personalización para cada usuario. 

**Nota:** en su inicial versión, la administración de la personalización solo permite la gestión según cada usuario.


