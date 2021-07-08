---
title: Novedades y cambios en la versión 10.0.19 de Dynamics 365 Supply Chain Management (junio de 2021)
description: En este tema se describen las características nuevas o modificadas en Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 7f98eee2a821191cefc27abbbd59373084c8b50c
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271458"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Novedades y cambios en la versión 10.0.19 de Dynamics 365 Supply Chain Management (junio de 2021)

[!include [banner](../includes/banner.md)]

En este tema se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.19. Esta versión tiene el número de compilación 10.0.837 y está disponible de la siguiente manera:

- **Vista previa de versión:** abril de 2021
- **Disponibilidad general de la versión (actualización automática):** junio de 2021
- **Disponibilidad general de la versión (actualización automática):** junio de 2021

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. La columna *Característica* proporciona enlaces al [plan de lanzamiento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), donde puede ver las fechas de lanzamiento oficiales de cada característica. La columna *Más información* proporciona más detalles y/o vínculos a la documentación relacionada.

La mayoría de estas características deben habilitarse mediante la [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para poder usarse.

| Área de características | Característica | Más información |
|---|---|---|
| Inventario y logística | [Optimización de exportación de entidad de datos de persona de contacto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | Cuando está característica está habilitada, los cambios en los datos referenciados no harán que los contactos se incluyan en la siguiente exportación incremental. Cuando está característica está deshabilitada, los cambios en los datos referenciados harán que los contactos se incluyan en la siguiente exportación incremental. |
| Inventario y logística | [Mejoras incrementales para las capacidades de ejecución del almacén con unidades de escalado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Mensajes del procesador de mensajes](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Ajuste de inventario de almacén](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Inventario y logística | [Funcionalidad de búsqueda para los campos Introducción de documento y Conclusión de documento en la página presupuesto de venta](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Esta función añade la funcionalidad de búsqueda para los campos **Introducción de documento** y **Conclusión de documento** en la página **Presupuesto de venta**.<br><br>De forma predeterminada, esta característica está habilitada. |
| Inventario y logística | [Ejecución de almacén con unidades de escalado de borde en su hardware personalizado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Implementar unidades de escalado de borde en hardware personalizado usando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Fabricación | [Ejecución de fabricación con unidades de escalado de borde en su hardware personalizado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Implementar unidades de escalado en el perímetro en hardware personalizado mediante LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planificada | [Programación de capacidad infinita para Optimización de planificación](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | Esta función permite la programación de la capacidad con una capacidad infinita para la optimización de la planificación. Sin esta función, los pedidos de producción planificados obtienen su tiempo de entrega del tiempo de entrega del inventario de productos liberados, independientemente del límite de tiempo de programación. |
| Planificada | Confirmación de pedidos planificados basada en consultas | [Poner en firme pedidos planificados](../master-planning/planning-optimization/planned-order-firming.md) |
| Gestión de información de productos | [Mejoras de la página de sugerencias de variantes](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Crear variantes de productos predefinidas](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada uno de estos proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario). Si desea utilizar alguna de estas funciones, debe habilitarlas explícitamente en [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Área de características | Característica&nbsp;nombre&nbsp;en característica&nbsp;administración | Más información |
|---|---|---|
| Ventas y marketing | Mejoras en el rendimiento de la limpieza del historial de ventas | La limpieza del historial de ventas puede llevar mucho tiempo si se ejecuta con poca frecuencia en entornos con un gran volumen de actualizaciones de ventas. Para reducir la duración y mejorar la fiabilidad, esta función divide la limpieza en lotes que se ejecutan por una duración limitada. Siempre que sea posible, se aprovecharán las capacidades de la base de datos para minimizar el bloqueo y evitar unir tablas transaccionales durante la limpieza. |
| Ventas y marketing | Actualizar la fecha de recepción solicitada con la fecha confirmada para pedidos entre empresas vinculadas | Esta función le permite controlar lo que sucederá con los valores del campo de fecha de compra y venta cuando utilice la entrega directa entre empresas. Puede elegir si el sistema actualizará las fechas solicitadas u omitirá actualizarlas. Si omite la actualización, las fechas solicitadas representarán lo que el cliente ha solicitado. Si habilita la actualización, las fechas solicitadas (cuando se usa el control de fecha de entrega) solo representan inicialmente lo que solicitó el cliente. Control de fecha de entrega, cuando sea diferente de *Ninguno*, anulará lo que se solicitó inicialmente. Puede configurar esta opción utilizando la nueva configuración **Actualizar la fecha de recepción solicitada con la fecha confirmada** en la configuración del proveedor de empresas vinculadas o cliente.<br><br>Si la función está desactivada, el sistema sobrescribirá la fecha de recepción solicitada en los pedidos de venta originales según la regla de control de la fecha de entrega, pero la fecha de envío solicitada permanecerá como está. |
| Gestión de almacenes | Redondear cantidades por debajo a la unidad de ventas más cercana durante la liberación al almacén | Esta función agrega una opción que puede restringir las cantidades de los pedidos en el momento de su liberación al almacén. Cuando está habilitada, las cantidades de los pedidos se redondearán a la unidad de ventas completa más cercana y los pedidos que incluyan cantidades de menos de una unidad de ventas se rechazarán para su liberación. |
| Gestión de almacenes | Método de oleada "Programar creación de trabajo" de toda la organización | Al habilitar esta función, el método de oleada *Programar creación de trabajo* se configura para ejecutarse en paralelo en todas las entidades legales. También se verán afectados varios ajustes adicionales. Para más información, consulte [Programar la creación del trabajo durante el lanzamiento](../warehousing/configure-wave-schedule-work-creation.md). |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes temas de ayuda. No están necesariamente relacionadas con las nuevas funciones agregadas para esta versión, como se enumeran en la sección anterior, pero pueden ayudarlo a aprovechar más las funciones existentes.

| Área de características | Temas nuevos o actualizados |
|---|---|
| Administración de cambios de ingeniería | [Preguntas frecuentes de administración de cambios de ingeniería](../engineering-change-management/change-management-faq.md) |
| Adquisición y abastecimiento | [Solicitudes de categoría desde proveedores](../procurement/category-requests-from-vendors.md) |
| Gestión de información de productos | [Gestionar la unidad de medida](../pim/tasks/manage-unit-measure.md)<br><br>[Cálculos para un modelo de configuración de productos](../pim/config-model-calculations.md) |
| Control de producción | [Secuencia numérica unificada para id. de trabajo](../production-control/unified-job-ids.md) |
| Administración de transporte | [Clases menores que la carga en camión](../transportation/ltl-class.md)<br><br>[Códigos NMFC](../transportation/nmfc-codes.md) |
| Gestión de almacenes | [Solucionar problemas de jerarquías de reserva en serie y por lotes del almacén](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Gestión de almacenes, creación y procesamiento de lanzamientos | [Creación y procesamiento de lanzamientos](../warehousing/wave-processing.md)<br><br>[Parámetros de almacén para el procesamiento de lanzamientos](../warehousing/wave-warehouse-parameters.md)<br><br>[Plantillas de lanzamiento](../warehousing/wave-templates.md)<br><br>[Asignación de lanzamientos](../warehousing/wave-allocation-method.md)<br><br>[Programar creación de trabajo durante lanzamiento](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Creación de contenedores](../warehousing/wave-containerization.md)<br><br>[Notificaciones de ejecución de lanzamientos](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform updates para aplicaciones de Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.19 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.19 de aplicaciones Finance and Operations (junio de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.19, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: plan del primer lanzamiento de versiones de 2021

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365: plan del primer lanzamiento de versiones de 2021](/dynamics365-release-plan/2021wave1/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
