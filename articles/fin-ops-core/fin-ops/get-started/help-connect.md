---
title: Conectar el sistema de ayuda
description: Este tema describe los componentes del sistema de Ayuda para aplicaciones de Finance and Operations y proporciona una visión general de cómo conectar los y un resumen de cómo crear la ayuda personalizada.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4427388d75c1aef40a978ce35c831d5b714f2562
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006181"
---
# <a name="connect-the-help-system"></a>Conectar el sistema de ayuda

[!include [banner](../includes/banner.md)]

Este tema describe los componentes del sistema de ayuda de las aplicaciones de Finance and Operations como Dynamics 365 Finance, Supply Chain Management, Commerce y Human Resources. Ofrece una visión general de cómo conectar estos componentes y un resumen de cómo crear una ayuda personalizada.

## <a name="help-architecture"></a>Arquitectura de la Ayuda

En el ejemplo siguiente se muestra las partes del sistema de Ayuda. El sistema de Ayuda del producto extrae artículos de https://docs.microsoft.com, además de guías de tareas guardadas en el Modelador de procesos empresariales de Lifecycle Services (LCS).

> [!NOTE]
> Las características que aparecen en el diagrama con un asterisco (\*) están planificadas, pero aún no se encuentran disponibles.

[![Arquitectura de la Ayuda](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conexión con el sistema de Ayuda

> [!NOTE]
> La pestaña **Guías de la tarea** no está actualmente disponible en Dynamics 365 Human Resources o Commerce. Estamos trabajando actualmente para permitir esta funcionalidad en una versión futura. Las Guías de tareas para la Introducción a Human Resources seguirán disponibles para cubrir las funcionalidades básicas. La ayuda de procedimiento también está disponible en el sitio de docs.microsoft.com para Human Resources y Commerce.

Con el formulario **Parámetros del sistema**, los administradores del sistema conectan las piezas del sistema de Ayuda para una implementación.

[![Formulario Parámetros del sistema con configuración de Ayuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

En la página **Parámetros del sistema**, siga estos pasos:

> [!IMPORTANT]
> La primera vez que abra la ficha **Ayuda** debe conectarse a Lifecycle Services. Asegúrese de hacer clic en el vínculo que hay en el medio del formulario, espere por la conexión, cierre el cuadro de diálogo y haga clic en **Aceptar** para obtener la página **Parámetros del sistema**.
>
> [![Conectarse a LCS](./media/connect-to-lcs-crop-1024x365.png "Conectarse a LCS")](./media/connect-to-lcs-crop.png)

1. Seleccione el proyecto de Lifecycle Services al que conectarse.
2. Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.
3. Establezca el orden de visualización de las bibliotecas de BPM. Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.

Una vez complete estos pasos, puede abrir el panel de **Ayuda** y hacer clic en la pestaña **Guías de tareas**. Verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en las aplicaciones de Finance and Operations. Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.

### <a name="showing-translated-task-guides"></a>Mostrar guías de tareas traducidas

Las guías de tareas traducidas se incluyeron por primera vez en la biblioteca unificada APQC de mayo de 2016 y en la biblioteca de introducción. En las aplicaciones de Finance and Operations, para ver la ayuda de la guía de tareas localizada, asegúrese de que está conectado a la biblioteca de mayo. El idioma en el que aparece una guía de tareas se controla para cada usuario mediante la configuración de idioma en **Opciones** &gt; **Preferencias**.

> [!NOTE]
> Aunque se han traducido muchas guías de tareas, ahora el cliente no muestra los nombres traducidos de las guías de tareas. Además, en la biblioteca de mayo de solo están disponibles en este momento las guías de tareas que se publicaron en febrero de 2016. Publicaremos una biblioteca actualizada con traducciones adicionales.
>
> - Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.
> - Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="creating-custom-help"></a>Creación de ayuda personalizada

Puede usar las guías de tareas para crear ayuda personalizada, o para conectar una página Web al panel de la Ayuda.

### <a name="create-custom-help-with-task-guides"></a>Creación de ayuda personalizada mediante guías de tareas

Puede crear ayuda personalizada para su implementación de Supply Chain Management y para Commerce creando grabaciones de tareas que reflejan su implementación y guardándolos en una Biblioteca de proceso empresarial LCS. No puede crear guías de tareas personalizadas para Human Resources.

Para socios, si promociona una biblioteca para que sea una biblioteca corporativa, e incluirla en una solución, esta estará disponible para sus clientes. También puede realizar una copia de la biblioteca global unificada APQC y, a continuación abrir su copia, abrir grabaciones de tareas desde allí, modificarlas y guardar las grabaciones con sus cambios. Para obtener más información, consulte [Recursos del grabador de tareas](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Conectar un sitio personalizado

Microsoft ha proporcionado documentación técnica y código de muestra que describen cómo crear y conectar un sitio personalizado de la ayuda al panel de la Ayuda. Para obtener más información, consulte:

- [Crear ayuda personalizada para aplicaciones de Finance and Operations (notas del producto)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Repositorio GitHub de ayuda personalizada](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Recursos adicionales

[Sistema de ayuda](help-overview.md)

[Recursos del Grabador de tareas](../../dev-itpro/user-interface/task-recorder.md)

[Crear documentación o formación con el Grabador de tareas](../../dev-itpro/user-interface/task-recorder-training-docs.md)
