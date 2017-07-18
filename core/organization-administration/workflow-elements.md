---
title: Elementos del flujo de trabajo
description: "Este artículo describe los diversos elementos que componen un flujo de trabajo."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a3a12080efcb138365c26981abd51222c51663ff
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="workflow-elements"></a>Elementos del flujo de trabajo

[!include[banner](../includes/banner.md)]


Este artículo describe los diversos elementos que componen un flujo de trabajo.

Un flujo de trabajo está compuesto de elementos. Las secciones que siguen describen cada tipo de elemento.

## <a name="tasks"></a>Tareas
Una *tarea* es una unidad de trabajo que se debe llevar a cabo. A un flujo de trabajo se le pueden agregar dos tipos de tareas: tareas manuales o tareas automatizadas.

### <a name="manual-task"></a>Tarea manual

Una *tarea manual* es una unidad de trabajo que debe llevar a cabo un usuario. Por ejemplo, un flujo de trabajo de informe de gastos podría incluir tareas manuales que requieran que los usuarios asignados realicen las siguientes acciones:

-   Revisar los recibos que se envían junto con los informes de gastos.
-   Llamar al director de un empleado.

### <a name="automated-task"></a>Tarea automatizada

Una *tarea automatizada* es una unidad de trabajo que debe llevar a cabo el sistema. No se requiere la intervención del usuario. Por ejemplo, un flujo de trabajo de pedidos de ventas puede incluir tareas automatizadas que requieran que el sistema realice las siguientes acciones:

-   Realizar una comprobación de crédito.
-   Crear un registro de cliente para el cliente si no existe ya un registro.

## <a name="approval-processes"></a>Procesos de aprobación
Un *proceso de aprobación* es un proceso que consta de pasos individuales. En cada paso de aprobación, el usuario puede realizar las acciones siguientes:

-   Aprobar el documento.
-   Rechazar el documento.
-   Solicitar que se realice un cambio en el documento.
-   Asignar el documento a otro usuario para que lo apruebe.

## <a name="lineitem-workflow-elements"></a>Elementos de flujo de trabajo de artículos de línea
Se puede crear un flujo de trabajo para procesar documentos o los artículos de línea de un documento. Por ejemplo, ha creado un flujo de trabajo de aprobación para las hojas de horas (Nos referiremos a este flujo de trabajo por el nombre de *flujo de trabajo de documento*). Puede agregar un *flujo de trabajo de artículos de línea* a dicho flujo de trabajo de documento. Cuando se ejecuta el artículo de cada línea en el documento, este se envía para su procesamiento. Quizás desee que el mismo flujo de trabajo de elementos procese todos los artículos de línea o, por lo contrario, tal vez prefiera que distintos flujos de trabajo de elementos procesen cada artículo de línea diferente. Imaginemos que un empleado ha enviado una hoja de horas que se asemeja a la siguiente ilustración. ![Flujo de trabajo con artículos de línea](./media/workflow_lineitemworkflow.gif) En esta situación, puede que desee crear los siguientes flujos de trabajo de elementos:

-   **Flujo de trabajo de elementos 1**: este flujo de trabajo se usa para procesar los artículos de línea cuando el id. de proyecto es 1111.
-   **Flujo de trabajo de elementos 2**: este flujo de trabajo se usa para procesar los artículos de línea cuando el id. de proyecto es 2222.
-   **Flujo de trabajo de elementos 3**: este flujo de trabajo se usa para procesar los artículos de línea cuando el id. de proyecto es 3333.

## <a name="flowcontrol-elements"></a>Elementos de control de flujo
Los siguientes elementos permiten diseñar flujos de trabajo con ramas alternativas o ramas que se ejecutan al mismo tiempo.

### <a name="manual-decision"></a>Decisión manual

Una *decisión manual* se encuentra en el punto en el que el flujo de trabajo se divide en dos ramas. Un usuario debe tomar una decisión, y es esta decisión la que determina la rama que se usa para procesar el documento enviado.

### <a name="conditional-decision"></a>Decisión condicional

Una *decisión condicional* se encuentra también en el punto en el que el flujo de trabajo se divide en dos ramas. Sin embargo, el sistema decide la rama que se usa para procesar el documento enviado. Para tomar esta decisión, el sistema evalúa el documento para determinar si reúne las condiciones especificadas.

### <a name="parallel-activity"></a>Actividad paralela

Una *actividad paralela* es un elemento de flujo de trabajo que incluye dos o más ramas de flujo de trabajo que se ejecutan al mismo tiempo.

### <a name="subworkflow"></a>Subflujo de trabajo

Un *subflujo de trabajo* es un flujo de trabajo que se ejecuta en el contexto de otro flujo de trabajo.




