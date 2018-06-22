---
title: Project Service Automation
description: "Esta solución usa la función de integración de datos para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation a través de Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: es-es
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a>Project Service Automation

La solución de integración de Project Service Automation en Finance and Operations usa la función de integración de datos para sincronizar los datos a través de instancias de Microsoft Dynamics 365 for Finance and Operations y Microsoft Dynamics 365 for Project Service Automation a través de Common Data Service (CDS). Las plantillas de integración que están disponibles con la característica de integración de datos habilitan el flujo de proyectos, los contratos de proyectos, las líneas de contratos de proyectos, los hitos de la línea del contrato, las tareas de proyecto, las categorías de transacciones de gastos, las estimaciones de horas y las estimaciones de gastos desde Project Service Automation hasta Finance and Operations.

> [!NOTE] 
> Si utiliza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0 debe instalar KB 4074835. Esto le permitirá integrar proyectos de precio fijo.
>
> Si usa Dynamics 365 for Finance and Operations versión 8.0 podrá usar la integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de función.
>
> Si utiliza Dynamics 365 for Finance and Operations versión 8.0.1 podrá sincronizar valores reales.
>
> Si utiliza Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, después de instalar KB 4132657 y 4132660 KB, podrá usar plantillas para integrar tareas de proyecto, categorías de transacción de gastos, estimaciones de hora, estimaciones de gastos y valores reales, y para configurar el bloqueo de funcionalidad. Si debe restablecer las distribuciones contables, se recomienda instalar también KB 4131710.

Para poder integrar Project Service Automation con Finance and Operations, debe configurar los parámetros de integración de Project Service Automation. Para obtener más información consulte los parámetros de integración de Project Service Automation.

Esta solución de integración le permite una sincronización directa en los siguientes casos:

- Mantener los contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.
- Crear proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.
- Mantener líneas de contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.
- Mantener hitos de líneas de contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.
- Mantener tareas de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance and Operations.
- Mantener categorías de transacciones de gastos en Finance and Operations y sincronizarlas directamente desde Finance and Operations hasta Project Service Automation.
- Crear estimaciones de horas proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance and Operations.
- Crear estimaciones de gastos proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance and Operations.

## <a name="data-synchronization"></a>Sincronización de datos
La ilustración siguiente muestra cómo se sincronizan los datos como parte de la integración entre Project Service Automation y Finance and Operations.

> [!NOTE]
> No todas las plantillas están actualmente disponibles. Las plantillas se publicarán a medida que estén completadas.

[![Integración de Project Service Automation con Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance-and-operations"></a>Requisitos del sistema para Finance and Operations

Para usar la solución de integración de Project Service Automation en Finance and Operations, debe instalar Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 con la actualización de plataforma 12 o posterior.

## <a name="system-requirements-for-project-service-automation"></a>Requisitos del sistema para Project Service Automation

Para usar la solución de integración de Project Service Automation en Finance and Operations, debe instalar los siguientes componentes:

- Microsoft Dynamics 365 for Project Service Automation versión 9.0.0.0 o posterior.
- Solución Prospect to cash para Dynamics 365 for Sales, versión 1.14.0.0 (v14) o posterior.
- Project Service Automation en la solución Operations for Dynamics 365 for Project Service Automation versión 1.0.0.0 o posterior.

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a>Instalar la solución de integración de Project Service Automation en Finance and Operations en su instancia de Project Service Automation.



