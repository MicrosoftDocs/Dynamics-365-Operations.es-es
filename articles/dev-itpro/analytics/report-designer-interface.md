---
title: Interfaz del diseñador de informes
description: En este artículo se explica cómo navegar por el Diseñador de informes y cómo utilizar las diversas opciones para satisfacer sus requerimientos específicos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e9b77e2b510a72d1e3fe3c68c997d58245a86a27
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "368039"
---
# <a name="report-designer-interface"></a>Interfaz del diseñador de informes

[!include [banner](../includes/banner.md)]

En este artículo se explica cómo navegar por el Diseñador de informes y cómo utilizar las diversas opciones para satisfacer sus requerimientos específicos.

## <a name="report-designer-menu-commands"></a>Comandos de menú del diseñador de informes

En las siguientes tablas se describen los comandos y las opciones de menú que se pueden usar cuando se diseñan informes financieros. Algunos comandos y opciones de menú sólo están disponibles en circunstancias específicas. Por ejemplo, los comandos para promocionar y degradar las unidades de informe solo están disponibles cuando se modifica una definición del organigrama.

### <a name="file-menu"></a>Menú Archivo

El menú **Archivo** está disponible para todos los usuarios e incluye los siguientes comandos.

| Comando                           | Descripción |
|-----------------------------------|-------------|
| Nuevo                               | Crear una nueva definición del informe, definición de la fila, definición de la columna, definición del organigrama, definición del grupo de informes o una carpeta. Hay opciones adicionales disponibles, en función de su rol de usuario. |
| Abierta                              | Abrir una definición de la fila, definición de la columna, definición del organigrama o definición del informe existentes. |
| Cerrar                             | Cerrar el bloque de creación actual. |
| Cerrar todo                         | Cerrar todos los bloques de creación. |
| Guardar                              | Guardar la definición de la fila, definición de la columna, definición del organigrama o definición del informe actuales. |
| Guardar como                           | Guardar la definición de la fila, definición de la columna, definición del organigrama o definición del informe actuales bajo un nuevo nombre. |
| Propiedades                        | Abra el cuadro de diálogo **Propiedades**, donde puede cambiar el nombre y la descripción de un informe. |
| Generar                          | Generar el informe actual. Este comando está disponible desde una definición del informe. |
| Ver informe                       | Abrir la versión más reciente del informe generado en Finance and Operations. Este comando está disponible desde una definición del informe si ha generado al menos un informe. |
| Definiciones de informe recientes         | Mostrar una lista de informes que se han creado o se han modificado recientemente. Puede seleccionar un informe en la lista. |
| Definiciones de filas recientes            | Mostrar una lista de definiciones de fila que se han creado o se han modificado recientemente. Puede seleccionar una definición en la lista. |
| Definiciones de columnas recientes         | Mostrar una lista de definiciones de columna que se han creado o se han modificado recientemente. Puede seleccionar una definición de columna en la lista. |
| Definiciones de organigramas recientes | Mostrar una lista de definiciones de organigramas que se han creado o se han modificado recientemente. Puede seleccionar una definición de organigrama en la lista. |
| Salir                              | Salir del diseñador de informes. |

### <a name="edit-menu"></a>Editar menú

El menú **Editar** está disponible para los usuarios que tienen el rol de **Diseñador** o **Administrador**. Este menú incluye los comandos siguientes.

