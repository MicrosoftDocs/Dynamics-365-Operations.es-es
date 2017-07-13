---
title: Componentes de los informes financieros
description: "En este artículo se describe cómo se utilizan los componentes o bloques de creación, de las definiciones de informe en los informes financieros. Estos bloques de creación incluyen definiciones de filas, definiciones de columnas y definiciones de organigramas. El artículo explica cómo organizar y bloquear bloques de creación y cómo trabajar con grupos de bloques de creación."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5c09b1fc061f95cd78e9f18c2bdf846fdbfc7cf1
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Componentes de los informes financieros
<a id="financial-report-components" class="xliff"></a>

[!include[banner](../includes/banner.md)]


En este artículo se describe cómo se utilizan los componentes o bloques de creación, de las definiciones de informe en los informes financieros. Estos bloques de creación incluyen definiciones de filas, definiciones de columnas y definiciones de organigramas. El artículo explica cómo organizar y bloquear bloques de creación y cómo trabajar con grupos de bloques de creación. 

La filosofía de diseño del diseñador de informes financieros es desglosar la información en el componente o el bloque de creación de menor tamaño y, a continuación, combinar y hacer coincidir los componentes según sea necesario. Por tanto, el formato del informe es independiente de los datos financieros y puede cambiar el diseño de un informe sin modificar los datos financieros en el sistema de Microsoft Dynamics ERP. Mediante este método de bloque de creación, puede combinar el texto, importes y cálculos para producir los informes que necesite. Además, esta flexibilidad promueve la creatividad, facilitando la visualización de sus operaciones de distintas maneras. Los bloques de creación individuales de una definición del informe son similares a una hoja de cálculo tridimensional, pero son más avanzados. Una definición del informe especifica la definición de filas, la definición de columnas y la definición opcional del organigrama que se debe usar para el informe. También incluye información sobre dónde almacenar el informe que se genera y cómo darle formato. Para una mejor reutilización y uso compartido, puede crear un grupo de bloques de creación, que es una recopilación de definiciones de informes, definiciones de filas, definiciones de columnas, definiciones de organigramas y conjuntos de dimensiones existentes asociados a una empresa.

##  Bloques de creación de un informe
<a id="building-blocks-of-a-report" class="xliff"></a>
| Bloque de creación            | Descripción                                                                                                                                                                                                                                                                              | Para obtener más información                                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Definición de filas            | Una definición de fila define las líneas descriptivas (por ejemplo, sueldos o ventas) en un informe. También se muestran los valores o las dimensiones de segmentos que contienen los valores para cada elemento de línea e incluye el formato y los cálculos de la fila.                                                    | [Definiciones de filas](row-definitions-financial-reporting.md)                       |
| Definición de columnas         | Una definición de columna define el período que se usará al extraer datos de las dimensiones financieras. También incluye el formato y los cálculos de la columna.                                                                                                                                 | [Definiciones de columna](column-definitions-financial-reports.md)         |
| Definiciones de los organigramas | Una definición del organigrama es similar a un gráfico organizativo. Contiene unidades de informes individuales que representan cada cuadro del gráfico. Las unidades pueden ser departamentos individuales de los datos financieros o unidades de un nivel más alto que resumen datos de otras unidades de informes. | [Definiciones de los organigramas](financial-reporting-tree-definitions.md) |
| Definición del informe         | Una definición del informe usa una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. También proporciona opciones y configuración adicionales que puede usar para personalizar un informe.                                                                    | [Definición del informe](design-financial-report-definitions.md)                  |

Si es la primera vez que diseña informes, es posible que desee usar el asistente de informes para crear de forma rápida una definición del informe que pueda personalizar más adelante. Si ya tiene experiencia con el diseño de informes y desea más flexibilidad para el diseño del informe, puede combinar bloques de creación nuevos o existentes para crear una nueva definición del informe. No es necesario comprender completamente todas las opciones disponibles de la definición de informes para enviar informes de calidad. Una vez que esté familiarizado con el diseño de informes, puede expandir las definiciones de informes para aprovecharse de características más avanzadas. Una vez que haya creado un informe básico, puede modificar la definición del informe y los bloques de creación en la definición del informe.

## Organizar los bloques de creación
<a id="organize-the-building-blocks" class="xliff"></a>
Usar carpetas para organizar los bloques de creación en el diseñador de informes. Todas las carpetas son específicas al tipo de bloques de creación que contienen. Por ejemplo, todas las carpetas que contienen definiciones de filas están ubicadas en el panel **Definiciones de las filas** del diseñador de informes.

### Crear una carpeta
<a id="create-a-folder" class="xliff"></a>

