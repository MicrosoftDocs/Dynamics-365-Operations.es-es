---
title: Novedades y cambios en Dynamics 365 Supply Chain Management (10.0.21 de octubre de 2021)
description: Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 91462cc589be6170418f7f78267feea5e25c037d
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "9123790"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Novedades y cambios en Dynamics 365 Supply Chain Management (10.0.21 de octubre de 2021)

[!include [banner](../includes/banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.21. Esta versión tiene el número de compilación 10.0.960 y está disponible de la siguiente manera:

- **Versión preliminar de la versión:** agosto de 2021
- **Disponibilidad general de la versión (actualización automática):** septiembre de 2021
- **Disponibilidad general de la versión (actualización automática):** octubre de 2021

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. La columna *Característica* proporciona enlaces al [plan de lanzamiento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), donde puede ver las fechas de lanzamiento oficiales de cada característica. La columna *Más información* proporciona más detalles y/o vínculos a la documentación relacionada.

La mayoría de estas características deben habilitarse mediante la [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para poder usarse.

| Área de características | Característica | Más información |
|---|---|---|
| Inventario&nbsp;y&nbsp;logística | [Complemento de contabilidad de inventario global para Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Página principal de Contabilidad de inventario global](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Inventario&nbsp;y&nbsp;logística | [Contabilizar ajustes disponibles utilizando códigos de motivo configurables conectados a cuentas de contrapartida](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Códigos de motivo de recuento de inventario](../warehousing/reason-codes-for-counting-journals.md) |
| Inventario&nbsp;y&nbsp;logística | [Directiva de exportación de datos de referencia del presupuesto de ventas](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Elija si los cambios en los datos referenciados por los presupuestos harán que esos presupuestos (o líneas) se incluyan en la siguiente exportación incremental. Sus exportaciones incrementales se ejecutarán más rápidamente si decide no incluir dichos presupuestos o líneas.<br><br>Esta función agrega una configuración llamada **Omitir los datos de referencia de presupuestos de ventas durante el seguimiento de cambios** en la página **Parámetros de cliente**. |
| Inventario&nbsp;y&nbsp;logística | [Ofertas selladas](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [Oferta cerrada para solicitudes de presupuesto](../procurement/sealed-bidding.md) |
| Inventario&nbsp;y&nbsp;logística | [Reserva flexible para el complemento de Visibilidad de inventario](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Reservas de visibilidad de inventario](../inventory/inventory-visibility-reservations.md) |
| Inventario&nbsp;y&nbsp;logística | [Mejoras en la deducción y en la ponderación para la gestión de las devoluciones](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Gestionar las deducciones utilizando el banco de trabajo de deducciones](../rebate-management/deduction-workbench.md )<br><br>[Procesar, revisar y registrar devoluciones](../rebate-management/process-review-post.md)<br><br>[Acuerdos de gestión de devoluciones](../rebate-management/rebate-management-deals.md) |
| Inventario&nbsp;y&nbsp;logística | [Instrucciones detalladas de la aplicación de almacén](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Inventario&nbsp;y&nbsp;logística | [Descansos laborales y actualizaciones de seguimiento para el coste en destino](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Seguimiento de actualización para colocación](../landed-cost/update-tracking-putaway.md )<br><br>[Procesamiento de mercancía en tránsito](../landed-cost/in-transit-processing.md) |
| Planificación maestra | [Días negativos para Optimización de planificación](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Tolerancia al retraso (días negativos)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada uno de estos proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario). Si desea utilizar alguna de estas funciones, debe habilitarlas explícitamente en [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Característica&nbsp;nombre&nbsp;en característica&nbsp;administración | Más información |
|---|---|---|
| Gestión de costes | Detalles del progreso del cierre de inventario | Esta función de vista previa permite una vista detallada del progreso de cierre del inventario. |
| Adquisición y abastecimiento | Evitar el consumo excesivo de reservas de presupuesto general cuando hay varias solicitudes de compra en el flujo de trabajo | Esta función de vista previa mejora la verificación de errores cuando los usuarios envían y aprueban solicitudes de compra que exceden el saldo restante de una línea de reserva de presupuesto general. Esto ayuda a evitar el consumo excesivo de reservas presupuestarias generales cuando hay varias solicitudes de compra en el flujo de trabajo. |
| Control de producción | Mostrar los números de serie completa, lote y matrícula de entidad de almacén en la interfaz de ejecución de planta de producción | Esta función proporciona una experiencia mejorada para ver listas de números de serie, lote y matrícula de entidad de almacén en la interfaz de ejecución de la planta de producción. La pantalla cambia de una vista de tarjeta con un número limitado de caracteres a una vista de lista que proporciona suficiente espacio para mostrar los valores completos. La lista también ofrece la posibilidad de buscar números específicos. |
| Ventas y marketing | Limitar el número de pedidos de ventas que pueden seleccionarse para registro | Esta función le permite definir el número máximo de pedidos de ventas que se pueden seleccionar al registrar confirmaciones, listas de selección, albaranes y facturas desde la página de lista de pedidos de ventas. Se habilita automáticamente. La función agrega una configuración llamada **Número máximo de pedidos de ventas para registrar** en la página **Parámetros de clientes**. La nueva configuración tiene un valor predeterminado de *100*. La función ayuda a mejorar el rendimiento de la página de lista de pedidos de ventas cuando se selecciona una cantidad sustancial de pedidos de ventas. No tiene ningún impacto en el número de pedidos de ventas que se pueden procesar mediante una tarea periódica. |
| Gestión de almacenes | Desacoplar el trabajo de ubicación de los avisos de envío por adelantado | Esta función es necesaria para enviar y recibir avisos de envío anticipados (ASN) cuando está ejecutando una carga de trabajo de administración de almacén en una unidad de escalado (como parte de una topología híbrida distribuida). Agrega una nueva tabla de base de datos dedicada a almacenar información sobre el trabajo de almacenamiento. Anteriormente, esta información se almacenaba en tablas que también se usaban para los ASN. |
| Gestión de almacenes | Asignar unidades mixtas | Permite que el sistema coloque artículos en ubicaciones que incluyan unidades mixtas (como cajas y estuches). Para cada línea de plantilla de asignación de posiciones, esta función le permite elegir si la línea debe ubicar los artículos en ubicaciones de unidades mixtas o de unidades individuales. |
| Gestión de almacenes | Use una API más rápida para el cierre o la reapertura de contenedores en la estación de embalaje | Cuando esta función de vista previa está habilitada, las transacciones de inventario relacionadas con los contenedores se crean mediante un nuevo proceso liviano que mejora el rendimiento del cierre o reapertura de los contenedores durante el procesamiento manual de la estación de embalaje. |

## <a name="features-turned-on-by-default-in-this-release"></a>Las características se han activado de forma predeterminada en esta versión

La tabla siguiente enumera las características que se han activado de forma predeterminada en 10.0.21. La mayoría de las características que se han activado de forma automática se pueden desactivar en [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Nombre de característica | Habilitar fecha | Fecha de adición de característica | Estado de la característica | Módulo |
| :--- | :--- | :--- | :--- | :--- |
| Almacenamiento de informe de inventario disponible | 01/09/2021 | 01/04/2020 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Transferir cancelación de pedido | 01/09/2021 | 13/07/2020 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Desbloquear diario de inventario | 01/09/2021 | 17/08/2020 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Vistas guardadas para Gestión del inventario | 01/09/2021 | 30/9/2020 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Navegación hasta la versión de L.M. desde las líneas de L.M. | 01/09/2021 | 11/11/2019 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Usar unidad de medida y la cantidad de unidad en diarios de inventario | 01/09/2021 | 11/11/2019 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Permite valores de atributos de lote vacíos | 01/09/2021 | 11/11/2019 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Incrementar automáticamente los números de línea de las líneas de pedido de transferencia de inventario | 01/09/2021 | 11/10/2019 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Flujo de trabajo de aprobación el diario de inventario | 01/09/2021 | 06/01/2020 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Habilitar característica de advertencia de parámetros de administración de calidad de inventario | 01/09/2021 | 07/10/2019 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Crear pedido de transferencia desde la línea de ventas | 01/09/2021 | 31/08/2019 | Activado de forma predeterminada | Gestión de inventario y almacenes |
| Selección de modelo de previsión según los detalles de la previsión de la demanda | 01/09/2021 | 11/10/2019 | Activado de forma predeterminada | Planificación maestra |
| Visualización del progreso de la planificación maestra | 01/09/2021 | 07/10/2019 | Activado de forma predeterminada | Planificación maestra |
| Puesta en firme automática para la Optimización de la planificación | 01/09/2021 | 11/10/2019 | Activado de forma predeterminada | Planificación maestra |
| Puesta en firme en paralelo de pedidos planificados | 01/09/2021 | 31/08/2019 | Activado de forma predeterminada | Planificación maestra |
| Mensaje de envío de la oferta realizado correctamente | 01/09/2021 | 15/05/2019 | Activado de forma predeterminada | Adquisición y abastecimiento |
| Vínculo de referencia de solicitud de presupuesto agregado al pedido de compra | 01/09/2021 | 31/08/2019 | Activado de forma predeterminada | Adquisición y abastecimiento |
| Capacidad de confirmar los pedidos de compra aceptados de la colaboración de proveedor en el lote | 01/09/2021 | 10/09/2019 | Activado de forma predeterminada | Adquisición y abastecimiento |
| Mejoras de cXML de compra | 01/09/2021 | 11/11/2019 | Activado de forma predeterminada | Adquisición y abastecimiento |
| Mostrar el vínculo &quot;Abrir solicitudes publicadas para presupuestos&quot; como icono | 01/09/2021 | 30/9/2020 | Activado de forma predeterminada | Adquisición y abastecimiento |
| Preguntas y respuestas sobre solicitudes de presupuestos | 01/09/2021 | 19/02/2020 | Activado de forma predeterminada | Adquisición y abastecimiento |
| Documentación de envío e información de producto de materiales peligrosos | 01/09/2021 | 14/06/2020 | Activado de forma predeterminada | Gestión de información de productos |
| Validación estricta en las cantidades de pedido predeterminadas | 01/09/2021 | 24/06/2020 | Activado de forma predeterminada | Gestión de información de productos |
| Característica de gestión del país de origen | 01/09/2021 | 13/07/2020 | Activado de forma predeterminada | Gestión de información de productos |
| Vistas guardadas para productos emitidos | 01/09/2021 | 30/9/2020 | Activado de forma predeterminada | Gestión de información de productos |
| Mejoras en los cuadros de diálogo Aprobar y Transferir trabajos | 01/09/2021 | 11/10/2019 | Activado de forma predeterminada | Control de producción |
| Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo | 01/09/2021 | 31/08/2019 | Activado de forma predeterminada | Control de producción |
| Se ha agregado un nuevo botón Detener descanso a la página Terminal de tarjeta de trabajo | 01/09/2021 | 19/02/2020 | Activado de forma predeterminada | Control de producción |
| Habilite la recepción parcial de los productos subcontratados y solucione un problema con el cálculo de rechazo para las líneas de L.M. del tipo Proveedor. | 01/09/2021 | 11/11/2019 | Activado de forma predeterminada | Control de producción |
| Vistas guardadas para el control de producción | 01/09/2021 | 17/08/2020 | Activado de forma predeterminada | Control de producción |
| Dynamics 365 Guides para fabricación | 01/09/2021 | 13/07/2020 | Activado de forma predeterminada | Control de producción |
| Ejecución de la planta de producción | 01/09/2021 | 30/9/2020 | Activado de forma predeterminada | Control de producción |
| Función para bloquear un dispositivo de tarjeta de trabajo y un terminal de tarjetas de trabajo para que se puedan desinfectar | 01/09/2021 | 10/05/2020 | Activado de forma predeterminada | Control de producción |
| Asignación de gastos en un pedido de ventas | 01/09/2021 | 30/9/2020 | Activado de forma predeterminada | Ventas y marketing |
| Limitar el número de pedidos de ventas que pueden seleccionarse para registro | 01/09/2021 | 01/09/2021 | Activado de forma predeterminada | Ventas y marketing |
| Eliminar historial de actualización de pedido de ventas | 01/09/2021 | 01/09/2021 | Activado de forma predeterminada | Ventas y marketing |
| Cambiar la secuencia numérica para el trabajo de recuento cíclico | 01/09/2021 | 07/10/2019 | Activado de forma predeterminada | Gestión de almacenes |
| Reabastecimiento de demanda de oleada basada en tareas | 01/09/2021 | 07/10/2019 | Obligatoria | Gestión de almacenes |
| Ocultar el campo Valor total en las páginas &quot;Todas las cargas&quot; y &quot;Detalles de la carga&quot; | 01/09/2021 | 07/10/2019 | Activado de forma predeterminada | Gestión de almacenes |
| Impresión de etiquetas de oleadas | 01/09/2021 | 19/02/2020 | Obligatoria | Gestión de almacenes |
| Asociar transacciones de inventario de pedido de compra a carga | 01/09/2021 | 06/01/2020 | Obligatoria | Gestión de almacenes |
| Diseños de etiquetas de matrícula de entidad de almacén mejorados | 01/09/2021 | 19/02/2020 | Activado de forma predeterminada | Gestión de almacenes |
| Bloqueo de trabajo en toda la organización | 01/09/2021 | 19/02/2020 | Obligatoria | Gestión de almacenes |
| Detalles de línea de trabajo | 01/09/2021 | 11/10/2019 | Activado de forma predeterminada | Gestión de almacenes |
| Hacer editable el campo de estado de inventario de movimiento de inventario de dispositivo móvil | 01/09/2021 | 16/10/2019 | Activado de forma predeterminada | Gestión de almacenes |
| Confirmar envíos salientes de trabajos por lotes | 01/09/2021 | 13/07/2020 | Activado de forma predeterminada | Gestión de almacenes |
| Controlar si se mostrará una página de resumen de recepción en los dispositivos móviles | 01/09/2021 | 01/04/2020 | Activado de forma predeterminada | Gestión de almacenes |
| Solicitar la resolución de nombres de &#39;Ubicación / N.º licencia&#39; ambiguos | 01/09/2021 | 01/04/2020 | Activado de forma predeterminada | Gestión de almacenes |
| Capturar variantes del producto y dimensiones de seguimiento en la aplicación de gestión de almacenes durante la recepción de artículos de carga | 01/09/2021 | 10/05/2020 | Activado de forma predeterminada | Gestión de almacenes |
| No permitir la creación de cargas, que no cumplan los requisitos de la plantilla de planificación de carga de oleada. | 01/09/2021 | 17/08/2020 | Activado de forma predeterminada | Gestión de almacenes |
| Evaluar todas las acciones para directivas de ubicación de SKU múltiples | 01/09/2021 | 30/9/2020 | Activado de forma predeterminada | Gestión de almacenes |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes artículos de ayuda. No están necesariamente relacionadas con las nuevas funciones agregadas para esta versión, como se enumeran en la sección anterior, pero pueden ayudarlo a aprovechar más las funciones existentes.

| Área de características | Artículos nuevos o actualizados |
|---|---|
| Planificación maestra | [Previsiones de inventario](../master-planning/inventory-forecast.md) |
| Planificación maestra | [Parámetros no utilizados por Optimización de planificación](../master-planning/planning-optimization/not-used-parameters.md) |
| Planificación maestra | [Métodos de reabastecimiento y modificación de cantidades](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Planificación maestra | [Programación con capacidad infinita](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Planificación maestra | [Ver historial del plan y registros de planificación](../master-planning/planning-optimization/plan-history-logs.md) |
| Gestión de almacenes | [Estrategias de embalaje de contenedores](../warehousing/container-packing-strategy-overview.md) |
| Gestión de almacenes | [Escenarios de ejemplo de recuento cíclico](../warehousing/cycle-counting-scenarios.md) |
| Gestión de almacenes | [Importar ASN entrantes a través de la entidad de datos V3](../warehousing/import-asn-data-entity.md) |
| Gestión de almacenes | [Selección en exceso de pedidos de ventas y pedidos de transferencia](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Gestión de almacenes | [Programar la impresión de etiquetas de oleada durante la oleada](../warehousing/configure-task-based-wave-label-printing.md) |
| Gestión de almacenes | [Novedades o cambios en la aplicación móvil Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform updates para aplicaciones de finanzas y operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.21 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.21 de aplicaciones de finanzas y operaciones (octubre de 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.21, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2021

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2021](/dynamics365-release-plan/2021wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

