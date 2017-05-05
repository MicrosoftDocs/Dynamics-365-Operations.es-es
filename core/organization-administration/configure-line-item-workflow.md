---
title: "Configuración de un flujo de trabajo de elementos"
description: "Este tema explica cómo configurar un elemento de flujo de trabajo de elementos."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c2b2c863d0783bd436db57d9fd3c7c5aa8dba5c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-line-item-workflow"></a>Configuración de un flujo de trabajo de elementos

[!include[banner](../includes/banner.md)]


Este tema explica cómo configurar un elemento de flujo de trabajo de elementos.

Para configurar un elemento de flujo de trabajo de elementos, en el editor de flujo de trabajo, haga clic con el botón derecho en el elemento y, a continuación, haga clic en **Propiedades** para abrir la página de **Propiedades**. A continuación use los siguientes procedimientos para configurar las propiedades del elemento de flujo de trabajo de elementos.

## <a name="name-the-lineitem-workflow-element"></a>Asignación de un nombre al elemento de flujo de trabajo de artículo de línea
Siga estos pasos para asignar un nombre al elemento de flujo de trabajo de elementos.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Nombre**, escriba un nombre único para el elemento de flujo de trabajo de elementos.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Especificación de si todos los elementos de línea se procesan con el mismo flujo de trabajo
Siga estos pasos para especificar si el mismo flujo de trabajo se usa para procesar todos los elementos de línea de un documento.

1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  Si el mismo flujo de trabajo procesa todos los artículos de línea de un documento, haga clic en **Invocar un solo flujo de trabajo para todos los artículos de línea**. A continuación, seleccione el flujo de trabajo que se va a usar para procesar los elementos de línea.
3.  Si un flujo de trabajo específico procesa los elementos de línea que cumplen un conjunto de condiciones concreto, haga clic en **Invocar un flujo de trabajo para cada artículo de línea**. A continuación, siga estos pasos para definir el conjunto de condiciones:
    1.  Haga clic en **Agregar**.
    2.  En la tabla, seleccione la condición.
    3.  En la pestaña **Nombre de condición**, escriba un nombre para el conjunto de condiciones que está definiendo.
    4.  Haga clic en **Agregar condición** para escribir una condición.
    5.  Escriba condiciones adicionales que sean necesarias.
    6.  Para comprobar que el conjunto de condiciones definido se ha configurado correctamente, haga clic en **Probar**. En la página **Probar condición de flujo de trabajo**, en el área **Validar condición**, seleccione un registro y haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas. Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.

    En la pestaña **Flujo de trabajo**, seleccione el flujo de trabajo para procesar los elementos de línea que cumplan con el conjunto de condiciones definido.





