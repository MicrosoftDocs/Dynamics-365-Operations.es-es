---
title: Versión preliminar de Dynamics 365 Supply Chain Management 10.0.19 (julio de 2021)
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
ms.openlocfilehash: 8bb4a7c8085b40ab3eca72675dbe7a3be412d8c1
ms.sourcegitcommit: 2eb7a9ae544f504155657c5c584cbac66c21dba4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2021
ms.locfileid: "5961690"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10019-july-2021"></a>Versión preliminar de Dynamics 365 Supply Chain Management 10.0.19 (julio de 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este tema se enumeran las características nuevas o modificadas en la versión preliminar de Microsoft Dynamics 365 Supply Chain Management de la versión 10.0.19. Esta versión tiene el número de compilación 10.0.837 y está disponible de la siguiente manera:

- **Vista previa de versión:** abril de 2021
- **Disponibilidad general de la versión (actualización automática):** junio de 2021
- **Disponibilidad general de la versión (actualización automática):** julio de 2021

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. La columna *Característica* proporciona enlaces al [plan de lanzamiento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), donde puede ver las fechas de lanzamiento oficiales de cada característica. La columna *Más información* proporciona vínculos a la documentación relacionada.

La mayoría de estas características deben habilitarse mediante la [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para poder usarse. Algunas de las funciones enumeradas todavía están en vista previa, mientras que otras pueden estar ya disponibles de manera general.

| Área de características | Característica | Más información |
|---|---|---|
| Inventario y logística | [Optimización de exportación de entidad de datos de persona de contacto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | *No disponible* |
| Inventario y logística | [Mejoras incrementales para las capacidades de ejecución del almacén con unidades de escalado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Mensajes del procesador de mensajes](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Ajuste de inventario de almacén](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Inventario y logística | [Funcionalidad de búsqueda para los campos Introducción de documento y Conclusión de documento en la página presupuesto de venta](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | *No disponible* |
| Inventario y logística | [Ejecución de almacén con unidades de escalado de borde en su hardware personalizado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Implementar unidades de escalado de borde en hardware personalizado usando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Fabricación | [Ejecución de fabricación con unidades de escalado de borde en su hardware personalizado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Implementar unidades de escalado de borde en hardware personalizado usando LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planificada | Confirmación de pedidos planificados basada en consultas | [Poner en firme pedidos planificados](../master-planning/planning-optimization/planned-order-firming.md) |
| Gestión de información de productos | [Mejoras de la página de sugerencias de variantes](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Crear variantes de productos predefinidas](../pim/tasks/create-predefined-product-variants.md) |

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

Microsoft Dynamics 365 Supply Chain Management 10.0.19 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.19 de aplicaciones Finance and Operations (julio de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

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