| Comando                                | Descripción |
|----------------------------------------|-------------|
| Deshacer                                   | Deshacer la última acción. |
| Rehacer                                   | Invertir la última acción que se deshizo. |
| Cortar                                    | Eliminar el texto seleccionado y copiarlo en el Portapapeles. |
| Copiar                                   | Copiar el texto seleccionado en el portapapeles. |
| Pegar                                  | Insertar el texto copiado o cortado más recientemente del portapapeles. |
| Borrar                                  | Eliminar el contenido de la celda seleccionada del bloque de creación. |
| Buscar                                   | Abra el cuadro de diálogo **Buscar y reemplazar**, donde puede buscar texto en el panel de vista. |
| Reemplazar                                | Abra el cuadro de diálogo **Buscar y reemplazar**, donde puede buscar y reemplazar texto en el panel de vista. |
| Insertar filas de dimensiones            | Abrir el cuadro de diálogo **Insertar filas de dimensiones**, donde puede seleccionar los valores de dimensión para incluir en la definición de filas. Este comando está disponible desde una definición de la fila. |
| Renumerar filas                          | Renumerar todos los códigos numéricos de la fila. Este comando está disponible desde una definición de la fila. |
| Vínculos de filas                              | Abrir el cuadro de diálogo **Vínculos de filas**, donde puede especificar las fuentes de los vínculos de datos en las definiciones de filas y en definiciones de los organigramas. Este comando está disponible desde una definición de la fila. |
| Ajuste de redondeo                    | Abrir el cuadro de diálogo **Ajustes de redondeo**, donde puede especificar los parámetros para redondear. Este comando está disponible desde una definición de la fila. |
| Gestionar conjuntos de dimensiones                  | Abrir el cuadro de diálogo **Conjuntos de dimensiones**, donde puede crear y modificar conjuntos de dimensiones. Este comando está disponible desde una definición de fila o una definición de organigrama. |
| Insertar fila                             | Insertar una fila en blanco en la definición de fila o una fila de cabecera en blanco en la definición de columna. Este comando está disponible desde una definición de fila o una definición de columna. |
| Eliminar fila                             | Eliminar la fila seleccionada de la definición de filas o la fila seleccionada del encabezado de la definición de columnas. Este comando está disponible desde una definición de fila o una definición de columna. |
| Insertar columna                          | Insertar una columna en blanco en la definición de la columna. Este comando está disponible desde una definición de columna. |
| Eliminar columna                          | Eliminar la columna seleccionada de la definición de la columna. Este comando está disponible desde una definición de columna. |
| Insertar las unidades de informe de dimensiones | Abrir el cuadro de diálogo **Insertar unidades de informe de dimensiones**, donde puede seleccionar los valores de dimensión para incluir en la definición del organigrama. Este comando está disponible desde una definición del organigrama. |
| Importar jerarquía del conjunto de dimensiones         | Abrir el cuadro de diálogo **Jerarquía del conjunto de dimensiones**, donde puede importar una jerarquía del conjunto de dimensiones de los datos financieros. Este comando está disponible desde una definición de organigrama para un ..\\financial-dimensions\\sistema basado en dimensiones. |
| Insertar unidad organizativa                  | Insertar una fila en blanco en la definición del organigrama. Este comando está disponible desde una definición del organigrama. |
| Eliminar unidad de informe                  | Eliminar la fila seleccionada de la unidad de informe de la definición del organigrama. Este comando está disponible desde una definición de organigrama. |

### <a name="view-menu"></a>Menú Ver

El menú **Visualización** está disponible para todos los usuarios e incluye los siguientes comandos.

| Comando         | Descripción                                                            |
|-----------------|------------------------------------------------------------------------|
| Panel de exploración | Mostrar u ocultar el panel de navegación.                                      |
| Barras de herramientas        | Seleccionar las barra de herramientas que son visibles.                                  |
| Barra de estado      | Mostrar u ocultar la información del estado en la ventana **Diseñador de informes**. |
| Página principal    | Abre la **Página principal**.                                             |

### <a name="format-menu"></a>Menú Formato

El menú **Formato** está disponible para los usuarios que tienen el rol de **Diseñador** o **Administrador**. Este menú incluye los comandos siguientes.

| Comando               | Descripción |
|-----------------------|-------------|
| Estilos y formato | Abra el cuadro de diálogo **Estilos y formato**, donde puede crear y modificar el estilo para el texto de definiciones de filas y definiciones de columnas. Este comando está disponible desde una definición de fila o una definición de columna. |
| Ancho de columna          | Abra el cuadro de diálogo **Ancho de columna**, donde puede establecer el ancho de la columna seleccionada. Este comando está disponible desde una definición de fila, una definición de columna o una definición de organigrama. |
| Ocultar                  | Ocultar la columna seleccionada. Este comando está disponible desde una definición de fila, una definición de columna o una definición de organigrama. |
| Mostrar                | Hacer visibles las columnas ocultas entre las columnas seleccionadas. Este comando está disponible desde una definición de fila, una definición de columna o una definición de organigrama. |

