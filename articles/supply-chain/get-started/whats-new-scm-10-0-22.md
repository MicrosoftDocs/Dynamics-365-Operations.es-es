---
title: Versión preliminar de Dynamics 365 Supply Chain Management 10.0.22 (noviembre de 2021)
description: En este tema se describen las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management 10.0.22.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3f5166338aebe784fe7f95372a437d4ed660de77
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579721"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10022-november-2021"></a>Versión preliminar de Dynamics 365 Supply Chain Management 10.0.22 (noviembre de 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este tema se enumeran las características nuevas o modificadas en la versión preliminar de Microsoft Dynamics 365 Supply Chain Management de la versión 10.0.22. Esta versión tiene el número de compilación 10.0.995 y está disponible de la siguiente manera:

- **Versión preliminar:** septiembre de 2021
- **Disponibilidad general de la versión (actualización automática):** octubre de 2021
- **Disponibilidad general de la versión (actualización automática):** noviembre de 2021

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. La columna *Característica* proporciona enlaces al [plan de lanzamiento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), donde puede ver las fechas de lanzamiento oficiales de cada característica. La columna *Más información* proporciona más detalles y/o vínculos a la documentación relacionada. Para determinar cómo activar una función, consulte la columna *Habilitado por*. Para obtener más información acerca de cómo usar la la administración de características, consulte [Visión general de la Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Puede que haya actualizaciones de este tema para incluir características que se incluyeron en la compilación después de la publicación inicial del tema.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Planificada | [Soporte de Planning Optimization para la asignación de recursos basada en capacidades](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-capability-based-resource-allocation) | [Programación con selección de recursos según la capacidad](../master-planning/planning-optimization/capability-based-scheduling.md) | Administración de características (*Programación de capacidad infinita para Optimización de planificación*) |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario). Si desea utilizar alguna de estas funciones, debe habilitarlas explícitamente en [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Área de características | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Gestión de costes | Cree comprobantes relacionados para reevaluaciones de redondeo de costos estándar | <p>Cuando se realiza una contabilización financiera de inventario (como una factura de orden de venta o una transacción de inventario), esta función hace que el sistema cree un comprobante separado para cualquier revalorización de redondeo de costos estándar relacionada y lo adjunte al comprobante de contabilización financiera como comprobante relacionado.</p><p>Sin esta función, el sistema registra las revalorizaciones de redondeo de costes estándar en la misma contabilización de comprobantes. Ese comportamiento a veces puede causar información de fecha conflictiva, porque las revaluaciones usan la fecha de la sesión o del sistema, mientras que las contabilizaciones financieras usan la fecha de contabilización.</p> |
| Topología híbrida distribuida | *(No se requiere administración de características).* | <p>Esta versión amplía las capacidades de planificación de carga saliente de la carga de trabajo de gestión de almacenes para unidades de escala en la nube y en el borde.</p><p>Para más información, vea [Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube](../cloud-edge/cloud-edge-workload-warehousing.md).</p> |
| Administración de cambios de ingeniería | Generación de variantes de productos de ingeniería | <p>Esta característica le permite generar varias variantes para un producto de ingeniería, según su color, tamaño, estilo o dimensiones de configuración.</p><p>Para más información, vea [Genere variantes para productos de ingeniería](../engineering-change-management/engineering-variants.md).</p> |
| Gestión de inventario y almacenes | Integración de Visibilidad de inventario con compensación de reserva | <p>Esta característica se puede habilitar solo después de que la función *Integración de visibilidad de inventario* está habilitada. Proporciona funcionalidad para compensar las reservas que se realizan en la visibilidad del inventario.</p><p>Para obtener más información, consulte [Reservas de Visibilidad de inventario](../inventory/inventory-visibility-reservations.md).</p> |
| Ventas y marketing | Limitar el número de pedidos de ventas que pueden seleccionarse para registro | <p>Esta característica está habilitada automáticamente. Agrega un campo **Número máximo de pedidos de ventas para registrar** a la página **Parámetros de clientes**. Este campo permite definir el número máximo de pedidos de ventas que se pueden seleccionar al registrar confirmaciones, listas de selección, albaranes y facturas desde la página de lista del pedido de ventas. El valor predeterminado es *100*.</p><p>Esta característica ayuda a mejorar el rendimiento de la página de lista del pedido de ventas cuando se selecciona una cantidad sustancial de pedidos de ventas. No tiene ningún impacto en el número de pedidos de ventas que se pueden procesar mediante una tarea periódica.</p> |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes temas de ayuda. Estos temas no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en la sección anterior. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Temas nuevos o actualizados |
|---|---|
| Administración de cambios de ingeniería | [Descripción general de la gestión de cambios de ingeniería](../engineering-change-management/product-engineering-overview.md) ahora enumera todas las funciones opcionales relacionadas disponibles en la administración de características |
| Planificación maestra | [Configuración de previsión de demanda](../master-planning/demand-forecasting-setup.md) |
| Planificación maestra | [Requisitos netos e información de diagrama de árbol con Optimización de planificación](../master-planning/planning-optimization/net-requirements.md) |
| Gestión de almacenes | [Liberar al almacén](../warehousing/release-to-warehouse-process.md) proporciona una descripción detallada del proceso completo de liberación al almacén |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform updates para aplicaciones de Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.22 incluye Platform updates. Para obtener más información, consulte [Actualizaciones de plataforma para la versión 10.0.22 de aplicaciones de Finance and Operations (noviembre de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22.md). <!-- KFM: Confirm link -->

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.22, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=615299).

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
