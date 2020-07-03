---
title: Personalizar la experiencia del usuario
description: Este tema explica cómo puede personalizar la aplicación.
author: jasongre
manager: AnnBe
ms.date: 05/18/2020
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
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb66db1e41dce6987bdfc52dd58e2b704ce36720
ms.sourcegitcommit: dc67232c9aa3223d42f22cc1f7aafbd121e7e616
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2020
ms.locfileid: "3412363"
---
# <a name="personalize-the-user-experience"></a>Personalizar la experiencia del usuario

[!include [banner](../includes/banner.md)]

Este tema explica cómo puede personalizar la aplicación.

Existen tres tipos básicos de personalizaciones.

- Las personalizaciones creadas en una página de configuración. Los ejemplos incluyen el tema de colores y la zona horaria.
- Personalizaciones relacionadas con el uso de la página. Estas personalizaciones se denominan personalizaciones *implícitas*. Por ejemplo, el sistema mantiene el seguimiento del ancho de las columnas de cuadrícula si las ajusta, y el estado de expandido o contraído de las fichas desplegables.
- Las personalizaciones que un usuario realiza para modificar el aspecto de una página cambiando la forma en que un elemento aparece o actúa en la página, a menudo mediante un modo de personalización interactivo. Estas personalizaciones se denominan personalizaciones *explícitas*. Por ejemplo, el usuario puede agregar, ocultar, o reordenar elementos en la página.

Cada personalización que un usuario haga es solo para dicho usuario, independientemente del tipo de personalización o de la empresa con la que el usuario interactúa actualmente. Los cambios que un usuario hace a una página no afectan a otros usuarios en el sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opciones de sistema válidas para el usuario actual

La página **Opciones de usuario** contiene varios valores para todo el sistema del usuario actual. Para abrir la página **Opciones de usuario** , seleccione el botón **Valores** (el símbolo de engranaje) en la barra de exploración y, a continuación, seleccione **Opciones de usuario**. La página **Opciones de usuario** tiene cuatro fichas que contienen distintas configuraciones del usuario:

- **Visual**: seleccione un tema de colores y el tamaño predeterminado de los elementos en las páginas.
- **Preferencias**: seleccione los valores predeterminados que se emplean cada vez que inicie el sistema. Estos valores incluyen la empresa, la página de inicio, y el modo de visualización o edición predeterminado. (El modo de edición o visualización determina si una página tiene bloqueada la visualización o está abierta para su edición cada vez que la abre). Esta ficha también incluye las opciones del idioma, la zona horaria, y la fecha, el tiempo, y los formatos de número. Finalmente, esta ficha incluye varias preferencias distintas que varían de versión en versión.
- **Cuenta:**: Ajuste su nombre de usuario y otras opciones relacionadas con la cuenta.
- **Flujo de trabajo**: seleccione las opciones relacionadas con el flujo de trabajo.

Además de modificar la configuración del usuario, también puede ver y eliminar sus datos de uso y personalizaciones con la página **Opciones de uso**. Simplemente seleccione **Datos de uso** en el panel Acciones.

Cuando se utiliza la aplicación, muchas de las selecciones se guardan para que pueda utilizar el sistema más fácilmente en el futuro. La ficha **Personalización** le permite ver y gestionar los cambios personales que realizó en las páginas del sistema. En esta ficha, también puede restablecer las llamadas de características (es decir, las ventanas emergentes que introducen nuevas características de sistema). Se le volverá a alertar de las características anteriormente encontradas.

> [!NOTE]
> Si la característica [Vistas guardadas](saved-views.md) está activada, puede ver y gestionar sus personalizaciones seleccionando **Personalización** en el panel Acciones de la página **Opciones de usuario**.

## <a name="implicit-personalizations"></a>Personalizaciones implícitas

Las personalizaciones implícitas son personalizaciones que se realizan simplemente interactuando con controles que guardan su estado visible actual.

