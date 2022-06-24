---
title: Conectar un experimento y editar variaciones
description: Este artículo describe cómo conectar un experimento en un servicio de terceros a Dynamics 365 Commerce y cómo editar variaciones para el experimento.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942831"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Conectar un experimento y editar variaciones

Este artículo describe cómo conectar su experimento en Commerce y realizar cambios en sus variaciones para que se alineen con su hipótesis. 

El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en artículos separados.

[ ![Recorrido del usuario de experimentación: conectar y editar.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Después de [configurar un experimento](experimentation-setup.md) en un servicio de terceros, conectará el experimento en Dynamics 365 Commerce y editará las variaciones del experimento.

## <a name="connect-your-experiment"></a>Conecte el experimento
Para conectar su experimento, iniciará el asistente **Conectar experimento**. El asistente lo guía a través de los pasos necesarios para conectar su experimento. Cuando complete el asistente, su experimento estará conectado y las variaciones se crearán y estarán listas para ser editadas.

Para empezar a conectar su experimento en el generador de sitios de Commerce, siga estos pasos.

1. Para iniciar el asistente **Conectar experimento**, seleccione **Experimentos** en el panel de navegación izquierdo y, a continuación, seleccione **Conectar**. Como alternativa, puede acceder al asistente desde una página o editor de fragmentos editándolo y seleccionando **Conectar experimento** en la barra de comandos.

    > [!NOTE]
    > - Una página solo se puede conectar a un experimento a la vez. Para conectar una página a un experimento diferente, primero elimine el experimento al que está conectada actualmente la página.
    > - Solo puede experimentar en páginas con un diseño personalizado. Si su página tiene un diseño preestablecido, primero conviértalo a un diseño personalizado. Puede hacerlo yendo a la página y seleccionando **Convertir a diseño personalizado** en la barra de comandos. Para obtener más información sobre diseños, consulte [Diseños preestablecidos y personalizados](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Si se está conectando a un experimento desde la pestaña **Experimentos** del panel de navegación izquierdo, seleccione el nombre del experimento de la lista que aparece.
1. Seleccione la página o el fragmento en el que desea ejecutar su experimento.
1. En el paso final del asistente, seleccione **Asistente para generar variaciones y salir**. Se crean variaciones para el experimento. 

> [!NOTE]
> Si desea programar cuándo se publicará su experimento en su sitio en vivo, asegúrese de que el contenido que desea asociar con el experimento esté disponible en un grupo de publicación *antes de* conectar el experimento. Para obtener más información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).

## <a name="edit-your-variations"></a>Edita tus variaciones

Cuando salga del asistente **Conectar experimento**, se crean variaciones para usted. Siga los pasos a continuación para editar las variaciones para que reflejen las opciones que necesita verificar en la hipótesis del experimento.

1. En la vista de editor, use el menú desplegable de variaciones debajo de la barra de comandos para editar cada variación según su hipótesis original. También es posible que desee establecer una variación de control o base dejando una de las variaciones sin cambios.
1. Seleccione el módulo en el que se va a experimentar, seleccione los puntos suspensivos (...) y luego seleccione **Agregar al experimento**.

> [!NOTE]
> Considere establecer una variación de control o base dejando una de las variaciones sin cambios.

## <a name="previous-step"></a>Paso anterior
[Configurar un experimento](experimentation-setup.md) 


## <a name="next-step"></a>Paso siguiente
[Obtener una vista previa y publicar un experimento](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
