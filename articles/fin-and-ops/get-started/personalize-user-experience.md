---
title: Personalizar la experiencia del usuario
description: Este tema explica cómo puede personalizar Microsoft Dynamics 365 for Finance and Operations.
author: TLeforMicrosoft
manager: AnnBe
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
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
ms.openlocfilehash: 53aff09746b92372bb38908a526942ebe9bb4c52
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "363485"
---
# <a name="personalize-the-user-experience"></a>Personalizar la experiencia del usuario

[!include [banner](../includes/banner.md)]

Este tema explica cómo puede personalizar Microsoft Dynamics 365 for Finance and Operations.

Hay tres clases básicas de personalizaciones en Finance and Operations.

- Las personalizaciones creadas en una página de configuración. Los ejemplos incluyen el tema de colores y la zona horaria.
- Las personalizaciones relacionadas con el uso de la página, denominadas personalizaciones *implícitas*. Por ejemplo, Finance and Operations mantiene el seguimiento del ancho de las columnas de cuadrícula si las ajusta, y el estado de expandido o contraído de las fichas desplegables.
- Las personalizaciones que un usuario realiza para modificar el aspecto de una página cambiando la forma en que un elemento aparece o actúa en la página, a menudo mediante un modo de personalización interactivo. Estas personalizaciones se denominan personalizaciones *explícitas*. Por ejemplo, el usuario puede agregar, ocultar, o reordenar elementos en la página.

Cada personalización que un usuario haga en Finance and Operations es solo para dicho usuario, independientemente del tipo de personalización o de la empresa con la que el usuario interactúa actualmente. Los cambios que un usuario hace a una página no afectan a otros usuarios en el sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opciones de sistema válidas para el usuario actual

La página **Opciones de usuario** contiene varios valores para todo el sistema del usuario actual. Para abrir la página **Opciones de usuario** , seleccione el menú **Valores** (el símbolo de engranaje) en la barra de exploración y, a continuación, seleccione **Opciones de usuario**. La página **Opciones de usuario** tiene cuatro fichas que contienen distintas configuraciones del usuario:

- **Visual**: seleccione un tema de colores y el tamaño predeterminado de los elementos en las páginas.
- **Preferencias**: seleccione los valores predeterminados que se emplean cada vez que inicie Finance and Operations. Estos valores incluyen la empresa, la página de inicio, y el modo de visualización o edición predeterminado. (El modo de edición o visualización determina si una página tiene bloqueada la visualización o está abierta para su edición cada vez que la abre). Esta ficha también incluye las opciones del idioma, la zona horaria, y la fecha, el tiempo, y el formato de número. Finalmente, esta ficha incluye varias preferencias distintas que varían de versión en versión.
- **Cuenta:**: Ajuste su nombre de usuario y otras opciones relacionadas con la cuenta.
- **Flujo de trabajo**: seleccione las opciones relacionadas con el flujo de trabajo.

## <a name="implicit-personalizations"></a>Personalizaciones implícitas

Las personalizaciones implícitas son personalizaciones que se realizan simplemente interactuando con controles que "recuerdan" su estado visible actual.