1.  En el diseñador de informe, seleccione el tipo de bloque de creación para organizar en el panel de navegación. Por ejemplo, para clasificar una definición de filas, haga clic en **Definiciones de filas**.
2.  En el panel de navegación, seleccione la carpeta existente en la que se creará la nueva carpeta y, a continuación, siga uno de estos pasos:
    -   Haga clic con el botón secundario en la carpeta principal y, a continuación, seleccione **Nueva carpeta**.
    -   Seleccione la carpeta principal, haga clic en **Archivo** y luego haga clic en **Nueva carpeta**.

3.  Cuando aparezca la nueva carpeta, escriba el nombre de la nueva carpeta y luego presione Entrar.

##  Bloquear un bloque de creación
<a id="lock-a-building-block" class="xliff"></a>
Puede crear una contraseña para bloquear y ayudar a proteger un bloque de creación. De esta manera puede agregar un nivel de seguridad a un componente del informe protegiendo todo el sistema. Una contraseña puede ayudar a proteger la información del bloque de creación que es importante para su proceso de notificaciones de fin de mes. Un usuario de cualquier rol puede bloquear un bloque de creación. Sin embargo, otros usuarios siempre tienen acceso de solo lectura a un componente bloqueado. Los usuarios pueden abrir, cambiar y guardar el componente bloqueado con un nombre nuevo. Un usuario que tiene el rol de administrador siempre puede tener acceso y cambiar un bloque de creación bloqueado.
1.  En el diseñador de informes, abra el componente del informe que quiere bloquear, por ejemplo una definición de fila, una definición de columna, una definición del informe o una definición del organigrama.
2.  En el menú **Herramientas**, haga clic en **Proteger/Desproteger**. También puede hacer clic en **Proteger/Desproteger** (un icono de candado) en la barra de herramientas.
3.  En el cuadro de diálogo **Proteger**, escriba y confirme una contraseña y, a continuación, haga clic en **Aceptar**. El icono de candado de la barra de herramientas se destaca cuando un bloque de creación abierto está bloqueado.

Para abrir un bloque de creación bloqueado, abra el bloque de creación y haga clic en el icono **Proteger/Desproteger** en la barra de herramientas. De forma alternativa, en el menú **Herramientas**, haga clic en **Desproteger**.

## Grupos de bloque de creación
<a id="building-block-groups" class="xliff"></a>

Los bloques de creación son las definiciones de la filas, las definiciones de las columnas, las definiciones de los organigramas y las definiciones de los informes que se crean para un informe. Los grupos de bloques de creación son colecciones de las definiciones y los conjuntos de dimensiones asociados a una empresa. Los grupos de bloques de creación pueden ser específicos de la empresa, o varias empresas pueden compartir el mismo conjunto de bloques de creación. Si algunas de las empresas tienen un plan de cuentas diferente, puede que desee usar un grupo de bloques de creación diferente para cada empresa. También puede que desee darle nombre a todos sus bloques de creación individuales para reflejar con qué empresa son compatibles.
### Crear un grupo de bloques de creación
<a id="create-a-building-block-group" class="xliff"></a>

1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2.  En el cuadro de diálogo **Grupos de bloque de creación**, haga clic en **Nuevo**.
3.  Escriba un nombre y una descripción únicos para el grupo de bloques de creación. Cada campo puede contener un máximo de 256 caracteres. (Este número incluye espacios).
4.  Haga clic en **Aceptar** para crear el nuevo grupo de bloques de creación.

### Asigne un grupo de bloques de creación
<a id="assign-a-building-block-group" class="xliff"></a>

Después de crear un grupo de bloques, debe asignarlo al menos a una empresa. Luego puede crear las definiciones del informe, fila, columna y organigrama y guardarlas en el grupo de bloques de creación. Debe cerrar todos los bloques de creación antes de comenzar el siguiente procedimiento.
1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Empresas**.
2.  En el cuadro de diálogo **Empresas**, seleccione la empresa a la que asignar un grupo de bloques de creación.
3.  Haga clic en **Modificar**.
4.  En el cuadro de diálogo **Modificar empresa**, en el campo **Grupo de bloques de creación**, seleccione el grupo de bloques de creación que desea asignar a la empresa, o haga clic en **Nuevo** para crear un nuevo grupo de bloques de creación.
5.  Haga clic en **Aceptar** para asignar el nuevo grupo de bloques de creación.
6.  Haga clic en **Cerrar** para cerrar el cuadro **Empresas**. El grupo de bloques de creación que seleccionó estará ahora asignado a la empresa. Ahora todas las nuevas definiciones de filas, las definiciones de columnas, etc. que se creen formarán parte del grupo de bloques de creación que está asignado a esta empresa. También puede importar un archivo o informe .tdbx de otro sistema.

###  Visualizar un grupo de bloques de creación
<a id="view-a-building-block-group" class="xliff"></a>

