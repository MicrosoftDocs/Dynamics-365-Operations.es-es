---
title: Diseños de pantalla para el punto de venta (POS)
description: Este tema proporciona información sobre los diseños de pantalla para experiencias con Dynamics 365 Retail point of sale (POS).
author: jblucher
manager: AnnBe
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c4636f5a023786e3871eb5d907e2e9546181827a
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811789"
---
# <a name="screen-layouts-for-the-point-of-sale-pos"></a>Diseños de pantalla para el punto de venta (POS)

[!include [banner](includes/banner.md)]

Este tema proporciona información sobre los diseños de pantalla para experiencias con Dynamics 365 Retail point of sale (POS).

La interfaz de usuario (IU) de Retail POS se puede configurar mediante una combinación de perfiles visuales y diseños de pantalla que se asignan a tiendas, registros y/o usuarios.

La siguiente ilustración muestra las relaciones entre las distintas entidades que comprenden los aspectos configurables de la IU del sistema PDV.

![Entidades de diseño de pantalla de PDV](../retail/media/POS-layout-configuration-entities-diagram.png)

## <a name="visual-profile"></a>Perfil visual

Los perfiles visuales se asignan a registros y especifican los elementos visuales que son específicos del registro y que se comparten entre los usuarios. Cada usuario que inicia sesión en el registro ve el mismo tema, colores e imágenes.

![Pantalla de bienvenida de PDV con tema claro](../retail/media/POS-Welcome-Screen-with-Light-theme.png)

![Pantalla de transacción de PDV con tema oscuro](../retail/media/POS-Transaction-Screen-with-Dark-theme.png)

- **Número de perfil** – El número del perfil es el identificador exclusivo del perfil visual.
- **Descripción** – Puede especificar un nombre descriptivo que ayude a identificar el perfil correcto para su situación.
- **Tema** – Puede seleccionar entre los temas de aplicación claro u oscuro. El tema afecta a los colores de fuente y de fondo en toda la aplicación.
- **Color de acento** – El color de acento se utiliza en el sistema PDV para distinguir o resaltar elementos visuales específicos como mosaicos, botones de comandos e hipervínculos. Normalmente, estos elementos se pueden accionar.
- **Color de encabezado** – Puede configurar el color del encabezado de la página para cumplir los requisitos de las marcas del minorista. Esta función solo está disponible en Retail, versión 1611.
- **Mostrar fecha/hora** - Cuando se activa, la fecha y hora actuales se mostrará en el encabezado del PDV.
- **Fondo de inicio de sesión** – Puede especificar una imagen de fondo para la pantalla de inicio de sesión. El tamaño de archivo de las imágenes de fondo se debe mantener lo más pequeño posible, ya que el almacenamiento y la carga de archivos grandes podría afectar al comportamiento y al rendimiento de la aplicación.
- **Fondo de la aplicación** – Puede especificar una imagen de fondo que se utiliza en lugar del color liso del tema en toda la aplicación. En cuanto a los fondos de inicio de sesión, el tamaño del archivo debe mantenerse lo más pequeño posible.

## <a name="screen-layouts"></a>Diseños de pantalla

Las configuraciones del diseño de pantalla determinan las acciones, el contenido y la posición de los controles de la interfaz de usuario en la pantalla de bienvenida del PDV y en la pantalla **Transacción**.

![Vista Diseño de pantalla de PDV](../retail/media/POS-Screen-Layout-View.png)

- **Pantalla de bienvenida** – En la mayoría de los casos, la pantalla de bienvenida es la página que verán los usuarios la primera vez que inicien sesión en el PDV. La pantalla de bienvenida puede constar de una imagen de marca y de cuadrículas de botones que proporcionan acceso a las operaciones del PDV. Normalmente, las operaciones que no son específicas de la transacción actual se colocan en esta pantalla.

    ![Pantalla de bienvenida de PDV](../retail/media/POS-Welcome-Screen.png)

- **Pantalla de transacción** – La pantalla **Transacción** es la pantalla principal del PDV para procesar transacciones de venta y pedidos. El contenido y el diseño se configuran mediante el diseñador de pantalla.

    ![Pantalla de transacción del PDV](../retail/media/POS-Transaction-Screen.png)

- **Pantalla de inicio predeterminada** – Algunos minoristas prefieren que los cajeros vayan directamente a la pantalla **Transacción** después de iniciar sesión. La configuración **Pantalla de inicio predeterminada** le permite especificar la pantalla predeterminada que aparece después de iniciar sesión para cada diseño de pantalla.

### <a name="assignment"></a>Asignación