- **Columnas de cuadrícula:** - Puede ajustar el ancho de una columna en una cuadrícula seleccionando la barra de tamaño de la izquierda o la derecha del encabezado de la columna y desplazándola hacia la izquierda o hacia la derecha hasta que la columna tenga la anchura deseada. Finance and Operations almacena el ancho que establece para una columna. A continuación cambia el tamaño según dicho ancho cada vez que abra la página que incluye la cuadrícula.
- **Fichas Desplegables**: algunas páginas tienen secciones extensibles llamadas *Fichas Desplegables*. Finance and Operations almacena información sobre las fichas desplegables que usted ha expandido y contraído. A continuación, cada vez que vuelve a la página, las mismas fichas desplegables se ampliarán o contraerán en función de su última interacción con la página. En algunos casos, puede ayudar a mejorar el rendimiento del sistema contrayendo una ficha desplegable, porque Finance and Operations no tiene que recuperar información para dicha ficha Desplegable hasta que se extienda la ficha Desplegable. Como se explica más adelante este tema, también puede cambiar el orden de las fichas desplegables de una página.
- **Cuadros informativos**: algunas páginas tienen una sección conocida como *panel de cuadro informativo*. Este panel contiene información solo de lectura que está relacionada con el tema actual de la página. Cada sección del panel del cuadro informativo se conoce como *cuadro informativo*. Puede ocultar o mostrar el panel completo del cuadro informativo y también puede ampliar o contraer cuadros informativos individuales. Finance and Operations almacena sus preferencias. A continuación, cada vez que vuelva a la página, se restablecerán el estado del panel del cuadro informativo y los cuadros informativos individuales, en función de su última interacción con la página. En algunos casos, puede ayudar a mejorar el rendimiento del sistema contrayendo un cuadro informativo, porque Finance and Operations no tiene que recuperar información para dicha ficha Desplegable hasta que se extienda la ficha Desplegable.
- **Paneles de acciones** – Un *Panel de acciones* aparece cerca de la parte superior de la mayoría de las páginas. El panel de acciones contiene botones para muchas de las acciones que puede realizar en la página actual. Estos botones se organizan a menudo en fichas. Puede anclar el panel de acciones abierto completo o puede contraerlo de forma predeterminada. A continuación, la próxima vez que abra la página, Finance and Operations restablecerá el estado anclado del panel de acciones. Si el panel de acciones se ancla abierto, Finance and Operations también mostrará a ficha de acciones que usó por última vez.
- **Filtros rápidos** – Un *filtro rápido* aparece sobre muchas cuadrículas. El filtro rápido le permite filtrar la cuadrícula, en función de una columna seleccionada. Finance and Operations almacena la columna en la que ha aplicado el filtro. A continuación, la próxima vez que abra la página que incluye la cuadrícula, la cuadrícula se filtrará en la misma columna. Sin embargo, puede filtrar la cuadrícula en otra columna.
- **Filtros de encabezado de columna** Cuando se filtra una cuadrícula con los *Filtros de encabezado de columna*, puede cambiar al operador del filtro según sea necesario para encontrar los datos que desee. Por ejemplo, puede cambiar el operador de **comienza con** a **es exactamente**. Cada vez que se utiliza un filtro de encabezado de columna y se modifica el operador del filtro, Finance and Operations almacena el cambio. A continuación restablecerá el operador del filtro la próxima vez que se filtre esa columna.
- **Panel de exploración** Puede abrir el *Panel de exploración* seleccionando el botón **Menú** en el panel izquierdo de cualquier página. (En ocasiones se hace referencia al botón **Menú** como *hamburguesa*, *menú de la hamburguesa*o *botón de la hamburguesa*). Puede anclar el panel abierto o puede mantenerlo contraído de forma predeterminada. Tras anclar y mantener abierto el panel de navegación, Finance and Operations se mantendrá abierto hasta que lo contraigan.

## <a name="explicit-personalizations"></a>Personalizaciones explícitas

Las distintas personas y empresas tienen una perspectiva diferente sobre los datos que son más importante para ellas, o los datos que no requieren para la forma en que ejecutan su negocio. En Finance and Operations puede ajustar la manera en la que la información se ordena o cómo se interactúa con ella. También puede especificar que cierta información debe mantenerse oculta. Estas capacidades son clave para tener una experiencia personal y productiva, y son ejemplos de personalizaciones explícitas. Las personalizaciones explícitas son aquellas personalizaciones que se realizan explícitamente con la intención de cambiar el aspecto o el comportamiento de un elemento o de una página.

### <a name="shortcut-menu-options"></a>Opciones del menú de acceso directo

Los menús de acceso directo proporcionan algunas formas de cambiar explícitamente una página para adaptarse mejor a sus requisitos o los requisitos de la empresa. (Un menú contextual también se conoce como *menú de botón secundario* o *menú contextual*).

Algunos de los cambios más habituales y más importantes que se pueden realizar en una página están disponibles directamente como opciones del menú contextual. Por ejemplo, a partir de la actualización 17 de la plataforma, si quiere agregar u ocultar las columnas en una cuadrícula, solo tiene que hacer clic con el botón secundario en un encabezado de la columna de la cuadrícula y, a continuación, seleccionar **Agregar columnas** u **Ocultar esta columna**.

Además, los tipos más básicos de personalización explícita están disponibles haciendo clic con el botón secundario en un elemento y después seleccionando **Personalizar**. (Tenga en cuenta que no todos los elementos en su página se pueden personalizar.) Si usa este método de personalización, aparecerá la ventana de la propiedad del elemento.

