---
title: "Parámetros de integración de Project Service Automation"
description: "Este tema explica cómo configurar cómo se especifican los datos predeterminados al integrar Microsoft Dynamics 365 for Project Service Automation con Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 33960a97f69d6bcc70a3035d4d68095ca6993a10
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="project-service-automation-integration-parameters"></a>Parámetros de integración de Project Service Automation

[!include[banner](../includes/banner.md)]

En la página **Parámetros de integración de Project Service Automation** puede configurar cómo se especifican los datos predeterminados al integrar Microsoft Dynamics 365 for Project Service Automation con Microsoft Dynamics 365 for Finance and Operations. Para que los proyectos se sincronicen con éxito de Project Service Automation en Finance and Operations, debe configurar los siguientes campos.

> [!NOTE]
> - La integración de tareas de proyectos, las categorías de la transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de la función están disponibles en Microsoft Dynamics 365 for Finance and Operations versión 8.0.
> - La integración de los valores reales está disponible en Microsoft Dynamics 365 for Finance and Operations versión 8.01 o posterior.
> - Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.

| Ficha                    | Campo                | Descripción |
|------------------------|----------------------|-------------|
| General                | Tipo de proyecto predeterminado | Permite seleccionar el tipo de proyecto predeterminado. Cuando los proyectos se sincronizan desde Project Service Automation, este valor se utiliza si no proporcionó un valor predeterminado en la plantilla de integración. Durante la sincronización, el campo **Tipo de proyecto** de los proyectos nuevos se establece en este valor. Sin embargo, el valor puede actualizarse cuando las líneas de contrato de proyecto se sincronizan desde Project Service Automation. |
|                        | Categoría de tiempo        | Seleccione la categoría de tiempo predeterminada. Este valor se utiliza cuando las estimaciones de horas se sincronizan desde Project Service Automation. Cuando las estimaciones de horas y los valores reales de horas se sincronizan desde Project Service Automation, el campo **Categoría** de las nuevas previsiones de horas de proyecto en Finance and Operations se establece en este valor. |
|                        | Categoría de cuota         | Seleccione la categoría de cuotas predeterminada. Este valor se utiliza cuando los valores reales de cuotas se sincronizan desde Project Service Automation. Cuando los valores reales de cuotas se sincronizan desde Project Service Automation, el campo **Categoría** de las nuevas transacciones de cuotas en Finance and Operations se establece en este valor. |
| Valores predeterminados del grupo de proyectos | Tipo de proyecto         | Haga clic en **Nuevo** para agregar una fila donde puede seleccionar el tipo de proyecto para el que establecer el grupo de proyecto predeterminado. Un tipo de proyecto específico puede seleccionarse solo una vez en la configuración. |
|                        | Grupo de proyectos        | Seleccione el grupo de proyectos predeterminado del tipo de proyecto seleccionado. Cuando se sincronicen proyectos nuevos desde Project Service Automation, el campo **Grupo de proyectos** se establece en el valor predeterminado del tipo de proyecto si no ha proporcionado un valor predeterminado en la plantilla de integración. |
| Valores predeterminados de tipo de facturación  | Tipo de facturación         | Haga clic en **Nuevo** para agregar una fila donde puede seleccionar el tipo de facturación para el que establecer la propiedad de línea predeterminada. Un tipo de facturación específico puede seleccionarse solo una vez en la configuración. |
|                        | Propiedad de la línea        | Seleccione la propiedad de línea predeterminada del tipo de facturación seleccionado. Cuando las nuevas estimaciones de hora, las nuevas estimaciones del gasto, o los nuevos valores reales se sincronicen desde Project Service Automation, el campo **Propiedad de línea** se establece en el valor predeterminado para el tipo de facturación. |
| Bloqueo de funcionalidad  | No aplicable       | Seleccione la funcionalidad que debe deshabilitarse en Finance and Operations para los proyectos y contratos que se originaron desde Project Service Automation. Por ejemplo, puede desactivar la capacidad de editar contratos y proyectos, crear estructuras de descomposición del trabajo y especificar hojas de horas en Finance and Operations. Los campos relacionados con la contabilidad continuarán estando habilitados, incluso si la configuración de parámetros no los deja disponibles. De forma predeterminada, todas las funcionalidades están habilitadas. |