Los diseños de pantalla se pueden asignar a la tienda, el registro o el nivel de usuario. La asignación del usuario anula las asignaciones del registro y tienda, y la asignación del registro anula la asignación de la tienda. En una situación sencilla en la que todos los usuarios utilizan el mismo diseño, independientemente del registro o el rol, el diseño de pantalla solo puede establecerse en el nivel de tienda. En escenarios en los que registros o usuarios específicos necesiten diseños especializados, se pueden asignar esos diseños.

### <a name="layout-sizes"></a>Tamaños de diseño

La mayoría de aspectos de la interfaz de usuario del sistema PDV son dinámicos, y el diseño cambia de tamaño automáticamente y se ajusta en función del tamaño y la orientación de la pantalla. Sin embargo, la pantalla **Transacción** de PDV debe configurarse para cada resolución de pantalla prevista.

Al iniciar, la aplicación del PDV selecciona automáticamente el tamaño de diseño más cercano que está configurado para el dispositivo. Un diseño de pantalla también puede contener configuraciones para los modos horizontal y vertical, y para dispositivos compactos y de tamaño completo. Por tanto, se puede asignar a los usuarios un diseño monopantalla que funciona con diferentes tamaños y factores de formulario que se utilizan en la tienda.

![Tamaños de diseño de PDV](../retail/media/POS-Screen-Layout-Sizes.png)

- **Nombre** – Puede introducir un nombre descriptivo para identificar el tamaño de la pantalla.
- **Tipo de diseño** – La aplicación de PDV puede mostrar su interfaz de usuario en distintos modos para ofrecer la mejor experiencia del usuario en un dispositivo determinado.

    - **Modern POS – Completo** – Los diseños completos suelen emplearse mejor para pantallas más grandes como monitores de escritorio y tabletas. Puede seleccionar los elementos de la interfaz de usuario que desea incluir, especificar el tamaño y la posición de esos elementos y configurar sus propiedades detalladas. Los diseños completos admiten la configuración vertical y horizontal.
    - **Modern POS – Compacto** – Los diseños compactos suelen ser mejores para teléfonos y tabletas pequeñas. Las posibilidades de diseño en los dispositivos compactos son limitadas. Puede configurar las columnas y los campos para los paneles de totales y de recepción.

- **Ancho/Alto** – Estos valores representan el tamaño efectivo de pantalla, en píxeles, que se espera para el diseño. Recuerde que algunos sistemas operativos utilizan una escala para pantallas de alta resolución.

> [!TIP]
> Puede conocer el tamaño de diseño necesario para una pantalla del PDV viendo la resolución en la aplicación. Inicie el PDV y vaya **Configuración \> Información sobre la sesión**. El PDV muestra el diseño de pantalla que se carga actualmente, el tamaño de diseño y la resolución de la ventana de la aplicación.

![Tamaños de diseño de PDV](../retail/media/POS-Session-Information.png)

### <a name="button-grids"></a>Cuadrículas de botones

Para cada tamaño de diseño de un diseño de pantalla, puede configurar y asignar cuadrículas de botones para la pantalla de bienvenida de PDV y la pantalla **Transacción**. Las cuadrículas de botones para la pantalla de bienvenida se disponen automáticamente de izquierda a derecha, del número inferior (pantalla de bienvenida 1) al número más alto.

En diseños de PDV completa, la colocación de las cuadrículas de botones se especifica en el diseñador de pantalla.

En diseños de PDV compacto, las cuadrículas de botones se disponen automáticamente de arriba a abajo, del número inferior (pantalla de transacción 1) al número más alto. Pueden obtener acceso en el menú **Acciones**.

![Cuadrículas de botones de diseño compacto](../retail/media/Compact-View-Button-Grids.png)

### <a name="images"></a>Imágenes

Para cada tamaño de diseño de un diseño de pantalla, puede especificar imágenes para incluirlas en la interfaz de usuario del sistema PDV. Para los diseños de PDV completos, se puede especificar una sola imagen para la pantalla de bienvenida. En la izquierda aparece una imagen como el primer elemento de la interfaz de usuario. En la pantalla **Transacción**, las imágenes se pueden utilizar como imágenes de pestaña o como un logotipo. Los diseños de PDV compactos no utilizan estas imágenes.

### <a name="screen-layout-designer"></a>Diseñador de pantalla

El diseñador de pantalla le permite configurar diversos aspectos de la pantalla **Transacción** de PDV para cada tamaño de diseño, en modos horizontal y vertical, y para los diseños completo y compacto. El diseñador de pantalla emplea la tecnología de implementación ClickOnce para descargar, instalar e iniciar la última versión de la aplicación cada vez que los usuarios acceden a ella. Asegúrese de comprobar los requisitos del explorador para ClickOnce. Algunos exploradores, como Google Chrome, requieren extensiones.

