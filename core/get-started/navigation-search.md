---
title: "Búsqueda de navegación"
description: "Este artículo explica cómo usar la función de búsqueda para navegar a páginas en Microsoft Dynamics 365 para las operaciones."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Búsqueda de navegación

Este artículo explica cómo usar la función de búsqueda para navegar a páginas en Microsoft Dynamics 365 para las operaciones.

La Dynamics 365 para las operaciones proporciona funcionalidades para una gran variedad de sectores y de verticales. La aplicación incluye varias áreas y páginas para ayudarle a realizar varias tareas. Para buscar rápidamente páginas que necesita rellenar sus tareas, utilice la función de búsqueda de navegación. Para usar esta característica, haga clic en **Buscar** para que aparezca el cuadro **Buscar**. A continuación, puede elegir escribir una o varias palabras en el cuadro. El sistema busca al instante páginas pertinentes en la aplicación que coincidan con las palabras que ha especificado. Por ejemplo, podría escribir “factura de proveedor” como la entrada y, a continuación, el sistema mostraría los resultados que coinciden con esa entrada. **Nota:** El cuadro **Buscar** le ayuda a encontrar páginas y a desplazarse por ellas. No le ayudará a encontrar datos o acciones específicos. 

[cuadro de búsqueda de![] (. /media/search-box.png])(. /media/search-box.png) Que la función de búsqueda de navegación sirve también de gran manera para que se desplazarse rápidamente a una página determinada. Por ejemplo, si es un Funcionario de proveedores que utilizan frecuentemente ** diario de pagos ** la página, podría especificar el “diario de pagos” en el cuadro de búsqueda. Dado que la entrada es una precisa - coincida para el título de la página, la página se muestra en la parte superior de los resultados de la búsqueda, y puede navegar rápidamente a ella. 

[![buscar-para-pago-Journal] (. /media/searching-for-payment-journal.png])(. /media/searching-for-payment-journal.png) 

La lista de resultados de la búsqueda muestra el título de la página junto con la ruta de desplazamiento. Esto le ayuda a reconocer la ubicación de la página en la aplicación. También le ayuda a diferenciar entre dos o más páginas similares en los resultados. Al buscar una página, su entrada se concilia con el título de la página, así como su ruta de navegación. Por ejemplo, si escribe “soportados” ** ** en el cuadro de búsqueda, verá los resultados de las páginas disponibles en su en el área de los clientesnúcleoaunque los títulos de la página no incluyan la palabra “soportados.” 

[(Buscar-para![palabra-] (soportados. /media/search-for-the-word-receivable.png])(. /media/search-for-the-word-receivable.png) 

De una perspectiva de contabilidad y gestión de seguridad, las superficies de la funcionalidad de búsqueda de navegación sólo:

-   Páginas que están habilitadas en la configuración actual (mediante las claves de configuración).
-   Páginas a las que el usuario tiene acceso en función del rol del usuario

La lista de resultados de la búsqueda está limitada a 10 artículos. Si no encuentra lo que busca en los resultados, debe intentar restringir o actualizar la entrada. Desde una perspectiva de desarrollo, es muy sencillo sacar provecho de la funcionalidad de búsqueda de navegación puesto que no hay prácticamente ningún retraso entre el desarrollo de los elementos de menú y su capacidad para aparecer en los resultados de la búsqueda. Siempre que los elementos de menú estén vinculados desde el panel de navegación o el panel de información, permitirán automáticamente las búsquedas. La funcionalidad de búsqueda de navegación también incluye una característica muy solicitada para los usuarios avanzados: la capacidad de navegar rápidamente a una página en función del nombre del formulario técnico. Muchos usuarios conocen tan bien el sistema que saben los nombres de formulario precisos con los que trabajan. Si es uno de estos usuarios, puede especificar **formulario:** seguido del nombre del formulario que busca. Por ejemplo, si especifica **formulario: vendinvoice**, los resultados de la búsqueda mostrarán todas las páginas en las que el nombre del formulario empieza por **vendinvoice**. 

[Buscar-para- formulario -vendinvoice - vendinvoice![] (. /media/search-for-form-vendinvoice.png])(. /media/search-for-form-vendinvoice.png)