Tras la creación y el uso de un grupo de bloques de creación, puede ver todos los bloques de creación que tiene asignados. También puede exportar o importar un grupo de bloques de creación y realizar un mantenimiento adicional en los grupos de bloques de creación.
1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2.  En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el bloque de creación que desea ver.
3.  Haga clic en **Ver** para abrir el cuadro de diálogo **Ver grupo de bloques de creación**, donde puede ver el contenido del grupo de bloques de creación.
4.  Haga clic en **Cerrar** para cerrar los cuadros de diálogo.

### Guardar un grupo de bloques de creación con un nuevo nombre
<a id="save-a-building-block-group-under-a-new-name" class="xliff"></a>

Puede guardar un grupo de bloques de creación existente con un nuevo nombre. Después puede modificar el nuevo grupo de bloques de creación sin cambiar el grupo de bloques de creación original.
1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2.  En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el grupo de bloques de creación que desea guardar con un nuevo nombre.
3.  Haga clic en **Guardar como**.
4.  Escriba un nombre y una descripción nuevos para el grupo de bloques de creación.
5.  Haga clic en **Aceptar**. El nuevo grupo de bloques de creación aparece en el cuadro de diálogo **Grupos de bloques de creación**.

###  Exportar un grupo de bloques de creación
<a id="export-a-building-block-group" class="xliff"></a>

Puede exportar un grupo de bloques de creación o bloques de creación de informes específicos en un grupo de bloques de creación. Puede utilizar el grupo de bloque de creación exportado como una copia de seguridad. También puede copiar los datos exportados entre los grupos de bloques de creación o las instalaciones de Finance and Operations. El diseñador de informes incluye los conjuntos de dimensiones y los estilos de fuente a los que se hace referencia junto con el grupo de bloques de creación.
1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2.  En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el grupo de bloques de creación que desea exportar y luego haga clic en **Exportar**.
3.  En el cuadro de diálogo **Exportar**, seleccione las definiciones del informe que desea exportar:
    -   Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán. Mantenga presionada la tecla CTRL para seleccionar varios elementos de una pestaña. **Nota**: Cuando selecciona informes para exportar, se seleccionan las filas, columnas, organigramas y conjuntos de dimensión asociados.

4.  Cuando haya terminado de seleccionar artículos para exportar, haga clic en **Exportar**.
5.  En el cuadro de diálogo **Guardar como**, seleccione una ubicación a la que desea exportar el grupo de bloques de creación.
6.  En el campo **Nombre del archivo**, especifique un nombre para el archivo. El diseñador de informes agrega automáticamente una extensión de nombre de archivo .tdbx.
7.  Haga clic en **Guardar**. El grupo de bloques de creación se guarda en la ubicación que ha especificado.

###  Importar un grupo de bloques de creación
<a id="import-a-building-block-group" class="xliff"></a>

Puede importar un grupo de bloques de creación en un grupo de bloques de creación existente o puede crear un nuevo grupo de bloques de creación para los datos. Todos los grupos de bloques de creación conservan sus referencias de empresa y estilos de fuente originales e incluyen los conjuntos de dimensiones pertinentes.
1.  En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2.  En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el grupo de bloques de creación al que desea importar un grupo de bloques de creación y luego haga clic en **Importar**.
3.  En el cuadro de diálogo **Abrir**, seleccione el grupo de bloques de creación que desea importar y luego haga clic en **Abrir**.
4.  En el cuadro de diálogo **Importar**, seleccione las definiciones del informe que desea importar:
    -   Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.
    -   Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.

5.  Cuando haya terminado de seleccionar artículos para importar, haga clic en **Importar**.

### Deshacer una desprotección de un bloque de creación
<a id="undo-a-checkout-of-a-building-block" class="xliff"></a>

Cuando abre un bloque de creación, otros usuarios tienen acceso de solo lectura a ese bloque de creación. A veces, los usuarios se olvidan de cerrar un bloque de creación o apagan el sistema sin cerrar el bloque de creación. Por tanto, el bloque de creación permanece desprotegido y ningún otro usuario puede abrirlo. En estos casos, un administrador de informes financieros puede usar el cuadro de diálogo **Elementos desprotegidos** para proteger los bloques de creación que los usuarios hayan dejado desprotegidos. **Nota**: Debe tener el rol de administrador para proteger los bloques de creación con el cuadro de diálogo **Elementos desprotegidos**.
1.  En el diseñador de informes, en el menú **Herramientas**, haga clic en **Elementos desprotegidos**.
2.  En el cuadro de diálogo **Elementos desprotegidos**, seleccione **Mostrar elementos de todos los usuarios**. La lista se actualizará para mostrar todos los bloques de creación que están desprotegidos y a los usuarios que los han desprotegido.
3.  Seleccione un bloque de creación y haga clic en **Deshacer desprotección**.
4.  Haga clic en **Sí** para proteger el bloque de creación.

# Consulte también
<a id="see-also" class="xliff"></a>

[Informes financieros](financial-reporting-intro.md)