[![Personalización de las propiedades de un elemento](./media/personalization-element-properties.jpg)](./media/personalization-element-properties.jpg)

Puede usar la ventana de propiedad para personalizar un elemento de las siguientes formas:

- Cambiar la etiqueta del elemento.
- Ocultar el elemento para que no se muestre en la página. Los datos del campo no se eliminan ni se modifican. La información simplemente deja de aparecer en la página.
- Incluur la información en la sección de resumen de la ficha desplegable (si el artículo se encuentra en una ficha desplegable).
- Omita el campo al presionar el tabulador para desplazarse por los campos de la página.
- Evitar que los datos en el campo (de cualquier registro) se editen.

La ventana de la propiedad puede incluir otras capacidades de personalización, en función del elemento. Por ejemplo, la ventana de propiedad de un mosaico puede permitirle ascender ese mosaico a un panel, y la ventana de la propiedad de un panel puede dejarle crear una nueva área de trabajo en el panel.

### <a name="the-personalization-toolbar"></a>La barra de herramientas de personalización

Si desea implementar varios cambios en una página o hacer cambios que no están disponibles con otros mecanismos (como reordenar elementos), puede utilizar la barra de herramientas **Personalización**. Para abrir la barra de herramientas **Personalización**, seleccione **Personalizar este formulario** en la ventana de la propiedad del elemento. También puede seleccionar **Personalizar este formulario** en el grupo **Personalizar** de la pestaña **Opciones** del panel de acciones de cada página.

[![Barra de herramientas de personalización](./media/personalization-personalizationtoolbar.jpg)](./media/personalization-personalizationtoolbar.jpg)

#### <a name="navigating-the-page"></a>Navegación por la página

Su habilidad para navegar en la página mientras la **Barra de herramientas de personalización** está abierta depende de la versión de la plataforma que está ejecutando.

- Antes de la actualización 19 de la plataforma, mientras que la barra de herramientas **Personalización** está abierta, la página es de solo lectura (no puede especificar nada) y no interactiva (solo puede realizar cambios en los elementos visibles en la página). Si desea realizar cambios en los elementos dentro de una sección contraída o en otra ficha, debe cerrar la barra de herramientas **Personalización** , expandir una sección o cambiar a la ficha deseada, y volver a abrir la barra de herramientas **Personalización**.

- Comenzando con la actualización 19 de la plataforma, si la barra de herramientas **Personalización** está abierta, la página sigue siendo de solo lectura pero es mucho más interactivos. Específicamente, puede ampliar o contraer el panel del cuadro informativo, cambiar de fichas, expandir y contraer secciones mientras que la barra de herramientas **Personalización** está abierta del mismo modo que lo haría normalmente en una página. Para aplicar un cambio de personalización a una sección o ficha que se puede contraer (por ejemplo para ocultar una ficha desplegable), tiene que activar el botón que aparece junto a la sección o la ficha que se puede contraer cuando enfoca con el teclado o cuando pasa el mouse sobre ella.

#### <a name="personalization-tools"></a>Herramientas de personalización

Las siguientes herramientas están disponibles en la barra de herramientas **Personalización**:

- Utilice la herramienta **Seleccionar** praa seleccionar y cambiar las propiedades de un elemento. Seleccione la herramienta **Seleccionar** y luego seleccione el elemento cuyas propiedades desee modificar. Cuando selecciona un elemento, la ventana de la propiedad del elemento aparece y usted podrá modificar las propiedades de dicho elemento. Es posible repetir el proceso para otros elementos que se pueden personalizar en dicha página. Sin embargo, debido al modo en que algunos artículos se usan, Finance and Operations no le dejará modificar algunas de sus propiedades. Por lo tanto, cuando seleccione un elemento, es posible que vea que algunas de sus propiedades no se pueden modificar. Por ejemplo, no puede ocultar un campo que es necesario.
- Elija la herramienta **Mover** si desea mover un elemento a otra ubicación dentro del grupo actual de elementos. (No puede mover un elemento fuera del grupo principal). Seleccione la herramienta **Mover** , y seleccione el elemento que debe moverse. Al seleccionar un elemento, Finance and Operations examina la página para determinar adónde se puede mover el elemento. A continuación crea una serie de “zonas de colocación". Mientras arrastra el elemento dentro del grupo actual, todas las “zonas de colocación" se muestran como una línea en color y negrita junto al área donde el elemento se puede colocar.
- Use la herramienta **Ocultar** para ocultar un elemento de la página. Seleccione la herramienta **Ocultar** , y seleccione el elemento que debe ocultarse. Al seleccionar la herramienta **Ocultar**, todos los elementos que se ocultan actualmente se hacen visibles y se muestran en un contenedor sombreado. A continuación puede mostrarlos. Seleccionando la herramienta **Seleccionar** puede ver qué aspecto tendrá la página cuando los elementos seleccionados se oculten.

    - Comenzando con la actualización 18 de la plataforma, puede ocultar los campos y las secciones necesarios que contienen los campos necesarios. Esto le permite crear una experiencia simplificada donde los campos obligatorios que son establecidos como valor predeterminado por la lógica de negocios no se muestran. Los campos necesarios ocultos también se muestran temporalmente si están vacíos cuando se intenta guardar.

