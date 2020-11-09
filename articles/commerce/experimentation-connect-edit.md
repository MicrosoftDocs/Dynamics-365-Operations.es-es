---
title: Conectar un experimento y editar variaciones
description: Este tema describe cómo conectar un experimento en un servicio de terceros a Dynamics 365 Commerce y cómo editar variaciones para el experimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 030640ba8907ae52c198ac96ad2c243b533d8c53
ms.sourcegitcommit: 7592c2dec0428d56843ab395d2a52c89f77f99b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "4096976"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Conectar un experimento y editar variaciones

Este tema describe cómo conectar su experimento en Commerce y realizar cambios en sus variaciones para que se alineen con su hipótesis. 

El siguiente diagrama muestra todos los pasos necesarios para configurar y ejecutar un experimento en un sitio web de comercio electrónico en Dynamics 365 Commerce. Los pasos adicionales se tratan en temas separados.

[ ![Recorrido del usuario de experimentación: conectar y editar](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Después de [configurar un experimento](experimentation-setup.md) en un servicio de terceros, conectará el experimento en Dynamics 365 Commerce y editará las variaciones del experimento.

## <a name="planning-considerations"></a>Consideraciones de planificación

Antes de conectar su experimento en Commerce, deberá tomar algunas decisiones que afecten la forma en que Commerce administra su contenido.

### <a name="determine-the-scope-of-your-experiment"></a>Determine el alcance de su experimento
Cuando conecta un experimento, se le solicita que defina el alcance del experimento. Los experimentos se definen como de alcance **parcial** o **total**.
- Escoja **parcial** si desea realizar un experimento en una parte específica de una página. Si selecciona esta opción, debe identificar qué módulos se incluyen en el experimento. Los cambios que se realizan en partes de la página o el fragmento predeterminados que no están relacionados con el experimento se sincronizan automáticamente entre las variaciones.
- Escoja **total** si desea realizar un experimento en una página completa o en un fragmento. Se crean copias separadas de la página o el fragmento predeterminados. No tendrá que seleccionar qué módulos están incluidos en el experimento porque toda la superficie de edición está disponible para cambiar. Puede agregar, eliminar o reordenar módulos según sea necesario. Sin embargo, si se realizan cambios en la página predeterminada o en el fragmento con el que está asociado el experimento, esos cambios deben sincronizarse manualmente en todas las variaciones.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Si asocia su experimento con una página que utiliza un diseño, solo puede definir el alcance del experimento como **total**.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Decida si quiere programar la publicación del experimento
Si desea programar cuándo se publicará su experimento en su sitio en vivo, asegúrese de que el contenido que desea asociar con el experimento esté disponible en un grupo de publicación *antes de* conectar el experimento. 

Para obtener más información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).


## <a name="connect-your-experiment"></a>Conecte el experimento
Para conectar su experimento, iniciará el asistente **Conectar experimento**. El asistente lo guía a través de los pasos necesarios para conectar su experimento. Cuando complete el asistente, su experimento estará conectado y las variaciones se crearán y estarán listas para ser editadas.

Para empezar a conectar su experimento en el generador de sitios de Commerce, siga estos pasos.

1. Para iniciar el asistente **Conectar experimento** , seleccione **Experimentos** en el panel de navegación izquierdo y, a continuación, seleccione **Conectar**. Como alternativa, puede acceder al asistente desde una página o editor de fragmentos editándolo y seleccionando **Conectar experimento** en la barra de comandos.

    > [!NOTE]
    > Una página solo se puede conectar a un experimento a la vez. Para conectar una página a un experimento diferente, primero elimine el experimento al que está conectada actualmente la página.

1. Elija la página o el fragmento en el que desea ejecutar su experimento.
1. Establezca el alcance de la experimentación en **parcial** o **total** , según la elección que hizo en la sección anterior [Determinar el alcance de su experimento](#determine-the-scope-of-your-experiment).
    > [!NOTE]
    > El indicador de la característica **Experimentar con páginas o fragmentos** debe estar habilitado si desea experimentar en una página completa o en un fragmento. Para obtener más información, consulte el tema [Experimención en Dynamics 365 Commerce](experimentation-overview.md).
    
1. En el paso final del asistente, seleccione **Asistente para generar variaciones y salir**. Se crean variaciones para el experimento. 

## <a name="edit-your-variations"></a>Edita tus variaciones
Cuando sale del asistente, se crean variaciones para usted. 

A continuación, editará las variaciones para que reflejen las opciones que necesita verificar en la hipótesis del experimento. Elija uno de los siguientes procedimientos que corresponda al alcance que eligió para su experimento en la sección anterior [Determinar el alcance de su experimento](#determine-the-scope-of-your-experiment).

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Editar variaciones para experimentos con alcance parcial
Siga estos pasos si definió el alcance de su experimento como **parcial** en el asistente **Conectar experimento**.

1. En la vista de editor, use el menú desplegable de variaciones debajo de la barra de comandos para editar cada variación según su hipótesis original. También es posible que desee establecer una variación de control o base dejando una de las variaciones sin cambios.
1. Seleccione el módulo en el que se va a experimentar, seleccione los puntos suspensivos (...) y luego seleccione **Agregar al experimento**.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Editar variaciones para experimentos con alcance total
Si definió el alcance de su experimento como **total** en el asistente **Conectar experimento** , mientras está en la vista de editor, use el menú desplegable de variaciones debajo de la barra de comandos para editar cada variación en función de su hipótesis original. 

> [!NOTE]
> En cualquier caso, también es posible que desee establecer una variación de control o base dejando una de las variaciones sin cambios.

## <a name="previous-step"></a>Paso anterior
[Configurar un experimento](experimentation-setup.md) 


## <a name="next-step"></a>Paso siguiente
[Obtener una vista previa y publicar un experimento](experimentation-preview-publish.md)
