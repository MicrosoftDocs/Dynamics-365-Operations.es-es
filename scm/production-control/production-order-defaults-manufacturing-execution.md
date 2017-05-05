---
title: "Configuración predeterminada de pedidos de producción en ejecución de fabricación"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70073
ms.assetid: 620944ae-3e20-444a-807e-65495f160904
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: b310e799c1ef0756291c5f7ab886531e4caf1945
ms.lasthandoff: 03/31/2017


---

# <a name="production-order-defaults-in-manufacturing-execution"></a>Configuración predeterminada de pedidos de producción en ejecución de fabricación

[!include[banner](../includes/banner.md)]




Xonsidere atentamente las opciones de la página **Valores predeterminados de pedido de producción** antes de que los trabajadores comiencen a realizar registros de los trabajos de producción. Si su empresa utiliza la funcionalidad multisitio, quizá le convendría configurar diferentes valores predeterminados para pedidos de producción en función del sitio. Los valores predeterminados de los pedidos para su integración con el control de producción se configuran en las siguientes fichas de la página **Valores predeterminados de pedido de producción**:

-   **General**: valores predeterminados del pedido generales para los trabajos de producción en la ejecución de fabricación.
-   **Inicio**: valores predeterminados de pedido que se usan cuando se inician las operaciones o los trabajos de producción.
-   **Operaciones**: valores predeterminados de pedido que se aplican a operaciones o trabajos de producción y realimentación sobre operaciones durante el proceso de producción.
-   **Notificar como terminado**: valores predeterminados de pedido que se aplican cuando se notifican los artículos como terminados en la última operación de un pedido de producción.
-   **Validación de cantidades**: valores predeterminados de pedido para validar las cantidades de realimentación y de inicio en pedidos de producción.

## <a name="types-of-production-jobs"></a>Tipos de trabajos de producción
En la ficha **Operaciones** puede seleccionar los tipos de trabajos de producción que requieran registro en la página **Registro del trabajo**. Normalmente, los trabajadores realizan registros en trabajos de configuración y de proceso. No obstante, si se aplica una programación de trabajos, puede seleccionar otros tipos de trabajos, como por ejemplo trabajos de transporte, en los que el trabajador debe además realizar registros al procesar un pedido de producción. **Importante**: asegúrese de seleccionar todos los tipos de trabajos pertinentes. Si no, es posible que los trabajos no aparezcan disponibles para su registro en la página **Registro del trabajo**. Alinee las seleccione con las selecciones de la columna **Gestión de trabajos** en la página **Grupos de rutas**. Si se selecciona **Gestión de trabajos** en un grupo de rutas, el tipo de trabajo se notificará como terminado en el pedido de producción. Esta notificación se produce cuando el trabajo se registra como terminado en la ejecución de fabricación. Cuando todos los tipos de trabajos para los que se ha seleccionado **Gestión de trabajos** se hayan notificado como terminados en una operación, la ejecución de fabricación también notificará la operación como terminada. **Nota**: algunos tipos de trabajo se pueden notificar manualmente a través de diarios de producción. En este caso, seleccione **Gestión de trabajos** para el tipo de trabajo, pero no seleccione el tipo de trabajo para su registro en la ficha **Operaciones** de la página **Valores predeterminados de pedido de producción**.

## <a name="bom-consumption-and-picking-list-journals"></a>Consumo de la lista de materiales y diarios de listas de selección
Se pueden configurar materiales para consumirlos automáticamente o manualmente durante la producción. El consumo automático se controla mediante el principio de vaciado que se especifica en las líneas de lista de materiales y por la configuración del campo **Consumo automático de L. MAT.** en los valores predeterminados del pedido de producción. Se puede configurar un consumo automático que tenga lugar cuando se inicie un pedido de producción o se notifique como terminado. También se puede producir en el nivel de trabajo, cuando se inicia un trabajo o se termina.

### <a name="controlling-material-consumption-when-a-production-order-is-started"></a>Control del consumo de materiales cuando se inicia un pedido de producción

El consumo de materiales durante el inicio de un pedido de producción se controla mediante el campo **Consumo automático de la L. MAT.** de la ficha **Inicio**. Los siguientes valores están disponibles:

-   **Principio de vaciado**: cuando se inicia un pedido de producción, las cantidades de materiales se consumirán según el principio de vaciado que se establece en las líneas de la lista de materiales de producción. Durante el inicio de la producción se consumirán solo las líneas de materiales donde se ha establecido el principio de vaciado en **Inicio**.
-   **Siempre**: las cantidades de materiales proporcionales a la cantidad iniciada se consumirán siempre.
-   **Nunca**: las cantidades de materiales nunca se consumirán.

### <a name="controlling-material-consumption-when-a-production-job-is-started-or-completed"></a>Control del consumo de materiales cuando se inicia o termina un trabajo de producción

El consumo de materiales durante el inicio o el término de un trabajo de producción se controla mediante el campo **Consumo automático de la L. MAT.** de la ficha **Operaciones**. Los siguientes valores están disponibles:

-   **Principio de vaciado**: cuando se inicia o termina una cantidad en un trabajo de producción, las cantidades de materiales se consumirán según el principio de vaciado que se establece en las líneas de la lista de materiales de producción. Solo se consumirán las líneas de materiales donde se ha establecido el principio de vaciado en **Inicio** o **Finalizar**.
-   **Siempre**: se consumirán siempre las cantidades de materiales proporcionales a la cantidad iniciada en el trabajo.
-   **Nunca**: las cantidades de materiales nunca se consumirán.

### <a name="controlling-material-consumption-when-a-production-order-is-reported-as-finished"></a>Control del consumo de materiales cuando un pedido de producción se notifique como finalizado

El consumo de materiales durante el proceso de notificación como terminado de un pedido de producción se controla mediante el campo **Consumo automático de la L. MAT.** de la ficha **Notificar como terminado**. Los siguientes valores están disponibles:

-   **Principio de vaciado**: cuando se notifica como terminado un pedido de producción, las cantidades de materiales se consumirán según el principio de vaciado que se establece en las líneas de la lista de materiales de producción. Solo se consumirán las líneas de materiales donde se ha establecido el principio de vaciado en **Finalizar**.
-   **Siempre**: se consumirán siempre las cantidades de materiales proporcionales a la cantidad notificada como terminada.
-   **Nunca**: las cantidades de materiales nunca se consumirán.





