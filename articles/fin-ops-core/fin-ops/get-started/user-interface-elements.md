---
title: Elementos de la interfaz de usuario
description: Este tema describe los elementos (UI) de la interfaz de usuario utilizados en la aplicación.
author: tlefor
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: ''
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: feb6d5751bc22c05dbd2f01f47d5a0f99fca07a0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754737"
---
# <a name="user-interface-elements"></a>Elementos de la interfaz de usuario

Este tema describe los elementos (UI) de la interfaz de usuario utilizados en la aplicación. Para que los usuarios puedan navegar por la interfaz, es importante conocer los nombres y las funciones de los elementos que componen la interfaz.

## <a name="overview"></a>Información general

- **Panel de acciones** - Es la barra de debajo de la barra de exploración. Aquí, puede seleccionar fichas para modificar registros que se muestran en la página. Puede editar y guardar los registros aquí.  
- **Cuadro informativo** - Puede ver la información y realizar un seguimiento de las actividades de ciertos registros en este panel.  
- **Panel del cuadro informativo** Aquí, puede desplazarse por distintos aspectos de un registro para verlos en el cuadro informativo.  
- **Panel de filtros** - En algunas páginas, puede seleccionar **Mostrar filtros** para abrir este panel. Permite precisar los resultados visibles para el usuario en la página.  
- **Barra de exploración** - la barra de la parte superior de la interfaz. Contiene el **Portal de Dynamics 365**, **Buscar**, el **selector de empresas**, el **Centro de acción**, la **Configuración**, la **Ayuda y soporte técnico** y el perfil de usuario.  
- **Lista de navegación** - En algunas páginas, puede desplazarse por este panel para encontrar un registro específico. Cuando se selecciona, los detalles del registro aparecerán en la página.  
- **Panel de exploración** - El panel situado más a la izquierda. Desde aquí, puede encontrar cualquier página en el producto.  
- **Página** - El enfoque central de interfaz. Las selecciones efectuadas en los otros componentes de la interfaz de usuario afectarán a los registros que se muestran aquí.  
- **Panel** - El panel situado más a la derecha. Se abrirá en algunos casos cuando los aspectos de un registro tengan que cambiarse y guardarse.  
- **Ficha** - Al hacer referencia al panel de acciones, es un menú de opciones que aparece cuando se selecciona una opción especificada en el panel de acciones.  

![En la imagen siguiente se muestra la posición de estos elementos en la interfaz.](media/user-interface-01.png)

## <a name="tabs-fields-and-sections"></a>Fichas, campos y secciones

Una *ficha* es una selección realizada en la página que abre otro aspecto de un registro en la misma página. Con frecuencia, permitirá cambiar determinados *campos*, o elementos de la interfaz de usuario que permiten introducir datos escritos. 

*Ficha desplegable* es una ficha con la ventaja adicional de permitir que haya varias fichas visibles al mismo tiempo. Puede expandir una ficha desplegable seleccionando la flecha que apunta hacia abajo que está en su extremo derecho.

![En la imagen siguiente se muestra un ejemplo de fichas y de fichas desplegables.](media/user-interface-02.png)

Una *sección* es similar a una ficha. La palabra “sección” se usa a menudo para describir las áreas de una página que organizan una categoría específica de información. En la imagen siguiente, extracto, órdenes y favoritos y vínculos son ejemplos de secciones.

![En la imagen siguiente se muestra un ejemplo de fichas y de una sección.](media/user-interface-03.png)

## <a name="dialog-boxes-and-drop-down-menus"></a>Cuadros de diálogo y menús desplegables

Un *cuadro de diálogo* es un panel que se abre cuando determinadas selecciones se realizan para cambiar o crear un registro. Los cuadros de diálogo contienen campos que le permiten introducir datos escritos. A veces, una campo dado permitirá que seleccione una flecha hacia abajo que abre una lista de opciones donde elegir. Esto se denomina *menú desplegable*. En la imagen siguiente, los campos **tipo** y **Grupo de clientes** contienen la opción de abrir un menú desplegable.

![En la imagen siguiente se muestra un ejemplo de un cuadro de diálogo.](media/user-interface-04.png)

En algunos casos, un cuadro de diálogo se abrirá acerca de un botón determinado cuando lo seleccione. Esto se denomina *cuadro de diálogo desplegable*. En la imagen siguiente, el botón **A partir de la fecha** se ha seleccionado y abrió un cuadro de diálogo desplegable.

![En la imagen siguiente se muestra un ejemplo de un cuadro de diálogo desplegable.](media/user-interface-05.png)

## <a name="notifications"></a>Notificaciones

Algunos cambios de los objetos que supervisa aparecerán como *notificaciones*. Las notificaciones pueden notificarle cuándo se modifica información de cliente específica, o puede alertarle cuando el sistema no puede aceptar entradas que ha agregado en determinados campos. Puede aprender a personalizar sobre qué recibirá notificaciones en [Información general de alertas](../get-started/alerts-overview.md).

Las notificaciones aparecen de distintas maneras.
- **Llamada de la función** - Aparecerá junto a un campo, ficha, u otro botón para proporcionar una explicación de para qué se usa la función. 
- **Centro de acción** El cuadro que contiene la notificación aparecerá junto al botón de Centro de acción en la barra de exploración. Puede ver los detalles acerca de la notificación seleccionando **Centro de acción**.  
- **Barra de mensajes** - Esto aparecerá debajo del panel de acciones.  

En la imagen siguiente se muestran ejemplos de estos tipos de notificaciones.

![En la imagen siguiente se muestran ejemplos de notificaciones.](media/user-interface-06.png)

- **Cuadro de mensaje** - Esto aparecerá sobre la interfaz y debe interactuarse con él para poder continuar utilizando el producto.  

![En la imagen siguiente se muestra un ejemplo de un cuadro de mensaje.](media/user-interface-07.png)

## <a name="toolbars-grids-and-lists"></a>Barras de herramientas, cuadrículas y listas

Una *barra de herramientas* contiene herramientas, como la capacidad de agregar campos o quitar registros. A veces, una barra de herramientas aparecerá en la página sobre una *cuadrícula*. Esta área, cuadrícula, es un nombre proporcionado a las filas de registros con varias columnas de datos. No todas las cuadrículas tienen barras de herramientas sobre ellas.

Una *lista* es el nombre proporcionado a una recopilación de registros por los que puede desplazarse. Puede reunir estos registros en la página seleccionándolos. Con frecuencia, esto abrirá una cuadrícula.

![En la imagen siguiente se muestran ejemplos de barras de herramientas, cuadrículas y listas.](media/user-interface-08.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]