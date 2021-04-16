---
title: Visión general de la creación de flujos de trabajo
description: Este tema explica cómo crear un flujo de trabajo.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 1e1c86e828eef39a6895416f4825c2853e23c826
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747768"
---
# <a name="create-workflows-overview"></a>Visión general de la creación de flujos de trabajo

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear un flujo de trabajo.

## <a name="open-the-workflow-editor"></a>Apertura del editor de flujo de trabajo

Los tipos de flujos de trabajo que puede crear varían según el módulo que está usando. Siga estos pasos para seleccionar el tipo de flujo de trabajo que va a crear y abrir el editor de flujo de trabajo.

1. Abra el módulo para el que desea crear un nuevo flujo de trabajo. Por ejemplo, para crear un flujo de trabajo para las solicitudes de compra, haga clic en **Adquisición y suministro de componentes**.
2. Haga clic en **Configuración** &gt; **Flujos de trabajo de \[nombre del módulo\]**.
3. En la página de lista que aparece, en el Panel de acciones, haga clic en **Nuevo**.
4. En la página **Crear flujo de trabajo**, seleccione el tipo de flujo de trabajo para crear y haga clic en **Crear flujo de trabajo**. Aparecerá el editor de flujo de trabajo. Ahora puede usar los siguientes procedimientos para diseñar el flujo de trabajo.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Arrastre de elementos de flujo de trabajo al lienzo

El área de **Elementos de flujo de trabajo** del editor de flujo de trabajo contiene los elementos que se pueden agregar al flujo de trabajo. Para agregar elementos al flujo de trabajo, arrástrelos al lienzo.

## <a name="connect-the-elements"></a>Conexión de los elementos

Para conectar un elemento de flujo de trabajo con otro, mantenga el puntero sobre uno de los elementos hasta que aparezcan puntos de conexión. Haga clic en uno de los puntos de conexión y arrástrelo a otro elemento. Asegúrese de conectar todos los elementos.

## <a name="configure-the-properties-of-the-workflow"></a>Configuración de las propiedades del flujo de trabajo

Siga estos pasos para configurar las propiedades del flujo de trabajo.

1. Haga clic en el lienzo para asegurarse de que no haya ningún elemento de flujo de trabajo seleccionado.
2. Haga clic en **Propiedades** para abrir la página de **Propiedades** correspondiente al flujo de trabajo.
3. Siga los procedimientos del tema [Configurar propiedades del flujo de trabajo](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Configuración de los elementos del flujo de trabajo

Configure los elementos que arrastró al lienzo. Para obtener más información acerca de cómo configurar cada elemento de flujo de trabajo, vea los siguientes temas:

- [Configurar tareas manuales en un flujo de trabajo](configure-manual-task-workflow.md)
- [Configurar tareas automatizadas en un flujo de trabajo](configure-automated-task-workflow.md)
- [Configurar los procesos de aprobación en un flujo de trabajo](configure-approval-process-workflow.md)
- [Configurar los pasos de aprobación en un flujo de trabajo](configure-approval-step-workflow.md)
- [Configurar decisiones manuales en un flujo de trabajo](configure-manual-decision-workflow.md)
- [Configurar decisiones condicionales en un flujo de trabajo](configure-conditional-decision-workflow.md)
- [Configurar ramas paralelas en un flujo de trabajo](configure-parallel-activity-workflow.md)
- [Configurar una rama paralela](configure-parallel-branch-workflow.md)
- [Configurar flujos de trabajo de elementos](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Resolución de los errores o advertencias

En el panel **Errores y advertencias** ubicado en la parte inferior del editor de flujo de trabajo se muestran los mensajes generados para el flujo de trabajo. Para encontrar el elemento en el que se produjo un error o advertencia, haga doble clic en el mensaje de error o advertencia. Antes de poder activar el flujo de trabajo, debe resolver todos los errores y advertencias.

## <a name="save-and-activate-the-workflow"></a>Guardado y activación del flujo de trabajo

Cuando esté listo para guardar y activar el flujo de trabajo, siga estos pasos.

1. Haga clic en **Guardar y cerrar** para cerrar el editor de flujo de trabajo y abrir la página **Guardar flujo de trabajo**.
2. Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo y a continuación, haga clic en **Aceptar**.
3. Si se han resuelto todos los errores y advertencias, se mostrará la página **Activar flujo de trabajo**. Seleccione una de las siguientes opciones:

    - Para activar esta versión del flujo de trabajo, haga clic en **Activar la nueva versión**. Cuando un flujo de trabajo está activo, los usuarios pueden enviar documentos a él para que se los procese.
    - Si no desea activar esta versión, haga clic en **No activar la versión nueva**. Podrá activar el flujo de trabajo en otro momento.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]