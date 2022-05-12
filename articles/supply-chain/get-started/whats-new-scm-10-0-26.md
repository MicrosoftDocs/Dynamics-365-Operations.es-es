---
title: Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.26 (mayo de 2022)
description: En este tema se describen las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management 10.0.26.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 0724045824f39f316c8b3dbb06a48eb6ca6dbef3
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625262"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Novedades y cambios en Dynamics 365 Supply Chain Management 10.0.26 (mayo de 2022)

[!include [banner](../includes/banner.md)]

En este tema se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión 10.0.26. Esta versión tiene el número de compilación 10.0.1192 y está disponible de la siguiente manera:

- **Vista previa de la versión:** marzo 2022
- **Disponibilidad general de la versión (actualización automática):** abril de 2022
- **Disponibilidad general de la versión (actualización automática):** mayo de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este tema para incluir características que se incluyeron en la compilación después de la publicación inicial del tema.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Inventario y logística | [Consulta de visibilidad de inventario disponible para admitir artículos avanzados de gestión de almacén](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Soporte de visibilidad de inventario para artículos WHS](../inventory/inventory-visibility-whs-support.md) | Administración de características:<br>*Habilitar artículos de almacén en Visibilidad de inventario* |
| Inventario y logística | [Disponible para prometer para el complemento de visibilidad de inventario](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [Planes de cambio de visibilidad de inventario disponible y neto no comprometido](../inventory/inventory-visibility-available-to-promise.md) | Habilitado por configuración de servicio |
| Fabricación | [Peso capturado de artículos para la interfaz de ejecución de la planta de producción](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [Cómo los trabajadores usan la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-use.md) | Administración de características:<br>*(Versión preliminar) Informe sobre artículos con peso capturado desde la interfaz de ejecución de la planta de producción* |
| Fabricación | Pestaña Mis trabajos en la interfaz de ejecución de la planta de producción <!-- KFM: Add link to release plan when available --> | [Cómo los trabajadores usan la interfaz de ejecución de la planta de producción](../production-control/production-floor-execution-use.md) | Administración de características:<br>*Pestaña Mis trabajos en la interfaz de ejecución de la planta de producción* |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [Gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Adquisición y abastecimiento | Registrar cantidades registradas de productos en existencias y restos de productos sin existencias para recepciones y facturas de proveedor | Esta característica cambia la forma en que se contabilizan las cantidades de productos no almacenados (como servicios) al procesar facturas de proveedores y envíos entrantes contra órdenes de compra. La característica modifica el comportamiento de la opción *Cantidad registrada y servicios* de cantidad para contabilizar recibos y facturas de proveedor cambiándola para que coincida con el comportamiento de la opción *Cantidad registrada y productos no almacenados* ya proporcionada al contabilizar cantidades para albaranes de ventas.<br><br>Cuando contabiliza un recibo de producto o una factura de proveedor utilizando la opción *Cantidad registrada y servicios* de cantidad, el sistema contabiliza la cantidad registrada de productos almacenados y contabiliza la cantidad restante de productos no almacenados (incluidos tanto los servicios como los que no son servicios). Sin esta función, el sistema sigue registrando la cantidad registrada de productos almacenados (incluidos los servicios configurados como artículos almacenados), pero siempre registra la cantidad total ordenada de productos de servicio no almacenados (e ignora los productos no almacenados que no son del tipo *Servicio*). |
| Adquisición y abastecimiento | Sincronizar las dimensiones de seguimiento en líneas de pedidos de compra y ventas de empresas vinculadas | Esta característica le permite controlar si las dimensiones de seguimiento del número de serie y de lote se sincronizan en las líneas de órdenes de compra y ventas de empresas vinculadas. Agrega nuevas configuraciones a las pestañas **Directivas de pedido de compra** y **Directivas de pedido de venta** de la página de configuración para clientes y proveedores **Empresas vinculadas**. También actualiza los nombres de algunas configuraciones cercanas relacionadas para mayor claridad.<br><br>Si utiliza gestión avanzada de almacenes (WMS), tenga en cuenta que esta función solo sincronizará el número de serie y lote cuando estas dimensiones estén por encima de la ubicación en la jerarquía de reservas de destino. |
| Gestión de información de productos | Limpiar valores de atributo del producto | Esta característica agrega una tarea periódica denominada **Limpiar valores de atributo del producto**, que limpia los registros de valores de atributos de productos que ya no están asociados a ningún producto a través de una categoría de producto. |
| Gestión de inventario y almacenes | (Rusia) Evitar discrepancias al emitir GTD para pedidos de compra que incluyan artículos habilitados para WMS | Esta función solo está disponible la localización en ruso. Evita las discrepancias que se producen al emitir números de declaración de aduanas (GTD) rusos para pedidos de compra de importación que incluyen artículos habilitados para almacenamiento avanzado (WMS). El proceso de emisión de GTD cambia algunos valores de dimensión de inventario en las transacciones de inventario relacionadas para las facturas incluidas en el diario personalizado, lo que genera discrepancias entre los registros de trabajo del pedido de compra y las transacciones de inventario de la compra. Cuando esta función está habilitada, el proceso de emisión de GTD genera un trabajo de ajuste que elimina dichas discrepancias. |
| Gestión de almacenes | Analizador mejorado para códigos de barras GS1 | Esta característica agrega un analizador mejorado para datos de símbolos GS1. El nuevo analizador implementa el algoritmo de especificación general GS1 para analizar los símbolos GS1 y proporciona una validación de datos más sólida. Para obtener más información consulte [Escanear códigos de barras GS1](../warehousing/gs1-barcodes.md). |
| Gestión de almacenes | Nuevas páginas de área de trabajo de planificación de la carga | Agrega dos nuevas páginas de área de trabajo de planificación de la carga: **Área de trabajo de planificación de la carga entrante** y **Área de trabajo de planificación de la carga saliente**. |
| Gestión de almacenes | Aplicación Warehouse Management: GTD en blanco | Esta función solo está disponible la localización en ruso. Permite a los trabajadores que utilizan la Warehouse Management mobile app dejar en blanco los números de declaración de aduanas (GTD) rusos cuando sea necesario. Si la dimensión de seguimiento de GTD está configurada para permitir valores en blanco, el sistema aceptará valores en blanco para GTD para operaciones de inventario siempre que haya inventario disponible. |

## <a name="new-and-updated-documentation-resources"></a>Recursos de documentación nuevos y actualizados

Recientemente hemos agregado o actualizado significativamente los siguientes temas de ayuda. Estos temas no están necesariamente relacionados con las nuevas funciones que se agregaron para esta versión, como se enumeran en las secciones anteriores. Sin embargo, pueden ayudarlo a aprovechar al máximo las funciones existentes.

| Área de características | Temas nuevos o actualizados |
|---|---|
| Gestión de costes | Se agregaron ejemplos y diagramas actualizados a cada uno de los siguientes temas:<ul><li>[FIFO con valor físico y marcado](../cost-management/fifo-physical-value-marking.md)</li><li>[LIFO con valor físico y marcado](../cost-management/lifo-physical-value-marking.md)</li><li>[Fecha LIFO con valor físico y marcado](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Ejecución del precio de coste promedio móvil](../cost-management/running-average-cost-price.md)</li><li>[Media ponderada con valor físico y marcado](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |
| Adquisición y abastecimiento | [Discrepancias en los datos de la línea de pedido de compra](../troubleshooting/procurement/purchase-order-line-data-issues.md) |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.26 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.26 de aplicaciones de Finanzas y Operaciones (mayo de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md).

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.26, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022](/dynamics365-release-plan/2022wave1/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el tema [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