- **Anchos de columnas de cuadrícula**: puede ajustar el ancho de una columna en una cuadrícula seleccionando la barra de tamaño de la izquierda o la derecha del encabezado de la columna y desplazándola hacia la izquierda o hacia la derecha hasta que la columna tenga el ancho que desee. La aplicación almacena el ancho que establece para una columna. A continuación, cambia el tamaño de la columna según dicho ancho cada vez que abra la página que incluye la cuadrícula.
- **Totales de columna de cuadrícula**: (solo disponible con el nuevo control de cuadrícula habilitado.) Puede decidir si se debe mostrar o no un total en la parte inferior de cualquier columna numérica en una cuadrícula, así como si el pie de página de la cuadrícula es visible. La aplicación almacena estos datos para que estas preferencias se recuerden la próxima vez que abra la página. Consulte el tema [Capacidades de cuadrícula](grid-capabilities.md) para más información. 
- **Fichas Desplegables**: algunas páginas tienen secciones extensibles llamadas *Fichas Desplegables*. La aplicación almacena información sobre las fichas desplegables que usted ha expandido y contraído. A continuación, cada vez que abra la página, las mismas fichas desplegables se ampliarán o contraerán en función de su última interacción con la página. En algunos casos, puede ayudar a mejorar el rendimiento del sistema contrayendo una ficha desplegable, porque la aplicación no tiene que recuperar información para dicha ficha desplegable hasta que se extienda. Como se explica más adelante este tema, también puede cambiar el orden de las fichas desplegables de una página.
- **Cuadros informativos**: algunas páginas tienen un panel de **información relacionada** que muestra la información de solo lectura relacionada con el asunto actual de la página. Cada sección del panel **Información relacionada** se conoce como *cuadro informativo*. Puede ocultar o mostrar el panel **Información relacionada** y también puede ampliar o contraer cuadros informativos individuales. La aplicación almacena estas preferencias. A continuación, cada vez que abra a la página, se expandirán o contraerán el panel **información relacionada** y los cuadros informativos individuales, en función de su última interacción con la página. En algunos casos, puede ayudar a mejorar el rendimiento del sistema contrayendo un cuadro informativo, porque la aplicación no tiene que recuperar información para dichos cuadros informativos hasta que se extiendan.
- **Paneles de acciones** – Un *panel Acciones* aparece cerca de la parte superior de la mayoría de las páginas. El panel Acciones contiene botones para muchas de las acciones que puede realizar en la página actual. Estos botones se organizan a menudo en fichas. Puede "anclar" el panel Acciones abierto completo o puede contraerlo de forma predeterminada. A continuación, cada vez que abra la página, el panel Acciones se abrirá o contraerá en función de su última interacción con la página. Si ha anclado el panel Acciones abierto, aparecerá la última ficha utilizada.
- **Filtros rápidos** – Un *filtro rápido* aparece sobre muchas cuadrículas. El filtro rápido le permite filtrar la cuadrícula, en función de una columna seleccionada. La aplicación almacena la columna en la que ha aplicado el filtro. A continuación, la próxima vez que abra la página que incluye la cuadrícula, la cuadrícula se filtrará en la misma columna. Sin embargo, puede seleccionar una columna diferente para filtrar la cuadrícula.
- **Filtros de encabezado de columna** Cuando se filtra una cuadrícula con los *Filtros de encabezado de columna*, puede cambiar al operador del filtro según sea necesario para encontrar los datos que desee. Por ejemplo, puede cambiar el operador de **comienza con** a **es exactamente**. Cada vez que se utiliza un filtro de encabezado de columna y se modifica el operador del filtro, la aplicación almacena el cambio. A continuación restablecerá el operador del filtro la próxima vez que se filtre esa columna.
- **Panel de exploración** Puede abrir el *Panel de exploración* seleccionando el botón **Expandir el panel de navegación** en el panel superior izquierdo de cualquier página. (En ocasiones se hace referencia al botón _**Menú**_ como *hamburguesa*, *menú de la hamburguesa* o *botón de la hamburguesa*.). Puede anclar el panel de navegación abierto o puede mantenerlo contraído de forma predeterminada. Tras anclar y mantener abierto el panel de navegación, la aplicación se mantendrá abierto hasta que lo contraigan.

## <a name="explicit-personalizations"></a>Personalizaciones explícitas

