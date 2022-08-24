---
title: Configurar la experiencia de ayuda para aplicaciones de finanzas y operaciones
description: Este artículo proporciona información sobre los componentes del sistema de ayuda para algunas aplicaciones Microsoft Dynamics 365.
author: edupont04
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: edupont
ms.search.region: Global
ms.author: edupont
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.form: SystemParameters
ms.openlocfilehash: 35dc37f6669a3f47dd82917be0e84d0b8698e8f8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282477"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>Configurar la experiencia de ayuda para aplicaciones de finanzas y operaciones

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

En este artículo, encontrará una descripción general de los componentes del sistema de ayuda para aplicaciones de finanzas y operaciones, como Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce y Dynamics 365 Human Resources. El artículo también explica cómo conectar estos componentes y proporciona un resumen del proceso para crear ayuda personalizada.

## <a name="help-architecture"></a>Arquitectura de la Ayuda

Las aplicaciones de finanzas y operaciones incluyen descripciones generales conceptuales y otros temas que se publican en el sitio de [documentación de Microsoft Dynamics 365](/dynamics365/). Se puede acceder a este contenido desde el panel **Ayuda** del producto. En el ejemplo siguiente se muestra las partes del sistema de Ayuda.

[![Arquitectura de la Ayuda.](./media/help-architecture.png)](./media/help-architecture.png)

El sistema de ayuda integrado en el producto extrae artículos de docs.microsoft.com y otros sitios web conectados. También extrae guías de tareas que se almacenan en Modelador de procesos empresariales (BPM), en Lifecycle Services de Microsoft Dynamics (LCS).

## <a name="adding-task-guides"></a>Adición de guías de tareas

> [!NOTE]
> La pestaña **Guías de tareas** no está actualmente en Recursos Humanos ni en Commerce. <!--We are currently working to enable this functionality in a future release.--> Sin embargo, las guías de tareas de la experiencia Introducción en Recursos humanos seguirán disponibles para cubrir las funcionalidades básicas. Tanto para Recursos Humanos como para Commerce, la ayuda de procedimiento está disponible en el sitio de [Documentación de Microsoft Dynamics 365](/dynamics365/).

En la página **Parámetros del sistema**, los administradores del sistema pueden configurar el acceso a las bibliotecas de guías de tareas relevantes para una implementación.

> [!NOTE]
> - Para configurar Ayuda, debe iniciar sesión con una cuenta en el mismo inquilino que el inquilino en el que se implementa la aplicación.
> - No es posible conectar una biblioteca LCS desde una instancia de la aplicación que se ejecute en un disco duro virtual (VHD) local.

[![Formulario Parámetros del sistema con configuración de Ayuda.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Para configurar guías de tareas para una solución, siga estos pasos en la página **Parámetros del sistema**.

> [!IMPORTANT]
> La primera vez que abra la ficha **Ayuda** debe conectarse a Lifecycle Services. Asegúrese de seleccionar el vínculo que está en la mitad del formulario, espere a la conexión, cierre el cuadro de diálogo y luego seleccione **Aceptar** para obtener la página **Parámetros del sistema**.
>
> [![Conectarse a LCS](./media/connect-to-lcs-crop-1024x365.png "Conectarse a LCS.")](./media/connect-to-lcs-crop.png)

1. Seleccione el proyecto de Lifecycle Services al que conectarse.
2. Seleccione las bibliotecas de BPM (dentro del proyecto seleccionado) desde la que recuperar grabaciones de tareas.
3. Establezca el orden de visualización de las bibliotecas de BPM. El orden de visualización define el orden en que las grabaciones de tareas de las bibliotecas aparecerán en el panel **Ayuda**.

Una vez completados estos pasos, puede abrir el panel **Ayuda** y seleccionar la pestaña **Guías de tareas**. Verá las guías de tareas que se aplican a la página en la que se encuentra actualmente en las aplicaciones de finanzas y operaciones. Si no se encuentra ninguna guía de tareas, puede escribir palabras clave para limitar la búsqueda.

### <a name="showing-translated-task-guides"></a>Mostrar guías de tareas traducidas

Las guías de tareas traducidas se distribuyeron por primera vez en la Biblioteca unificada APQC de mayo de 2016 y en la biblioteca Introducción. Para ver la ayuda de la guía de tareas localizada, asegúrese de que su solución Dynamics 365 está conectada a la biblioteca de mayo de 2016. Los usuarios pueden cambiar el idioma en el que aparece una guía de tareas cambiando la configuración de idioma en **Opciones** &gt; **Preferencias**.

> [!NOTE]
> Pese a que se han traducido muchas guías de tareas, actualmente el cliente no muestra los nombres traducidos de las guías de tareas. Además, en la biblioteca de mayo de 2016, solo están disponibles traducciones para las guías de tareas que se publicaron en febrero de 2016. Microsoft publicará una biblioteca actualizada que incluye traducciones adicionales.
>
> - Si se ha traducido una guía de tareas, al abrir esa guía de tareas, todo el texto de la guía de tareas aparecerá en el idioma seleccionado.
> - Si se ha traducido aún una guía de tareas, al abrirla, solo parte del texto (el texto de los controles) aparecerá en el idioma seleccionado.

## <a name="adding-custom-help"></a>Adición de ayuda personalizada

Puede usar las guías de tareas para crear ayuda personalizada o puede conectar un sitio web de ayuda personalizada al panel **Ayuda**.

### <a name="create-custom-help-by-using-task-guides"></a>Creación de ayuda personalizada mediante guías de tareas

Puede crear ayuda personalizada para las aplicaciones soportadas, creando grabaciones de tareas que reflejen su implementación y luego guardándolas en una biblioteca de proceso empresarial en LCS. No puede crear guías de tareas personalizadas para Recursos humanos.

Si es socio y promociona una biblioteca para que sea biblioteca corporativa e incluirla en una solución, esta quedará a disposición de sus clientes. También puede realizar una copia de la biblioteca unificada APQC y luego abrir las grabaciones de tareas en la copia, editarlas y guardar los cambios. Para obtener más información, consulte [Recursos del grabador de tareas](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Conectar un sitio de ayuda personalizada

Las aplicaciones de finanzas y operaciones rara vez se usan en su forma original. En su lugar, la solución se personaliza y se extiende para satisfacer las necesidades de la organización. También puede personalizar y ampliar la experiencia de Ayuda. Por ejemplo, puede agregar ayuda personalizada al panel **Ayuda** integrado del producto.

Microsoft ha proporcionado un kit de herramientas para ayudarle a implementar y conectar ayuda personalizada al panel **Ayuda**. Para obtener información acerca de cómo puede configurar una solución de ayuda personalizada que esté conectada al panel **Ayuda**, consulte [Resumen de ayuda personalizada](../../dev-itpro/help/custom-help-overview.md).

Si desea colaborar con Microsoft en herramientas y procesos para personalizar la ayuda, complete el formulario en [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Consulte también

[Sistema de ayuda](help-overview.md)  
[Resumen de ayuda personalizada](../../dev-itpro/help/custom-help-overview.md)  
[Recursos del Grabador de tareas](../../dev-itpro/user-interface/task-recorder.md)  
[Crear documentación o formación con el Grabador de tareas](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Repositorio GitHub de ayuda personalizada](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

