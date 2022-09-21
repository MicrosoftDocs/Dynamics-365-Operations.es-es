---
title: Página de inicio del sensor de Data Intelligence
description: Este artículo proporciona información general del sensor de Data Intelligence. Las organizaciones pueden usar esta función para impulsar los procesos comerciales en Microsoft Dynamics 365 Supply Chain Management, basados en señales de Internet de las cosas (IoT) de máquinas y equipos en la planta de producción.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2e4cd8d4d4ffcd10d02fbf26615f12cdd6ccca9e
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428442"
---
# <a name="sensor-data-intelligence-home-page"></a>Página de inicio del sensor de Data Intelligence

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

El sensor de Data Intelligence para Microsoft Dynamics 365 Supply Chain Management permite a organizaciones dirigir procesos de negocio en Supply Chain Management, basados en señales de Internet de las cosas (IoT) de máquinas y equipo en la planta de producción. Es una versión actualizada y renombrada de la característica *Inteligencia IoT* que antes estaba disponible para Supply Chain Management.

Sensor Data Intelligence le permite realizar las tareas siguientes:

- Recopilar detalles de máquinas y equipos para actualizar los valores de contador de activos de mantenimiento en Supply Chain Management e impulsar el mantenimiento predictivo.
- Configure la solución mediante un asistente de incorporación simple en lugar de instalar y configurar manualmente los componentes en Microsoft Dynamics Lifecycle Services (LCS).
- Implemente componentes en su propia suscripción, de modo que tenga más flexibilidad para administrar los componentes de Azure.
- Configure, escale y amplíe la solución como lógica empresarial que se ejecuta en componentes de Azure. Esos componentes ahora se administran en su propia suscripción. Por lo tanto, puede personalizarlos según sea necesario para satisfacer sus necesidades comerciales únicas.

## <a name="business-scenarios"></a>Escenarios empresariales

Sensor Data Intelligence permite varios tipos de funcionalidad, cada uno de los cuales está representado por un *escenario* en el sistema. Cada escenario proporciona un conjunto especializado de opciones de configuración en el sistema, como se detalla en la siguiente tabla.

| Situación | Description |
|---|---|
| [Tiempo de inactividad de activo](sdi-scenario-asset-downtime.md) | Realice un seguimiento preciso de la eficiencia de los activos de la máquina mediante el uso de datos de sensores para rastrear el tiempo de inactividad de la máquina. |
| [Mantenimiento de activos](sdi-scenario-asset-maintenance.md) | Minimice los costos de mantenimiento y prolongue la vida útil de los activos mejorando los planes de mantenimiento basados en lecturas de sensores de puntos de control críticos para los activos de la máquina. |
| [Estado de la máquina](sdi-scenario-equipment-downtime.md) | Asegure la eficiencia de la operación mediante el uso de lecturas de sensores para notificar a los planificadores sobre interrupciones de la máquina y brindar opciones para mitigar posibles demoras. |
| [Calidad de producto](sdi-scenario-product-quality.md) | Garantice la calidad de los lotes de productos comparando las lecturas de los sensores con las propiedades reales de cada lote de productos, como la humedad, la temperatura o las métricas de calidad definidas a medida. El sistema notificará a los usuarios cuando ocurran desviaciones. |
| [Retrasos de producción](sdi-scenario-production-delays.md) | Utilice las lecturas de los sensores para comparar el tiempo de ciclo real con el tiempo de ciclo planificado y notifique a los supervisores cuando la producción no esté a tiempo. Los supervisores pueden entonces intervenir según sea necesario para garantizar la máxima eficiencia operativa. |

## <a name="architecture"></a>Arquitectura

El siguiente diagrama arquitectónico proporciona una descripción general de la solución y sus componentes.

![Diagrama arquitectónico de Sensor Data Intelligence.](media/sdi-architecture.png "Diagrama arquitectónico de Sensor Data Intelligence")