Las distintas personas y empresas tienen una perspectiva diferente sobre los datos que son más importante para ellas, y los datos que no requieren para la forma en que ejecutan su negocio. Pede ajustar la manera en la que la información se ordena o cómo se interactúa con ella. También puede especificar que cierta información debe mantenerse oculta. Estas capacidades son clave para tener una experiencia personal y productiva, y son ejemplos de personalizaciones explícitas. Las personalizaciones explícitas son aquellas personalizaciones que se realizan explícitamente con la intención de cambiar el aspecto o el comportamiento de un elemento o de una página.

### <a name="shortcut-menu-options"></a>Opciones del menú de acceso directo

Los menús de acceso directo proporcionan algunas formas de cambiar explícitamente una página para adaptarse mejor a sus requisitos o los requisitos de la empresa. (Un menú contextual también se conoce como *menú de botón secundario* o *menú contextual*).

Algunos de los cambios más habituales y más importantes que se pueden realizar en una página están disponibles directamente como opciones del menú contextual. Por ejemplo, a partir de la actualización 17 de la plataforma, si quiere agregar u ocultar las columnas en una cuadrícula, solo tiene que hacer clic con el botón secundario en un encabezado de la columna y, a continuación, seleccionar **Agregar columnas** u **Ocultar esta columna**.

Además, los tipos más básicos de personalización explícita están disponibles haciendo clic con el botón secundario en un elemento y después seleccionando **Personalizar**. (Tenga en cuenta que no todos los elementos en su página se pueden personalizar.) Si usa este método de personalización, aparecerá la ventana de la propiedad del elemento.

![Personalización de las propiedades de un elemento](./media/cli-element-property-window.png)

Puede usar la ventana de propiedad para personalizar un elemento de las siguientes formas:

- Cambiar la etiqueta del elemento.
- Ocultar el elemento para que no se muestre en la página. Los datos del campo no se eliminan ni se modifican. La información simplemente deja de aparecer en la página.
- Incluir la información en la sección de resumen de la ficha desplegable (si el artículo se encuentra en una ficha desplegable).
- Omitir el campo de modo que nunca reciba el enfoque cuando se desplace por la página.
- Evitar que los datos en el campo (de cualquier registro) se editen.
- Designe un campo para que sea necesario para la entrada de datos. Si no se ha introducido ningún valor en este campo, aparecerá con un borde rojo y un asterisco para indicar este estado. Esta opción solo está disponible a partir de la versión 10.0.11 cuando las características [Vistas guardadas](saved-views.md) y **Designar campos según sea necesario utilizando personalización** están habilitadas.

La ventana de la propiedad puede incluir otras capacidades de personalización, en función del elemento. Por ejemplo, la ventana de propiedad de un mosaico puede permitirle ascender ese mosaico a un panel, y la ventana de la propiedad de un panel puede dejarle crear una nueva área de trabajo en el panel.

### <a name="the-personalization-toolbar"></a>La barra de herramientas de personalización

Si desea implementar varios cambios en una página o hacer cambios que no están disponibles con otros mecanismos (como reordenar elementos), puede utilizar la barra de herramientas **Personalización**. Para abrir la barra de herramientas **Personalización**, siga uno de estos pasos:

- Seleccione **Personalizar esta página** en la ventana de propiedades del artículo.
- En el panel Acciones de la página, seleccione **Personalizar esta página** en el grupo **Personalizar** en la ficha **Opciones**.
- Seleccione el botón **Configuración** (el símbolo de engranaje) en la barra de navegación y, a continuación, seleccione **Personalizar**.

