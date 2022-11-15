---
title: Características quitadas o en desuso en Dynamics 365 Supply Chain Management
description: En este artículo se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 722b34e89a54715db39259549c11a78d69d2b4d3
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739880"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Características quitadas o en desuso en Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Este artículo se actualizará a medida que se documenten nuevas características quitadas o en desuso para Dynamics 365 Supply Chain Management.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación.

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones de finanzas y operaciones se puede encontrar en los [Informes de referencia técnica](/dynamics/s-e/). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones de finanzas y operaciones.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10029-release"></a>Funciones quitadas o en desuso en la versión 10.0.29 de Supply Chain Management

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>Pedidos de transferencia de existencias que tienen impuesto sobre el precio de transferencia

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo de la depreciación/eliminación** | La funcionalidad de [Órdenes de transferencia de acciones que tienen impuesto sobre el precio de transferencia](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md) está siendo reemplazada por lafuncionalidad [Órdenes de traslado de stock para India](../../finance/localizations/apac-ind-stock-transfer.md). |
| **¿Reemplazado por otra característica?**   | Sí, la funcionalidad de [Órdenes de transferencia de acciones que tienen impuesto sobre el precio de transferencia](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md) está siendo reemplazada por lafuncionalidad [Órdenes de traslado de stock para India](../../finance/localizations/apac-ind-stock-transfer.md). |
| **Áreas de producto afectadas** | Supply Chain Management - inventario |
| **Opción de implementación** | Nube y local |
| **Status** | <p>En desuso. La funcionalidad *Órdenes de transferencia de acciones que tienen impuesto sobre el precio de transferencia* no recibirá soporte con correcciones de errores y correcciones de seguridad.</p><p>Después de abril de 2023, se les pedirá a los clientes que utilicen la funcionalidad mejorada, *Órdenes de traslado de stock para India*, por defecto. Después de octubre de 2023, la funcionalidad *Órdenes de transferencia de acciones que tienen impuesto sobre el precio de transferencia* ya no estará disponible y se les pedirá a los clientes que pasen a la funcionalidad mejorada *Órdenes de traslado de stock para India*.</p><p>Para más información, vea [Órdenes de traslado de stock para India](../../finance/localizations/apac-ind-stock-transfer.md).</p> |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Funciones quitadas o en desuso en la versión 10.0.19 de Supply Chain Management

### <a name="job-card-device"></a>Dispositivo de tarjetas de trabajo

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo de la depreciación/eliminación** | El [dispositivo de tarjeta de trabajo](../production-control/config-job-card-device.md) está siendo reemplazado por la nueva [interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md). |
| **¿Reemplazado por otra característica?**   | Sí, el [dispositivo de tarjeta de trabajo](../production-control/config-job-card-device.md) está siendo reemplazado por la nueva [interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md). |
| **Áreas de producto afectadas** | Supply Chain Management: control de producción |
| **Opción de implementación** | Nube y local |
| **Estado** | En desuso. El dispositivo de tarjeta de trabajo recibirá soporte con correcciones de errores y seguridad, pero ya no se proporcionarán mejoras de funciones. Después de abril de 2022, el dispositivo de tarjeta de trabajo ya no recibirá soporte y se les pedirá a los clientes que se pasen a la nueva interfaz de ejecución de planta de producción. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Funciones quitadas o en desuso en la versión 10.0.18 de Supply Chain Management

