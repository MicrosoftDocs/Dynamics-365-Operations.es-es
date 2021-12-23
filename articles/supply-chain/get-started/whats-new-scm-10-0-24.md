---
title: Versión preliminar de Dynamics 365 Supply Chain Management 10.0.24 (febrero de 2022)
description: En este tema se describen las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management 10.0.24.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 1b5742ddf7e5e2c5c32c446a0bde08f4964d6b95
ms.sourcegitcommit: 96515ddbe2f65905140b16088ba62e9b258863fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2021
ms.locfileid: "7891883"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10024-february-2022"></a>Versión preliminar de Dynamics 365 Supply Chain Management 10.0.24 (febrero de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este tema se enumeran las características nuevas o modificadas en la versión preliminar de Microsoft Dynamics 365 Supply Chain Management de la versión 10.0.24. Esta versión tiene el número de compilación 10.0.1084 y está disponible de la siguiente manera:

- **Versión preliminar:** diciembre de 2021
- **Disponibilidad general de la versión (actualización automática):** enero de 2022
- **Disponibilidad general de la versión (actualización automática):** febrero de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este tema para incluir características que se incluyeron en la compilación después de la publicación inicial del tema.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Topología híbrida distribuida | [Cargas de trabajo de ejecución de almacén mejoradas en unidades de escala](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube](../cloud-edge/cloud-edge-workload-warehousing.md) | Habilitado por defecto. |
| Planificada | [Soporte de optimización de la planificación para días de administración y el margen de emisión](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [Márgenes de seguridad](../master-planning/planning-optimization/safety-margins.md) | Habilitado por defecto. |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Control de producción | Comprobación de disponibilidad de material a petición para pedidos de producción | Esta característica hace que resulte más rápido abrir la página **Pedidos de producción para liberar**, que está disponible en el espacio de trabajo **Gestión de planta de producción**. Sin esta característica, el sistema comprueba automáticamente si los materiales están disponibles para todos los pedidos de fabricación enumerados en cuanto se abre la página, lo que puede llevar mucho tiempo si se tiene un gran número de pedidos. Cuando esta función está activada, el sistema proporciona un botón en la barra de herramientas, que puede utilizar para iniciar la comprobación de materiales solo para los pedidos seleccionados y cuando sea necesario. |
| Control de producción | (Versión preliminar) Registrar el consumo de material en la interfaz de ejecución de planta de producción (no WMS) | Esta característica permite a los trabajadores utilizar la interfaz de ejecución de la planta de producción para registrar el consumo de material, los números de lote y los números de serie. Esta característica solo admite artículos que no están habilitados para utilizar procesos de almacén avanzados (WMS). La compatibilidad con elementos habilitados para WMS está programada para una versión futura.<p>Algunos fabricantes, especialmente aquellos dentro de las industrias de proceso, necesitan registrar explícitamente la cantidad de material consumido para cada lote o pedido de producción. Por ejemplo, los trabajadores pueden usar una balanza para pesar la cantidad de material consumido mientras trabajan. Para garantizar la trazabilidad total del material, estas organizaciones también deben registrar qué números de lote se consumieron al producir cada producto. |
| Control de producción | Notificar como finalizada la carga de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube | Esta función permite a los trabajadores usar la aplicación móvil Warehouse Management notificar que se ha finalizado una producción o un pedido por lotes cuando la aplicación se ejecuta en una carga de trabajo de administración de almacén en una unidad de escala en la nube o en el perímetro. Para más información, consulte [Notificar como terminado y almacenado en una unidad de escalado](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF). |
| Control de producción | Iniciar el pedido de producción en la carga de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube | Esta función permite a los trabajadores usar la aplicación móvil Warehouse Management iniciar una producción o un pedido por lotes cuando la aplicación se ejecuta en una carga de trabajo de administración de almacén en una unidad de escala en la nube o en el perímetro. |
| Gestión de almacenes | Nuevas páginas de área de trabajo de planificación de la carga | Habilita dos nuevas páginas de área de trabajo de planificación de la carga: **Área de trabajo de planificación de la carga entrante** y **Área de trabajo de planificación de la carga saliente**. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes temas de ayuda. Estos temas no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en la sección anterior. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Temas nuevos o actualizados |
|---|---|
| Gestión de costes | [Informes de valor de inventario](../cost-management/inventory-value-report-storage.md) |
| Gestión de costes | [Ejemplos de informes de valor de inventario y lógica](../cost-management/inventory-value-report-examples.md) |
| Planificación maestra | [Parámetros de fecha y hora utilizados por Optimización de planificación](../master-planning/planning-optimization/date-time-used.md) |
| Planificación maestra | [Configuración de previsión de demanda](../master-planning/demand-forecasting-setup.md) |
| Planificación maestra | [Usar el diario de existencias de seguridad para actualizar la cobertura mínima para artículos](../master-planning/safety-stock-journal.md) |
| Control de producción | [Personalizar la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-customize.md) |
| Control de producción | [Estilo de la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-styles.md) |
| Ventas y marketing | [Mejoras de rendimiento de limpieza del historial de ventas](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Gestión de almacenes | [Cuentas de usuario de dispositivo móvil](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform updates para aplicaciones de Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.24 incluye Platform updates. Para obtener más información, consulte [Actualizaciones de plataforma para la versión 10.0.24 de aplicaciones de Finance and Operations (noviembre de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.24, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2021

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2021](/dynamics365-release-plan/2021wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
