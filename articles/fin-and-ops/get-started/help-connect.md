---
title: Conectar el sistema de ayuda
description: Este tema describe los componentes del sistema de Ayuda para Microsoft Dynamics 365 for Finance and Operations y proporciona una visión general de cómo conectar los y un resumen de cómo crear la ayuda personalizada.
author: margoc
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 673b01648127fe1d19fb3c75c4d6812c4f22c761
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561984"
---
# <a name="connect-the-help-system"></a>Conectar el sistema de ayuda

[!include [banner](../includes/banner.md)]

Este tema describe los componentes del sistema de ayuda de Microsoft Dynamics 365 for Finance and Operations. Ofrece una visión general de cómo conectar estos componentes y un resumen de cómo crear una ayuda personalizada.

## <a name="help-architecture"></a>Arquitectura de la Ayuda

En la ilustración siguiente se muestran las partes del sistema de Ayuda de Finance and Operations. El sistema de Ayuda del producto extrae artículos del sitio de Finance and Operations en https://docs.microsoft.com, además de guías de tareas guardadas en el Modelador de procesos empresariales de Lifecycle Services (LCS).

> [!NOTE]
> Las características que aparecen en el diagrama con un asterisco (\*) están planificadas, pero aún no se encuentran disponibles.

[![Arquitectura de la Ayuda](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conexión con el sistema de Ayuda

> [!NOTE]
> La pestaña **Guías de la tarea** no está actualmente disponible en Microsoft Dynamics 365 for Talent y Microsoft Dynamics 365 for Retail. Estamos trabajando actualmente para permitir esta funcionalidad en una versión futura. Las Guías de tareas para la Introducción a Talent seguirán disponibles para cubrir las funcionalidades básicas. La ayuda de procedimientos también está disponible en el sitio de docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) para Retail y Talent.

Con el formulario **Parámetros del sistema**, los administradores del sistema conectan las piezas del sistema de Ayuda para una implementación.

[![Formulario Parámetros del sistema con configuración de Ayuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

En la página **Parámetros del sistema**, siga estos pasos:

> [!IMPORTANT]
> La primera vez que abra la ficha **Ayuda** debe conectarse a Lifecycle Services. Asegúrese de hacer clic en el vínculo que hay en el medio del formulario, espere por la conexión, cierre el cuadro de diálogo y haga clic en **Aceptar** para obtener la página **Parámetros del sistema**.
>
> [![Conectar a LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar a LCS")](./media/connect-to-lcs-crop.png)

1. Seleccione el proyecto de Lifecycle Services al que conectarse.
2. Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.

    - En cuanto a Finance and Operations, para el contenido de Microsoft, seleccione la Biblioteca unificada APQC más reciente para Finance and Operations.
    - Para Retail, lanzaremos al mercado una biblioteca en un futuro próximo.
    - No necesita seleccionar una biblioteca para Talent, la conexión para la biblioteca correcta se establece automáticamente.

3. Establezca el orden de visualización de las bibliotecas de BPM. Esto determina el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.

Una vez complete estos pasos, puede abrir el panel de **Ayuda** y hacer clic en la pestaña **Guías de tareas**. Verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en Finance and Operations. Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.

### <a name="showing-translated-task-guides"></a>Mostrar guías de tareas traducidas

Las guías de tareas traducidas se incluyeron por primera vez en la biblioteca unificada APQC de mayo de 2016 y en la biblioteca de introducción. En Finance and Operations, para ver la ayuda de la guía de tareas localizada, asegúrese de que está conectado a la biblioteca de mayo. El idioma en el que aparece una guía de tareas se controla para cada usuario mediante la configuración de idioma en **Opciones** &gt; **Preferencias**.

> [!NOTE]
> Aunque se hayan traducido muchas guías de tareas, actualmente el cliente de Finance and Operations no muestra los nombres traducidos de las guías de tareas. Además, en la biblioteca de mayo de solo están disponibles en este momento las guías de tareas que se publicaron en febrero de 2016. Publicaremos una biblioteca actualizada con traducciones adicionales.
>
> - Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.
> - Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="creating-custom-help"></a>Creación de ayuda personalizada

Puede usar las guías de tareas para crear ayuda personalizada, o para conectar una página Web al panel de la Ayuda.

### <a name="create-custom-help-with-task-guides"></a>Creación de ayuda personalizada mediante guías de tareas

Puede crear ayuda personalizada para su implementación de Finance and Operations y para Retail creando grabaciones de tareas que reflejan su implementación y guardándolos en una Biblioteca de proceso empresarial LCS. No puede crear guías de tareas personalizadas para Talent.

Para socios, si promociona una biblioteca para que sea una biblioteca corporativa, e incluirla en una solución, esta estará disponible para sus clientes. También puede realizar una copia de la biblioteca global unificada APQC y, a continuación abrir su copia, abrir grabaciones de tareas desde allí, modificarlas y guardar las grabaciones con sus cambios. Para obtener más información, consulte el tema [Cómo crear una grabación de tareas para usarla como documentación o formación](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Conectar un sitio personalizado

Microsoft ha proporcionado documentación técnica y código de muestra que describen cómo crear y conectar un sitio personalizado de la ayuda al panel de la Ayuda. Para obtener más información, consulte:

- [Crear Ayuda personalizada para Finance and Operations (documentación técnica)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Repositorio GitHub de ayuda personalizada](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la ayuda](help-overview.md)

[Visión general del Grabador de tareas](../../dev-itpro/user-interface/task-recorder.md)

[Cómo crear una grabación de tareas para usarla como documentación o formación](../../dev-itpro/user-interface/task-recorder-training-docs.md)
