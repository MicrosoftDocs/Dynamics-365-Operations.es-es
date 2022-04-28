---
title: Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.23 (enero de 2022)
description: En este tema se describen las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management 10.0.23.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 876f5a5f8ebf77a65ba3aa6271a2957b7dc2cb96
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570489"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.23 (enero de 2022)

[!include [banner](../includes/banner.md)]

En este tema se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.23. Esta versión tiene el número de compilación 10.0.1037 y está disponible de la siguiente manera:

- **Versión preliminar:** octubre de 2021
- **Disponibilidad general de la versión (actualización automática):** diciembre de 2021
- **Disponibilidad general de la versión (actualización automática):** enero de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. La columna *Característica* proporciona enlaces al [plan de lanzamiento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), donde puede ver las fechas de lanzamiento oficiales de cada característica. La columna *Más información* proporciona más detalles y/o vínculos a la documentación relacionada. Para determinar cómo activar una función, consulte la columna *Habilitado por*. Para obtener más información acerca de cómo usar la la administración de características, consulte [Visión general de la Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Puede que haya actualizaciones de este tema para incluir características que se incluyeron en la compilación después de la publicación inicial del tema.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Libreta de direcciones global | Definir un estado/provincia predeterminado para cada país o región en la configuración de direcciones | Ahora puede definir un estado/provincia predeterminado para cada país o región en la configuración de direcciones para la libreta de direcciones global. Cuando se establece un estado/provincia predeterminado, será el valor predeterminado introducido en los campos de estado/provincia cuando cree un nuevo registro de condado o ciudad para ese país o región. Consulte también [Configuración de dirección](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Habilitado por defecto. |
| Inventario&nbsp;y&nbsp;logística | [Pausar tareas en la aplicación móvil Warehouse Management](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Configurar desvíos para pasos en los elementos del menú del dispositivo móvil](../warehousing/warehouse-app-detours.md) | Administración de características (*Desvíos de aplicaciones de Warehouse Management*) |
| Inventario&nbsp;y&nbsp;logística | [Campos promocionados de aplicación de almacén](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Configurar campos promocionados para pasos en el dispositivo móvil](../warehousing/warehouse-app-promoted-fields.md)| Administración de características (*Campos promocionados de la aplicación Warehouse*) |
| Fabricación | [Integración de sistemas de ejecución de fabricación](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Integrar con sistemas de ejecución de fabricación de terceros](../production-control/mes-integration.md) | Gestión de funciones (*Integración del sistema de ejecución de fabricación*) |
| Fabricación | [Informe de coproductos y productos derivados de la interfaz de ejecución de planta de producción](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [Cómo los trabajadores usan la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-use.md) | Administración de características (*Informe de coproductos y productos derivados de la interfaz de ejecución de planta de producción*) |
| Planificada | [Compatibilidad de Optimización de planificación para planificación basada en prioridades](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Planificación basada en prioridades](../master-planning/planning-optimization/priority-based-planning.md) | Gestión de funciones (*Compatibilidad de MRP basada en prioridad para la Optimización de planificación*) |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características nuevas de esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas características, debe hacerlo en [administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), donde se enumeran utilizando los nombres que se muestran en la columna *Nombre de la característica en la administración de características* de la siguiente tabla.

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Administración de activos | Cuentas de contrapartida para gastos en diarios de órdenes de trabajo | Esta característica le permite especificar una cuenta de contrapartida para cada gasto enumerado en un diario de orden de trabajo. Por lo general, puede asociar una cuenta de proveedor con cada gasto, pero también se admiten otros tipos de cuentas. Agrega dos nuevas columnas (**Tipo de cuenta de contrapartida** y **Cuenta de contrapartida**) a la ficha desplegable **Gasto** en la página **Diario de órdenes de trabajo**.|
| Gestión de costes | Crear asientos relacionados para revalorizaciones de redondeo de coste estándar | <p>Cuando se realiza una contabilización financiera de inventario (como una factura de orden de venta o una transacción de inventario), esta función hace que el sistema cree un comprobante separado para cualquier revalorización de redondeo de costos estándar relacionada y lo adjunte al comprobante de contabilización financiera como comprobante relacionado.</p><p>Sin esta función, el sistema registra las revalorizaciones de redondeo de costes estándar en la misma contabilización de comprobantes. Ese comportamiento a veces puede causar información de fecha conflictiva, porque las revaluaciones usan la fecha de la sesión o del sistema, mientras que las contabilizaciones financieras usan la fecha de contabilización.</p> |
| Gestión de inventario y almacenes | \[Rusia\] Registrar transacciones de inventario financieras Storno según el indicador de corrección del asiento financiero de los pedidos de ventas | Esta característica afecta la funcionalidad de correcciones de notas de crédito para Rusia. Permite el registro de transacciones de inventario para facturas de ventas de acuerdo con la opción de corrección en el libro de contabilidad. Cuando esta característica está habilitada, no hay más discrepancias entre la marca **Corrección** en el comprobante financiero de la transacción de inventario y la marca **Storno** en transacciones de inventario. |
| Gestión de inventario y almacenes | (Rusia) Ejecutar cálculo de informe de facturación de saldo de inventario por lotes | Para la traducción al ruso de Supply Chain Management, esta característica proporciona la posibilidad de ejecutar el informe de *facturación de saldo de inventario* por lotes, almacenarlo y ver los informes generados anteriormente. |
| Gestión de inventario y almacenes | (Rusia) Usar traducciones al idioma local en los formularios principales específicos del país o la región en Administración de inventario | Para la traducción al ruso de Supply Chain Management, esta característica permite el uso de traducciones rusas para nombres de productos/artículos y unidades de medida en las siguientes impresiones de inventario específicas de Rusia: Lista de recuento (INV-3), Lista de recuento (INV-5) y Lista de recuento (INV-6). |
| Planificación maestra | Azure Machine Learning Service para previsión de demanda | Esta característica permite que Azure Machine Learning Service genere pronósticos de demanda basados en datos históricos. Para obtener más información, consulte [Configuración de la previsión de demanda](../master-planning/demand-forecasting-setup.md). |
| Adquisición y abastecimiento | Eliminar historial de actualización de pedido de compra | Esta característica le permite eliminar registros históricos temporales relacionados con actualizaciones de órdenes de compra. Agrega un nuevo botón llamado **Eliminar historial de actualización de compra** al panel de acciones en la página **Todas las órdenes de compra**. De forma predeterminada, esta característica está habilitada. |
| Control de producción | (Versión preliminar) Selección automática de materiales habilitados para almacén para las listas de selección con registro automático | Esta característica permite seleccionar y resolver automáticamente dimensiones de inventario para diarios de lista de selección registrados automáticamente, derivados y de lista de selección previa. |
| Control de producción | Validar la caducidad de las materias primas frente a la fecha de consumo planificada | Esta característica cambia la forma en que se validan las fechas de vencimiento de los lotes al reservar un lote de materia prima para utilizarlo durante la producción. Cuando esta característica está habilitada, la fecha de vencimiento del lote se valida con la fecha de consumo planificado (la fecha de la materia prima), según lo establecido en la línea de lista de materiales de producción o en la línea de fórmula de orden de lote. Cuando esta característica está desactivada, la fecha de vencimiento del lote se valida con la fecha de entrega planificada de la producción o el pedido del lote (como anteriormente). |
| Ventas y marketing | Eliminar historial de actualización de ventas según la antigüedad | Esta función le permite establecer la antigüedad máxima de los registros que se deben mantener al ejecutar la tarea periódica **Limpieza del historial de actualización de ventas**. Se eliminarán los registros más antiguos. Esto es útil cuando configura la tarea para que se ejecute periódicamente porque el vencimiento siempre se calcula en relación con la fecha en que se ejecuta la tarea. Sin esta función, solo puede establecer una fecha específica para conservar los registros más antiguos. Para obtener más información, consulte [Programar la limpieza de datos del historial de ventas](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Ventas y marketing | Mejorar el rendimiento de los 100 mejores clientes | Esta característica mejora el rendimiento del informe de clientes **Los 100 mejores** ejecutando siempre el informe en todos los clientes (que es su uso previsto) en lugar de permitir consultas personalizadas. Cuando esta característica está habilitada, todas las configuraciones de **Registros a incluir** están deshabilitadas en el cuadro de diálogo del informe **Los 100 mejores**. |
| Gestión de almacenes | Compatibilidad de unidades de escalado para la liberación de pedidos salientes al almacén | Cuando esta característica está habilitada, los pedidos salientes se pueden liberar desde el centro directamente a la unidad de escalado, desde donde se van a cumplir los pedidos. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes temas de ayuda. Estos temas no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en la sección anterior. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Temas nuevos o actualizados |
|---|---|
| Administración de cambios de ingeniería | [Atributos de ingeniería y búsqueda de atributos de ingeniería](../engineering-change-management/engineering-attributes-and-search.md) ahora describe cómo funciona la ingeniería de herencia de atributos. |
| Planificación maestra | [Planificación maestra con previsiones de demanda](../master-planning/planning-optimization/demand-forecast.md) y [Previsión de las claves de reducción](../master-planning/reduction-keys.md) ahora proporcionan más información sobre cómo trabajar con claves de reducción. |
| Planificación maestra | [Cumplimiento de existencias de seguridad para los artículos](../master-planning/safety-stock-replenishment.md) ahora proporciona más información sobre el uso de claves mínimas/máximas. |
| Planificación maestra | [Previsiones de inventario](../master-planning/inventory-forecast.md) ahora proporciona más información sobre la asignación de previsiones. |
| Planificación maestra | [Programación de suministros](../master-planning/supply-schedule.md) |
| Gestión de almacenes | [Parámetros globales de dispositivos móviles](../warehousing/mobile-device-parameters.md) |
| Gestión de almacenes | [Anclaje](../warehousing/anchoring.md) |
| Ventas y marketing | El comercio de empresas vinculadas se describe ahora en detalle, comenzando con [Configurar el comercio de empresas vinculadas](../sales-marketing/intercompany-trade-set-up.md) y sus temas relacionados. |
| Administración de inventario | La documentación de visibilidad de inventario se ha ampliado y actualizado, comenzando con [Información general sobre el complemento de visibilidad de inventario](../inventory/inventory-visibility.md) y sus temas relacionados. |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.23 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.23 de aplicaciones de Finanzas y Operaciones (noviembre de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.23, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

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