- Utilice la herramienta **Resumen** cuando desee que aparezca un elemento en la sección de resumen de la ficha desplegable. La herramienta Resumen se aplica solo a los campos que están dentro de una ficha desplegable. Al seleccionar la herramienta **Resumen**, todos los campos que se seleccionan como campos de resumen se muestran en un contenedor sombreado. Puede agregar interactivamente campos al resumen de ficha desplegable y quitar campos del resumen de ficha desplegable seleccionando los campos.
- Use la herramienta **Omitir** para quitar un elemento de la secuencia del tabulador del teclado de la página. Al seleccionar la herramienta **Omitir**, todos los elementos que se omiten se muestran en un contenedor sombreado. A continuación puede hacer que vuelvan a ser parte de la secuencia de fichas.
- Elija la herramienta **Editar** para marcar un elemento como editable o no editable. Al seleccionar la herramienta **Editar**, todos los elementos que actualmente no son editables se muestran en un contenedor sombreado. A continuación puede hacer que vuelvan a ser editables. Tenga en cuenta que algunos campos son necesarios y no se pueden convertir en no editables. Un símbolo de candado aparece junto a dichos campos.
- Use el botón **Insertar** para ver una lista de elementos que se pueden insertar en una página.

    - Seleccione la herramienta **Campo** en **Insertar** para agregar un campo a la página. Al usar la herramienta **Campo**, puede agregar solamente los campos que forman parte de la definición de la página pero que no se muestran actualmente en la página. Para obtener información sobre cómo crear nuevos campos que no son parte de la definición de la página actual, consulte [Campos personalizados](user-defined-fields.md). Tras seleccionar la herramienta **Campo**, primero debe seleccionar el grupo o el área donde desee agregar un campo. Un cuadro de diálogo muestra la lista de campos relacionados con el grupo o el área que ha seleccionado. En el cuadro de diálogo, seleccione uno o varios campos para añadirlos y luego seleccione **Insertar**. Para quitar un campo que ha agregado anteriormente, repita el proceso, pero desactive la selección del campo en el cuadro de diálogo.
    - Seleccione la herramienta **PowerApp** en **Insertar** para insertar una aplicación que se creó usando Microsoft PowerApps en la página. Para obtener información detallada acerca de cómo insertar una aplicación de PowerApps en una página, consulte [Integrar PowerApps](embed-power-apps.md).

- Seleccione el botón **Administrar** para ver una lista de las opciones de administración relacionadas con todas las personalizaciones de la página actual.

    - Seleccione **Desactivar** para restablecer la página a su valor predeterminado, estado instalado. Todas las personalizaciones en la página actual se desactivarán. No existen una acción de deshacer. Por lo tanto, use esta opción si está seguro que desea restablecer la página.
    - Seleccione **Importación** para cargar una personalización de un archivo que usted o otro usuario creó anteriormente para la página. Todas las personalizaciones actuales de la página se reemplazan con las personalizaciones del archivo seleccionado.
    - Seleccione **Exportar** para guardar las personalizaciones de la página en un archivo. Puede compartir sus personalizaciones con otros usuarios. Estos usuarios solo tienen que importar el archivo que contiene sus personalizaciones de la página.

- Seleccione el botón **Cerrar** para cerrar la barra de herramientas **Personalización** y devuelva la página a su estado interactivo anterior.

