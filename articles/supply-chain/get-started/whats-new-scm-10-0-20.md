---
title: Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.20 (agosto de 2021)
description: En este tema se describen las características nuevas o modificadas en Dynamics 365 Supply Chain Management 10.0.20.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1aada0d3ebe80e1efb92815c6d429ed5638dabdbac165aa09be1ca281c51b255
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773522"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.20 (agosto de 2021)

[!include [banner](../includes/banner.md)]

En este tema se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.20. Esta versión tiene el número de compilación 10.0.886 y está disponible de la siguiente manera:

- **Vista previa de la versión:** mayo 2021
- **Disponibilidad general de la versión (actualización automática):** julio de 2021
- **Disponibilidad general de la versión (actualización automática):** agosto de 2021

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. La columna *Característica* proporciona enlaces al [plan de lanzamiento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), donde puede ver las fechas de lanzamiento oficiales de cada característica. La columna *Más información* proporciona más detalles y/o vínculos a la documentación relacionada.

La mayoría de estas características deben habilitarse mediante la [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para poder usarse.

| Área de características | Característica | Más información |
|---|---|---|
| Inventario&nbsp;y&nbsp;logística | [Mejora del rendimiento de los detalles del pedido de ventas](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Esta característica hace que la interfaz de usuario sea más receptiva al abrir pedidos de ventas, especialmente pedidos que incluyen muchas líneas. |
| Fabricación | [Invocar flujos de automatización de procesos para crear pedidos de calidad](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [Invocar flujos de automatización de procesos para crear pedidos de calidad](../production-control/process-automation-quality-orders.md ) |
| Fabricación | [Ejecución mejorada de interfaz de ejecución de planta de producción para fabricación](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [Configurar la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) |
| Gestión de información de productos | [Gestionar cambios en fórmulas y sus componentes](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [Gestionar cambios en fórmulas y sus componentes](../engineering-change-management/manage-formula-changes.md) |
| Gestión de información de productos | [Comprobaciones de preparación de producto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [Preparación de producto](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada uno de estos proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario). Si desea utilizar alguna de estas funciones, debe habilitarlas explícitamente en [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Área de características | Característica&nbsp;nombre&nbsp;en característica&nbsp;administración | Más información |
|---|---|---|
| Planificación maestra | Autorización paralela de previsión de la demanda ajustada | Esta característica permite la autorización paralela de la previsión de demanda ajustada de la página **Previsión de la demanda ajustada**. La intención de esta función es aumentar el rendimiento cuando se autoriza una gran cantidad de pronósticos. Al autorizar, el usuario puede especificar el **Número de hilos** en el diálogo de autorización. |
| Planificación maestra | (Versión preliminar) Consolidación y puesta en firme por lotes de pedidos de lote masivos y empaquetados planificados | Esta característica permite usar trabajos por lotes para poner en firme y consolidar pedidos masivos y empaquetados planificados. |
| Control de producción | Copiar rutas genéricas | Esta característica mejora la función de copia de ruta para permitir a los usuarios copiar rutas que no son específicas de un artículo. Permite que el sistema actualice toda la información relevante (como el sitio, el grupo de rutas, los requisitos de recursos y varias horas) después de que se haya utilizado la función de copia de ruta para sobrescribir una ruta que aún no está asignada a un elemento. |
| Control de producción | Actualizar requisitos de recursos relacionados cuando se cambia una operación de ruta | Esta característica permite al sistema actualizar los requisitos de recursos relacionados después de que un usuario cambie la operación de un paso de ruta existente. |
| Gestión de información de productos | Preprocesamiento del informe de la lista de materiales para evitar el tiempo de espera | Esta función hace que el informe de la lista de materiales se procese previamente. Esto evitará problemas de tiempo de espera cuando haya una gran carga de datos para el informe. |
| Adquisición y abastecimiento | Habilitar el restablecimiento de los flujos de trabajo relacionados con la compra | Esta función de vista previa le permite restablecer los siguientes flujos de trabajo al estado de borrador: pedido de compra, cambio de proveedor y solicitudes de compra. |
| Gestión del transporte | Habilitar la creación de un diario de facturas de proveedor al descartar un albarán de flete | Cuando esta función está habilitada, el diario de facturas del proveedor correspondiente solo se creará por motivos de conciliación cuando esté utilizando la opción pagar al proveedor. De lo contrario, siempre se creará el diario de facturas. |
| Gestión de almacenes | Validar plantillas seleccionadas para los trabajos de reabastecimiento | Esta función ayuda a garantizar que los usuarios seleccionen plantillas de reabastecimiento válidas al configurar un trabajo de reabastecimiento. Evita que los usuarios creen un trabajo de reabastecimiento sin una plantilla y que seleccionen plantillas de tipo *Demanda de oleada*, que no creará ningún trabajo de reabastecimiento y puede llevar mucho tiempo procesarlo. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes temas de ayuda. No están necesariamente relacionadas con las nuevas funciones agregadas para esta versión, como se enumeran en la sección anterior, pero pueden ayudarlo a aprovechar más las funciones existentes.

| Área de características | Temas nuevos o actualizados |
|---|---|
| Administración de cambios de ingeniería | [Transacciones y estados del ciclo de vida de producto](../engineering-change-management/product-lifecycle-state-transactions.md) |
| Gestión de inventarios | [Complemento de visibilidad de inventario](../inventory/inventory-visibility.md)<br><br>[Descripción general de la gestión de la calidad y las no conformidades](../inventory/quality-management-processes.md) (más todos los temas relacionados con la gestión de la calidad) |
| Adquisición y abastecimiento | [Mantener certificación de proveedor](../../finance/public-sector/manage-vendor-certification.md) |
| Control de producción | [Estilo de la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-styles.md) |
| Gestión de almacenes | [Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management](../warehousing/step-icons-titles.md)<br><br>[Procesamiento diferido del movimiento manual de inventario](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform updates para aplicaciones de Finance and Operations

Microsoft Dynamics 365 Supply Chain Management 10.0.20 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.20 de aplicaciones Finance and Operations (julio de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.20, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8). 

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
