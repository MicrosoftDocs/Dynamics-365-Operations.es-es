---
title: Versión preliminar de Dynamics 365 Supply Chain Management 10.0.29 (octubre de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Supply Chain Management 10.0.29.
author: kamaybac
ms.date: 08/12/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d95cd9b55f473bed2e3fe69e63837040385f03ac
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334757"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10029-october-2022"></a>Versión preliminar de Dynamics 365 Supply Chain Management 10.0.29 (octubre de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión preliminar 10.0.29. Esta versión tiene el número de compilación 10.0.1326 y está disponible con la siguiente programación:

- **Versión preliminar de la versión:** agosto de 2022
- **Disponibilidad general de la versión (actualización automática):** septiembre de 2022
- **Disponibilidad general de la versión (actualización automática):** octubre de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Inventario y logística | [Asignar y reservar artículos de WMS en Visibilidad de inventario](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/allocate-reserve-whs-items-inventory-visibility) | Próximamente | Habilitado por defecto |
| Inventario y logística | [Precargar listas de inventario disponibles optimizadas](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/query-inventory-visibility-summary-entity) | Próximamente | Habilitado por defecto |
| Automatización del suministro de fabricación contra pedido | [Automatización del suministro de fabricación contra pedido](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-to-order-supply-automation) | [Automatización del suministro de fabricación contra pedido](../master-planning/make-to-order-supply-automation.md) | Administración de características:<br>*Automatización del suministro de fabricación contra pedido* |
| Planificada | [Ver y aplicar conocimientos detallados para DDMRP](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/view-apply-detailed-insights-ddmrp) | [Descripción general de la Planificación de requisitos de materiales basada en la demanda](../master-planning/planning-optimization/ddmrp-overview.md) | Administración de características:<br>*(Versión preliminar) DDMRP para optimización de planificación* |
| Control de producción | [Hacer que los bienes terminados estén disponibles físicamente antes de registrarlos en los diarios](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/make-finished-goods-physically-before-posting) | [Hacer que los bienes terminados estén disponibles físicamente antes de registrarlos en los diarios](../production-control/deferred-posting.md) | Administración de características:<br>*(Versión preliminar) Hacer que los bienes terminados estén disponibles físicamente antes de registrarlos en los diarios* |
| Gestión de almacenes | [Busque datos relevantes dentro de la aplicación móvil del almacén](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/look-up-relevant-data-within-warehouse-mobile-app) | [Consultar datos mediante los desvíos de la aplicación móvil Warehouse Management](../warehousing/warehouse-app-data-inquiry.md) | Administración de características:<br>*Flujo de solicitudes de datos en la aplicación de Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Gestión de costes | Optimización del cálculo de precios pendientes de coproductos | Esta función soluciona un conflicto que a veces puede ocurrir cuando los precios de los coproductos se calculan mediante el uso de varios subprocesos. Hace que el sistema se asegure de que el precio de cada coproducto se calcule una sola vez. El resultado de ese cálculo se usa luego como entrada para todos los demás cálculos. Si ya existe un precio pendiente, se utiliza ese precio. |
| Planificación maestra | Agrupar transacciones en la optimización de planificación | Esta función puede ayudar a reducir la cantidad de pedidos planificados que se generan para suministrar una sola línea de pedido de ventas cuando utiliza la Optimización de la planificación. Cuando esta función está activada, la Optimización de la planificación agrupará todas las transacciones de inventario de una línea de pedido en un solo requisito para la cantidad total. (Este comportamiento coincide con el comportamiento del motor de planificación incorporado). La oferta y la demanda se agrupan por separado. Por lo tanto, la función ayuda a reducir el volumen de transacciones cuando tiene transacciones divididas y cuando usa dimensiones (como números de lote o números de serie) que no son dimensiones de cobertura. |
| Adquisición y abastecimiento | Poner al proveedor en espera para pedidos de compra | Esta característica le permite poner a un proveedor en espera para órdenes de compra. Agrega un nuevo tipo de retención de *Orden de compra* que marca a un proveedor como en espera para órdenes de compra. No podrá crear nuevas órdenes de compra para los proveedores que están en espera para las órdenes de compra, pero aún podrá continuar con las facturas o pagos abiertos para esos proveedores. |
| Ventas y marketing | Calcular el importe neto de las líneas en importación | Esta característica le permite controlar si el sistema debe recalcular los totales de línea cuando importa datos a través de la entidad *Líneas de orden de venta*, *Líneas de cotización de ventas* o *Líneas de pedido de devolución* usando OData o doble escritura. Solo tiene efecto cuando también tiene políticas de evaluación de acuerdos comerciales que restringen los cambios en el campo **Importe neto** para líneas de orden de venta, líneas de oferta de venta y/o líneas de orden de devolución. Agrega una configuración llamada **Calcular el importe neto de la línea** a la página **Cuentas por cobrar > Configuración > Parámetros de cuentas por cobrar**. Cuando esta configuración se establece en *Sí*, el sistema siempre volverá a calcular los importes de las líneas cuando sea necesario (ignorando así cualquier política de evaluación de acuerdos comerciales para el importe neto de la línea). Cuando el ajuste se establece en *No*, el sistema nunca calculará automáticamente el importe neto de la línea, incluso cuando los cambios entrantes en el precio, la cantidad o el descuento de la línea impliquen que el importe neto de la línea se deba volver a calcular. Esta función está habilitada de manera predeterminada e inicialmente establece **Calcular el importe neto de la línea** en *Sí*. La configuración *No* coincide con el comportamiento del sistema anterior a la versión 10.0.23 y se proporciona principalmente para admitir escenarios de integración heredados.<br><br>Para más información, vea [Recalcular importes netos de línea al importar pedidos de venta, presupuestos y devoluciones](../sales-marketing/calc-line-net-amounts-import.md). |
| Ventas y marketing | Calcular totales de ventas mediante varios subprocesos | Esta función ayuda a mejorar el rendimiento al permitir que el sistema utilice el procesamiento paralelo cuando calcula los totales de ventas en un lote. La característica añade un nuevo campo **Número de hilos** al cuadro de diálogo **Calcular totales de ventas**. Si elige ejecutar el cálculo en un lote, puede usar este campo para establecer la cantidad máxima de subprocesos. Si establece el valor en *0* (cero) o *1*, se utilizará un solo subproceso. Los valores por encima de 1 habilitan los subprocesos múltiples. |
| Ventas y marketing | Actualizar precios y descuentos especificados manualmente para empresas vinculadas | Esta función agrega soporte para políticas de cambio manual para pedidos de empresas vinculadas. Incluye soporte para transferir políticas de cambio manual entre órdenes de compra y ventas de empresas vinculadas. Anteriormente, las políticas de cambio manual solo se admitían para pedidos que no eran de empresas vinculadas. Cuando esta función está habilitada, el sistema le dará la opción de actualizar precios y descuentos después de guardar los cambios en un pedido de empresas vinculadas. Esta opción le permite elegir si desea aplicar los nuevos detalles de precios y descuentos al pedido de empresas vinculadas o dejar el pedido sin cambios. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes artículos de Ayuda. Estos artículos no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en las secciones anteriores. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Artículos nuevos o actualizados |
|---|---|
| Planificación maestra, CTP | [Calcule las fechas de entrega de pedidos de ventas usando CTP](../master-planning/planning-optimization/calculate-delivery-dates-using-ctp.md) |
| Planificación maestra, DDMRP | [Descripción general de la Planificación de requisitos de materiales basada en la demanda](../master-planning/planning-optimization/ddmrp-overview.md)<br>[Activar la característica DDMRP para su sistema](../master-planning/planning-optimization/ddmrp-enable.md)<br>[Posicionamiento de inventario](../master-planning/planning-optimization/ddmrp-inventory-positioning.md)<br>[Perfil y niveles de búfer](../master-planning/planning-optimization/ddmrp-buffer-profile-and-levels.md)<br>[Planificación basada en la demanda](../master-planning/planning-optimization/ddmrp-planning.md)<br>[Ejecución visual y colaborativa](../master-planning/planning-optimization/ddmrp-visual-and-collaborative-execution.md) |
| Gestión de almacenes | [Empaquetar contenedores para envío](../warehousing/packing-containers.md)<br>[Trabajos de embalaje para empaquetar contenedores de salida y procesar envíos](../warehousing/packing-work.md) |

## <a name="feature-state-changes-in-this-release"></a>Cambios de estado de características en esta versión

La tabla siguiente enumera las características que se han convertido en obligatorias o activadas de forma predeterminada en la versión 10.0.29. Todas estas funciones se activarán automáticamente para su sistema tan pronto como actualice a la versión 10.0.29. Las funciones obligatorias no se pueden desactivar, pero las funciones que están activadas de forma predeterminada aún se pueden desactivar usando [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La tabla también enumera las funciones que anteriormente estaban en versión preliminar pública, pero que cambiaron para estar disponibles de forma general en la versión 10.0.29. Este cambio indica que las funciones ahora se recomiendan para su uso en entornos de producción. Estas funciones están desactivadas de forma predeterminada a menos que se indique lo contrario. Por lo tanto, debe utilizar [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitarlas si desea usarlas.

| Módulo | Nombre de característica | Nuevo estado de la característica |
| --- | --- | --- |
| Administración de activos | [Funcionalidad de administración de activos para la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Gestión de costes | [Cambiar la etiqueta de Cancelación en Cierre y ajuste a Invertir](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/change-terminology-inventory-closing-cancellation-inventory-closing-reverse) | Obligatoria |
| Gestión de costes | Limpiar versiones de gestión de costes transversales de detalles de cálculo de L. MAT | Obligatoria |
| Gestión de costes | [Comparar almacenamiento de precios de artículos](../cost-management/compare-item-price.md) | Obligatoria |
| Gestión de costes | [Nivel de cálculo de costes](../cost-management/cost-calculation-level.md) | Activado de forma predeterminada |
| Gestión de costes | Habilitar la configuración del número de lote definido por el usuario para la inversión de cierre de inventario | Activado de forma predeterminada |
| Gestión de costes | [Detalles del progreso del cierre de inventario](whats-new-scm-10-0-21.md) | Activado de forma predeterminada |
| Gestión de costes | [Almacenamiento de informes de valor de inventario](../cost-management/inventory-value-report-storage.md) | Obligatoria |
| Gestión de costes | Limpieza de datos del informe del valor del inventario | Obligatoria |
| Gestión de costes | Media móvil, secuencia de costes de reserva | Obligatoria |
| Gestión de costes | Mostrar registro de cierre de inventario en cuadrícula | Obligatoria |
| Gestión de costes | Mostrar los artículos con transacciones que no están liquidadas completamente en formato de resumen | Obligatoria |
| Gestión de inventario y almacenes | Permite valores de atributos de lote vacíos | Obligatoria |
| Gestión de inventario y almacenes | Incrementar automáticamente los números de línea de las líneas de pedido de transferencia de inventario | Obligatoria |
| Gestión de inventario y almacenes | Crear pedido de transferencia desde la línea de ventas | Obligatoria |
| Gestión de inventario y almacenes | Deshabilitar el campo de línea del diario de inventario en el flujo de trabajo | Obligatoria |
| Gestión de inventario y almacenes | Habilitar característica de advertencia de parámetros de administración de calidad de inventario | Obligatoria |
| Gestión de inventario y almacenes | (China) Excluir los costes de emisión y recepción físicas del coste promedio mensual | Activado de forma predeterminada |
| Gestión de inventario y almacenes | [Flujo de trabajo de aprobación el diario de inventario](../inventory/inventory-journal-workflow.md) | Obligatoria |
| Gestión de inventario y almacenes | [Almacenamiento de informe de inventario disponible](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/inventory-on-hand-report-storage) | Obligatoria |
| Gestión de inventario y almacenes | [Vistas guardadas para Gestión del inventario](saved-views-scm.md) | Obligatoria |
| Gestión de inventario y almacenes | Transferir cancelación de pedido | Obligatoria |
| Gestión de inventario y almacenes | Usar unidad de medida y la cantidad de unidad en diarios de inventario | Obligatoria |
| Gestión de inventario y almacenes | Desbloquear diario de inventario | Obligatoria |
| Fabricación | [Selección automática de materiales habilitados para almacén para las listas de selección con registro automático](whats-new-scm-10-0-23.md) | Disponibilidad general |
| Fabricación | Habilitar la visualización de dimensiones del inventario en la lista de materiales para operaciones de ruta de producción | Obligatoria |
| Fabricación | [Habilite esta opción para especificar números de lote y serie mientras se notifica como terminado desde el dispositivo de tarjeta de trabajo](../production-control/report-finished-job-device.md) | Activado de forma predeterminada |
| Fabricación | Mejora de la selección de la cantidad de peso capturado en producción | Activado de forma predeterminada |
| Fabricación | [Búsqueda de trabajos para la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Fabricación | [Integración de sistemas de ejecución de fabricación](../production-control/mes-integration.md) | Activado de forma predeterminada |
| Fabricación | [Vista "Mi día" de la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Activado de forma predeterminada |
| Fabricación | [Comprobación de disponibilidad de material a petición para pedidos de producción](whats-new-scm-10-0-24.md) | Activado de forma predeterminada |
| Fabricación | [Pasar por alto la reserva de producción predeterminada](../production-control/override-default-reservation-principle.md) | Obligatoria |
| Fabricación | [Registrar el consumo de material en la interfaz de ejecución de planta de producción (no WMS)](../production-control/production-floor-execution-configure.md) | Disponibilidad general |
| Fabricación | [Informe sobre artículos con peso capturado desde la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-configure.md) | Disponibilidad general |
| Fabricación | [Informe de coproductos y productos derivados de la interfaz de ejecución de planta de producción](../production-control/production-floor-execution-configure.md) | Activado de forma predeterminada |
| Fabricación | [Informe sobre los elementos de planificación en la interfaz de ejecución de la planta de producción](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | Activado de forma predeterminada |
| Fabricación | [Vistas guardadas para control de producción](saved-views-scm.md) | Obligatoria |
| Fabricación | [Mostrar los números de serie completa, lote y matrícula de entidad de almacén en la interfaz de ejecución de planta de producción](../production-control/production-floor-execution-configure.md) | Obligatoria |
| Fabricación | [Validar la caducidad de las materias primas frente a la fecha de consumo planificada](whats-new-scm-10-0-23.md) | Activado de forma predeterminada |
| Planificación maestra | [Puesta en firme automática para la Optimización de la planificación](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoria |
| Planificación maestra | [Consolidación y puesta en firme por lotes de pedidos de lote masivos y empaquetados planificados](whats-new-scm-10-0-20.md) | Activado de forma predeterminada |
| Planificación maestra | [Incluir artículos con disponibilidad al habilitar filtros de procesamiento previo](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/master-planning-include-items-on-hand-when-pre-processing-filters-are-enabled) | Activado de forma predeterminada |
| Planificación maestra | [Programación de capacidad infinita para Optimización de planificación](../master-planning/planning-optimization/infinite-capacity-planning.md) | Activado de forma predeterminada |
| Planificación maestra | [Márgenes de Optimización de planificación](../master-planning/planning-optimization/safety-margins.md) | Obligatoria |
| Planificación maestra | [Días negativos para Optimización de planificación](../master-planning/planning-optimization/delay-tolerance.md) | Obligatoria |
| Planificación maestra | [Autorización paralela de previsión de la demanda ajustada](whats-new-scm-10-0-20.md) | Obligatoria |
| Planificación maestra | [Puesta en firme de pedido planificado con filtrado](../master-planning/planning-optimization/planned-order-firming.md) | Obligatoria |
| Planificación maestra | [Pedidos de producción planificados para la optimización de la planificación](../master-planning/planning-optimization/production-planning.md) | Obligatoria |
| Planificación maestra | [Acuerdos comerciales de compra para la optimización de la planificación](../master-planning/planning-optimization/purchase-trade-agreement.md) | Obligatoria |
| Planificación maestra | [Vistas guardadas para pedidos planificados](saved-views-scm.md) | Obligatoria |
| Adquisición y abastecimiento | Carga los importes De y A en los pedidos de compra | Obligatoria |
| Adquisición y abastecimiento | Deshabilitar el botón Restablecer de la distribución de la solicitud de compra | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Habilitar el restablecimiento de los flujos de trabajo relacionados con la compra](whats-new-scm-10-0-20.md) | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Limitar el número de líneas de pedido de compra por tarea por lotes](whats-new-scm-10-0-27.md) | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Combinar las dimensiones financieras del proveedor con la dimensión financiera del vínculo de dimensión activo en el pedido de compra](whats-new-scm-10-0-25.md) | Obligatoria |
| Adquisición y abastecimiento | [Registrar cantidades registradas de productos en existencias y restos de productos sin existencias para recepciones y facturas de proveedor](whats-new-scm-10-0-26.md) | Disponibilidad general |
| Adquisición y abastecimiento | [Evitar el consumo excesivo de reservas de presupuesto general cuando hay varias solicitudes de compra en el flujo de trabajo](whats-new-scm-10-0-21.md) | Activado de forma predeterminada |
| Adquisición y abastecimiento | [Parte responsable del acuerdo de compra](../procurement/purchase-agreements.md) | Obligatoria |
| Adquisición y abastecimiento | [Vistas guardadas para pedidos de compra](saved-views-scm.md) | Obligatoria |
| Gestión de información de productos | Preprocesamiento de informe de lista de materiales para evitar el tiempo de espera | Obligatoria |
| Gestión de información de productos | Dimensiones financieras predeterminadas por separado cuando se usan plantillas de artículos | Obligatoria |
| Gestión de información de productos | Habilitar grupos de dimensiones de productos para plantillas de artículos | Obligatoria |
| Gestión de información de productos | Mejoras en entidades de artículo-código de barras | Obligatoria |
| Gestión de información de productos | Volver a generar nombres de variante del producto a partir de la nomenclatura | Obligatoria |
| Gestión de información de productos | [Vistas guardadas para productos emitidos](saved-views-scm.md) | Obligatoria |
| Gestión de información de productos | [Mejoras de la página de sugerencias de variantes](../pim/tasks/create-predefined-product-variants.md) | Obligatoria |
| Ventas y marketing | [Asignación de gastos en un pedido de ventas](/dynamics365-release-plan/2020wave1/dynamics365-supply-chain-management/miscellaneous-charges-enhancements) | Obligatoria |
| Ventas y marketing | Eliminar historial de actualización de pedido de ventas | Obligatoria |
| Ventas y marketing | [Eliminar historial de actualización de ventas según la antigüedad](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) | Obligatoria |
| Ventas y marketing | [Optimización de exportación de entidad de datos de persona de contacto](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | Obligatoria |
| Ventas y marketing | Copiar grupo de descuento total para nota de abono de ventas | Obligatoria |
| Ventas y marketing | [Habilitar la búsqueda para la introducción del documento de presupuesto de ventas y los campos de conclusiones del documento](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Obligatoria |
| Ventas y marketing | [Mejorar el rendimiento de los 100 mejores clientes](whats-new-scm-10-0-23.md) | Obligatoria |
| Ventas y marketing | Incluir registros en espera en tareas de limpieza del historial | Obligatoria |
| Ventas y marketing | Limitar el número de líneas de pedidos de venta por tarea por lotes | Activado de forma predeterminada |
| Ventas y marketing | [Limitar el número de pedidos de ventas que pueden seleccionarse para registro](whats-new-scm-10-0-21.md) | Obligatoria |
| Ventas y marketing | Recalcular el saldo estimado del cliente | Obligatoria |
| Ventas y marketing | [Registro de línea de pedido de devolución de ventas con precisión decimal con y sin peso capturado](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | Obligatoria |
| Ventas y marketing | [Vistas guardadas para ventas y marketing](saved-views-scm.md) | Obligatoria |
| Ventas y marketing | [Confirmación del pedido de ventas con un solo clic](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/single-click-sales-order-confirmation) | Obligatoria |
| Gestión del transporte | Permitir quitar la conciliación de los albaranes de flete de las líneas de factura de flete sin un diario de facturas de proveedor registrado | Activado de forma predeterminada |
| Gestión del transporte | [Habilitar la creación de un diario de facturas de proveedor al descartar un albarán de flete](whats-new-scm-10-0-20.md) | Activado de forma predeterminada |
| Gestión del transporte | [Envío de paquetes pequeños](../warehousing/small-parcel-shipping.md) | Obligatoria |
| Gestión del transporte | [Documento de certificación de origen de USMCA](../transportation/usmca-certification-of-origin.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Zona de ubicación adicional](../warehousing/additional-location-zones.md) | Obligatoria |
| Gestión de almacenes | [Cancelar trabajo](../warehousing/cancel-warehouse-work.md) | Obligatoria |
| Gestión de almacenes | [Consolidar envío](../warehousing/configure-shipment-consolidation-policies.md) | Obligatoria |
| Gestión de almacenes | [Crear y procesar pedidos de transferencia desde la aplicación de almacén](../warehousing/create-transfer-order-from-warehouse-app.md) | Obligatoria |
| Gestión de almacenes | Plantillas de tránsito directo con directivas de ubicación | Activado de forma predeterminada |
| Gestión de almacenes | [Desacoplar el trabajo de ubicación de los avisos de envío por adelantado](whats-new-scm-10-0-21.md) | Obligatoria |
| Gestión de almacenes | [Operaciones de colocación diferidas](../warehousing/deferred-processing-manual-inventory-movement.md) | Obligatoria |
| Gestión de almacenes | Colocación diferida: contenedor | Activado de forma predeterminada |
| Gestión de almacenes | Procesamiento put diferido: habilitar para la característica de plantilla de auditoría con el evento de desencadenado establecido en Anterior | Obligatoria |
| Gestión de almacenes | [Deshabilitar las recepciones esperadas de pedidos de calidad que muestrean el inventario bloqueado](../inventory/inventory-blocking.md) | Activado de forma predeterminada |
| Gestión de almacenes | Habilitar la validación rápida para dispositivos móviles de almacén | Obligatoria |
| Gestión de almacenes | [Analizador mejorado para códigos de barras GS1](../warehousing/gs1-barcodes.md) | Disponibilidad general |
| Gestión de almacenes | [Reserva flexible de matrícula de entidad de almacén comprometida de pedido](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obligatoria |
| Gestión de almacenes | [Reserva flexible de la dimensión de nivel de almacén](../warehousing/flexible-warehouse-level-dimension-reservation.md) | Obligatoria |
| Gestión de almacenes | [Uso de la ubicación de consolidación de artículos](../warehousing/item-consolidation-location-utilization.md) | Activado de forma predeterminada |
| Gestión de almacenes | Historial de recepción de matrículas de entidad de almacén | Activado de forma predeterminada |
| Gestión de almacenes | [Consolidación de envíos manual](../warehousing/consolidate-shipments-manual-workbench.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Servicio de selección manual de línea de transferencia para administración o usuarios de confianza similares](whats-new-scm-10-0-28.md) | Disponibilidad general |
| Gestión de almacenes | [Interfaz de equipo de gestión de material](../warehousing/mhax.md) | Obligatoria |
| Gestión de almacenes | [Nuevas páginas de área de trabajo de planificación de la carga](whats-new-scm-10-0-24.md) | Disponibilidad general |
| Gestión de almacenes | [Visualización de carga de trabajo de salida](../warehousing/outbound-workload-visualization.md) | Obligatoria |
| Gestión de almacenes | [Tránsito directo planificado](../warehousing/planned-cross-docking.md) | Obligatoria |
| Gestión de almacenes | [Procesar eventos de la aplicación de almacén](../warehousing/warehouse-app-events.md) | Obligatoria |
| Gestión de almacenes | Mejora de la consulta para la plantilla de trabajo Ubicación de coproducto y producto derivado | Obligatoria |
| Gestión de almacenes | [Redondear cantidades por debajo a la unidad de ventas más cercana durante la liberación al almacén](whats-new-scm-10-0-19.md) | Obligatoria |
| Gestión de almacenes | [Vista guardada para el área de trabajo de planificación de la carga](saved-views-scm.md) | Obligatoria |
| Gestión de almacenes | [Vista guardada para la página de detalles del trabajo](saved-views-scm.md) | Obligatoria |
| Gestión de almacenes | [Vista guardada para procesamiento de oleadas](saved-views-scm.md) | Obligatoria |
| Gestión de almacenes | [Vistas guardadas para procesamiento de carga](saved-views-scm.md) | Obligatoria |
| Gestión de almacenes | [Vistas guardadas para procesamiento de envíos](saved-views-scm.md) | Obligatoria |
| Gestión de almacenes | [Digitalizar códigos de barras de GS1](../warehousing/gs1-barcodes.md) | Disponibilidad general |
| Gestión de almacenes | Detalles de etiqueta de oleada de envío | Obligatoria |
| Gestión de almacenes | [Asignar unidades mixtas](whats-new-scm-10-0-21.md) | Obligatoria |
| Gestión de almacenes | [Use una API más rápida para el cierre o la reapertura de contenedores en la estación de embalaje](whats-new-scm-10-0-21.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Validar plantillas seleccionadas para los trabajos de reabastecimiento](whats-new-scm-10-0-20.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Campos promocionados de aplicación de almacén](../warehousing/warehouse-app-promoted-fields.md) | Obligatoria |
| Gestión de almacenes | [Instrucciones detalladas de la aplicación de almacén](../warehousing/mobile-app-titles-instructions.md) | Obligatoria |
| Gestión de almacenes | [Estado de ubicación de almacén](../warehousing/warehouse-location-status.md) | Obligatoria |
| Gestión de almacenes | [Desvíos de la aplicación Warehouse Management](../warehousing/warehouse-app-detours.md) | Activado de forma predeterminada |
| Gestión de almacenes | [Detalles del trabajo por lotes de oleada](../warehousing/wave-processing.md) | Obligatoria |
| Gestión de almacenes | [Notificaciones de ejecución de lanzamientos](../warehousing/wave-execution-notifications.md) | Obligatoria |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.29 incluye Platform updates. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.29 de aplicaciones de Finanzas y Operaciones (junio de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). <!--KFM: Confirm link -->

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.29, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022](/dynamics365-release-plan/2022wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