### <a name="company-menu"></a>Menú de la empresa

El menú **Empresa** está disponible para los usuarios que tienen el rol de **Diseñador** o **Administrador**. Este menú incluye los comandos siguientes.

| Comando               | Descripción                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Empresas             | Abrir el cuadro de diálogo **Empresas**, donde puede crear y modificar empresas.                                          |
| Grupos de bloque de creación | Abra el cuadro de diálogo **Grupos de bloque de creación**, donde puede crear, modificar, importar y exportar los grupos de bloque de creación. |

### <a name="go-menu"></a>Menú Ir

El menú **Ir** está disponible para todos los usuarios e incluye los comandos siguientes.

> [!NOTE]
> Estos comandos no tienen un efecto visible a menos que el panel de navegación esté visible.

| Comandos                   | Descripción                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Definiciones del informe         | Mostrar las definiciones del informe en el panel de navegación.                                    |
| Definiciones de las filas            | Mostrar las definiciones de la fila en el panel de navegación.                                       |
| Definiciones de la columna         | Mostrar las definiciones de la columna en el panel de navegación.                                    |
| Definiciones de los organigramas | Mostrar las definiciones de los organigramas en el panel de navegación.                            |
| Seguridad                   | Mostrar la información de seguridad para los usuarios, los grupos y las empresas en el panel de navegación. |

### <a name="tools-menu"></a>Menú Herramientas

El menú **Herramientas** está disponible para todos los usuarios, pero algunos comandos han limitado disponibilidad. Este menú incluye los comandos siguientes.

| Comando                       | Descripción |
|-------------------------------|-------------|
| Proteger                       | Aplicar una contraseña a la unidad del bloque de creación actual. Este comando está disponible para los usuarios que tienen el rol de **Diseñador** o de **Administrador**. |
| Estado de la cola de informes           | Abra el cuadro de diálogo **Estado de la cola de informes**, donde puede ver todos los informes generados recientemente y los detalles de cada informe. |
| Información del sistema de origen     | Muestra los ajustes del sistema de Microsoft Dynamics ERP. Este comando está disponible para los usuarios que tienen el rol de **Diseñador** o de **Administrador**. |
| Elementos desprotegidos             | Mostrar las definiciones de la filas, las definiciones de las columnas, las definiciones de los organigramas y las definiciones de los informes que están actualmente abiertas. Este comando está disponible para los usuarios que tienen el rol de **Diseñador** o de **Administrador**. |
| Actualizar los datos financieros en caché | Actualizar los datos en la columna de las dimensiones financieras. |
| Opciones                       | Abra el cuadro de diálogo **Opciones**, donde puede modificar las preferencias de usuario para el diseñador de informes. |

### <a name="window-menu"></a>Menú Ventana

El menú **Ventana** está disponible para todos los usuarios e incluye los siguientes comandos.

| Comando              | Descripción |
|----------------------|-------------|
| Colocar en mosaico horizontal    | Mostrar todas las ventanas abiertas unas al lado de otras. |
| Colocar en mosaico vertical      | Mostrar todas las ventanas abiertas, unas encima de otras. |
| Cascada              | Poner todas las ventanas abiertas unas encima de otras, de modo que la barra de título de cada ventana esté visible. |
| Inmovilización horizontal    | Inmovilizar la fila seleccionada de modo que, cuando se desplaza, esa fila sigue siendo visible en la ventana. Este comando está disponible para los usuarios que tienen el rol de **Diseñador** o de **Administrador**. |
| Inmovilización vertical      | Inmovilizar la columna seleccionada de modo que, cuando se desplaza, esa columna sigue siendo visible en la ventana. Este comando está disponible para los usuarios que tienen el rol de **Diseñador** o de **Administrador**. |
| Lista de ventanas abiertas | Mostrar una lista de ventanas que están abiertas. Seleccionar una ventana para traerla en la parte delantera |

