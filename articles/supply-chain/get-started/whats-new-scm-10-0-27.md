---
title: Novedades o cambios en Dynamics 365 Supply Chain Management 10.0.27 (julio de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Supply Chain Management 10.0.27.
author: kamaybac
ms.date: 04/22/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: a50fcbe313901beab610400d8c59dd375f1af93e
ms.sourcegitcommit: d770f0e6a012675a3027641704be804beb99754b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2022
ms.locfileid: "9022632"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10027-july-2022"></a>Novedades o cambios en Dynamics 365 Supply Chain Management 10.0.27 (julio de 2022)

[!include [banner](../includes/banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.27. Esta versión tiene el número de compilación 10.0.1227 y está disponible con la siguiente programación:

- **Vista previa de versión:** abril de 2022
- **Disponibilidad general de la versión (actualización automática):** junio de 2022
- **Disponibilidad general de la versión (actualización automática):** julio de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Inventario y logística | [Asignación de inventario para el complemento de visibilidad de inventario](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-allocation-inventory-visibility-add-in) | [Asignación de inventario para para visibilidad de inventario](../inventory/inventory-visibility-allocation.md) | Habilitado por defecto |
| Fabricación | Vista "Mi día" de la interfaz de ejecución de la planta de producción | [Cómo utilizan los trabajadores la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-use.md) y [Mostrar saldos de vacaciones en la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-payroll-stats.md) | Administración de características:<br>*Vista "Mi día" de la interfaz de ejecución de la planta de producción* |
| Planificada | [Soporte de optimización de planificación para subcontrataciones](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-subcontracting) | [Gestionar el trabajo de subcontratación en la producción](../production-control/manage-subcontract-work-production.md) | Habilitado por defecto |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Planificación maestra | Considerar el plazo de entrega de inventario al crear un pedido de transferencia planificado | Al crear un pedido de transferencia planificado, esta característica provoca que el sistema tenga en cuenta el plazo de entrega de inventario especificado en la configuración predeterminada de pedidos del artículo al calcular la fecha de recepción del pedido de transferencia planificado para la configuración del control de fecha de entrega como plazo de tipo *Ninguno* o *Ventas*. Si se especifica el plazo de entrega de transferencia, su valor se tomará para el cálculo de la fecha de recepción, y los días de transporte se pasarán por alto. |
| Adquisición y abastecimiento | Información de impuestos de contrato de agente predeterminado en líneas de facturas de proveedor | Esta característica introduce una lógica para establecer valores predeterminados para los campos **Impuestos** e **Impuestos de artículos** en las líneas de factura de proveedor de contrato de agente. Esta lógica solo se aplica cuando el tipo de cargo en la línea de contrato del agente es libro mayor/libro mayor. El grupo de impuestos de artículos tomará su valor predeterminado desde la categoría de compras de agente (si está configurada) o el tipo de cargo. El grupo de impuestos tomará su valor predeterminado desde la cuenta de proveedor. |
| Adquisición y abastecimiento | Limitar el número de líneas de pedido de compra por tarea por lotes | Esta característica le ayuda a optimizar el rendimiento del sistema al registrar confirmaciones y recepciones de producto. Agrega una nueva configuración denominada **Líneas por tarea** a la pestaña **Entrega** de la página **Parámetros de adquisición y abastecimiento**. La nueva configuración permite limitar el número de líneas de pedido de compra procesadas por cada tarea por lotes. Por lo tanto, ayuda a evitar que las tareas por lotes de gran tamaño hagan que el sistema vaya más lento. |
| Gestión de información de productos | Rellenar los valores de atributos del producto | Esta característica agrega una tarea periódica denominada *Rellenar valores de atributos del producto*. Esta nueva tarea periódica crea los registros de valores de atributos de productos que faltan para los atributos asociados a productos a través de una categoría de productos. |
| Control de producción | Configuración adicional de la interfaz de ejecución de la planta de producción | <p>Esta característica agrega las siguientes opciones a la página **Configurar ejecución de planta de producción**:</p><ul><li>**Abrir automáticamente el cuadro de diálogo de inicio al completar la búsqueda** - Si está habilitada esta opción, el cuadro de diálogo **Iniciar trabajo** se abrirá automáticamente cuando los trabajadores usen la barra de búsqueda para encontrar el trabajo.</li><li>**Abrir automáticamente el cuadro de diálogo de progreso del informe al completar la búsqueda** - Si está habilitada esta opción, el cuadro de diálogo **Progreso del informe** se abrirá automáticamente para el trabajo cuando los trabajadores usen la barra de búsqueda para encontrar el trabajo.</li><li>**Cantidad restante predeterminada en el cuadro de diálogo de progreso del informe** – Cuando esta opción está habilitada, el cuadro de diálogo **Progreso del informe** muestra la cantidad restante para informar sobre un trabajo de producción.</li></ul><p>Para obtener más información, vea [Configurar la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md).</p> |
| Control de producción | Equipos de producción en la interfaz de ejecución de la planta de producción | <p>Cuando varios trabajadores están asignados al mismo trabajo de producción, ahora pueden nombrar un trabajador como piloto. Los trabajadores restantes se convierten automáticamente en asistentes de ese piloto. Para el equipo resultante, solo el piloto debe registrar el estado del trabajo, mientras que los registros de tiempo se aplican a todos los miembros del equipo. Esta característica también admite un escenario denominado *recurso de asistencia*. En este escenario, un trabajador puede registrarse como asistente de otro trabajador, quien luego se convierte en el piloto del grupo recién formado.</p><p>Para obtener más información, consulte [Cómo los trabajadores usan la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-use.md).</p> |
| Control de producción | Informe sobre los elementos de planificación en la interfaz de ejecución de la planta de producción | Esta característica simplifica el proceso de informes sobre pedidos de lotes para planificación de artículos en la interfaz de ejecución de planta de producción. Cuando se crea un pedido de lote para un producto con el tipo de producción *Elemento de planificación*, solo se puede notificar como terminado en los coproductos o productos derivados de ese pedido de lote. Los pedidos de lotes para elementos de planificación se usan normalmente para admitir procesos de desensamblado, en los que un producto de materia prima se desensambla en varios productos únicos. Al notificar como terminado un pedido de lote para un elemento de planificación, los trabajadores verán ahora solo los coproductos y productos derivados en el cuadro de diálogo **Progreso del informe**. Anteriormente, también mostraba el elemento de planificación y este comportamiento podía confundir a los trabajadores. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes artículos de Ayuda. Estos artículos no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en las secciones anteriores. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Artículos nuevos o actualizados |
|---|---|
| Gestión de costes | [Fecha de media ponderada con valor físico y marcado incluido](../cost-management/weighted-average-date.md) |
| Topología híbrida distribuida | [Intentar escalar unidades en una topología híbrida distribuida](../cloud-edge/cloud-edge-try-out.md) |
| Doble escritura | [Sincronizar a petición con el motor de precios de Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/pricing-engine.md) |
| Gestión de almacenes | [Liberar al almacén](../warehousing/release-to-warehouse-process.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.27 incluye Platform updates. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.27 de aplicaciones de Finanzas y Operaciones (junio de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-27.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.27, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=673271).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022](/dynamics365-release-plan/2022wave1/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