> [!IMPORTANT]
> Debe configurar un diseño de pantalla para cada tamaño de diseño que se defina y que se utilice en el PDV.

### <a name="full-layout-designer"></a>Diseñador completo

El diseñador completo permite a los usuarios arrastrar controles de la interfaz de usuario en la pantalla **Transacción** de PDV y configurar los valores de estos controles.

![Diseñador completo de PDV (modo horizontal)](../retail/media/POS-Full-Layout-Designer-Landscape.png)

- **Importar diseño/Exportar diseño** – Puede exportar e importar diseños de pantalla de PDV como archivos XML, de manera que pueda volver a utilizarlos y compartirlos con facilidad entre entornos. Es importante que importe diseños para los tamaños de diseño correctos. De lo contrario, puede que los elementos de interfaz de usuario no se ajusten correctamente en la pantalla.
- **Horizontal/Vertical** – Si el dispositivo de PDV permite a los usuarios cambiar entre los modos horizontal y vertical, debe definir un diseño de pantalla para cada modo. El PDV detecta automáticamente la rotación de la pantalla y muestra el diseño correcto.
- **Cuadrícula de diseño** – El diseñador de PDV emplea una cuadrícula de 4 píxeles. Los controles de la interfaz de usuario "se ajustan" a la cuadrícula para ayudarle a alinear correctamente el contenido.
- **Zoom del diseñador** – Puede acercar o alejar la vista de diseñador para ver mejor el contenido en la pantalla de PDV. Esta función resulta útil cuando la resolución de pantalla en el sistema PDV difiere significativamente de la resolución de la pantalla que se utiliza en el diseñador.
- **Mostrar/ocultar barra de navegación** – Para diseños de PDV completos, puede seleccionar si la barra de navegación izquierda es visible en la pantalla **Transacción**. Esta función resulta útil para pantallas que tiene una resolución más baja. Para establecer la visibilidad, haga clic con el botón derecho en la barra de exploración del diseñador, y active o desactive la casilla de verificación **Siempre visible**. Si la barra de navegación está oculta, los usuarios del PDV pueden seguir teniendo acceso mediante el menú de la parte superior izquierda.

    ![Mostrar/ocultar barra de navegación](../retail/media/Navigation-Bar.PNG)

- **Controles de PDV** – El diseñador de PDV admite los siguientes controles. Puede configurar muchos controles haciendo clic con el botón derecho y usando el menú contextual.

    ![Controles de interfaz de usuario de PDV](../retail/media/POS-UI-Controls.png)

    - **Teclado numérico** – El teclado numérico es el mecanismo principal para la entrada de usuario en la pantalla **Transacción** del PDV. Puede configurar el control para que se muestre el teclado numérico completo. Esta opción es ideal para dispositivos con pantalla táctil. De forma alternativa, puede configurarla para que se muestre solo el campo de entrada. En este caso, se utiliza un teclado físico para la entrada. Los ajustes del teclado numérico están disponibles solo en los diseños completos. Para diseños compactos, el teclado numérico completo siempre se muestra en la pantalla **Transacción**.
    - **Panel de totales** – Puede configurar el panel de totales en una o dos columnas para mostrar valores como el recuento de líneas, el importe de descuento, los gastos, el subtotal y los impuestos. Los diseño compactos solo admiten una única columna.
    - **Panel de recepción** – El panel de recepción contiene las líneas de ventas, las líneas de pago y la información de entrega para los productos y servicios que se procesan en el PDV. Puede especificar columnas, anchos y posiciones. En diseños compactos, también puede configurar información adicional que aparece en la fila debajo de la línea principal.
    - **Tarjeta de cliente** – La tarjeta del cliente muestra información sobre el cliente que está asociado a la transacción actual. Puede configurar la tarjeta del cliente para que se oculte o muestre la información adicional.
    - **Control de fichas** – Puede agregar el control de fichas a un diseño de pantalla y, a continuación, colocar otros controles como el teclado numérico, la tarjeta de cliente o las cuadrículas de botones, dentro de la ficha. El control de fichas es un contenedor que le ayuda a introducir más contenido en la pantalla. El control de fichas solo está disponible en los diseños completos.
    - **Imagen** – Puede usar el control de imagen para mostrar el logotipo de la tienda u otra imagen de marca en la pantalla **Transacción**. El control de imagen solo está disponible en los diseños completos.
    - **Productos recomendados** - Si el control de productos recomendados está configurado para el entorno, muestra las sugerencias de productos del aprendizaje automático.
    - **Control personalizado** – El control personalizado actúa como un marcador de posición en el diseño de pantalla y le permite reservar espacio para el contenido personalizado. El control personalizado solo está disponible en los diseños completos.

