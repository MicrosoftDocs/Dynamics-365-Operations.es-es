---
title: "Visión general del sistema de flujo de trabajo"
description: "En este artículo se describe el sistema de flujo de trabajo en Microsoft Dynamics 365 for Operations."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 08c36f02f88fef7508730b6c01a1c99a0f77fb0c
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-system-overview"></a>Visión general del sistema de flujo de trabajo

[!include[banner](../includes/banner.md)]


En este artículo se describe el sistema de flujo de trabajo en Microsoft Dynamics 365 for Operations.

<a name="what-is-workflow"></a>¿Qué significa flujo de trabajo?
-----------------

El término *flujo de trabajo* se puede definir de dos maneras: como sistema y como proceso empresarial.
### <a name="workflow-is-a-system"></a>Flujo de trabajo es un sistema

El flujo de trabajo es un sistema que se instala junto con Dynamics 365 for Operations y se ejecuta en Application Object Server (AOS). El sistema de flujo de trabajo proporciona funciones que se pueden usar para crear flujos de trabajo individuales, o procesos empresariales.

### <a name="workflow-is-a-business-process"></a>Flujo de trabajo es un proceso empresarial

Un flujo de trabajo representa un proceso empresarial. El flujo de trabajo define el flujo o movimiento de un documento en el sistema al mostrar quién debe completar una tarea, tomar una decisión o aprobar un documento. Por ejemplo, en la siguiente ilustración se muestra un flujo de trabajo de informes de gastos. ![Flujo de trabajo con elementos asignados a usuarios](./media/workflow_user.gif) Para comprender mejor este flujo de trabajo, supongamos que Sam envía un informe de gastos por un valor de 7.000 USD. En esta situación, Ivan debe revisar los recibos que Sam le envía. A continuación, Frank y Sue deben aprobar el informe de gastos. Ahora supongamos que Sam envía un informe de gastos por un total de 11.000 USD. En esa situación, Ivan debe revisar los recibos y Frank, Sue y Ann deben aprobar el informe de gastos.
Ventajas del uso del sistema de flujo de trabajo
-------------------------------------

El uso del sistema de flujo de trabajo en una organización ofrece varias ventajas:
-   **Procesos coherentes**: puede definir cómo determinados documentos —por ejemplo, solicitudes de compra e informes de gastos— se procesan. Al usar el sistema de flujo de trabajo, puede asegurarse de que los documentos se procesarán y aprobarán de manera coherente y eficiente.
-   **Visibilidad de procesos**: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de las instancias de flujo de trabajo. De este modo, puede determinar si se deben realizar cambios en el flujo de trabajo para mejorar la eficiencia.
-   **Lista de trabajo centralizada**: los usuarios pueden ver una lista de trabajo centralizada con las tareas y aprobaciones de flujo de trabajo que tienen asignadas.