[![Barra de herramientas de personalización](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Navegación por la página

Cuando la barra de herramientas **Personalización** está abierta, la página subyacente es de solo lectura (es decir no puede editar datos), pero sigue siendo interactiva. Específicamente, puede ampliar o contraer el panel **Información relacionada**, cambiar de ficha y expandir o contraer secciones de la misma manera que realiza normalmente dichas acciones en la página. Para aplicar una personalización a una sección o ficha que se puede contraer (por ejemplo para ocultar una ficha desplegable), basta con seleccionar el botón que aparece junto a la sección o la ficha que se puede contraer cuando enfoca con el teclado o cuando pasa el mouse sobre ella.

#### <a name="personalization-tools"></a>Herramientas de personalización

Las siguientes herramientas están disponibles en la barra de herramientas **Personalización**:

- Utilice la herramienta **Seleccionar** praa seleccionar y cambiar las propiedades de un elemento. Para utilizar esta herramienta, seleccione el botón **Seleccionar** en la barra de herramientas, y seleccione el artículo deseado. La ventana de la propiedad del elemento aparece y podrá modificar las propiedades de dicho elemento. Es posible repetir el proceso para otros elementos que se pueden personalizar en la página. Tenga en cuenta que algunas propiedades de personalización no pueden estar disponibles en algunos casos. Por ejemplo, no puede bloquear un campo que es necesario.
- Use la herramienta **Ocultar** para ocultar un elemento de la página. Para utilizar esta herramienta, seleccione el botón **Ocultar** en la barra de herramientas, y seleccione el artículo que desea ocultar. Al usar la herramienta **Ocultar**, todos los elementos que se ocultan actualmente se hacen visibles pero se muestran en un contenedor sombreado. A continuación puede hacer que un elemento sea visible seleccionándolo. Para ver el aspecto de la página con los artículos ocultos, cambie a otra herramienta de personalización.
- Use la herramienta **Agregar un campo** para agregar un campo en la página. Al usar esta herramienta, puede agregar solamente los campos que forman parte de la definición de la página. Para obtener información sobre cómo crear nuevos campos que no son parte de la definición de la página actual, consulte [Crear y trabajar con campos personalizados](user-defined-fields.md). Tras seleccionar el botón **Agregar un campo** en la barra de herramientas, primero debe seleccionar el grupo o el área donde desee agregar un campo. Un cuadro de diálogo muestra la lista de campos relacionados con el grupo o el área que ha seleccionado. En el cuadro de diálogo, seleccione uno o varios campos para añadirlos y luego seleccione **Insertar**. Para quitar un campo que ha agregado anteriormente, repita el proceso, pero desactive la selección del campo en el cuadro de diálogo.
- Elija la herramienta **Mover** si desea mover un elemento a otra ubicación dentro del grupo actual de elementos. Tenga en cuenta que no puede mover un elemento fuera del grupo principal. Para utilizar esta herramienta, seleccione el botón **Mover** en la barra de herramientas, y seleccione el artículo que desea mover. Al seleccionar un elemento, la aplicación determina las ubicaciones adónde se puede mover el elemento. Estas ubicaciones se conocen como *zonas de colocación*. Mientras arrastra el elemento dentro del grupo actual, todas las zonas de colocación se muestran como una línea en color y negrita junto al área donde el elemento se puede colocar.
- Use la herramienta **Omitir** para quitar un elemento de la secuencia del tabulador del teclado de la página. Al seleccionar el botón **Omitir** de la barra de herramientas, todos los elementos que se omiten se muestran en un contenedor sombreado. Puede agregar o quitar interactivamente campos de la secuencia de fichas.
- Utilice la herramienta **Mostrar en encabezado** cuando desee que aparezca un campo en la sección de resumen de la ficha desplegable. Al seleccionar el botón **Mostrar en encabezado** en la barra de herramientas, todos los campos que se seleccionan como campos de resumen se muestran en un contenedor sombreado. Puede agregar interactivamente campos al resumen de ficha desplegable y quitar campos seleccionando los campos.
- Use la herramienta **Obligatorio** para designar un elemento como obligatorio para la entrada de datos. Al seleccionar el botón **Obligatorio** de la barra de herramientas, todos los elementos que se han personalizado para ser obligatorios se muestran en un contenedor sombreado. Puede hacer que vuelvan a ser no obligatorios. Esta opción solo está disponible a partir de la versión 10.0.12 cuando está habilitada la característica **Designar campos según sea necesario utilizando personalización**.

    > [!IMPORTANT]
    > La versión 10.0.12 es una versión preliminar. El contenido y la funcionalidad están sujetos a cambios. Para obtener más información acerca las versiones preliminares, consulte [Disponibilidad de actualización del servicio](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/public-preview-releases).

- Elija la herramienta **Bloquear** para marcar un elemento como editable o no editable. Al seleccionar el botón **Bloquear** de la barra de herramientas, todos los elementos que no se pueden editar en ese momento se muestran en un contenedor sombreado. A continuación puede hacer que vuelvan a ser editables. Tenga en cuenta que algunos campos son necesarios y no se pueden convertir en no editables. Un símbolo de candado aparece junto a dichos campos.
- Utilice el botón **Agregar una aplicación desde Power Apps** para insertar una aplicación que se creó usando Microsoft Power Apps en la página. Para obtener información detallada acerca de cómo insertar una aplicación de Power Apps en una página, consulte [Integrar aplicaciones desde Power Apps](embed-power-apps.md). Esta opción solo está disponible cuando la característica [Vistas guardadas](saved-views.md) está deshabilitada.  
- Utilice el botón **Agregar una aplicación** para insertar una aplicación, ya sea una creada desde Microsoft Power Apps o un tercero, en la página. Esta opción solo está disponible cuando la característica [Vistas guardadas](saved-views.md) está habilitada. 
- Utilice la herramienta **Borrar** para restablecer la página a su valor predeterminado, estado instalado. Todas las personalizaciones en la página actual se desactivarán. No existen una acción de deshacer. Por lo tanto, use esta herramienta solo si está seguro que desea restablecer la página.
- Use la herramienta **Importación** para cargar una personalización de un archivo que usted o otro usuario creó anteriormente. Al importar las personalizaciones para una página, puede seleccionar si deben agregarse o reemplazar a todas sus personalizaciones existentes en la página. No existen una acción de deshacer. Por lo tanto, tras importar personalizaciones, debe borrar manualmente o deshacer los cambios que no desee.
- Use la herramienta **Exportar** para guardar las personalizaciones de la página en un archivo. Puede compartir sus personalizaciones con otros usuarios. Estos usuarios solo tienen que importar el archivo que contiene sus personalizaciones de la página.
- Seleccione el botón **Cerrar** para cerrar la barra de herramientas **Personalización** y devuelva la página a su estado interactivo anterior.

Tradicionalmente, cuando se utiliza la barra de herramientas **Personalización**, sus personalizaciones se hacen efectivas a medida que se crean. Sin embargo, si está activada la característica [Vistas guardadas](saved-views.md), debe guardar específicamente las personalizaciones en la vista que decida.

En algunos casos, cuando seleccione una herramienta, un símbolo de candado aparecerá al lado de un elemento. Este símbolo indica que no podrá modificar las propiedades del elemento relacionadas con la herramienta seleccionada, ya que los cambios realizados a dichas propiedades impedirían que la página funcione correctamente.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Agregar un mosaico, lista o vínculo a un espacio de trabajo

Para algunas páginas que incluyan listas, la característica de personalización **Agregar al espacio de trabajo** está disponible en el grupo **Personalizar** en la ficha **Opciones** del panel Acciones. Esta característica permite insertar la información pertinente de lista actual a un espacio de trabajo específico. La información que aparece en el espacio de trabajo se puede basar en la lista completa o en una versión filtrada y guardada de la lista. También puede especificar si la información que aparece en el espacio de trabajo aparecerá como una lista, un mosaico de resumen que puede mostrar el número de elementos de la lista, o como un vínculo.

> [!NOTE]
> Si la característica [Vistas guardadas](saved-views.md) está activada, el contenido que se inserta en un espacio de trabajo se vincula directamente a una vista. La consulta de la vista se utiliza para capturar datos en el espacio de trabajo, y el mosaico o el vínculo correspondiente en el espacio de trabajo abre la página de esa vista para aplicar la consulta y las personalizaciones a la vista.

[![Agregar al espacio de trabajo](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Para agregar una lista a un espacio de trabajo, primero debe clasificar o filtrar la lista de la página para que muestre la información tal y como desee que aparezca en el área de trabajo. (Si está activada la característica Vistas guardadas, no podrá continuar hasta que guarde una vista que tenga estas condiciones.) A continuación, seleccione **Agregar al espacio de trabajo**. Seleccione un área de trabajo y, a continuación, en el campo **Presentación**, seleccione **Lista**. Tras seleccionar **Configurar**, aparecerá un cuadro de diálogo, donde puede seleccionar las columnas que deben aparecer en la lista del área de trabajo. También puede especificar la etiqueta que se debe usar para la lista del espacio de trabajo.
- Para agregar un mosaico a un espacio de trabajo, primero debe filtrar la lista de la página para que muestre los datos que debe resumir o a los que quiere tener acceso rápido. (Si está activada la característica Vistas guardadas, no podrá continuar hasta que guarde una vista que tenga estas condiciones.) A continuación, seleccione **Agregar al espacio de trabajo**. Seleccione un área de trabajo y, a continuación, en el campo **Presentación**, seleccione **Mosaico**. Tras seleccionar **Configurar**, aparece un cuadro de diálogo donde puede especificar la etiqueta que se debe usar para el mosaico en el espacio de trabajo. También puede especificar si el mosaico debe mostrar un recuento. Una vez que el mosaico se agrega al espacio de trabajo, puede seleccionarlo para abrir la página actual del espacio de trabajo. Puede ver la lista filtrada que está asociada al mosaico.
- Para agregar un vínculo a un espacio de trabajo, primero filtre la lista de la página para que muestre los datos que le interesan. (Si está activada la característica Vistas guardadas, no podrá continuar hasta que guarde una vista que tenga estas condiciones.) A continuación, seleccione **Agregar al espacio de trabajo**. Seleccione un área de trabajo y, a continuación, en el campo **Presentación**, seleccione **Vínculo**. Tras seleccionar **Configurar**, aparece un cuadro de diálogo donde puede especificar la etiqueta que debe utilizarse para el vínculo. También puede especificar de forma opcional una etiqueta para una nueva sección que contenga este vínculo.

Una vez que ha agregado una lista, el mosaico o el vínculo a un espacio de trabajo, puede abrir dicho espacio de trabajo y reordenar los elementos que contiene tal y como desee.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Agregar un resumen de un espacio de trabajo a un panel de información

Algunas áreas de trabajo contienen mosaicos de recuento (es decir, mosaicos que contienen), y es posible que desee que dichos mosaicos aparezcan también en el panel. En un espacio de trabajo, haga clic con el botón secundario en un mosaico de recuento, seleccione **Personalizar**y, a continuación, seleccione **Anclar al panel de información** en la ventana de propiedades del mosaico. La próxima vez que abra y actualice el panel de información seleccionado, verá el recuento debajo del mosaico de navegación del espacio de trabajo. Puede seleccionar dicho recuento para ir directamente a los datos que representa.

### <a name="personalizing-your-dashboard"></a>Personalización del panel de información

El panel de información suele ser la primera página que verá al abrir la aplicación. Puede personalizar el panel de información de modo que muestre solo los mosaicos del espacio de trabajo que desea ver. También puede reorganizar los mosaicos de modo que se encuentren en el orden que prefiere consultarlos, cambiar el nombre de los mosaicos de navegación de espacio de trabajo, o agregar un mosaico de espacio de trabajo nuevo.

Para personalizar el panel de información, haga clic con el botón secundario en cualquier mosaico y, a continuación seleccione **Personalizar** para abrir la ventana de la propiedad del mosaico.

- Si desea ocultar o cambiar el nombre del mosaico seleccionado, puede realizar ese cambio directamente en la ventana de la propiedad.
- Si desea reordenar los mosaicos del espacio de trabajo, en la ventana de la propiedad, seleccione **Personalizar esta página** para abrir la barra de herramientas **Personalización**. Podrá entonces usar la herramienta **Mover** para reorganizar los mosaicos tal y como desee.
- Para agregar un nuevo mosaico del espacio de trabajo, en la ventana de la propiedad, seleccione **Agregar un espacio de trabajo**. Se creará un nuevo mosaico del espacio de trabajo en la parte inferior del panel de información. Puede cambiar el nombre de este nuevo mosaico de área de trabajo tal y como desee. También puede agregar listas, mosaicos y vínculos al área de trabajo tal y como se describe en la sección [Agregar listas, mosaicos o vínculos a las áreas de trabajo](#adding-a-tile-list-or-link-to-a-workspace) de este tema.


## <a name="sharing-personalizations"></a>Uso compartido de personalizaciones
Tras personalizar una página, puede compartir sus personalizaciones con otros usuarios exportando la página personalizada. A continuación puede pedir a los demás usuarios que abran la página personalizada e importen el archivo de personalización que ha creado. Como alternativa, puede dar sus personalizaciones a un usuario que tenga privilegios de administración. Ese usuario puede aplicar su archivo de personalización a muchos usuarios al mismo tiempo, utilizando la página de administración **Personalización**.

## <a name="administration-of-personalizations"></a>Administración de personalizaciones
La página **Personalización** es el centro de administración de personalizaciones a nivel de la organización. El contenido y las capacidades de esta página dependen de si se ha habilitado la característica **Vistas guardadas**.  

Para clientes que han habilitado la característica **Vistas guardadas**, consulte la sección "Gestión global de vistas" en el tema [Vistas guardadas](saved-views.md).  

Para los clientes que no hayan activado todavía la característica [Vistas guardadas](saved-views.md), esta página tiene cuatro pestañas:

- **Aplicar**: puede importar o seleccionar una personalización para uno o varios usuarios. Para aplicar una personalización a uno o varios usuarios, seleccione primero un rol y a los usuarios con dicho rol. A continuación seleccione una personalización para aplicarla a los usuarios seleccionados o importe un archivo de personalización. La personalización se validará y aplicará a todos los usuarios seleccionados la próxima vez que abran la página seleccionada.
- **Borrar**: puede borrar todas las personalizaciones de una página o espacio de trabajo de uno o varios usuarios. Primero seleccione una página o espacio de trabajo para ver la lista de los usuarios que la han personalizado. A continuación, seleccione los usuarios que deberían tener borradas las personalizaciones de esa página o espacio de trabajo, y seleccione **Borrar**. Se eliminan todas las personalizaciones que los usuarios seleccionados han aplicado a la página o al espacio de trabajo seleccionado. Esta acción no se puede deshacer. Sin embargo, si se guardó una personalización para la página o el espacio de trabajo, se podrá volver a importar dicha personalización.
- **Usuarios**: seleccione un usuario para ver la lista de páginas que este usuario ha personalizado. A continuación puede habilitar o deshabilitar la capacidad del usuario seleccionado para utilizar personalizaciones para páginas determinadas o el sistema completo. También puede importar, exportar o borrar una personalización para el usuario. Además, puede restablecer las llamadas de características del usuario. En este caso, si el usuario descartó anteriormente algunas ventanas emergentes que introducían nuevas características, aparecerán de nuevo la próxima vez que el usuario se encuentre con aquellas características.
- **Sistema:** – Puede desactivar temporalmente la personalización para todos los usuarios del sistema. En este caso, todas las personalizaciones se eliminan para todos los usuarios, y todas las páginas se restablecen a su estado predeterminado. Si vuelve a habilitar más tarde la personalización, todas las personalizaciones se volverán a aplicar. También puede desactivar permanentemente todas las personalizaciones para todos los usuarios del sistema. No es posible recuperar las personalizaciones que se han eliminado. Por lo tanto, antes de realizar esta tarea, asegúrese de exportar todas las personalizaciones que pueda querer más tarde.

## <a name="personalizing-inventory-dimensions"></a>Personalización de dimensiones de inventario

Al personalizar la configuración de dimensiones de inventario en una página, tenga en cuenta los valores que se han creado usando la opción **Dimensión de visualización**. Por ejemplo, puede usar la personalización para ocultar una columna de la dimensión de inventario del número de lote, pero la columna aparecerá la próxima vez que la página esté abierta. Este comportamiento se produce porque la configuración de **Visualización de dimensiones** controla las columnas de la dimensión de inventario que se muestran. Los ajustes de **visualización de dimensiones** se aplican a todas las páginas y estos valores anulan cualquier configuración personalizada de campos de dimensión de inventario en las páginas individuales.

En consecuencia, en el ejemplo anterior, si no desea que la columna de la dimensión de inventario de número de lote aparezca en una página, debe borrar dicha dimensión como parte de la opción **Dimensiones de la pantalla** para esa página.