### <a name="help-menu"></a>Menú Ayuda

El menú **Ayuda** está disponible para todos los usuarios e incluye los siguientes comandos.

| Comando | Descripción                                                              |
|---------|--------------------------------------------------------------------------|
| Ayuda    | Abra la página del tema de ayuda de Finance and Operations para los informes financieros. |
|         |                                                                          |

## <a name="report-designer-toolbar-buttons"></a>Botones de la barra de herramientas del diseñador de informes
En las siguientes tablas se describen los botones de la barra de herramientas que se pueden usar cuando se diseñan informes. Algunos botones de la barra de herramientas sólo están disponibles en determinadas circunstancias Por ejemplo, los botones para promocionar y degradar las unidades de notificaciones solo están disponibles cuando se modifica una definición del organigrama.

### <a name="standard-toolbar"></a>Barra de herramientas estándar

La barra de herramientas estándar ofrece acceso rápido para archivar y editar comandos. Esta barra de herramientas incluye los siguientes botones.

| Botón                                                                                       | Descripción |
|----------------------------------------------------------------------------------------------|-------------|
| [![Nuevo botón](./media/rowc130389.png)](./media/rowc130389.png)                              | Crear una nueva definición del informe, definición de la fila, definición de la columna o definición del organigrama (en blanco). |
| [![Botón Abrir](./media/openfolderc130389.png)](./media/openfolderc130389.png)               | Abrir una definición de la fila, definición de la columna, definición del organigrama o definición del informe existentes. |
| [![Botón Guardar](./media/savec130389.png)](./media/savec130389.png)                           | Guardar la definición de la fila, definición de la columna, definición del organigrama o definición del informe actuales. |
| [![Botón Copiar](./media/copyc130389.png)](./media/copyc130389.png)                           | Copiar el texto seleccionado en el portapapeles. |
| [![Botón Cortar](./media/cutc130389.png)](./media/cutc130389.png)                              | Eliminar el texto seleccionado y copiarlo en el Portapapeles. |
| [![Botón Pegar](./media/pastec130389.png)](./media/pastec130389.png)                        | Insertar el texto del portapapeles. |
| [![Botón Deshacer](./media/undoc130389.png)](./media/undoc130389.png)                           | Deshacer la última acción. |
| [![Botón Rehacer](./media/redoc130389.png)](./media/redoc130389.png)                           | Invertir la última acción que se deshizo. |
| [![Botón Buscar](./media/findc130389.png)](./media/findc130389.png)                           | Abra el cuadro de diálogo **Buscar y reemplazar**, donde puede buscar y reemplazar texto en la ventana activa. |
| [![Botón Insertar fila](./media/insertrowc130389.png)](./media/insertrowc130389.png)           | Insertar una fila en blanco en la definición de fila o una fila de cabecera en blanco en la definición de columna. Este botón está disponible desde una definición de fila o una definición de columna. |
| [![Botón insertar columna](./media/insertcolumnc130389.png)](./media/insertcolumnc130389.png)  | Insertar una columna en blanco en la definición de la columna. Este botón está disponible desde una definición de columna. |
| [![Botón Bloquear](./media/lockc130389.png)](./media/lockc130389.png)                           | Aplicar una contraseña a la unidad del bloque de creación actual. Este botón está disponible para los usuarios que tienen el rol de **Diseñador** o de **Administrador**. |
| [![Botón Vínculo de filas](./media/rowlinkc130389.png)](./media/rowlinkc130389.png)                 | Abrir el cuadro de diálogo **Vínculos de filas**, donde puede especificar las fuentes de los vínculos de datos en las definiciones de filas y en definiciones de los organigramas. Este botón está disponible desde una definición de la fila. |
| [![Botón Promover](./media/promotec130389.png)](./media/promotec130389.png)                  | Promueva una unidad de la definición del organigrama. Cuando selecciona una unidad secundaria y hace clic en **Promover**, la unidad secundaria se transfiere al mismo nivel que su unidad principal. |
| [![Botón Degradar](./media/demotec130389.png)](./media/demotec130389.png)                     | Degrade una unidad de la definición del organigrama. Cuando selecciona una unidad y hace clic en **Degradar**, la unidad se convierte en la unidad secundaria que la precede. |
| [![Botón Expandir](./media/expandtreebuttonc130389.png)](./media/expandtreebuttonc130389.png) | Expandir todas las unidades de la definición del organigrama en el nivel de la unidad seleccionada. |
| [![Botón Contraer](./media/collapsec130389.png)](./media/collapsec130389.png)               | Contraer el organigrama. |
| [![Botón Ayuda](./media/helpc130389.png)](./media/helpc130389.png)                           | Abra la Ayuda. |

