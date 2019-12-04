---
title: Introducción a la optimización de la planificación
description: Este tema explica cómo empezar a usar la función de optimización de la planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774043"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a>Introducción a la optimización de la planificación

La funcionalidad de optimización de la planificación no admite actualmente todas las características disponibles en el motor de planificación que se incorpora en Microsoft Dynamics 365 Supply Chain Management. Por lo tanto, es importante que evalúe si la función que están disponible actualmente en la optimización de la planificación cumplirá sus requisitos. De forma predeterminada, la funcionalidad de optimización de la planificación no está activada Dynamics Lifecycle Services (LCS) de forma predeterminada. Por lo tanto, tiene una oportunidad de realizar la evaluación antes de que se active.

Finalmente, la optimización de la planificación reemplazará al motor de planificación de Supply Chain Management integrado.

Antes de activar o desactivar la planificación de optimización, se recomienda encarecidamente que evalúe los resultados del análisis de aptitud de optimización de la planificación. Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).

### <a name="licensing"></a>Licencias

Si puede ejecutar con la planificación maestra con su licencia actual, no es necesario comprar una licencia adicional de empezar a usar la optimización de la planificación.

### <a name="install-the-add-in"></a>Instalar el complemento

Para usar la optimización de la planificación, instale el complemento de optimización de la planificación para Dynamics 365 Supply Chain Management. Puede obtener acceso al complemento desde su proyecto de LCS y activar la funcionalidad de optimización de la planificación desde la interfaz de usuario (IU) de Supply Chain Management.

1. Inicie sesión en LCS y abra el entorno deseado.
1. Vaya a **Detalles completos**.
1. Seleccione **Mantener** o descienda hasta la ficha desplegable **Complementos del entorno**.
1. Seleccione **Instalar un nuevo complemento**.
1. Seleccione **optimización de la planificación**.
1. Siga la guía de instalación y acepte los términos y condiciones.
1. Seleccione **Instalar**.

### <a name="planning-optimization-integration"></a>Integración de la optimización de la planificación

Para configurar si el complemento de optimización de la planificación se debe usar para la planificación maestra, vaya **Planificación maestra** \> **Configuración** \> **Integración de la optimización de la planificación** \> **Parámetros de integración**.

#### <a name="connection-status"></a>Estado de conexión

El estado de la conexión indica el estado actual de la conexión entre Supply Chain Management y el servicio de optimización de la planificación. La tabla siguiente muestra los posibles valores.

| Estado de conexión | Descripción | ¿Se puede usar optimización de la planificación? |
|---|---|---|
| Conectada | Una conexión se ha establecido entre el servicio de optimización de la planificación y Supply Chain Management. | Sí |
| Habilitando conexión | Una petición para activar la conexión al servicio de optimización de la planificación está actualmente en curso. | No |
| Desconectado | No hay conexión al servicio de optimización de la planificación. La conexión se puede cambiar desde LCS, según lo descrito antes en este tema. | No |
| Deshabilitando conexión | Una petición para desactivar la conexión al servicio de optimización de la planificación está actualmente en curso. | No |
| Obteniendo estado | El sistema está esperando por la información del estado del servicio de optimización de la planificación. | No |

#### <a name="the-use-planning-optimization-option"></a>La opción de optimización de la planificación de uso

Si se establece la opción **optimización de la planificación de uso** se determina el motor de planificación que se usa para la planificación maestra:

- **Sí**: la optimización de la planificación se utiliza para la planificación maestra.
- **No**: el motor de planificación de Supply Chain Management integrado se utiliza para la planificación maestra.

> [!NOTE]
> Si se activan los trabajos por lotes existentes de planificación creados para el motor de planificación de Supply Chain Management integrado se activan mientras que la opción **optimización de la planificación de uso** está establecida en **Sí**, estos trabajos fallarán.

### <a name="integration-with-the-setup"></a>Integración con la configuración

Si la vista previa de optimización de la planificación está activada, la planificación maestra se realiza mediante el complemento de optimización de la planificación. En este caso, se ven afectados los resultados y las características de la planificación maestra.

## <a name="related-resources"></a>Recursos relacionados

[Términos y condiciones de la vista previa](https://go.microsoft.com/fwlink/?linkid=2015274)

[Visión general de la optimización de la planificación](planning-optimization-overview.md)

[Análisis de aptitud de la optimización de la planificación](planning-optimization-fit-analysis.md)

[Ver el historial del plan y los registros de planificación](plan-history-logs.md)

[Aplicar filtros a un plan](plan-filters.md)

[Cancelar un trabajo de planificación](cancel-planning-job.md)
