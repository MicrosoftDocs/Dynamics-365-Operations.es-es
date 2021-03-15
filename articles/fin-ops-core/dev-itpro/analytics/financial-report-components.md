---
title: Componentes de los informes financieros
description: En este artículo se describe cómo se utilizan los componentes o bloques de creación, de las definiciones de informe en los informes financieros.
author: aprilolson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: d066ee69887f05c8fe14eebac1111c4db26ec628
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093985"
---
# <a name="financial-report-components"></a>Componentes de los informes financieros

[!include [banner](../includes/banner.md)]

En este artículo se describe cómo se utilizan los componentes o bloques de creación, de las definiciones de informe en los informes financieros. Estos bloques de creación incluyen definiciones de filas, definiciones de columnas y definiciones de organigramas. El artículo se explica cómo organizar y bloquear bloques de creación.

La filosofía de diseño del diseñador de informes financieros es desglosar la información en el componente o el bloque de creación de menor tamaño y, a continuación, combinar y hacer coincidir los componentes según sea necesario. Por tanto, el formato del informe es independiente de los datos financieros y puede cambiar el diseño de un informe sin modificar los datos financieros en el sistema de Microsoft Dynamics ERP. Mediante este método de bloque de creación, puede combinar el texto, importes y cálculos para producir los informes que necesite. Además, esta flexibilidad promueve la creatividad, facilitando la visualización de sus operaciones de distintas maneras. Los bloques de creación individuales de una definición del informe son similares a una hoja de cálculo tridimensional, pero son más avanzados. Una definición del informe especifica la definición de filas, la definición de columnas y la definición opcional del organigrama que se debe usar para el informe. También incluye información sobre dónde almacenar el informe que se genera y cómo darle formato.

## <a name="building-blocks-of-a-report"></a>Bloques de creación de un informe

| Bloque de creación            | Descripción | Para obtener más información |
|---------------------------|-------------|----------------------|
| Definición de filas            | Una definición de fila define las líneas descriptivas (por ejemplo, sueldos o ventas) en un informe. También se muestran los valores o las dimensiones de segmentos que contienen los valores para cada elemento de línea e incluye el formato y los cálculos de la fila. | [Definiciones de filas](row-definitions-financial-reporting.md) |
| Definición de columnas         | Una definición de columna define el período que se usará al extraer datos de las dimensiones financieras. También incluye el formato y los cálculos de la columna. | [Definiciones de columna](column-definitions-financial-reports.md) |
| Definiciones de los organigramas | Una definición del organigrama es similar a un gráfico organizativo. Contiene unidades de informes individuales que representan cada cuadro del gráfico. Las unidades pueden ser departamentos individuales de los datos financieros o unidades de un nivel más alto que resumen datos de otras unidades de informes. | [Definiciones de los organigramas](financial-reporting-tree-definitions.md) |
| Definición del informe         | Una definición del informe usa una definición de filas, una definición de columnas y una definición opcional del organigrama para crear un informe. También proporciona opciones y configuración adicionales que puede usar para personalizar un informe. | [Definición del informe](design-financial-report-definitions.md) |

Si es la primera vez que diseña informes, es posible que desee usar el asistente de informes para crear de forma rápida una definición del informe que pueda personalizar más adelante. Si ya tiene experiencia con el diseño de informes y desea más flexibilidad para el diseño del informe, puede combinar bloques de creación nuevos o existentes para crear una nueva definición del informe. No es necesario comprender completamente todas las opciones disponibles de la definición de informes para enviar informes de calidad. Una vez que esté familiarizado con el diseño de informes, puede expandir las definiciones de informes para aprovecharse de características más avanzadas. Una vez que haya creado un informe básico, puede modificar la definición del informe y los bloques de creación en la definición del informe.

## <a name="organize-the-building-blocks"></a>Organizar los bloques de creación
Usar carpetas para organizar los bloques de creación en el diseñador de informes. Todas las carpetas son específicas al tipo de bloques de creación que contienen. Por ejemplo, todas las carpetas que contienen definiciones de filas están ubicadas en el panel **Definiciones de las filas** del diseñador de informes.

### <a name="create-a-folder"></a>Crear una carpeta

1. En el diseñador de informe, seleccione el tipo de bloque de creación para organizar en el panel de navegación. Por ejemplo, para clasificar una definición de filas, haga clic en **Definiciones de filas**.
2. En el panel de navegación, seleccione la carpeta existente en la que se creará la nueva carpeta y, a continuación, siga uno de estos pasos:

    - Haga clic con el botón secundario en la carpeta principal y, a continuación, seleccione **Nueva carpeta**.
    - Seleccione la carpeta principal, haga clic en **Archivo** y luego haga clic en **Nueva carpeta**.

3. Cuando aparezca la nueva carpeta, escriba el nombre de la nueva carpeta y luego presione Entrar.

## <a name="lock-a-building-block"></a> Bloquear un bloque de creación
Puede crear una contraseña para bloquear y ayudar a proteger un bloque de creación. De esta manera puede agregar un nivel de seguridad a un componente del informe protegiendo todo el sistema. Una contraseña puede ayudar a proteger la información del bloque de creación que es importante para su proceso de notificaciones de fin de mes. Un usuario de cualquier rol puede bloquear un bloque de creación. Sin embargo, otros usuarios siempre tienen acceso de solo lectura a un componente bloqueado. Los usuarios pueden abrir, cambiar y guardar el componente bloqueado con un nombre nuevo. Un usuario que tiene el rol de administrador siempre puede tener acceso y cambiar un bloque de creación bloqueado.

