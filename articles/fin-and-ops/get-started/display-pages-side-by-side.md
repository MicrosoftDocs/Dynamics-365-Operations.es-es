---
title: "Visualizar páginas en paralelo con el icono Abrir en una ventana nueva"
description: "Este artículo explica cómo mostrar páginas en paralelo en Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 09/07/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17611
ms.assetid: fc589d76-3927-4486-ab83-e86b9b47ba2c
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b375e87af24a17633d6d1590277ece9e2df189da
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="display-pages-side-by-side-using-the-open-in-new-window-icon"></a>Visualizar páginas en paralelo con el icono Abrir en una ventana nueva

[!include[banner](../includes/banner.md)]


Este artículo explica cómo mostrar páginas en paralelo en Microsoft Dynamics 365 for Finance and Operations.

Microsoft Dynamics 365 for Finance and Operations le ayuda a realizar las tareas de manera eficaz. En algunos casos, puede que desee ver varias páginas en paralelo para completar las tareas con rapidez. Como ejemplo, puede que desee validar o especificar líneas en más de un diario. Normalmente, para ello tendría que avanzar y retroceder entre la página que muestra una lista de diarios y la página que muestra líneas para un diario dado. Sin embargo, la característica **Abrir en una ventana nueva** le permite mostrar estas páginas en paralelo para que pueda llevar a cabo sus tareas con rapidez. 

Siguiendo con el ejemplo mencionado anteriormente, al ver las líneas, puede hacer clic en el icono **Abrir en ventana nueva**. 

[![open-in-new-window-icon](./media/open-in-new-window-icon.png)](./media/open-in-new-window-icon.png) 

Al hacer clic en el icono de **Abrir en una ventana nueva** se abre la página de líneas en un nuevo explorador emergente y, a continuación, navega por el explorador original en el historial hasta la página que mostraba la lista de diarios. Se podrán mostrar ambas páginas en paralelo. Cuando termine de ver un diario, puede cambiar el diario seleccionado en la página de lista de diarios y la página de líneas en la ventana emergente mostrará automáticamente las líneas del diario recién seleccionado. 

[![pages-show-side-by-side](./media/pages-show-side-by-side.png)](./media/pages-show-side-by-side.png) 

La actualización y la vinculación dinámica se produce debido a las relaciones que hay entre los datos que apoyan estas páginas. Si el sistema no reconoce la relación entre los datos, la ventana emergente no se actualizará automáticamente en respuesta a un cambio en la ventana de la que se originó. 

Algunas páginas tienen varias vistas, como la vista de cuadrícula, la vista de encabezado y la vista de detalles. El icono **Abrir en ventana nueva** hace que la página completa se abra en la nueva ventana del explorador. Por lo tanto, no puede mantener dos vistas de la misma página en paralelo con la característica **Abrir en ventana nueva**. Sin embargo, casi todas esas páginas tienen una lista de navegación que puede usar para pasar de un registro a otro y lograr una experiencia similar. 

Antes de usar la característica **Abrir en una ventana nueva**, debe configurar el bloqueador de elementos emergentes del explorador para permitir mensajes emergentes desde la dirección URL del sitio de Finance and Operations. Como ejemplo, podría permitir mensajes emergentes de "\*.dynamics.com". 

La característica **Abrir en ventana nueva** solo está disponible cuando hay más de una página abierta en la ventana. Además, la ventana emergente se cierra automáticamente cuando no hay más páginas abiertas (es decir, cuando se cierra la última página de esa ventana). Finance and Operations también cierra las páginas abiertas cuando navega a otra área de la aplicación. Por lo tanto, si tiene ventanas emergentes abiertas y navega a otra área de la aplicación, las ventanas emergentes se cierran automáticamente porque el sistema cerró las páginas de esas ventanas. 

La barra superior de las ventanas emergentes muestra información acerca de la empresa en la que se abrió la página y es de solo lectura. Las ventanas emergentes también dependen de la ventana del explorador principal de Finance and Operations. Si se cierra o se actualiza la ventana principal, todas las ventanas emergentes serán de solo lectura. Esto significa que podrá seguir viendo la información en estas ventanas, pero no podrá interactuar con ella.




