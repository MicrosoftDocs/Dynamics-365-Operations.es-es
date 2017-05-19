---
title: "Conexión del sistema de ayuda"
description: "Este tema describe los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations y proporciona una visión general de cómo conectarlos y un resumen de cómo crear la ayuda personalizada."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f9af4de5f15125569d8f3e78f36e6a2b9c2a089b
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="connect-the-help-system"></a>Conexión del sistema de ayuda

[!include[banner](../includes/banner.md)]


En este tema se describen los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations. Ofrece una visión general de cómo conectar estos componentes y un resumen de cómo crear una ayuda personalizada. 

<a name="help-architecture"></a>Arquitectura de la Ayuda
-----------------

En la ilustración siguiente se muestran las partes del sistema de Ayuda de Microsoft Dynamics 365 for Operations. El sistema de Ayuda del producto extrae artículos del sitio de Dynamics 365 for Operations en on https://docs.microsoft.com, además de guías de tareas guardadas en el Modelador de procesos empresariales de Microsoft Dynamics Lifecycle Services (LCS). 
**Nota:** Las características que aparecen en el diagrama con un asterisco (\*) están planificadas, pero aún no se encuentran disponibles. [![Arquitectura de la Ayuda](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conexión con el sistema de Ayuda
Con el formulario **Parámetros del sistema**, los administradores del sistema conectan las piezas del sistema de Ayuda para una implementación. [![Formulario de parámetros del sistema con configuración de la Ayuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) En la página **Parámetros del sistema**, siga estos pasos:

> [!IMPORTANT]
> La primera vez que abra la ficha **Ayuda** debe conectarse a Lifecycle Services. Asegúrese de hacer clic en el vínculo que hay en medio del formulario, esperar la conexión, cerrar el cuadro de diálogo y hacer clic en **Aceptar** para ir a la página **Parámetros del sistema**.[![Conectarse a LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)

1.  Seleccione el proyecto de Lifecycle Services al que conectarse.
2.  Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.
3.  Establezca el orden de visualización de las bibliotecas de BPM. Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.

Tras completar estos pasos, puede abrir el panel **Ayuda** y hacer clic en la pestaña **Guías de tareas**. Ahora verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en Dynamics 365 for Operations. Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.

### <a name="showing-translated-task-guides"></a>Mostrar guías de tareas traducidas

Las guías de tareas traducidas se incluyeron por primera vez en la biblioteca unificada APQC de mayo de 2016 y en la biblioteca de introducción. En Dynamics 365 for Operations, para ver la ayuda de la guía de tareas localizada, asegúrese de que está conectado a la biblioteca de mayo. El idioma en el que aparece una guía de tareas se controla para cada usuario mediante la configuración de idioma en **Opciones** &gt; **Preferencias**. 

> [!NOTE]
> Aunque se hayan traducido muchas guías de tareas, actualmente el cliente de Dynamics 365 for Operations no muestra los nombres traducidos de las guías de tareas. Además, en la biblioteca de mayo de solo están disponibles en este momento las guías de tareas que se publicaron en febrero de 2016. Publicaremos una biblioteca actualizada con traducciones adicionales.
> -   Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.
> -   Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="creating-custom-help"></a>Creación de ayuda personalizada
Puede crear ayuda personalizada para su implementación de Dynamics 365 for Operations creando grabaciones de tareas que reflejan su implementación y guardándolos en una Biblioteca de proceso empresarial LCS. Para socios, si promociona una biblioteca para que sea una biblioteca corporativa, e incluirla en una solución, esta estará disponible para sus clientes. También puede realizar una copia de la biblioteca global unificada APQC y, a continuación abrir su copia, abrir grabaciones de tareas desde allí, modificarlas y guardar las grabaciones con sus cambios. Para obtener más información, consulte el tema [Cómo crear una grabación de tareas para usarla como documentación o formación](../user-interface/task-recorder.md).

<a name="see-also"></a>Consulte también
--------

[Visión general de la ayuda](help-overview.md)

[Visión general del Grabador de tareas](../user-interface/task-recorder.md)

[Cómo crear una grabación de tareas para usarla como documentación o formación](../user-interface/task-recorder-training-docs.md)





