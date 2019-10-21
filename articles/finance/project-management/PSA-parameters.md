---
title: Parámetros de integración de Project Service Automation
description: Este tema explica cómo configurar cómo se especifican los datos predeterminados cuando se integra Microsoft Dynamics 365 for Project Service Automation con Microsoft Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: f7cef5384812e0dcb7d5e084ddd7668a7687a259
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175023"
---
# <a name="project-service-automation-integration-parameters"></a>Parámetros de integración de Project Service Automation

[!include[banner](../includes/banner.md)]

En la página **Parámetros de la integración de Project Service Automation** , puede configurar cómo se especifican los datos predeterminados cuando se integra Dynamics 365 Project Service Automation con Dynamics 365 Finance. Para que los proyectos se sincronicen con éxito de Project Service Automation en Finance, debe configurar los siguientes campos.

> [!NOTE]
> - La integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de funciones están disponibles la versión 8.0.
> - La integración de los reales está disponible en la versión 8.0.1 o posterior.


| Tabulador                    | Campo                | Descripción |
|------------------------|----------------------|-------------|
| General                | Tipo de proyecto predeterminado | Permite seleccionar el tipo de proyecto predeterminado. Cuando los proyectos se sincronizan desde Project Service Automation, este valor se utiliza si no proporcionó un valor predeterminado en la plantilla de integración. Durante la sincronización, el campo **Tipo de proyecto** de los proyectos nuevos se establece en este valor. Sin embargo, el valor puede actualizarse cuando las líneas de contrato de proyecto se sincronizan desde Project Service Automation. |
|                        | Categoría de tiempo        | Seleccione la categoría de tiempo predeterminada. Este valor se utiliza cuando las estimaciones de horas se sincronizan desde Project Service Automation. Cuando las estimaciones de horas y los valores reales de horas se sincronizan desde Project Service Automation, el campo **Categoría** de las nuevas previsiones de horas de proyecto en Finance se establece en este valor. |
|                        | Categoría de cuota         | Seleccione la categoría de cuotas predeterminada. Este valor se utiliza cuando los valores reales de cuotas se sincronizan desde Project Service Automation. Cuando los valores reales de cuotas se sincronizan desde Project Service Automation, el campo **Categoría** de las nuevas transacciones de cuotas en Finance se establece en este valor. |
| Valores predeterminados del grupo de proyectos | Tipo de proyecto         | Haga clic en **Nuevo** para agregar una fila donde puede seleccionar el tipo de proyecto para el que establecer el grupo de proyecto predeterminado. Un tipo de proyecto específico puede seleccionarse solo una vez en la configuración. |
|                        | Grupo de proyectos        | Seleccione el grupo de proyectos predeterminado del tipo de proyecto seleccionado. Cuando se sincronicen proyectos nuevos desde Project Service Automation, el campo **Grupo de proyectos** se establece en el valor predeterminado del tipo de proyecto si no ha proporcionado un valor predeterminado en la plantilla de integración. |
| Valores predeterminados de tipo de facturación  | Tipo de facturación         | Haga clic en **Nuevo** para agregar una fila donde puede seleccionar el tipo de facturación para el que establecer la propiedad de línea predeterminada. Un tipo de facturación específico puede seleccionarse solo una vez en la configuración. |
|                        | Propiedad de la línea        | Seleccione la propiedad de línea predeterminada del tipo de facturación seleccionado. Cuando las nuevas estimaciones de hora, las nuevas estimaciones del gasto, o los nuevos valores reales se sincronicen desde Project Service Automation, el campo **Propiedad de línea** se establece en el valor predeterminado para el tipo de facturación. |
| Bloqueo de funcionalidad  | No aplicable       | Seleccione la funcionalidad que debe deshabilitarse en Finance para los proyectos y contratos que se originaron desde Project Service Automation. Por ejemplo, puede desactivar la capacidad de editar contratos y proyectos, crear estructuras de descomposición del trabajo y especificar hojas de horas en Finance. Los campos relacionados con la contabilidad continuarán estando habilitados, incluso si la configuración de parámetros no los deja disponibles. De forma predeterminada, todas las funcionalidades están habilitadas. |