### <a name="formatting-toolbar"></a>Barra de herramientas de formato

La barra de herramientas de formato proporciona de fácil acceso a los comandos de estilo. Esta barra de herramientas incluye los siguientes botones.

| Botón                                                                                                       | Descripción                                             |
|--------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|
| [![Botón Estilo de fuente](./media/formattingc130389.png)](./media/formattingc130389.png)                         | Aplicar el estilo de fuente seleccionado al texto actual.      |
| [![Botón Fuente](./media/fonttype.png)](./media/fonttype.png)                                                 | Definir el texto actual al estilo de fuente seleccionado.              |
| [![Botón Tamaño de fuente](./media/fontsize.png)](./media/fontsize.png)                                            | Definir el texto actual al tamaño de fuente (en puntos). |
| [![Botón Negrita](./media/boldc130389.png)](./media/boldc130389.png)                                           | Poner el texto actual en negrita.                             |
| [![Botón cursiva](./media/italicsc130389.png)](./media/italicsc130389.png)                                   | Poner el texto actual en cursiva.                           |
| [![Botón Subrayado](./media/underlinec130389.png)](./media/underlinec130389.png)                            | Surayar el texto actual.                             |
| [![Botón Reducir sangría](./media/outdentlsc130389.png)](./media/outdentlsc130389.png)                      | Reducir la sangría del texto actual.                |
| [![Botón Aumentar sangría](./media/indentlsc130389.png)](./media/indentlsc130389.png)                        | Aumentar la sangría del texto actual.                |
| [![Botón Color de fondo](./media/fillbackgroundcolorc130389.png)](./media/fillbackgroundcolorc130389.png) | Cambiar el color de fondo de la celda actual.        |
| [![Botón color de fuente](./media/fontcolorc130389.png)](./media/fontcolorc130389.png)                           | Cambiar el color del texto actual                   |

### <a name="report-designer-toolbar"></a>Barra de herramientas del diseñador de informes

La barra de herramientas del diseñador de informes ofrece acceso rápido a los comandos para navegar por el diseñador de informes. Esta barra de herramientas incluye los siguientes botones.

| Botón                                                                                              | Descripción |
|-----------------------------------------------------------------------------------------------------|-------------|
| [![Botón Definición del informe](./media/reportc130389.png)](./media/reportc130389.png)                 | Mostrar la definición del informe indicada en el menú **Ventana**. |
| [![Botón Definición de la fila](./media/rowc130389.png)](./media/rowc130389.png)                          | Mostrar la definición de filas que se asigna a la definición del informe activo. |
| [![Botón Definición de la columna](./media/columnc130389.png)](./media/columnc130389.png)                 | Mostrar la definición de columnas que se asigna a la definición del informe activo. |
| [![Botón Definición del organigrama](./media/treec130389.png)](./media/treec130389.png)             | Mostrar la definición del organigrama que se asigna a la definición del informe activo. |
| [![Botón Visor de informes](./media/reportviewerc130389.png)](./media/reportviewerc130389.png)         | Iniciar el visor de informes y mostrar la versión más reciente del informe generado. Este botón está disponible desde una definición del informe si ha generado al menos un informe. |
| [![Botón Generar informe](./media/generate-to-ddvc130389.png)](./media/generate-to-ddvc130389.png) | Genera un informe a partir de la definición de informe activa. Este botón está disponible desde una definición de informe. |

## <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)

[Generar un informe financiero](generate-financial-report.md)