Cuando se usa la barra de herramientas **Personalización**, las operaciones Guardar son implícitas. Sus personalizaciones se hacen efectivas tan pronto como las crea y no es necesario que seleccione un botón **Guardar**. En algunos casos, cuando seleccione una herramienta, un símbolo de candado aparecerá al lado de un elemento. Este símbolo indica que no podrá modificar las propiedades del elemento relacionadas con la herramienta seleccionada, ya que los cambios realizados a dichas propiedades impedirían que la página funcione correctamente.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Agregar un mosaico, lista o enlace a un espacio de trabajo

Para algunas páginas que incluyen listas, hay disponible una característica de personalización adicional. El botón **Agregar al área de trabajo** en el grupo **Personalizar** en la pestaña **Opciones** del panel de acciones le permite mostrar la información de la lista actual en un área de trabajo específica. Puede mostrar una vista filtrada y clasificada de la información del área de trabajo, o bien puede mostrar la vista predeterminada. También puede especificar si la información que aparece en el área de trabajo aparecerá como una lista, un mosaico de resumen que puede mostrar el número de elementos de la lista, o como un vínculo.

[![Agregar al espacio de trabajo](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Para agregar una lista a un espacio de trabajo, primero debe clasificar o filtrar la lista de la página para que muestre la información tal y como desee que aparezca en el área de trabajo. A continuación seleccione **Agregar al área de trabajo**. Seleccione un área de trabajo y, a continuación, en el campo **Presentación**, seleccione **Lista**. Tras seleccionar **Configurar**, aparecerá un cuadro de diálogo, donde puede seleccionar las columnas que deben aparecer en la lista del área de trabajo. También puede especificar la etiqueta que se debe usar para la lista del área de trabajo.
- Para agregar un mosaico a un espacio de trabajo, primero debe filtrar la lista de la página para que muestre los datos que quiere resumir o a los que quiere tener acceso rápido. A continuación seleccione **Agregar al área de trabajo**. Seleccione un área de trabajo y, a continuación, en el campo **Presentación**, seleccione **Mosaico**. Tras seleccionar **Configurar**, aparece un cuadro de diálogo donde puede especificar la etiqueta para usar para el mosaico en el área de trabajo. También puede especificar si el mosaico debe mostrar un recuento. Una vez que el mosaico se agrega al área de trabajo, puede seleccionarlo para abrir la página actual del área de trabajo y ver la lista filtrada que está asociada al mosaico.
- Para agregar un vínculo a un espacio de trabajo, primero filtre la lista de la página para que muestre los datos que le interesan. A continuación seleccione **Agregar al área de trabajo**. Seleccione un área de trabajo y, a continuación, en el campo **Presentación**, seleccione **Vínculo**. Tras seleccionar **Configurar**, aparece un cuadro de diálogo donde puede especificar la etiqueta del vínculo. También puede especificar de forma opcional una etiqueta para una nueva sección que contenga este vínculo.

Una vez que la lista, el mosaico, o el vínculo se hayan agregado a un área de trabajo, puede abrir dicha área de trabajo y reordenar los elementos que contiene tal y como desea.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Agregar un resumen de un espacio de trabajo a un panel de información

Algunas áreas de trabajo contienen mosaicos de recuento (es decir, mosaicos que contienen), y es posible que desee que dichos mosaicos aparezcan también en el panel. En un espacio de trabajo, haga clic con el botón derecho en un mosaico y seleccione **Personalizar**. A continuación, en la ventana de la propiedad del mosaico, seleccione **Anclar al panel**. La próxima vez que abra (y actualice) el panel de información seleccionado, verá el recuento debajo del mosaico de navegación del área de trabajo. Puede seleccionar dicho recuento para ir directamente a los datos que representa.

### <a name="personalizing-your-dashboard"></a>Personalización del panel de información

El panel de información suele ser la primera página que verá al abrir Finance and Operations. Puede personalizar el panel de información de modo que muestre solo los mosaicos del espacio de trabajo que desea ver. También puede reorganizar los mosaicos de modo que se encuentren en el orden que prefiere consultarlos, cambiar el nombre de los mosaicos de navegación de área de trabajo, o agregar un mosaico de espacio de trabajo completamente nuevo.

Para personalizar el panel de información, haga clic con el botón secundario en cualquier mosaico y, a continuación seleccione **Personalizar** para abrir la ventana de la propiedad del mosaico.

- Si desea ocultar o cambiar el nombre del mosaico seleccionado, puede realizar ese cambio directamente en la ventana de la propiedad.
- Si desea reordenar los mosaicos del espacio de trabajo, en la ventana de la propiedad, seleccione **Personalizar este formulario** para abrir la barra de herramienta **Personalización**. Podrá entonces usar la herramienta **Mover** para organizar los mosaicos tal y como desee.
- Para crear un nuevo mosaico del espacio de trabajo, en la ventana de la propiedad, seleccione **Agregar un área de trabajo**. Se creará un nuevo mosaico del espacio de trabajo en la parte inferior del panel de información. Puede cambiar el nombre de este nuevo mosaico de área de trabajo tal y como desee. También puede agregar listas, mosaicos y vínculos al área de trabajo tal y como se describe en la sección [Agregar listas, mosaicos o vínculos a las áreas de trabajo](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace) de este tema.

## <a name="administration-of-personalization"></a>Administración de la personalización

Tras personalizar una página, puede compartir sus personalizaciones con otros usuarios exportando la página personalizada. A continuación puede pedir a los demás usuarios que abran la página personalizada e importen el archivo de personalización que ha creado. Como alternativa, puede dar su personalización a un usuario que tenga privilegios de administración. Dicho usuario puede aplicar su archivo de personalización a muchos usuarios al mismo tiempo.

Los usuarios con privilegios de administración también pueden gestionar las personalizaciones para otros usuarios en la página **Personalización**. Esta página tiene cuatro fichas:

- **Aplicar**: puede importar o seleccionar una personalización para uno o varios usuarios. Para aplicar una personalización a uno o varios usuarios, seleccione primero un rol y a los usuarios con dicho rol. A continuación seleccione una personalización para aplicarla a los usuarios seleccionados o importe un archivo de personalización. La personalización se validará y aplicará a todos los usuarios seleccionados la próxima vez que abran la página seleccionada.
- **Borrar**: puede borrar todas las personalizaciones de una página o espacio de trabajo de uno o varios usuarios. Primero seleccione una página o espacio de trabajo para ver la lista de los usuarios que la han personalizado. A continuación, seleccione los usuarios que deberían tener borradas las personalizaciones de esa página o espacio de trabajo, y seleccione **Borrar**. Se eliminan todas las personalizaciones que los usuarios seleccionados han aplicado a la página o al espacio de trabajo seleccionado. Esta acción no se puede deshacer. Sin embargo, si se guardó una personalización para la página o el espacio de trabajo, se podrá volver a importar dicha personalización.
- **Administrador por usuario** Seleccione un usuario para ver la lista de páginas que esta persona ha personalizado. A continuación puede habilitar o deshabilitar la capacidad del usuario seleccionado para utilizar personalizaciones para páginas determinadas o el sistema completo. También puede importar, exportar o borrar una personalización para el usuario seleccionado.
- **Sistema:** – Puede desactivar temporalmente todas las personalizaciones para todos los usuarios del sistema. En este caso, las personalizaciones se eliminan. Todas las páginas simplemente se restablecen a su estado predeterminado para todos los usuarios. Si vuelve a habilitar más tarde la personalización, todas las personalizaciones se volverán a aplicar. También puede desactivar permanentemente todas las personalizaciones para todos los usuarios del sistema. No es posible recuperar las personalizaciones que se han eliminado. Por lo tanto, antes de realizar esta tarea, asegúrese de exportar todas las personalizaciones que pueda querer más tarde.

## <a name="personalization-of-inventory-dimensions"></a>Personalización de dimensiones de inventario

Al personalizar la configuración de dimensiones de inventario en una página, tenga en cuenta los valores que se han creado usando la opción **Dimensión de visualización**. Por ejemplo, puede usar la personalización para ocultar una columna de la dimensión de inventario del número de lote, pero la columna aparecerá la próxima vez que la página esté abierta. Este comportamiento se produce porque la configuración de **Visualización de dimensiones** controla las columnas de la dimensión de inventario que se muestran.

Los ajustes de **visualización de dimensiones** se aplican a todas las páginas y estos valores anulan cualquier configuración personalizada de campos de dimensión de inventario en las páginas individuales.

En consecuencia, en el ejemplo anterior, si no desea que la columna de la dimensión de inventario de número de lote aparezca, debe borrar dicha dimensión como parte de la opción **Dimensiones de la pantalla** de la tabla. Este cambio se aplicará finalmente no solo a una página determinada, sino en todas las páginas.
