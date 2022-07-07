---
title: Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.25 (abril de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Supply Chain Management 10.0.25.
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: af344d3771583a99851c070e3735258ac964b5d7
ms.sourcegitcommit: 78576abe5c7cbab1bb69d26c999b038e8c24873a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954507"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10025-april-2022"></a>Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.25 (abril de 2022)

[!include [banner](../includes/banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.25. Esta versión tiene el número de compilación 10.0.1149 y está disponible de la siguiente manera:

- **Versión preliminar de versión:** febrero de 2022
- **Disponibilidad general de la versión (actualización automática):** marzo de 2022
- **Disponibilidad general de la versión (actualización automática):** abril de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se incluyeron en la compilación después de la publicación inicial del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Inventario&nbsp;y&nbsp;logística | [Mejoras para materiales peligrosos](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | Próximamente | Administración de características:<br>*Mejoras para materiales peligrosos* |
| Inventario&nbsp;y&nbsp;logística | [Trabajo de embalaje para estaciones de embalaje](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | Próximamente | Administración de características:<br>*Trabajo de embalaje para estaciones de embalaje* |
| Inventario&nbsp;y&nbsp;logística | [Escanear códigos de barras en el almacén utilizando los estándares de formato GS1](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [Códigos de barras GS1 y códigos QR](../warehousing/gs1-barcodes.md) | Administración de características:<br>*Digitalizar códigos de barras de GS1* |
| Fabricación | [Consumo de material y reservas en la interfaz de ejecución de planta de producción](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [Cómo los trabajadores usan la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-use.md) | Administración de características:<br>*(Versión preliminar) Registrar el consumo de material en la interfaz de ejecución de planta de producción (no WMS)*<br><br>Y/o:<br><br>Administración de características:<br>*(Vista previa) Registrar el consumo de material en la interfaz de ejecución de planta de producción (con WMS habilitado)* |
| Fabricación | [Registro de consumo de material en unidaes de escalado](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [Cargas de trabajo de ejecución de fabricación para unidades de escalado en el perímetro y en la nube](../cloud-edge/cloud-edge-workload-manufacturing.md) | Administración de características:<br>*Registrar el consumo de material en la aplicación móvil en una unidad de escalado* |
| Planificada | [Mantenimiento de calendario centralizado de optimización de planificación](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [Calendarios y planificación maestra](../master-planning/supply-chain-calendars-master-planning.md) | Habilitado por defecto |
| Planificada | [Sugerencias de optimización de la planificación para optimizar el suministro existente](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [Mensajes de acción](../master-planning/action-messages.md) | Habilitado por defecto |
| Planificada | Pedidos planificados simplificados | [Pedidos planificados simplificados](../master-planning/planning-optimization/planned-orders-simplified.md ) | Administración de características:<br>*Pedidos planificados simplificados* |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Gestión de inventario y almacenes | (Polonia) Permitir vincular varias facturas de DUA a una línea de pedido de compra en una DUA | Esta característica le permite dividir líneas de órdenes de compra y vincularlas a un solo documento administrativo (SAD) cuando esas líneas de órdenes de compra se registraron para varias facturas diferentes (como para diferentes envíos). |
| Adquisición y abastecimiento | Consolidar varias solicitudes de compra en un único pedido de compra por fecha contable | Esta función permite consolidar múltiples solicitudes de compra en una sola orden de compra si las diferentes solicitudes de compra tienen fechas contables diferentes. Las reglas de política de compras de creación de órdenes de compra y consolidación de la demanda se pueden configurar para automatizar la decisión de agrupar líneas de solicitud por fecha contable en el nivel de orden de compra. La consolidación de órdenes de compra por fecha contable no se admite si el control presupuestario está habilitado porque la fecha contable se usa para reservas de presupuesto y compromiso. Por lo tanto, debe retenerse durante la transición de la solicitud de compra al pedido de compra. |
| Adquisición y abastecimiento | Mostrar configuración de campo de respuesta a solicitud de presupuesto predeterminada heredada | Esta característica reintroduce la configuración del campo de respuesta de solicitud de cotización (RFQ) predeterminada heredada, que se eliminó anteriormente de la interfaz de usuario. Esta configuración no proporciona ninguna funcionalidad lista para usar, pero se puede personalizar para proporcionarla según sea necesario. Habilite esta característica si su organización ya ha agregado funcionalidad para la configuración del campo de respuesta de RFQ predeterminado o planea hacerlo. Cuando esta característica está habilitada, puede acceder a la configuración yendo a la página **Parámetros de adquisición y abastecimiento**, abriendo la pestaña **Solicitud de presupuesto** y seleccionando los **campos de respuesta de solicitud de presupuesto predeterminada**. |
| Adquisición y abastecimiento | Combinar las dimensiones financieras del proveedor con la dimensión financiera del vínculo de dimensión activo en el pedido de compra | Esta función le permite fusionar dimensiones financieras de proveedores con dimensiones financieras de vínculo de dimensión activo después de la aprobación de la solicitud de compra si configura un vínculo entre una dimensión financiera y la dimensión de inventario del sitio. Las reglas de política de compras de consolidación de demanda y creación de órdenes de compra se pueden configurar para impulsar la decisión de fusionar dimensiones financieras de proveedores con dimensión financiera de enlace de dimensión activa en el nivel de encabezado de orden de compra. |
| Control de producción | (Rusia) Habilitar la configuración de la ubicación predeterminada para la fórmula o L. MAT de producción y el consumo o reserva GTD automáticos en producción | La función habilita opciones adicionales para la producción a partir de materias primas importadas (solo localización en ruso):<ul><li>Opción para establecer la ubicación predeterminada automática para fórmulas de producción y listas de materiales tanto en grupos de recursos como en almacenes.</li><li>Reserva automática de materias primas por parte de la dimensión *número GTD* en almacenes activados por WMS según el algoritmo de reserva no WMS. Esto se aplica en los casos en que una política de trabajo para *recogida de materia prima* existe con **Método de creación de trabajo** ajustado a *Nunca* y la configuración del almacén, la ubicación y el número de artículo coincide con las transacciones de inventario de la orden de producción (lote).</li><li>Consumo automático de materias primas por dimensión *número GTD* al contabilizar la lista de selección, de acuerdo con la reserva adquirida descrita anteriormente.</li></ul> |
| Gestión de almacenes | (Vista previa) Compatibilidad con unidades de escalado para pedidos de almacén entrantes y salientes | Esta función hace que el sistema cree órdenes de almacenaje de salida durante el proceso de liberación a almacén y que cree órdenes de almacenaje de entrada cuando las órdenes de transferencia se contabilizan como enviadas. Luego, el sistema sincroniza cada pedido de almacén entrante o saliente con la unidad de báscula responsable de enviar o recibir el pedido. Tenga en cuenta que después de habilitar esta característica, sus cargas de trabajo de ejecución de almacén deben actualizarse. Para más información, vea [Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube](../cloud-edge/cloud-edge-workload-warehousing.md).<br><br>Esta función requiere la característica *Separar el trabajo de almacenamiento de los ASN* y habilitará la capacidad de recibir órdenes de transferencia mediante el proceso de recepción de matrículas en la aplicación móvil Warehouse Management. |

## <a name="feature-state-changes-in-this-release"></a>Cambios de estado de características en esta versión

La tabla siguiente enumera las características que se han convertido en obligatorias o activadas de forma predeterminada a partir de 10.0.25. Todas estas funciones se activarán automáticamente para su sistema tan pronto como actualice a 10.0.25. Las funciones obligatorias no se pueden desactivar, pero las funciones que están activadas de forma predeterminada aún se pueden desactivar usando [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La tabla también enumera las funciones que anteriormente estaban en versión preliminar pública, pero que cambiaron para estar disponibles de forma general en 10.0.25, lo que significa que ahora se recomienda su uso en entornos de producción. Estas funciones están desactivadas de forma predeterminada a menos que se indique lo contrario, por lo que debe usar [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitarlos si desea utilizarlos.

| Módulo | Nombre de característica | Estado de la característica |
| --- | --- | --- |
| Administración de activos | [Aplicar reglas para agrupar órdenes de trabajo mientras se ejecuta un plan de mantenimiento](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | Disponibilidad general |
| Administración de activos | [Mejoras de mantenimiento basadas en contador](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | Disponibilidad general |
| Gestión de costes | [Nivel de cálculo de costes](../cost-management/cost-calculation-level.md) | Disponibilidad general |
| Gestión de costes | Habilitar la configuración del número de lote definido por el usuario para la inversión de cierre de inventario | Disponibilidad general |
| Gestión de costes | [Detalles del progreso del cierre de inventario](whats-new-scm-10-0-21.md) | Disponibilidad general |
| Gestión de costes | [Opciones de dimensiones financieras predeterminadas para la revalorización de coste estándar de inventario](../cost-management/manage-standard-cost-updates.md) | Disponibilidad general |
| Gestión de costes | Limpieza de datos del informe del valor del inventario | Activado de forma predeterminada |
| Gestión de costes | [Almacenamiento de informes de valor de inventario](../cost-management/inventory-value-report-storage.md) | Activado de forma predeterminada |
| Gestión de costes | Mostrar registro de cierre de inventario en cuadrícula | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Habilitar la administración de cambios en productos existentes](../engineering-change-management/change-management-existing-products.md) | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Administración de cambios de ingeniería](../engineering-change-management/product-engineering-overview.md) | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Notificaciones de ingeniería para producción](../engineering-change-management/engineering-change-management.md) | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Herencia de atributos mejorada para la administración de cambios de ingeniería](../engineering-change-management/engineering-attributes-and-search.md) | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Administrar cambios en fórmulas y sus componentes](../engineering-change-management/manage-formula-changes.md) | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Comprobaciones de preparación de producto](../engineering-change-management/product-readiness.md) | Activado de forma predeterminada |
| Administración de cambios de ingeniería | [Generación de variantes de productos de ingeniería](../engineering-change-management/engineering-variants.md) | Activado de forma predeterminada |
| Gestión de inventario y almacenes | Navegación hasta la versión de L.M. desde las líneas de L.M. | Obligatoria |
| Planificación maestra | [Consolidación y puesta en firme por lotes de pedidos de lote masivos y empaquetados planificados](whats-new-scm-10-0-20.md) | Disponibilidad general |
| Planificación maestra | Planificación de recursos con mantenimiento | Disponibilidad general |
| Planificación maestra | Habilitar las características del asistente para la configuración del plan maestro | Obligatoria |
| Planificación maestra | [Selección de modelo de previsión según los detalles de la previsión de la demanda](../master-planning/manual-adjustments-baseline-forecast.md) | Obligatoria |
| Planificación maestra | [Visualización del progreso de la planificación maestra](../master-planning/tasks/monitor-master-planning-run.md) | Obligatoria |
| Planificación maestra | [Puesta en firme en paralelo de pedidos planificados](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoria |
| Planificación maestra | [Puesta en firme de pedido planificado con filtrado](../master-planning/planning-optimization/planned-order-firming.md) | Activado de forma predeterminada |
| Planificación maestra | [Vistas guardadas para pedidos planificados](saved-views-scm.md) | Activado de forma predeterminada |
| Adquisición y abastecimiento | Deshabilitar el botón Restablecer de la distribución de la solicitud de compra | Disponibilidad general |
| Adquisición y abastecimiento | [Habilitar el restablecimiento de los flujos de trabajo relacionados con la compra](whats-new-scm-10-0-20.md) | Disponibilidad general |
| Adquisición y abastecimiento | Capacidad de confirmar los pedidos de compra aceptados de la colaboración de proveedor en el lote | Obligatoria |
| Adquisición y abastecimiento | Estado cerrado de acuerdo de compra | Obligatoria |
| Adquisición y abastecimiento | Agregar líneas a facturas de pedidos de compra asociadas a un acuerdo de compra | Activado de forma predeterminada |
| Adquisición y abastecimiento | Agregar el campo Cantidad pedida a la página de registro de recepción de productos | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Permitir que los proveedores soliciten categorías de compras mediante la colaboración de proveedor](../procurement/category-requests-from-vendors.md) | Activado de forma predeterminada |
| Adquisición y abastecimiento | Carga los importes De y A en los pedidos de compra | Activado de forma predeterminada |
| Adquisición y abastecimiento | Configuración de gastos con sitio y almacén | Activado de forma predeterminada |
| Adquisición y abastecimiento | Habilitar el cálculo de aranceles sobre la compra basado en arancel anual | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Parte responsable del acuerdo de compra](../procurement/purchase-agreements.md) | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Vistas guardadas para pedidos de compra](saved-views-scm.md) | Activado de forma predeterminada |
| Gestión de información de productos | [Validación estricta en las cantidades de pedido predeterminadas](../production-control/default-order-settings.md) | Obligatoria |
| Gestión de información de productos | Preprocesamiento de informe de lista de materiales para evitar el tiempo de espera | Activado de forma predeterminada |
| Gestión de información de productos | Dimensiones financieras predeterminadas por separado cuando se usan plantillas de artículos | Activado de forma predeterminada |
| Gestión de información de productos | Habilitar grupos de dimensiones de productos para plantillas de artículos | Activado de forma predeterminada |
| Gestión de información de productos | Volver a generar nombres de variante del producto a partir de la nomenclatura | Activado de forma predeterminada |
| Gestión de información de productos | [Mejoras de la página de sugerencias de variantes](../pim/tasks/create-predefined-product-variants.md) | Activado de forma predeterminada |
| Control de producción | Mejora de la selección de la cantidad de peso capturado en producción | Disponibilidad general |
| Control de producción | Se ha agregado un nuevo botón Detener descanso a la página Terminal de tarjeta de trabajo | Obligatoria |
| Control de producción | [Habilitar la generación automática de matrícula de entidad de almacén al informar como terminado en el dispositivo de tarjetas de trabajo](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Control de producción | Habilitar la recepción parcial de los productos subcontratados y solucione un problema con el cálculo de rechazo para las líneas de L.M. del tipo Proveedor | Obligatoria |
| Control de producción | [Función para bloquear un dispositivo de tarjeta de trabajo y un terminal de tarjetas de trabajo para que se puedan desinfectar](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Control de producción | Mejoras en los cuadros de diálogo Aprobar y Transferir trabajos | Obligatoria |
| Control de producción | [Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Control de producción | [Imprimir etiqueta desde dispositivo de tarjeta de trabajo](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Control de producción | [Ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Control de producción | [Funcionalidad de administración de activos para la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Activado de forma predeterminada |
| Control de producción | [Búsqueda de trabajos para la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Activado de forma predeterminada |
| Control de producción | [Pasar por alto la reserva de producción predeterminada](../production-control/override-default-reservation-principle.md) | Activado de forma predeterminada |
| Control de producción | [Mostrar los números de serie completa, lote y matrícula de entidad de almacén en la interfaz de ejecución de planta de producción](whats-new-scm-10-0-21.md) | Activado de forma predeterminada |
| Ventas y marketing | [Mejora del rendimiento de los detalles del pedido de ventas](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | Disponibilidad general |
| Ventas y marketing | Mejora del rendimiento de los detalles del pedido presupuesto de ventas | Disponibilidad general |
| Ventas y marketing | Directiva de exportación de datos de referencia del pedido de ventas | Obligatoria |
| Ventas y marketing | [Directiva de eliminación de línea de pedido de ventas para línea de pedido de compra](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | Obligatoria |
| Ventas y marketing | [Directiva de exportación de datos de referencia del presupuesto de ventas](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| Obligatoria |
| Ventas y marketing | [Optimización de exportación de entidad de datos de persona de contacto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Activado de forma predeterminada |
| Ventas y marketing | Habilitar la búsqueda para la introducción del documento de presupuesto de ventas y los campos de conclusiones del documento | Activado de forma predeterminada |
| Ventas y marketing | [Mejorar el rendimiento de los 100 mejores clientes](whats-new-scm-10-0-23.md) | Activado de forma predeterminada |
| Ventas y marketing | Recalcular el saldo estimado del cliente | Activado de forma predeterminada |
| Ventas y marketing | [Registro de línea de pedido de devolución de ventas con precisión decimal con y sin peso capturado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Activado de forma predeterminada |
| Ventas y marketing | [Vistas guardadas de ventas y marketing](saved-views-scm.md) | Activado de forma predeterminada |
| Ventas y marketing | Confirmación del pedido de ventas con un solo clic | Activado de forma predeterminada |
| Gestión de almacenes | [Plantillas de tránsito directo con directivas de ubicación](../warehousing/planned-cross-docking.md) | Disponibilidad general |
| Gestión de almacenes | [Deshabilitar las recepciones esperadas de pedidos de calidad que muestrean el inventario bloqueado](../inventory/inventory-blocking.md) | Disponibilidad general |
| Gestión de almacenes | Historial de recepción de matrículas de entidad de almacén | Disponibilidad general |
| Gestión de almacenes | [Interfaz de equipo de gestión de material](../warehousing/mhax.md) | Disponibilidad general |
| Gestión de almacenes | [Redondear cantidades por debajo a la unidad de ventas más cercana durante la liberación al almacén](whats-new-scm-10-0-19.md) | Disponibilidad general |
| Gestión de almacenes | Soporte de unidad de escalado para listas de trabajo de aplicaciones de almacén | Disponibilidad general |
| Gestión de almacenes | Detalles de etiqueta de oleada de envío | Disponibilidad general |
| Gestión de almacenes | [Use una API más rápida para el cierre o la reapertura de contenedores en la estación de embalaje](whats-new-scm-10-0-21.md) | Disponibilidad general |
| Gestión de almacenes | [Validar plantillas seleccionadas para los trabajos de reabastecimiento](whats-new-scm-10-0-20.md) | Disponibilidad general |
| Gestión de almacenes | Permitir que la plantilla de reabastecimiento use trabajo de reabastecimiento inmediato existente (entre unidades) | Obligatoria |
| Gestión de almacenes | Asignación automática de los GUID en la creación de usuarios de WHS | Obligatoria |
| Gestión de almacenes | Capturar variantes del producto y dimensiones de seguimiento en la aplicación de gestión de almacenes durante la recepción de artículos de carga | Obligatoria |
| Gestión de almacenes | [Cambiar el estado de inventario de artículos controlados por dimensiones de seguimiento](../inventory/inventory-statuses.md) | Obligatoria |
| Gestión de almacenes | [Cambiar grupo de trabajo en trabajo](../warehousing/change-work-pool-on-work.md) | Obligatoria |
| Gestión de almacenes | [Posición completa del clúster](../warehousing/cluster-position-full.md) | Obligatoria |
| Gestión de almacenes | [Característica de ubicación de clúster](../warehousing/putaway-clusters.md) | Obligatoria |
| Gestión de almacenes | [Confirmar y transferir](../warehousing/confirm-and-transfer.md) | Obligatoria |
| Gestión de almacenes | [Confirmar envíos salientes de trabajos por lotes](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | Obligatoria |
| Gestión de almacenes | [Controlar si se mostrará una página de resumen de recepción en los dispositivos móviles](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obligatoria |
| Gestión de almacenes | [Procesamiento diferido de la operación de movimiento de inventario manual](../warehousing/deferred-processing-manual-inventory-movement.md) | Obligatoria |
| Gestión de almacenes | No permitir la creación de cargas, que no cumplan los requisitos de la plantilla de planificación de carga de oleada | Obligatoria |
| Gestión de almacenes | [Diseños de etiquetas de matrícula de entidad de almacén mejorados](../warehousing/document-routing-layout-for-license-plates.md) | Obligatoria |
| Gestión de almacenes | [Evaluar todas las acciones para directivas de ubicación de SKU múltiples](/troubleshoot/dynamics-365/supply-chain/warehousing/evaluate-multiple-location-directive-actions) | Obligatoria |
| Gestión de almacenes | Ocultar el campo Valor total en las páginas "Todas las cargas" y "Detalles de la carga" | Obligatoria |
| Gestión de almacenes | Configuración de creación de etiquetas de matrículas de entidad de almacén | Obligatoria |
| Gestión de almacenes | Corrección manual de línea de carga para administradores o usuarios de confianza similares | Obligatoria |
| Gestión de almacenes | [Posición de matrícula de entidad de almacén de ubicación](../warehousing/location-license-plate-positioning.md) | Obligatoria |
| Gestión de almacenes | [Combinación de dimensiones de producto de ubicación](../warehousing/location-product-dimension-mixing.md) | Obligatoria |
| Gestión de almacenes | Hacer editable el campo de estado de inventario de movimiento de inventario de dispositivo móvil | Obligatoria |
| Gestión de almacenes | Servicio de recogida manual de línea de ventas para administración o para usuarios de confianza similares | Obligatoria |
| Gestión de almacenes | [Impedir que las matrículas de entidad de almacén enviadas se usen en almacenes que no sean el almacén de destino](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | Obligatoria |
| Gestión de almacenes | Solicitar la resolución de nombres de "Ubicación / N.º licencia" ambiguos | Obligatoria |
| Gestión de almacenes | [Control de calidad](../warehousing/quality-check.md) | Obligatoria |
| Gestión de almacenes | [Configuración de usuario, iconos y títulos de pasos mejorados para la nueva aplicación de almacén](../warehousing/install-configure-warehouse-management-app.md) | Obligatoria |
| Gestión de almacenes | [Zona de ubicación adicional](../warehousing/additional-location-zones.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Crear y procesar pedidos de transferencia desde la aplicación de almacén](../warehousing/create-transfer-order-from-warehouse-app.md) | Activado de forma predeterminada |
| Gestión de almacenes | Habilitar la validación rápida para dispositivos móviles de almacén | Activado de forma predeterminada |
| Gestión de almacenes | [Tiempo de ejecución máximo para el trabajo de limpieza de entradas disponibles de gestión de almacenes](../warehousing/onhand-cleanup.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Visualización de carga de trabajo de salida](../warehousing/outbound-workload-visualization.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Procesar eventos de la aplicación de almacén](../warehousing/warehouse-app-events.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Vista guardada para el área de trabajo de planificación de la carga](saved-views-scm.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Vista guardada para la página de detalles del trabajo](saved-views-scm.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Vista guardada para procesamiento de oleadas](saved-views-scm.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Vistas guardadas para procesamiento de carga](saved-views-scm.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Vistas guardadas para procesamiento de envíos](saved-views-scm.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Detalles del trabajo por lotes de oleada](../warehousing/wave-processing.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Notificaciones de ejecución de lanzamientos](../warehousing/wave-execution-notifications.md) | Activado de forma predeterminada |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.25 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.25 de aplicaciones de Finanzas y Operaciones (abril de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.25, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868).

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