### <a name="supply-chain-management--warehousing-the-warehouse-app"></a><a name="wma"></a>Supply Chain Management- Almacenes (la aplicación de almacenes)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de abril de 2021, *Supply Chain Management - Almacenamiento* (la aplicación de almacén) está obsoleta y no se admitirá después de abril de 2022. Ahora es reemplazado por la *Aplicación móvil Warehouse Management*, que se lanzó con la versión 10.0.17 de Supply Chain Management. La nueva aplicación es un reemplazo completo, pero utiliza el mismo marco subyacente, lo que facilita la migración. Si es necesario, las dos aplicaciones se pueden usar una al lado de la otra para ayudar a los usuarios a adaptarse gradualmente a medida que aprenden a usar la nueva aplicación.<br><br>Para más información sobre la nueva aplicación móvil Warehouse Management, consulte [Aplicación móvil Warehouse Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) e [Instalar y conectar la aplicación móvil Warehouse Management](../warehousing/install-configure-warehouse-management-app.md). |
| **¿Reemplazado por otra característica?**   | Sí, reemplazada por la nueva aplicación móvil Warehouse Management. |
| **Áreas de producto afectadas**         | Supply Chain Management: aplicación de almacén |
| **Opción de implementación**              | Nube y local |
| **Estado**                         | En desuso. La aplicación del almacén recibirá soporte con correcciones de errores y seguridad, pero ya no se proporcionarán mejoras de funciones. Después de abril de 2022, la antigua aplicación de almacén ya no será compatible y se les pedirá a los clientes que se pasen a la nueva aplicación móvil de Warehouse Management. La aplicación de almacén anterior se eliminará de Microsoft Store y Google Play Store.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Funciones quitadas o en desuso en la versión 10.0.15 de Supply Chain Management

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La compatibilidad de Internet Explorer 11 con Dynamics 365 está en desuso

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de diciembre de 2020, queda en desuso la compatibilidad de Microsoft Internet Explorer 11 con todos los productos de Dynamics 365 e Internet Explorer 11 no se admitirá después de agosto de 2021.<br><br>Esto afectará a los clientes que usan productos Dynamics 365 que están diseñados para usarse a través de una interfaz de Internet Explorer 11. Después de agosto de 2021, Internet Explorer 11 no será compatible con dichos productos de Dynamics 365. |
| **¿Reemplazado por otra característica?**   | Recomendamos que los clientes hagan la transición a Microsoft Edge.|
| **Áreas de producto afectadas**         | Todos los productos Dynamics 365 |
| **Opción de implementación**              | Todos|
| **Estado**                         | En desuso. Internet Explorer 11 no se admitirá después de agosto de 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Usar el motor de planificación maestro de Supply Chain Management para escenarios de fabricación

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para mejorar el rendimiento y minimizar la carga de la base de datos SQL durante las ejecuciones de planificación maestra, la optimización de planificación reemplaza el motor integrado de planificación maestra de Supply Chain Management. La optimización de planificación permite realizar ejecuciones de planificación rápida que se pueden realizar incluso durante el horario de oficina. Esto permite a los planificadores reaccionar de inmediato a los cambios en la demanda o los parámetros de planificación. |
| **¿Reemplazado por otra característica?**   | Sí, la optimización de la planificación reemplazará al motor de planificación maestro de Supply Chain Management integrado. |
| **Áreas de producto afectadas**         | Supply Chain Management: planificación maestra |
| **Opción de implementación**              | Solo en la nube. Optimización de planificación no se admite en implementaciones locales. |
| **Estado**                         | En desuso. El 1 de abril de 2022, los escenarios de fabricación ya no serán compatibles con el motor de planificación maestra de Supply Chain Management integrado. A partir de esa fecha, Microsoft detendrá todo el desarrollo activo en escenarios de fabricación para el motor de planificación integrado, no lanzará ninguna característica nueva y solo lanzará correcciones de errores críticos. Después de esa fecha, todas las empresas que requieran soporte para escenarios de fabricación deben utilizar la Optimización de la planificación para sus cálculos de planificación maestra. Se espera que la Optimización de la planificación sea totalmente compatible con los escenarios de fabricación para octubre de 2022. Para más información, consulte [Resumen de la planificación maestra obsoleta](../master-planning/deprecated-master-planning-overview.md).<br><br>Las compañías con implementaciones locales de Supply Chain Management pueden continuar usando el motor de planificación maestra integrado para escenarios de fabricación después de abril de 2022. Sin embargo, no se proporcionarán más mejoras de funciones. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Funciones quitadas o en desuso en la versión 10.0.11 de Supply Chain Management

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Usar el motor de planificación maestro de Supply Chain Management para escenarios de distribución

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para mejorar el rendimiento y minimizar la carga de la base de datos SQL durante las ejecuciones de planificación maestra, la optimización de planificación reemplaza el motor integrado de planificación maestra de Supply Chain Management. La optimización de planificación permite realizar ejecuciones de planificación rápida que se pueden realizar incluso durante el horario de oficina. Esto permite a los planificadores reaccionar de inmediato a los cambios en la demanda o los parámetros de planificación. |
| **¿Reemplazado por otra característica?**   | Sí, la optimización de la planificación reemplazará al motor de planificación maestro de Supply Chain Management integrado. |
| **Áreas de producto afectadas**         | Supply Chain Management: planificación maestra |
| **Opción de implementación**              | Solo en la nube. Optimización de planificación no se admite en implementaciones locales. |
| **Estado**                         | En desuso. El 1 de abril de 2021, los escenarios de distribución ya no serán compatibles con lel motor de planificación maestra de Dynamics 365 Supply Chain Management integrado. Para escenarios de distribución, los clientes deben usar Optimización de planificación para los cálculos de planificación maestra. Para más información, consulte [Resumen de la planificación maestra obsoleta](../master-planning/deprecated-master-planning-overview.md). Los clientes con implementaciones locales de Dynamics 365 Supply Chain Management pueden continuar usando el motor de planificación maestra de Supply Chain Management para escenarios de distribución después de abril de 2021. Sin embargo, no se proporcionarán más mejoras de funciones. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas

Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

