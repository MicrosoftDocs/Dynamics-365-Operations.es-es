---
title: "Creación de un flujo de trabajo"
description: "Este tema explica cómo crear un flujo de trabajo."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, UnifiedOperations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 138cf8d60f5a6e1ec1e46837a516e981c8ff4c19
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# <a name="create-a-workflow"></a>Creación de un flujo de trabajo

[!include[banner](../includes/banner.md)]


Este tema explica cómo crear un flujo de trabajo.

<a name="open-the-workflow-editor"></a>Apertura del editor de flujo de trabajo
------------------------

El módulo de Microsoft Dynamics 365 for Finance and Operations en el que está trabajando determina los tipos de flujo de trabajo que puede crear. Siga estos pasos para seleccionar el tipo de flujo de trabajo que va a crear y abrir el editor de flujo de trabajo.

1.  Abra el módulo para el que desea crear un nuevo flujo de trabajo. Por ejemplo, para crear un flujo de trabajo para las solicitudes de compra, haga clic en **Adquisición y suministro de componentes**.
2.  Haga clic en **Configuración** &gt; **Flujos de trabajo de \[nombre del módulo\]**.
3.  En la página de lista que aparece, en el Panel de acciones, haga clic en **Nuevo**.
4.  En la página **Crear flujo de trabajo**, seleccione el tipo de flujo de trabajo para crear y haga clic en **Crear flujo de trabajo**. Aparecerá el editor de flujo de trabajo. Ahora puede usar los siguientes procedimientos para diseñar el flujo de trabajo.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Arrastre de elementos de flujo de trabajo al lienzo
El área de **Elementos de flujo de trabajo** del editor de flujo de trabajo contiene los elementos que se pueden agregar al flujo de trabajo. Para agregar elementos al flujo de trabajo, arrástrelos al lienzo.

## <a name="connect-the-elements"></a>Conexión de los elementos
Para conectar un elemento de flujo de trabajo con otro, mantenga el puntero sobre uno de los elementos hasta que aparezcan puntos de conexión. Haga clic en uno de los puntos de conexión y arrástrelo a otro elemento. Asegúrese de conectar todos los elementos.

## <a name="configure-the-properties-of-the-workflow"></a>Configuración de las propiedades del flujo de trabajo
Siga estos pasos para configurar las propiedades del flujo de trabajo.

1.  Haga clic en el lienzo para asegurarse de que no haya ningún elemento de flujo de trabajo seleccionado.
2.  Haga clic en **Propiedades** para abrir la página de **Propiedades** correspondiente al flujo de trabajo.
3.  Siga los procedimientos del tema [Configurar las propiedades del flujo de trabajo](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configuración de los elementos del flujo de trabajo
Configure los elementos que arrastró al lienzo. Para obtener más información acerca de cómo configurar cada elemento de flujo de trabajo, vea los siguientes temas:

-   [Configuración de una tarea manual](configure-manual-task-workflow.md)
-   [Configuración de una tarea automatizada](configure-automated-task-workflow.md)
-   [Configuración de un proceso de aprobación](configure-approval-process-workflow.md)
-   [Configuración de un paso de aprobación](configure-approval-step-workflow.md)
-   [Configuración de una decisión manual](configure-manual-decision-workflow.md)
-   [Configuración de una decisión condicional](configure-conditional-decision-workflow.md)
-   [Configuración de una actividad paralela](configure-parallel-activity-workflow.md)
-   [Configuración de una rama paralela](configure-parallel-branch-workflow.md)
-   [Configuración de un flujo de trabajo de elementos](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Resolución de los errores o advertencias
En el panel **Errores y advertencias** ubicado en la parte inferior del editor de flujo de trabajo se muestran los mensajes generados para el flujo de trabajo. Para encontrar el elemento en el que se produjo un error o advertencia, haga doble clic en el mensaje de error o advertencia. Antes de poder activar el flujo de trabajo, debe resolver todos los errores y advertencias.

## <a name="save-and-activate-the-workflow"></a>Guardado y activación del flujo de trabajo
Cuando esté listo para guardar y activar el flujo de trabajo, siga estos pasos.

1.  Haga clic en **Guardar y cerrar** para cerrar el editor de flujo de trabajo y abrir la página **Guardar flujo de trabajo**.
2.  Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo y a continuación, haga clic en **Aceptar**.
3.  Si se han resuelto todos los errores y advertencias, se mostrará la página **Activar flujo de trabajo**. Seleccione una de las siguientes opciones:
    -   Para activar esta versión del flujo de trabajo, haga clic en **Activar la nueva versión**. Cuando un flujo de trabajo está activo, los usuarios pueden enviar documentos a él para que se los procese.
    -   Si no desea activar esta versión, haga clic en **No activar la versión nueva**. Podrá activar el flujo de trabajo en otro momento.






