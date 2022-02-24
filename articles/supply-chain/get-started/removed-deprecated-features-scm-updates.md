---
title: Características quitadas u obsoletas de Dynamics 365 Supply Chain Management
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d4d2805e36f132660152370cbeee856862ad6faa
ms.sourcegitcommit: 069ed5789517b550065e5e2317658fec4027359e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2020
ms.locfileid: "4689544"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Características quitadas u obsoletas de Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Este tema se actualizará a medida que se documenten nuevas características quitadas o en desuso para Dynamics 365 Supply Chain Management.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Funciones quitadas o en desuso en la versión 10.0.15 de Supply Chain Management

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La compatibilidad de Internet Explorer 11 con Dynamics 365 está en desuso

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de diciembre de 2020, queda en desuso la compatibilidad de Microsoft Internet Explorer 11 con todos los productos de Dynamics 365 e Internet Explorer 11 no se admitirá después de agosto de 2021.<br><br>Esto afectará a los clientes que usan productos Dynamics 365 que están diseñados para usarse a través de una interfaz de Internet Explorer 11. Después de agosto de 2021, Internet Explorer 11 no será compatible con dichos productos de Dynamics 365. |
| **¿Reemplazado por otra característica?**   | Recomendamos que los clientes hagan la transición a Microsoft Edge.|
| **Áreas de producto afectadas**         | Todos los productos Dynamics 365 |
| **Opción de implementación**              | Todos|
| **Estado**                         | En desuso. Internet Explorer 11 no se admitirá después de agosto de 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Usar el motor de planificación maestro de Supply Chain Management para escenarios de fabricación

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para mejorar el rendimiento y minimizar la carga de la base de datos SQL durante las ejecuciones de planificación maestra, la optimización de planificación reemplaza el motor integrado de planificación maestra de Supply Chain Management. La optimización de planificación permite realizar ejecuciones de planificación rápida que se pueden realizar incluso durante el horario de oficina. Esto permite a los planificadores reaccionar de inmediato a los cambios en la demanda o los parámetros de planificación. |
| **¿Reemplazado por otra característica?**   | Sí, la optimización de la planificación reemplazará al motor de planificación maestro de Supply Chain Management integrado. |
| **Áreas de producto afectadas**         | Supply Chain Management: planificación maestra |
| **Opción de implementación**              | Solo en la nube. Optimización de planificación no se admite en implementaciones locales. |
| **Estado**                         | En desuso. El 1 de octubre de 2021, los escenarios de fabricación ya no serán compatibles con el motor de planificación maestra de Dynamics 365 Supply Chain Management integrado. Para escenarios de fabricación, los clientes deben usar Optimización de planificación para los cálculos de planificación maestra. Para obtener más información, consulte la [documentación de Optimización de planificación](https://go.microsoft.com/fwlink/?linkid=2105830). Los clientes con implementaciones locales de Dynamics 365 Supply Chain Management pueden continuar usando el motor de planificación maestra de Supply Chain Management para escenarios de fabricación después de octubre de 2021. Sin embargo, no se proporcionarán más mejoras de funciones. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Funciones quitadas o en desuso en la versión 10.0.11 de Supply Chain Management

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Usar el motor de planificación maestro de Supply Chain Management para escenarios de distribución

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para mejorar el rendimiento y minimizar la carga de la base de datos SQL durante las ejecuciones de planificación maestra, la optimización de planificación reemplaza el motor integrado de planificación maestra de Supply Chain Management. La optimización de planificación permite realizar ejecuciones de planificación rápida que se pueden realizar incluso durante el horario de oficina. Esto permite a los planificadores reaccionar de inmediato a los cambios en la demanda o los parámetros de planificación. |
| **¿Reemplazado por otra característica?**   | Sí, la optimización de la planificación reemplazará al motor de planificación maestro de Supply Chain Management integrado. |
| **Áreas de producto afectadas**         | Supply Chain Management: planificación maestra |
| **Opción de implementación**              | Solo en la nube. Optimización de planificación no se admite en implementaciones locales. |
| **Estado**                         | En desuso. El 1 de abril de 2021, los escenarios de distribución ya no serán compatibles con lel motor de planificación maestra de Dynamics 365 Supply Chain Management integrado. Para escenarios de distribución, los clientes deben usar Optimización de planificación para los cálculos de planificación maestra. Para obtener más información, consulte la [documentación de Optimización de planificación](https://go.microsoft.com/fwlink/?linkid=2105830). Los clientes con implementaciones locales de Dynamics 365 Supply Chain Management pueden continuar usando el motor de planificación maestra de Supply Chain Management para escenarios de distribución después de abril de 2021. Sin embargo, no se proporcionarán más mejoras de funciones. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas

Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).
