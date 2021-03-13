---
title: Obtener una vista previa y publicar un experimento
description: Este tema describe cómo obtener una vista previa y publicar un experimento desde Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 32115378be00df771c6ff658da0c090446edf8b0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009957"
---
# <a name="preview-and-publish-an-experiment"></a>Obtener una vista previa y publicar un experimento

Este tema describe cómo obtener una vista previa y publicar su experimento en Dynamics 365 Commerce después de que haya [conectado su experimento y editado sus variaciones](experimentation-connect-edit.md). El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en temas separados.

[ ![Recorrido del usuario de experimentación: vista previa y publicación](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Vista previa de las variaciones del experimento
Puede obtener una vista previa de sus variaciones y seguir editándolas hasta que se vean como desea.

Para mostrar una vista previa de las variaciones del experimento en el generador de sitios de Commerce, siga estos pasos.

1. En el menú desplegable de variaciones situado debajo de la barra de comandos, seleccione el contenido del que desea obtener una vista previa. 
1. En la barra de comandos, seleccione **Vista previa**. Se muestra una vista previa de cómo se verá el contenido cuando se publique.
1. Para obtener una vista previa de una variación diferente, selecciónela en el menú desplegable de variaciones y seleccione **Vista previa** de nuevo.

## <a name="publish-your-experiment"></a>Publique su experimento
Si no está utilizando un grupo de publicación para programar cuándo se activa su experimento y desea publicarlo de inmediato, seleccione **Publicar** en la barra de comandos. Se publicarán todas las variaciones que pertenezcan al experimento.
    
> [!IMPORTANT]
> Si la página tiene una URL no publicada, primero debe publicar la URL o no será visible para los usuarios de su sitio web. Para más detalles, consulte [Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Utilice grupos de publicación para programar cuándo se activa su experimento
Las variaciones creadas en el creador de sitios se pueden programar para su publicación mediante un grupo de publicación. Dentro de un grupo de publicación, puede conectar una página o un fragmento a su experimento seleccionando **Experimentos** en el panel de navegación izquierdo. Para hacer esto también puede seleccionar **Páginas** o **Fragmentos**, y seguir las instrucciones de [Conectar un experimento y editar variaciones](experimentation-connect-edit.md). Para obtener información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).

Al utilizar grupos de publicación con experimentos, hay algunas consideraciones importantes que debe tener en cuenta.
- Cuando agrega una página o un fragmento que tiene un experimento en ejecución a un grupo de publicación, el experimento se eliminará de la página o el fragmento en el grupo de publicación.
- Los experimentos que están conectados a las páginas de un sitio activo no están disponibles para las páginas de los grupos de publicación y viceversa. Del mismo modo, las páginas que tienen experimentos en ejecución en un sitio en vivo no están disponibles para otros experimentos en grupos de publicación y viceversa.
- Cuando publica o programa un grupo de publicación, se publica todo el contenido del grupo de publicación, independientemente de si hay un experimento asociado con el grupo de publicación.
- Debido a que un grupo de publicación continúa persistiendo después de que se haya publicado en un sitio activo, los experimentos en el grupo de publicación también persistirán. Por lo tanto, no podrá asociar otros experimentos con la misma página o fragmento. Para evitar esta limitación, elimine cualquier grupo de publicación con experimentos persistentes. Del mismo modo, si desea eliminar un experimento en un sitio activo que también existe en un grupo de publicación, elimínelo primero del grupo de publicación.

## <a name="previous-step"></a>Paso anterior
[Conectar y editar un experimento](experimentation-connect-edit.md)

## <a name="next-step"></a>Paso siguiente
[Ejecutar y supervisar un experimento](experimentation-run-monitor.md)
