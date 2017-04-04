---
title: "Conexión del sistema de ayuda"
description: "Este tema describe los componentes del sistema de Ayuda de Microsoft Dynamics 365 for Operations y proporciona una visión general de cómo conectarlos y un resumen de cómo crear la ayuda personalizada."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
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
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>Conexión del sistema de ayuda

Este tema describe los componentes del sistema de ayuda de Microsoft Dynamics 365 para las operaciones. Ofrece una visión general de cómo conectar estos componentes y un resumen de cómo crear ayuda personalizada. 

<a name="help-architecture"></a>Arquitectura de la Ayuda
-----------------

La ilustración siguiente muestra las partes de Dynamics 365 para el sistema de Ayuda de las operaciones. El sistema de ayuda de en- producto extrae los artículos de Dynamics 365 para el sitio de las operaciones en https://docs.microsoft.com, junto con la tarea dirige almacenado en modelador del proceso empresarial de servicios (LCS) del ciclo de vida. 
** Nota: ** Las características que aparecen en el gráfico con un asterisco (\*) se planifican, pero no están disponibles aún. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conexión del sistema de ayuda
** Mediante los parámetros del sistema ** la página, administradores del sistema los conectan piezas del sistema de ayuda de una implementación. [formulario Parámetros del sistema![con los valores de la Ayuda] (. /media/system-parameters_ops-1024x437.png])(. /media/system-parameters_ops.png) ** En los parámetros del sistema ** la página, siga estos pasos:

1.  ** Importante: ** La primera vez que abra el ** Ayuda ** la ficha, debe conectar con los servicios del ciclo de vida. Asegúrese de haga clic en el vínculo del medio del formulario, espere la conexión, cierre el cuadro de diálogo, y haga clic en ** éste ** para obtener ** los parámetros del sistema ** a la página. Esta [! Conectar al [] (CD. /media/connect-to-lcs-crop-1024x365.png “Conectars al CD”)](. /media/connect-to-lcs-crop.png)
2.  Seleccione el proyecto de Lifecycle Services al que conectarse.
3.  Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.
4.  Establezca el orden de visualización de las bibliotecas de BPM. Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.

Tras completar estos pasos, puede abrir el panel **Ayuda** y hacer clic en la pestaña **Guías de tareas**. Ahora verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en Dynamics 365 for Operations. Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.

### <a name="showing-translated-task-guides"></a>Mostrar guías de tareas traducidas

Traducidas le orienta acerca de la primera tarea se han registrado en la biblioteca unificada APQC de mayo de 2016, y la biblioteca de la Introducción. En Dynamics 365 for Operations, para ver la ayuda de la guía de tareas localizada, asegúrese de que está conectado a la biblioteca de mayo. El idioma que una guía de la tarea aparece en se controla para cada usuario por la configuración de idioma ** bajo las opciones ** &gt; ** preferencias **. **Nota:** Aunque se han traducido muchas guías de tareas, actualmente el cliente de Dynamics 365 for Operations no muestra los nombres traducidos de las guías de tareas. Además, solo las guías de la tarea lanzadas a partir en febrero de 2016 están disponibles en traducción en la biblioteca de mayo. Publicaremos una biblioteca actualizada con traducciones adicionales.

-   Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.
-   Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="creating-custom-help"></a>Creación de ayuda personalizada
Puede crear ayuda personalizada para su implementación de Dynamics 365 for Operations creando grabaciones de tareas que reflejan su implementación y guardándolos en una Biblioteca de proceso empresarial LCS. Para socios, si promociona una biblioteca para que sea una biblioteca corporativa, e incluirla en una solución, esta estará disponible para sus clientes. También puede realizar una copia de la biblioteca global unificada APQC y, a continuación abrir su copia, abrir grabaciones de tareas desde allí, modificarlas y guardar las grabaciones con sus cambios. Para obtener más información, consulte [de cómo crear una tarea que registra para utilizar como documentación o que usuarios (.]. /user-interface/task-recorder.md).

<a name="see-also"></a>Consulte también
--------

[Help overview](help-overview.md)

[Visión general del Grabador de tareas (.]. /user-interface/task-recorder.md)

[Cómo crear una grabación de tareas para usarla como documentación o formación](../user-interface/task-recorder-training-docs.md)

[Creando nuevas bibliotecas de formación para Dynamics 365 para las operaciones de servicios del ciclo de vida utilizando el Grabador de tareas (vínculo externo)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