1. En el diseñador de informes, abra el componente del informe que quiere bloquear, por ejemplo una definición de fila, una definición de columna, una definición del informe o una definición del organigrama.
2. En el menú **Herramientas**, haga clic en **Proteger/Desproteger**. También puede hacer clic en **Proteger/Desproteger** (un icono de candado) en la barra de herramientas.
3. En el cuadro de diálogo **Proteger**, escriba y confirme una contraseña y, a continuación, haga clic en **Aceptar**. El icono de candado de la barra de herramientas se destaca cuando un bloque de creación abierto está bloqueado.

Para abrir un bloque de creación bloqueado, abra el bloque de creación y haga clic en el icono **Proteger/Desproteger** en la barra de herramientas. De forma alternativa, en el menú **Herramientas**, haga clic en **Desproteger**.

## <a name="building-block-groups"></a>Grupos de bloque de creación

Los bloques de creación son las definiciones de la filas, las definiciones de las columnas, las definiciones de los organigramas y las definiciones de los informes que se crean para un informe. Los grupos de bloques de creación son colecciones de las definiciones y de los conjuntos de dimensiones.

### <a name="view-a-building-block-group"></a>Ver un grupo de bloques de creación

Puede ver todos los bloques de creación asignados a un grupo de bloques de creación. También puede exportar o importar un grupo de bloques de creación.

1. En el Diseñador de Informes, en el menú **Compañía**, haga clic en **Grupos de bloques de creación**.
2. En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el bloque de creación que desea ver.
3. Haga clic en **Ver** para abrir el cuadro de diálogo **Ver grupo de bloques de creación**, donde puede ver el contenido del grupo de bloques de creación.
4. Haga clic en **Cerrar** para cerrar los cuadros de diálogo.

### <a name="export-a-building-block-group"></a>Exportar un grupo de bloques de creación

Puede exportar un grupo de bloques de creación o bloques de creación de informe a un grupo de bloques de creación. Puede usar el grupo de bloques de creación exportado como copia de seguridad. También puede copiar los datos exportados entre instalaciones. El diseñador de informes incluye los conjuntos de dimensiones y los estilos de fuente a los que se hace referencia junto con el grupo de bloques de creación.

1. En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2. En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el grupo de bloques de creación que se va a exportar y, a continuación, haga clic en **Exportar**.
3. En el cuadro de diálogo **Exportar**, seleccione las definiciones del informe que desea exportar:

    - Para exportar todas las definiciones de informes y los loques de creación asociados, haga clic en **Seleccionar todo**.
    - Para exportar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, haga clic en la pestaña apropiada y, a continuación, seleccione los artículos que se exportarán. Mantenga presionada la tecla CTRL para seleccionar varios elementos de una pestaña.

    > [!NOTE]
    > Cuando se seleccionan informes para exportar, se seleccionan las filas, las columnas, los organigramas y los grupos de dimensión asociados.

4. Cuando haya terminado de seleccionar artículos para exportar, haga clic en **Exportar**.
5. En el cuadro de diálogo **Guardar como**, seleccione una ubicación a la que desea exportar el grupo de bloques de creación.
6. En el campo **Nombre del archivo**, especifique un nombre para el archivo. El diseñador de informes agrega automáticamente una extensión de nombre de archivo .tdbx.
7. Haga clic en **Guardar**. El grupo de bloques de creación se guarda en la ubicación que ha especificado.

### <a name="import-a-building-block-group"></a> Importar un grupo de bloques de creación

Puede importar un grupo de bloques de creación en un grupo de bloques de creación existente. Todos los grupos de bloques de creación conservan sus referencias de empresa y estilos de fuente originales e incluyen los conjuntos de dimensiones pertinentes.

1. En el diseñador de informes, en el menú **Empresa**, haga clic en **Grupos de bloques de creación**.
2. En el cuadro de diálogo **Grupos de bloques de creación**, seleccione el grupo en el que desea importar un grupo de bloques de creación y haga clic en **Importar**.
3. En el cuadro de diálogo **Abrir**, seleccione el grupo de bloques de creación que se debe importar y haga clic en **Abrir**.
4. En el cuadro de diálogo **Importar**, seleccione las definiciones del informe que desea importar:

    - Para importar todas las definiciones de informes y los bloques de creación asociados, haga clic en **Seleccionar todo**.
    - Para importar informes, filas, columnas, organigramas o conjuntos de dimensiones específicos, seleccione los informes, filas, columnas, orgnaigramas o conjuntos de dimensiones que desea importar.

5. Cuando haya terminado de seleccionar artículos para importar, haga clic en **Importar**.

### <a name="undo-a-checkout-of-a-building-block"></a>Deshacer una desprotección de un bloque de creación

Cuando abre un bloque de creación, otros usuarios tienen acceso de solo lectura a ese bloque de creación. A veces, los usuarios se olvidan de cerrar un bloque de creación o apagan el sistema sin cerrar el bloque de creación. Por tanto, el bloque de creación permanece desprotegido y ningún otro usuario puede abrirlo. En estos casos, un administrador de informes financieros puede usar el cuadro de diálogo **Elementos desprotegidos** para proteger los bloques de creación que los usuarios hayan dejado desprotegidos.

> [!NOTE]
> Debe tener el rol Administrador para proteger bloques de creación usando el cuadro de diálogo **Elementos desprotegidos**.

1. En el diseñador de informes, en el menú **Herramientas**, haga clic en **Elementos desprotegidos**.
2. En el cuadro **Elementos desprotegidos**, active la casilla **Mostrar elementos de todos los usuarios**. La lista se actualiza para mostrar todos los bloques de creación desprotegidos y los usuarios que los hayan desprotegido.
3. Seleccione un bloque de creación y haga clic en **Deshacer desprotección**.
4. Haga clic en **Sí** para proteger el bloque de creación.

## <a name="additional-resources"></a>Recursos adicionales

[Informes financieros](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]