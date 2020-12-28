---
title: Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube
description: Este tema proporciona información sobre la función que permite que las unidades de báscula ejecuten procesos seleccionados de la carga de trabajo de administración de su almacén.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516870"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> No todas las funciones comerciales son totalmente compatibles en la versión preliminar pública cuando se utilizan unidades de escala de carga de trabajo. Asegúrese de utilizar solo los procesos que este tema describe explícitamente como compatibles.

## <a name="warehouse-execution-on-scale-units"></a>Ejecución de almacén en unidades de escala

Esta característica permite que las unidades de báscula ejecuten procesos seleccionados de las capacidades de administración del almacén. Las unidades de escala en la nube ejecutan sus cargas de trabajo en la nube utilizando capacidad de procesamiento dedicada en su región de Microsoft Azure. Para las unidades de escala de borde, puede ejecutar algunas cargas de trabajo de forma independiente en las instalaciones, incluso cuando las unidades de escala están desconectadas temporalmente de la nube.

En este tema, las ejecuciones de gestión de almacenes en un almacén que se define como una unidad de escala se conocen como *Sistema de ejecución de almacén* (*WES*).

## <a name="prerequisites"></a>Requisitos previos

Debe tener un centro de Dynamics 365 Supply Chain Management y una unidad de escala que se ha implementado con la carga de trabajo de gestión del almacén. Para más información sobre la arquitectura y el proceso de implementación, vea [Unidades de escalado en la nube y en el perímetro para cargas de trabajo de gestión de almacenes y fabricación](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Cómo funciona la carga de trabajo de WES en unidades de escala

Para los procesos de la carga de trabajo de gestión del almacén, los datos se sincronizan entre el concentrador y las unidades de escala.

Una unidad de escala puede mantener solo los datos que posee. El concepto de propiedad de los datos para las unidades de báscula ayuda a evitar conflictos entre varios maestros. Por lo tanto, es importante que comprenda qué procesos son propiedad del concentrador y cuáles son propiedad de las unidades de escala.

Las unidades de escala poseen los siguientes datos:

- **Datos de procesamiento de ondas** - Los métodos de proceso de ondas seleccionados se manejan como parte del procesamiento de ondas de la unidad de escala.
- **Datos de procesamiento de trabajo** - Se admiten los siguientes tipos de procesamiento de órdenes de trabajo:

    - Movimientos de inventario (movimiento manual y movimiento por trabajo de plantilla)
    - Órdenes de compra (trabajo de almacenamiento a través de una orden de almacén)
    - Pedidos de ventas (trabajos de selección y carga sencillos)

- **Datos de recepción de pedidos de almacén** - Estos datos se utilizan solo para órdenes de compra que se liberan manualmente a un almacén.
- **Datos de la matrícula** - Se pueden crear placas de matrícula en el cubo y la unidad de escala. Se ha proporcionado un manejo de conflictos dedicado. Tenga en cuenta que estos datos no son específicos del almacén.

## <a name="outbound-process-flow"></a>Flujo de proceso de salida

El centro posee los siguientes datos:

- Todos los documentos de origen, como pedidos de venta y pedidos de transferencia
- Asignación de pedidos y procesamiento de carga saliente
- La liberación al almacén, la creación de envíos y los procesos de creación de oleadas.

Las unidades de escala son propietarias del procesamiento de oleadas real (como la asignación de trabajo, el trabajo de reabastecimiento y la creación de trabajos por demanda) después del lanzamiento de la oleada. Por lo tanto, los trabajadores del almacén pueden procesar el trabajo saliente utilizando una aplicación de almacén que está conectada a la unidad de báscula.

![Flujo de procesamiento de oleada](./media/wes_wave_processing_flow.png "Flujo de procesamiento de oleada")

## <a name="inbound-process-flow"></a>Flujo de proceso de entrada

El centro posee los siguientes datos:

- Todos los documentos de origen, como pedidos de compra y pedidos de devolución de ventas
- Procesamiento de carga de entrada

> [!NOTE]
> El flujo de la orden de compra entrante es conceptualmente diferente del flujo de salida, donde la unidad de báscula que realiza el procesamiento depende de si la orden ha sido liberada a un almacén.

Si está usando el proceso de *liberación al almacén*, se crean las órdenes de almacén y la propiedad del flujo de recepción relacionado se asigna a la unidad de escala. El hub no podrá registrar la recepción entrante.

El trabajadore puede ejecutar el proceso de recepción utilizando una aplicación de almacén que está conectada a la unidad de báscula. Luego, la unidad de báscula registra los datos y se reportan contra el pedido de almacén de entrada. La creación y el procesamiento del almacenamiento posterior también serán manejados por la unidad de báscula.

Si no está utilizando el proceso de *liberación al almacén* y por lo tanto no están usando *pedidos de almacén*, el centro puede procesar la recepción del almacén y el procesamiento del trabajo independientemente de las unidades de escala.

![Flujo de proceso de entrada](./media/wes_Inbound_flow.png "Flujo de proceso de entrada")

## <a name="supported-processes-and-roles"></a>Procesos y roles admitidos

No todos los procesos de gestión de almacenes son compatibles con una carga de trabajo de WES en una unidad de báscula. Por lo tanto, le recomendamos que asigne roles que coincidan con la funcionalidad que está disponible para cada usuario.

Para facilitar este proceso, un rol de muestra que se denomina *Jefe de almacén en carga de trabajo* se incluye en los datos de demostración en **Administracion del sistema \> Seguridad \> Configuración de seguridad**. El propósito de esta función es permitir que los gerentes de almacén accedan al WES en la unidad de báscula. El rol otorga acceso a las páginas que son relevantes en el contexto de una carga de trabajo alojada en una unidad de escala.

Los roles de usuario en una unidad de escala se asignan como parte de la sincronización de datos inicial desde el centro a la unidad de escala.

Para modificar los roles que se asignan a un usuario, vaya a **Administracion del sistema \> Seguridad \> Asignar usuarios a roles** en la unidad de escala. A los usuarios que actúan como gerentes de almacén solo en unidades de escalado se les debe asignar el rol *Jefe de almacén en carga de trabajo*. Este enfoque garantizará que esos usuarios tengan acceso solo a la funcionalidad admitida. Elimine cualquier otro rol asignado a esos usuarios.

A los usuarios que actúan como gerentes en el centro y unidades de escalado se les debe asignar el rol de *Trabajador de almacén* existente. Tenga en cuenta que esta función otorga a los trabajadores del almacén acceso a funciones (como el procesamiento de órdenes de transferencia) que aparecen en la interfaz de usuario (UI) pero que actualmente no son compatibles con las unidades de escala.

## <a name="supported-wes-processes"></a>Procesos WES compatibles

Los siguientes procesos de ejecución de almacén se pueden habilitar para una carga de trabajo de WES en una unidad de báscula:

- Métodos de oleada seleccionados para pedidos de cliente y reabastecimiento de demanda
- Ejecución de órdenes de trabajo a partir de órdenes de venta y reabastecimiento de demanda mediante la aplicación de almacén
- Consultar el inventario disponible mediante la aplicación de almacén
- Creación y ejecución de movimientos de inventario mediante la aplicación de almacén
- Registrar órdenes de compra y realizar trabajos de almacenamiento mediante la aplicación de almacén

Los siguientes tipos de órdenes de trabajo se admiten actualmente para cargas de trabajo WES en implementaciones de unidades de báscula:

- Pedidos de ventas
- Reabastecimiento
- Movimiento de inventario
- Órdenes de compra que están vinculadas a órdenes de almacén

Actualmente, no se admite ningún otro procesamiento de documentos de origen en unidades de escala. Por ejemplo, para una carga de trabajo WES en una unidad de báscula, no puede realizar las siguientes acciones:

- Publicar un pedido de transferencia.
- Procesar las operaciones de envío y picking del almacén de salida.

> [!IMPORTANT]
> Si usa una carga de trabajo en una unidad de escala, no puede ejecutar procesos no admitidos para el almacén específico en el concentrador.

Actualmente, la siguiente funcionalidad de administración de almacenes no es compatible con las unidades de escala:

- Procesamiento de entrada y salida para artículos que tienen dimensiones de seguimiento activas (como dimensiones de número de serie o lote)
- Procesamiento de cambios de estado de inventario
- Procesamiento de inventario que tiene un valor de estado de bloqueo
- Integración con la gestión de la calidad
- Integración con producción
- Procesamiento de elementos con peso capturado
- Procesamiento de sobreentregas y entregas insuficientes
- Procesamiento de inventario disponible negativo

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>Saliente (compatible solo para pedidos de venta y reabastecimiento de demanda)

La siguiente tabla muestra qué funciones de salida son compatibles y dónde se admiten, cuando las cargas de trabajo de administración de almacén se utilizan en unidades de escala de borde y nube.

> [!WARNING]
> Debido a que solo se admite el procesamiento de pedidos de venta, el procesamiento de gestión de almacén de salida no se puede utilizar para pedidos de transferencia.
>
> Algunas funciones de almacén no estarán disponibles en los almacenes que ejecutan las cargas de trabajo de gestión de almacén en una unidad de báscula.

| Proceso                                                      | Concentrador | Carga de trabajo de WES en una unidad de escala |
|--------------------------------------------------------------|-----|------------------------------|
| Procesamiento de documentos de origen                                   | Sí | N.º |
| Procesado de la administración del transporte y la carga                | Sí | N.º |
| Liberar al almacén                                         | Sí | N.º |
| Consolidación de envíos                                       | N.º  | N.º |
| Trabajo de tránsito directo (trabajo de selección)                                 | N.º  | N.º |
| Procesamiento de ola de envíos                                     | No, pero la finalización del estado de la onda se maneja en el hub |<p>Sí, pero no se admiten las siguientes funcionalidades:</p><ul><li>Creación de obra paralela</li><li>Creación y clasificación de carga</li><li>Creación de contenedores</li><li>Impresión de etiquetas de oleadas</li></li></ul><p><b>Nota:</b> Se requiere acceso al concentrador para finalizar el estado de la onda como parte del procesamiento de la onda.</p> |
| Procesamiento de trabajos de almacén (incluida la impresión de matrículas)     | N.º  | <p>Sí, pero solo para las siguientes capacidades:</p><ul><li>Selección de ventas (sin el uso de dimensiones de seguimiento activas)</li><li>Carga de ventas (sin el uso de dimensiones de seguimiento activas)</li></ul> |
| Picking en clúster                                              | N.º  | N.º |
| Procesamiento de embalaje                                           | N.º  | N.º |
| Procesamiento de ordenación de salida                                  | N.º  | N.º |
| Impresión de documentos relacionados con la carga                           | Sí | N.º |
| Conocimiento de embarque y generación de ASN                            | Sí | N.º |
| Confirmación de envío y procesamiento de albarán                | Sí | N.º |
| Picking corto (pedidos de venta)                                 | N.º  | N.º |
| Cancelación de trabajo                                            | N.º  | N.º |
| Cambio de lugar de trabajo (órdenes de venta)                      | N.º  | N.º |
| Trabajo completo (órdenes de venta)                                 | N.º  | N.º |
| Bloquear y desbloquear trabajo                                       | N.º  | N.º |
| Cambiar usuario                                                  | N.º  | N.º |
| Imprimir informe de trabajo                                            | N.º  | N.º |
| Etiqueta de oleada                                                   | N.º  | N.º |
| Invertir el trabajo                                                 | N.º  | N.º |

### <a name="inbound"></a>Entrada

La siguiente tabla muestra qué funciones de entrada son compatibles y dónde se admiten, cuando las cargas de trabajo de administración de almacén se utilizan en unidades de escala de borde y nube.

| Proceso                                                          | Concentrador | Carga de trabajo de WES en una unidad de escala |
|------------------------------------------------------------------|-----|------------------------------|
| Procesamiento&nbsp;de&nbsp;documentos de origen                                       | Sí | N.º |
| Procesado de la administración del transporte y la carga                    | Sí | N.º |
| Confirmación de envío                                            | Sí | N.º |
| Envío de órdenes de compra al almacén (procesamiento de órdenes de almacén) | Sí | N.º |
| Recepción de artículo del pedido de compra y ubicación                        | <p>Si,&nbsp;cuando&nbsp;no hay&nbsp;una orden de almacén</p><p>No, cuando hay un pedido de almacén</p> | <p>Sí, cuando hay una orden de almacén y cuando una orden de compra no forma parte de una <i>carga</i>. Sin embargo, se deben usar dos elementos del menú del dispositivo móvil, uno para recibir (<i>Recepción de artículo de orden de compra</i>) y otro, con la opción <b>Usar trabajo existente</b> habilitada, para procesar el almacenamiento.</p><p>No, cuando no hay un pedido de almacén.</p> |
| Recepción de línea del pedido de compra y ubicación                        | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción de pedido de devolución y ubicación                               | Sí | N.º |
| Recepción de matrícula de entidad de almacén mixta y ubicación                        | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción de artículo de carga                                              | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción de matrícula de entidad de almacén y ubicación                              | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción de artículo del pedido de transferencia y ubicación                        | Sí | N.º |
| Recepción de línea del pedido de transferencia y ubicación                        | Sí | N.º |
| Cancelación de trabajo                                                | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | <p>Si, pero la opción <b>Dar de baja el recibo al cancelar el trabajo</b> (en la página <b>Parámetros de gestión de almacén</b>) no es compatible.</p> |
| Procesamiento de recepción de producto de pedido de compra                        | Sí | N.º |
| Creación de trabajo de cross docking como parte de la recepción                 | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |

### <a name="warehouse-operations-and-exception-handing"></a>Operaciones de almacén y manejo de excepciones

La siguiente tabla muestra qué funciones de control de excepciones y operaciones de almacén son compatibles y dónde se admiten, cuando las cargas de trabajo de administración de almacén se utilizan en unidades de escala de borde y nube.

| Proceso                                            | Concentrador | Carga de trabajo de WES en una unidad de escala |
|----------------------------------------------------|-----|------------------------------|
| Consulta de número de licencia                              | Sí | Sí                          |
| Consulta de artículo                                       | Sí | Sí                          |
| Consulta de ubicación                                   | Sí | Sí                          |
| Cambiar almacén                                   | Sí | Sí                          |
| Movimiento                                           | N.º  | Sí                          |
| Plantilla de movimiento por                               | N.º  | Sí                          |
| Ajuste (entrada/salida)                                | Sí | N.º                           |
| Ciclo de recuento y procesamiento de discrepancias de recuento | Sí | N.º                           |
| Reimpresión de etiqueta (impresión de matrícula)             | Sí | N.º                           |
| Creación de matrícula de entidad de almacén                                | Sí | N.º                           |
| Interrupción de matrícula de entidad de almacén                                | Sí | N.º                           |
| Registro de entrada del conductor                                    | Sí | N.º                           |
| Registro de salida del conductor                                   | Sí | N.º                           |
| Cambiar código de disposición de lote                      | Sí | N.º                           |
| Mostrar lista de trabajo abierta                             | Sí | N.º                           |
| Consolidar matrículas de entidad de almacén                         | N.º  | N.º                           |
| Quitar el contenedor del grupo                        | N.º  | N.º                           |
| Cancelar trabajo                                        | N.º  | N.º                           |
| Procesamiento de reabastecimiento mín./máx.                   | N.º  | N.º                           |
| Procesamiento de reabastecimiento de slotting                  | N.º  | N.º                           |

### <a name="production"></a>Producción

Actualmente, no se admite la integración de la gestión de almacén para escenarios de producción, como se indica en la siguiente tabla.

| Proceso | Concentrador | Carga de trabajo de WES en una unidad de escala |
|---------|-----|------------------------------|
| <p>Todos los procesos de gestión de almacenes relacionados con la producción. A continuación, encontrará algunos ejemplos:</p><li>Liberar al almacén</li><li>Procesamiento de oleadas de producción</li><li>Picking de materia prima</li><li>Ubicación de bienes terminados</li><li>Ubicación de coproducto y producto derivado</li><li>Ubicación de kanban</li><li>Picking de kanban</li><li>Iniciar pedido de producción</li><li>Residuo de producción</li><li>Último pallet de producción</li><li>Registrar lista de selección</li><li>Vaciar kanban</li></ul> | N.º | N.º |

## <a name="maintaining-scale-units-for-wes"></a>Mantenimiento de unidades de escala para WES

Varios trabajos por lotes se ejecutan tanto en el concentrador como en las unidades de escala.

En la implementación del concentrador, puede mantener manualmente los trabajos por lotes. Puede gestionar los siguientes tres trabajos en **Gestion de almacenes \> Tareas periódicas \> Gestión de la carga de trabajo de back-office**:

- Procesar los eventos de actualización del estado del trabajo
- Procesar eventos de transferencia de control de ejecución de oleada
- Registrar recepciones de pedido de origen

En la carga de trabajo, en unidades de escalado, puede gestionar los siguientes dos trabajos en **Gestion de almacenes \> Tareas periódicas \> Gestión de la carga de trabajo**:

- Procesar registros de tabla de oleada
- Procesar eventos de transferencia de control de ejecución de oleada
