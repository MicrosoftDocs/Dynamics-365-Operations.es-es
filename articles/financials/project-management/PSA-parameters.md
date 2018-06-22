---
title: "Parámetros de integración de Project Service Automation"
description: Puede configurar el valor predeterminado de los datos cuando integran Project Service Automation con Dynamics 365 for Finance and Operations.
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Parámetros de integración de Project Service Automation

En la página **Parámetros de integración de Project Service Automation** puede configurar cómo los datos toman el valor predeterminado al integrar Project Service Automation con Finance and Operations. A continuación mostramos qué debe configurarse para que los proyectos se sincronicen con éxito de Project Service Automation en Finance and Operations.

> [!NOTE]
> La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Dynamics 365 for Finance and Operations versión 8.0.




| **Ficha**                      | **Campo**                          | **Descripción**                    |
|------------------------------|------------------------------------|--------------------------------|
| **General**                  | **Tipo de proyecto predeterminado**               | Seleccione el valor predeterminado de **Tipo de proyecto**, que es cuando los proyectos se sincronizan desde Project Service Automation si no ha proporcionado un valor predeterminado en la plantilla de integración. Durante la sincronización, los proyectos nuevos tendrán **Tipo de proyecto** establecido a este valor y se pueden actualizar cuando las líneas del contrato de proyecto se sincronizan desde Project Service Automation.               |
| **General**                  | **Categoría de tiempo**                      | Seleccione el valor predeterminado de **Categoría de tiempo**, que es cuando las estimaciones de hora se sincronizan desde Project Service Automation. Durante la sincronización, las nuevas previsiones de horas en Finance and Operations tendrán **Categoría** establecido en este valor cuando las estimaciones de horas y los valores reales de hora se sincronizan desde Project Service Automation.   |
| **General**                  | **Categoría de cuota**                       | Seleccione el valor predeterminado de **Categoría de cuota**, que es cuando los valores reales de cuota se sincronizan desde Project Service Automation. Durante la sincronización, las nuevas transacciones de cuotas en Finance and Operations tendrán **Categoría** establecido en este valor cuando los valores reales de las cuotas se sincronicen desde Project Service Automation.          |
| **Valores predeterminados del grupo de proyectos**   | **Tipo de proyecto** | Haga clic en **Nuevo** para agregar una fila donde puede seleccionar el tipo de proyecto para el que establecer el grupo de proyecto predeterminado. Un tipo de proyecto específico puede seleccionarse solo una vez en la configuración.              
|                              | **Grupo de proyectos**          | Seleccione el grupo de proyectos predeterminado del tipo de proyecto especificado. Cuando sincronice proyectos nuevos desde Project Service Automation, el **Grupo de proyectos** será el valor predeterminado basado en el tipo de proyecto si no ha proporcionado un valor predeterminado en la plantilla de integración.  |
| **Valores predeterminados de tipo de facturación**    | **Tipo de facturación** | Haga clic en **Nuevo** para agregar una fila donde puede seleccionar el tipo de facturación para el que establecer la propiedad de línea predeterminada. Un tipo de facturación específico puede seleccionarse solo una vez en la configuración.          |
|                              | **Propiedad de la línea**| Seleccione la propiedad de línea predeterminada del tipo de facturación especificado. Cuando las nuevas estimaciones de hora, las nuevas estimaciones del gasto, o los nuevos valores reales se sincronicen desde Project Service Automation, la **Propiedad de línea** será el valor predeterminado basado en el tipo de facturación.          |
| **Bloqueo de funcionalidad**    |                   | Seleccione la funcionalidad que debe deshabilitarse en Finance and Operations para los proyectos y contratos que se originaron desde Project Service Automation. Por ejemplo, puede optar por desactivar la capacidad de editar contratos y proyectos, crear estructuras de descomposición del trabajo y especificar hojas de horas en Finance and Operations. Los campos relacionados con la contabilidad continuarán estando habilitados, incluso si la configuración de parámetros no los deja disponibles. De forma predeterminada, todas las funcionalidades se habilitarán.           |

