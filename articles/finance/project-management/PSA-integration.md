---
title: Visión general de Project Service Automation
description: Este tema proporciona información acerca de la solución de integración de Dynamics 365 Project Service Automation a Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250562"
---
# <a name="project-service-automation-overview"></a>Visión general de Project Service Automation

[!include[banner](../includes/banner.md)]

La solución de integración de Project Service Automation en Finance usa la característica de integración de datos para sincronizar datos a través de instancias de Dynamics 365 Finance y Dynamics 365 Project Service Automation mediante Common Data Service. Las plantillas de integración que están disponibles con la característica de integración de datos habilitan el flujo de proyectos, los contratos de proyectos, las líneas de contratos de proyectos, los hitos de la línea del contrato, las tareas de proyecto, las categorías de transacciones de gastos, las estimaciones de horas y las estimaciones de gastos desde Project Service Automation hasta Finance.

> [!NOTE]
> - Si utiliza la versión 7.3.0, debe instalar KB 4074835. A continuación, podrá integrar proyectos de precio fijo.
> - Si está usando la versión 7.3.0 y trae transacciones de cuotas de Project Service Automation, debe instalar KB 4345320 para incluir esas cuotas en la factura del proyecto.
> - Si usa la versión 8.0 podrá usar la integración de tareas de proyectos, las categorías de transacción de gastos, las estimaciones de hora, las estimaciones de gastos y el bloqueo de función.
> - Si utiliza la versión 8.0.1, o posterior, podrá sincronizar reales.

Para poder integrar Project Service Automation Finance, debe configurar los parámetros de integración de Project Service Automation. Para obtener más información consulte los [parámetros de integración de Project Service Automation](PSA-parameters.md).

Esta solución de integración le permite una sincronización directa en los siguientes casos:

- Mantener los contratos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.
- Crear proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.
- Mantener las líneas de contrato de proyecto en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance.
- Mantener los hitos de líneas de contrato de proyecto en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.
- Mantener las tareas de proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance.
- Mantener categorías de transacciones de gastos en Finance y sincronizarlas directamente desde Finance hasta Project Service Automation.
- Crear estimaciones de horas proyectos en Project Service Automation y sincronizarlas directamente desde Project Service Automation hasta Finance.
- Crear estimaciones de gastos de proyectos en Project Service Automation y sincronizarlos directamente desde Project Service Automation hasta Finance.
- Cree datos reales de tiempo, gastos y cuotas del proyecto en Project Service Automation y cree transacciones del proyecto en el diario de integración de Project Service Automation para que se puedan registrar en Finance.

## <a name="data-synchronization"></a>Sincronización de datos

La ilustración siguiente muestra cómo se sincronizan los datos como parte de la integración entre Project Service Automation y Finance.

> [!NOTE]
> No todas las plantillas están actualmente disponibles. Las plantillas se publicarán a medida que estén completadas.

[![Integración de Project Service Automation con Finance](./media/PSA-integration.png)](./media/PSA-integration.png)

## <a name="system-requirements-for-finance"></a>Requisitos del sistema para Finance

Para usar la solución de integración de Project Service Automation en Finance, debe instalar , Enterprise Edition 7.3 con la Platform update 12 o posterior.

## <a name="system-requirements-for-project-service-automation"></a>Requisitos del sistema para Project Service Automation

Para usar la solución de integración de Project Service Automation en Finance, debe instalar los siguientes componentes:

- Dynamics 365 Project Service Automation versión 9.0.0.0 o posterior
- Solución Prospect to cash para Dynamics 365 Sales, versión 1.14.0.0 (v14) o posterior
- Solución de integración de Project Service Automation con Finance para Dynamics 365 Project Service Automation versión 1.0.0.0. o posterior

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a>Instalar la solución de integración de Project Service Automation en Finance en su instancia de Project Service Automation.

Descargue la solución de integración de Project Service Automation en Finance desde [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) y siga las instrucciones que se incluyen con la solución.