### <a name="compact-layout-designer"></a>Diseñador de diseño compacto

Al igual que el diseñador de diseño completo, el diseñador de diseño compacto le permite configurar el diseño de pantalla de PDV para teléfonos y tabletas pequeñas. Sin embargo, en este caso, el diseño en sí es fijo. Puede configurar los controles en el diseño haciendo clic con el botón derecho y usando el menú contextual. Sin embargo, no puede usar la función de arrastrar y colocar para contenido adicional.

![Diseñador de diseño compacto](../retail/media/Compact-Layout-Designer.png)

### <a name="button-grid-designer"></a>Diseñador de cuadrícula de botones

El diseñador de cuadrícula de botones le permite configurar botones de cuadrícula que se pueden usar en la pantalla de bienvenida de PDV y la pantalla **Transacción** para diseños completos y compactos. La misma cuadrícula de botones se puede usar en diseños y tipos de diseño. Al igual que el diseñador de pantalla, el diseño de cuadrícula de botones emplea la tecnología de implementación ClickOnce para descargar, instalar e iniciar la última versión de la aplicación cada vez que los usuarios acceden a ella. Asegúrese de comprobar los requisitos del explorador para ClickOnce. Algunos exploradores, como Google Chrome, requieren extensiones.

![Diseñador de cuadrícula de botones](../retail/media/Button-Grid-Designer.png)

- **Nuevo botón** – Haga clic para agregar un nuevo botón a la cuadrícula de botones. De forma predeterminada, los nuevos botones aparecen en la esquina superior izquierda de la cuadrícula. Sin embargo, puede organizar los botones arrastrándolos en el diseño.

    > [!IMPORTANT]
    > El contenido de la cuadrícula de botones se puede superponer. Cuando organice botones, asegúrese de que no oculten otros botones.

- **Nuevo diseño** – Haga clic para configurar automáticamente un diseño de cuadrícula de botones especificando el número de botones por fila y columna.
- **Propiedades de botón** – Puede configurar las propiedades del botón haciendo clic con el botón derecho en el botón y usando el menú contextual.

    > [!IMPORTANT]
    > Algunos ajustes de la cuadrícula de botones solo se aplican a Enterprise POS, no a Retail Modern POS o Cloud POS.

    ![Propiedades del botón de cuadrícula de botones](../retail/media/Button-grid-button-properties.png)

    - **Acción** – En la lista de operaciones de PDV aplicables, seleccione la operación que se invoca cuando se hace clic en el botón en el PDV.

        Para la lista de operaciones de PDV admitidas, consulte [Operaciones del punto de ventas (PDV) en línea y sin conexión](pos-operations.md).

    - **Parámetros de acción** – Algunas operaciones de PDV utilizan parámetros adicionales cuando se invocan. Por ejemplo, para la operación Agregar producto, los usuarios pueden especificar el producto que desea agregar.
    - **Texto del botón** – Especifique el texto que aparece en el botón del PDV.
    - **Ocultar texto del botón** – Utilice esta casilla de verificación para ocultar o mostrar el texto del botón. El texto del botón suele estar oculto para botones pequeños que solo muestran un icono.
    - **Información sobre herramientas** – Especifique texto de Ayuda adicional que aparece cuando los usuarios pasan el ratón por encima del botón.
    - **Tamaño en columnas/Tamaño en filas** – Puede especificar lo alto y ancho que es el botón.

        ![Tamaños de los botones del PDV en filas y columnas](../retail/media/POS-Button-Sizes-In-Rows-And-Columns.png)

    - **Fuente personalizada** – Cuando seleccione la casilla de verificación **Habilitar fuente personalizada para PDV**, puede especificar una fuente distinta de la fuente predeterminada del sistema para el PDV.
    - **Tema personalizado** – De forma predeterminada, los botones de PDV emplean el color de acento del perfil visual. Al seleccionar la casilla de verificación **Usar tema personalizado**, puede especificar colores adicionales.

        > [!NOTE]
        > Retail Modern POS y Cloud POS utilizan solo los valores **Color de fondo** y **Color de fuente**.

    - **Imagen de los botones** – Los botones pueden incluir imágenes o iconos. Seleccione entre las imágenes disponibles que se especifican en **Retail \> Configuración de canal \> Configuración de PDV \> PDV \> Imágenes**.

![Cuadrícula de botones de ejemplo en el PDV](../retail/media/Example-Button-Grid-In-POS.png)

## <a name="additional-resources"></a>Recursos adicionales

[Instalar el diseñador de punto de venta (TPV) de Retail](install-pos-layout-designer.md)
