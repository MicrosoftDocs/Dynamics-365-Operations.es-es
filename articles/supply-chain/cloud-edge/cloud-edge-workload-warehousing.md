---
title: Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube
description: Este tema proporciona información sobre la función que permite que las unidades de báscula ejecuten procesos seleccionados de la carga de trabajo de administración de su almacén.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2c2d2604dc1948d067311a12d00422ef074ac61a
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641170"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabajo de gestión de almacenes para unidades de escalado en el perímetro y en la nube

[!include [banner](../includes/banner.md)]

> [!WARNING]
> No todas las funciones comerciales de gestión de almacenes son totalmente compatibles con los almacenes que ejecutan una carga de trabajo en una unidad de escalado. Asegúrese de utilizar solo los procesos que este tema describe explícitamente como compatibles.

## <a name="warehouse-execution-on-scale-units"></a>Ejecución de almacén en unidades de escala

Las cargas de trabajo de gestión de almacenes permiten que las unidades de escala en la nube y en el borde ejecuten procesos seleccionados de las capacidades de gestión de almacenes.

## <a name="prerequisites"></a>Requisitos previos

Debe tener un centro de Dynamics 365 Supply Chain Management y una unidad de escala que se ha implementado con la carga de trabajo de gestión del almacén. Para obtener más información sobre la arquitectura y el proceso de implementación, consulte [Escale unidades en una topología híbrida distribuida](cloud-edge-landing-page.md).

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>Cómo funciona la carga de trabajo de ejecución de almacén en unidades de escala

Para los procesos de la carga de trabajo de gestión del almacén, los datos se sincronizan entre el concentrador y las unidades de escala.

Una unidad de escala puede mantener solo los datos que posee. El concepto de propiedad de los datos para las unidades de báscula ayuda a evitar conflictos entre varios maestros. Por lo tanto, es importante que comprenda qué datos de procesos son propiedad del concentrador y cuáles son propiedad de las unidades de escala.

Dependiendo de los procesos comerciales, el mismo registro de datos puede cambiar la propiedad entre el concentrador y las unidades de escala. En la siguiente sección se proporciona un ejemplo de este escenario.

> [!IMPORTANT]
> Algunos datos se pueden crear tanto en el concentrador como en la unidad de báscula. Ejemplos incluyen **Matrículas** y **Números de lote**. Se proporciona manejo de conflictos dedicado en caso de un escenario en el que se crea el mismo registro único tanto en el concentrador como en una unidad de escala durante el mismo ciclo de sincronización. Cuando esto suceda, la próxima sincronización fallará y deberá ir a **Administración del sistema > Consultas > Consultas sobre cargas de trabajo > Registros duplicados**, donde puede ver y combinar los datos.

## <a name="outbound-process-flow"></a>Flujo de proceso de salida

El proceso de propiedad de los datos de salida depende de si está utilizando el proceso de planificación de carga. En todos los casos, el hub posee el *documentos fuente*, como órdenes de venta y órdenes de transferencia, así como el proceso de asignación de órdenes y los datos de transacciones de órdenes relacionadas. Pero cuando utiliza el proceso de planificación de carga, las cargas se crearán en el concentrador y, por lo tanto, inicialmente serán propiedad del concentrador. Como parte del proceso *Liberar al almacén*, la propiedad de los datos de carga se transfiere a la implementación de la unidad de báscula dedicada, que se convertirá en el propietario del siguiente *procesamiento de oleadas de envíos* (como asignación de trabajo, trabajo de reabastecimiento y creación de trabajo por demanda). Por lo tanto, los trabajadores del almacén solo pueden procesar las ventas salientes y el trabajo de órdenes de transferencia mediante una aplicación móvil de Warehouse Management que esté conectada a la implementación que ejecuta la carga de trabajo de la unidad de báscula específica.

Tan pronto como el proceso de trabajo final coloca el inventario en una ubicación de envío final (muelle), la unidad de escalado le indica al centro que actualice las transacciones de inventario del documento de origen a *Recogido*. Hasta que este proceso se ejecute y se vuelva a sincronizar, el inventario disponible en la carga de trabajo de la unidad de báscula se reservará físicamente en el nivel del almacén y podrá procesar inmediatamente la confirmación del envío saliente sin esperar a que se complete esta sincronización. El albarán de venta posterior y el envío de la orden de facturación o transferencia para la carga se manejarán en el centro.

El siguiente diagrama muestra el flujo de salida e indica dónde tienen lugar los procesos comerciales individuales. (Seleccione el diagrama para ampliarlo).

[![Flujo de procesamiento de salida.](media/wes_outbound_warehouse_processes-small.png "Flujo de procesamiento de salida")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Procesamiento de salida con planificación de carga

Cuando utiliza el proceso de planificación de carga, las cargas y los envíos se crean en el centro y la propiedad de los datos se transfiere a las unidades de báscula como parte del proceso *Liberar al almacén*, como se ilustra en la siguiente figura.

![Procesamiento de salida con planificación de carga.](./media/wes_outbound_processing_with_load_planning.png "Procesamiento de salida con planificación de carga")

### <a name="outbound-processing-without-load-planning"></a>Procesamiento de salida sin planificación de carga

Cuando no utiliza el proceso de planificación de carga, los envíos se crean en las unidades de báscula. También se crean cargas en las unidades de escala como parte del proceso de ondulación.

![Procesamiento de salida sin planificación de carga.](./media/wes_outbound_processing_without_load_planning.png "Procesamiento de salida sin planificación de carga")

## <a name="inbound-process-flow"></a>Flujo de proceso de entrada

El centro posee los siguientes datos:

- Todos los documentos de origen, como pedidos de compra y de producción
- Procesamiento de carga de entrada
- Todos los costes y actualizaciones financieras

> [!NOTE]
> El flujo del pedido de compra entrante es conceptualmente diferente del flujo de salida. Puede operar el mismo almacén en la unidad de escalado o en el concentrador, dependiendo de si el pedido de compra se ha entregado al almacén. Después de que haya enviado un pedido al almacén, solo podrá trabajar con ese pedido mientras esté conectado a la unidad de escalado.
>
> Si está usando el proceso de *Liberación al almacén*, se crean los [*pedidos de almacén*](cloud-edge-warehouse-order.md) y la propiedad del flujo de recepción relacionado se asigna a la unidad de escala. El hub no podrá registrar la recepción entrante.

Debe iniciar sesión en el concentrador para usar el proceso *Liberar al almacén*. Para el procesamiento de pedidos de compra, vaya a una de las siguientes páginas para ejecutarlo o programarlo:

- **Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra > Almacén > Acciones > Liberación a almacén**
- **Gestión de almacén > Despachar al almacén > Despacho automático de pedidos de ventas**

Cuando usa **Liberación automática de órdenes de compra**, puede seleccionar líneas de pedido de compra específicas en función de una consulta. Un escenario típico sería configurar un trabajo por lotes recurrente que libere todas las líneas de órdenes de compra confirmadas que se espera lleguen al día siguiente.

El trabajador puede ejecutar el proceso de recepción utilizando una aplicación móvil Warehouse Management que está conectada a la unidad de báscula. Luego, la unidad de báscula registra los datos y se reportan contra el pedido de almacén de entrada. La creación y el procesamiento del almacenamiento posterior también serán manejados por la unidad de báscula.

Si no está utilizando el proceso de *liberación al almacén* y por lo tanto no están usando *pedidos de almacén*, el centro puede procesar la recepción del almacén y el procesamiento del trabajo independientemente de las unidades de escala.

![Flujo de proceso de entrada.](./media/wes-inbound-ga.png "Flujo de proceso de entrada")

Cuando un trabajador realiza un registro entrante utilizando un proceso de recepción de la aplicación móvil Warehouse Management contra la unidad de báscula, se registra un recibo contra la orden de almacén relacionada, que se almacena en la unidad de báscula. La carga de trabajo de la unidad de báscula le indicará al centro que actualice las transacciones de la línea de orden de compra relacionada a *Registrado*. Tan pronto como termine, podrá ejecutar un recibo de producto de orden de compra en el centro de conectividad.

El siguiente diagrama muestra el flujo de entrada e indica dónde tienen lugar los procesos comerciales individuales. (Seleccione el diagrama para ampliarlo).

[![Flujo de procesamiento de entrada](media/wes_inbound_warehouse_processes-small.png "Flujo de procesamiento de entrada")](media/wes_inbound_warehouse_processes.png)

## <a name="supported-processes-and-roles"></a>Procesos y roles admitidos

No todos los procesos de gestión de almacenes son compatibles con una carga de trabajo de ejecución de almacén en una unidad de báscula. Por lo tanto, le recomendamos que asigne roles que coincidan con la funcionalidad que está disponible para cada usuario.

Para facilitar este proceso, un rol de muestra que se denomina *Jefe de almacén en carga de trabajo* se incluye en los datos de demostración en **Administración del sistema \> Seguridad \> Configuración de seguridad**. El propósito de esta función es permitir que los gerentes de almacén accedan a la carga de tgrabajo de ejecución de almacén en la unidad de báscula. El rol otorga acceso a las páginas que son relevantes en el contexto de una carga de trabajo alojada en una unidad de escala.

Los roles de usuario en una unidad de escala se asignan como parte de la sincronización de datos inicial desde el centro a la unidad de escala.

Para modificar los roles que se asignan a un usuario, vaya a **Administración del sistema \> Seguridad \> Asignar usuarios a roles**. A los usuarios que actúan como gerentes de almacén solo en unidades de escalado se les debe asignar el rol *Jefe de almacén en carga de trabajo*. Este enfoque garantizará que esos usuarios tengan acceso solo a la funcionalidad admitida. Elimine cualquier otro rol asignado a esos usuarios.

A los usuarios que actúan como gerentes en el centro y unidades de escalado se les debe asignar el rol de *Trabajador de almacén* existente. Tenga en cuenta que esta función otorga a los trabajadores del almacén acceso a funciones (como el procesamiento de recepción de pedidos de transferencia) que aparecen en la interfaz de usuario (UI) pero que actualmente no son compatibles con las unidades de escala.

### <a name="supported-warehouse-execution-processes"></a>Procesos de ejecución de almacén compatibles

Los siguientes procesos de ejecución de almacén se pueden habilitar para una carga de trabajo de ejecución de almacén en una unidad de báscula:

- Métodos de oleada seleccionados para pedidos de venta y transferencia (validación, craeción de carga, asignación, reabastecimiento de demanda, creación de contenedores, creación de trabajo e impresión de etiquetas de oleada)

- Procesar el trabajo de almacén de pedidos de transferencia y ventas utilizando la aplicación del almacén (incluido el trabajo de reabastecimiento)
- Consultar el inventario disponible mediante la aplicación de almacén
- Creación y ejecución de movimientos de inventario mediante la aplicación de almacén
- Creación y procesamiento del trabajo de recuento cíclico mediante la aplicación de almacén
- Realizar ajustes de inventario mediante la aplicación de almacén
- Registrar órdenes de compra y realizar trabajos de almacenamiento mediante la aplicación de almacén

Los siguientes tipos de trabajo se pueden crear en una unidad de báscula y, por lo tanto, se pueden procesar como parte de una carga de trabajo de gestión de almacén:

- **Movimientos de inventario**: movimiento manual y movimiento por trabajo de plantilla.
- **Recuento cíclico**: incluido un proceso de aprobación/rechazo como parte de las operaciones de recuento.
- **Pedidos de compra**: trabajo de almacenamiento a través de un pedido de almacén cuando los pedidos de compra no se asocian con las cargas.
- **Pedidos de ventas**: selección y carga sencillos.
- **Problema de transferencia**: recogida y carga sencillas.
- **Reabastecimiento**: sin incluir materias primas para la producción.
- **Guardado de productos terminados**: después del proceso de producción de informes como terminado.
- **Eliminación de coproductos y subproductos**: después del proceso de producción de informes como terminado.

Actualmente, no se admite ningún otro tipo de procesamiento de documentos de origen o trabajo de almacén en unidades de escalado. Por ejemplo, para una carga de trabajo de ejecución de almacén en una unidad de escalado, no puede realizar un proceso de recepción de pedidos de transferencia (recepción de transferencias); en su lugar, esto debe procesarse mediante la instancia del centro de conectividad.

> [!NOTE]
> Los elementos del menú de dispositivo móvil y los botones para funciones no compatibles no se muestran en la _aplicación móvil Warehouse Management_ cuando está conectada a una implementación de unidad de escalado.
> 
> Cuando ejecuta una carga de trabajo en una unidad de escalado, no puede ejecutar procesos no admitidos para ese almacén específico en el concentrador. Las tablas que se proporcionan más adelante en este tema documentan las capacidades admitidas.
>
> Los tipos de trabajo de almacén seleccionados se pueden crear tanto en el concentrados como en las unidades de escalado, pero solo se pueden mantener en el concentrador o la unidad de escalado propietarios (la implementación que creó los datos).
>
> Incluso cuando un proceso específico es compatible con la unidad de escalado, tenga en cuenta que es posible que todos los datos necesarios no se sincronicen desde el concentrador a la unidad de escalado, o viceversa, lo que puede resultar en un procesamiento inesperado del sistema. Ejemplos de este escenario incluyen:
> 
> - Si usa una consulta de directiva de ubicación que se une a un registro de tabla de datos que solo existe en la implementación del concentrador.
> - Si usa el estado de ubicación o las funciones de carga volumétrica de ubicación. Estos datos no se sincronizarán entre las implementaciones y, por lo tanto, solo funcionarán cuando se actualice el inventario de ubicación disponible en una de las implementaciones.

Actualmente, la siguiente funcionalidad de gestión de almacenes no es compatible con las cargas de trabajo de las unidades de escalado:

- Procesamiento entrante de líneas de pedido de compra asignadas a una carga.
- Procesamiento entrante de pedidos de compra para un proyecto.
- Administración del coste de aterrizaje, uso de viajes y seguimiento de mercancías en tránsito.
- Procesamiento de entrada y salida para artículos que tienen dimensiones de seguimiento activas **Propietario** o **Número de serie**.
- Procesamiento de inventario que tiene un valor de estado de bloqueo.
- Cambio de un estado de inventario durante cualquier proceso de movimiento de trabajo.
- Reservas de dimensión de nivel de almacén flexibles de pedidos confirmados.
- Uso de la funcionalidad *Estado de ubicación de almacén* (los datos no se sincronizan entre las implementaciones).
- Uso de la funcionalidad *Posición de matrícula de entidad de almacén de ubicación*.
- Uso de *Filtros de producto* y *Grupos de filtros de producto*, incluida la configuración **Número de días para mezclar lotes**.
- Integración con la gestión de la calidad.
- Procesamiento con elementos con peso capturado.
- Procesamiento con artículos solo habilitados para la administración de transporte (TMS).
- Procesamiento con inventario disponible negativo.
- Procesamiento de trabajos de almacén con notas de envío.
- Procesamiento de trabajos de almacén con manipulación de materiales y automatización de almacén.
- Imágenes de datos maestros del producto (por ejemplo, en la aplicación móvil Warehouse Management).
- Uso compartido de datos entre empresas para productos.

> [!WARNING]
> Algunas funciones de almacén no estarán disponibles para los almacenes que ejecutan las cargas de trabajo de gestión de almacenes en una unidad de escalado y tampoco se admiten en el concentrador o en la carga de trabajo de la unidad de escalado.
> 
> Otras capacidades pueden procesarse en ambos, pero requerirán un uso cuidadoso en algunas situaciones, como cuando el inventario disponible se actualiza para el mismo almacén tanto en el concentrador como en la unidad de escalado debido al proceso de actualización de datos asincrónicos.
> 
> Las funcionalidades específicas (como *bloquear trabajo*), que son compatibles tanto con el concentrador como con las unidades de escalado solo serán compatibles con el propietario de los datos.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Saliente (compatible solo para pedidos de venta y transferencia)

La siguiente tabla muestra qué funciones de salida son compatibles y dónde se admiten, cuando las cargas de trabajo de gestión de almacén se utilizan en unidades de escala de borde y nube.

| Proceso                                                      | Concentrador | Carga de trabajo de ejecución de almacén en una unidad de escala |
|--------------------------------------------------------------|-----|------------------------------|
| Procesamiento de documentos de origen                                   | Sí | N.º |
| Procesado de la administración del transporte y la carga                | Sí, pero solo los procesos de planificación de carga. El procesamiento de gestión de transporte no es compatible  | N.º |
| Liberar al almacén                                         | Sí | N.º |
| Tránsito directo planificado                                        | N.º  | N.º |
| Consolidación de envíos                                       | Sí, al utilizar la planificación de carga | Sí |
| Procesamiento de ola de envíos                                     | N.º  |Si, excepto **Carga y clasificación** |
| Mantener envíos por ola                                  | N.º  | Sí|
| Procesamiento de trabajos de almacén (incluida la impresión de matrículas)        | N.º  | Sí, pero solo para las capacidades compatibles antes mencionadas |
| Picking en clúster                                              | N.º  | Sí|
| Procesamiento de embalaje manual, incluido el procesamiento de trabajo 'Selección de contenedor empaquetado' | N.º <P>Se puede realizar algún procesamiento después de un proceso de selección inicial gestionado por una unidad de escalada, pero no se recomienda debido a las siguientes operaciones bloqueadas.</p>  | N.º |
| Quitar el contenedor del grupo                                  | N.º  | N.º |
| Procesamiento de ordenación de salida                                  | N.º  | N.º |
| Impresión de documentos relacionados con la carga                           | Sí | Sí|
| Conocimiento de embarque y generación de ASN                            | N.º  | Sí|
| Confirmación de envío                                             | N.º  | Sí|
| Confirmación de envío con "Confirmar y transferir"            | N.º  | N.º |
| Procesamiento de albaranes y facturas                        | Sí | N.º |
| Selección corta (pedidos de venta y transferencia)                    | N.º  | Sí, sin eliminar las reservas para los documentos originales|
| Selección en exceso (pedidos de venta y transferencia)                     | N.º  | Sí|
| Cambio de lugar de trabajo (pedidos de venta y transferencia)         | N.º  | Sí|
| Trabajo completo (pedidos de venta y transferencia)                    | N.º  | Sí|
| Imprimir informe de trabajo                                            | Sí | Sí|
| Etiqueta de oleada                                                   | N.º  | Sí|
| División del trabajo                                                   | N.º  | Sí|
| Procesamiento de trabajo: dirigido por 'Carga de transporte'            | N.º  | N.º |
| Reducir cantidad seleccionada                                       | N.º  | N.º |
| Invertir el trabajo                                                 | N.º  | N.º |
| Invertir confirmación de envíos                                | N.º  | Sí|

### <a name="inbound"></a>Entrada

La siguiente tabla muestra qué funciones de entrada son compatibles y dónde se admiten, cuando las cargas de trabajo de gestión de almacén se utilizan en unidades de escala de borde y nube.

| Proceso                                                          | Concentrador | Carga de trabajo de ejecución de almacén en una unidad de escala<BR>*(Los artículos marcados con "Sí" se aplican solo a los pedidos de almacén)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Procesamiento&nbsp;de&nbsp;documentos de origen                             | Sí | No |
| Procesado de la administración del transporte y la carga                    | Sí | No |
| Coste de aterrizaje y recepción de mercancía en tránsito                       | Sí | No |
| Confirmación de envío entrante                                    | Sí | No |
| Envío de órdenes de compra al almacén (procesamiento de órdenes de almacén) | Sí | N.º |
| Cancelación de líneas de pedido de almacén<p>Tenga en cuenta que esto solo se aplica cuando no se ha realizado ningún registro en la línea</p> | Sí | N.º |
| Recepción de artículo del pedido de compra y ubicación                       | <p>Si,&nbsp;cuando&nbsp;no hay&nbsp;una orden de almacén</p><p>No, cuando hay un pedido de almacén</p> | <p>Sí, cuando un pedido de compra no forma parte de una <i>carga</i></p> |
| Recepción de línea del pedido de compra y ubicación                       | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | <p>Sí, cuando un pedido de compra no forma parte de una <i>carga</i></p></p> |
| Recepción de pedido de devolución y ubicación                              | Sí | N.º |
| Recepción de matrícula de entidad de almacén mixta y ubicación                       | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | Sí |
| Recepción de artículo de carga                                              | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción de matrícula de entidad de almacén y ubicación                             | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción de artículo del pedido de transferencia y ubicación                       | Sí | N.º |
| Recepción de línea del pedido de transferencia y ubicación                       | Sí | N.º |
| Cancelar trabajo (entrante)                                            | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | <p>Si, pero solo cuando la opción <b>Dar de baja el recibo al cancelar el trabajo</b> (en la página <b>Parámetros de gestión de almacén</b>) se ha desactivado</p> |
| Procesamiento de recepción de producto de pedido de compra                        | Sí | N.º |
| Recepción de pedidos de compra con entrega incompleta                      | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | Sí, pero solo haciendo una solicitud de cancelación desde el concentrador |
| Recepción de pedidos de compra con entrega excesiva                       | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | Sí  |
| Recepción con la creación del trabajo *Tránsito directo*                 | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción con la creación del trabajo *Pedido de calidad*                  | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción con la creación del trabajo *Muestreo de artículos de calidad*          | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción con la creación del trabajo *Calidad en control de calidad*       | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Recepción con la creación de pedido de calidad                            | <p>Sí, cuando no hay un pedido de almacén</p><p>No, cuando hay un pedido de almacén</p> | N.º |
| Procesamiento de trabajo: dirigido por *Ubicación de clúster*                 | Sí | N.º |
| Procesamiento de trabajo con *Selección corta*                               | Sí | N.º |
| Carga de matrícula de entidad de almacén                                           | Sí | Sí |

### <a name="warehouse-operations-and-exception-handing"></a>Operaciones de almacén y manejo de excepciones

La siguiente tabla muestra qué funciones de control de excepciones y operaciones de almacén son compatibles y dónde se admiten, cuando las cargas de trabajo de gestión de almacén se utilizan en unidades de escala de borde y nube.

| Proceso                                            | Concentrador | Carga de trabajo de ejecución de almacén en una unidad de escala |
|----------------------------------------------------|-----|------------------------------|
| Consulta de número de licencia                              | Sí | Sí                          |
| Consulta de artículo                                       | Sí | Sí                          |
| Consulta de ubicación                                   | Sí | Sí                          |
| Cambiar almacén                                   | Sí | Sí                          |
| Movimiento                                           | Sí | Sí                          |
| Plantilla de movimiento por                               | Sí | Sí                          |
| Transferencia de almacén                                 | Sí | N.º                           |
| Crear pedidos de transferencia desde la aplicación de almacén           | Sí | N.º                           |
| Ajuste (entrada/salida)                                | Sí | Sí, pero no para el escenario de ajuste en el que la reserva de inventario debe eliminarse mediante la opción **Eliminar reservas** en los tipos de ajuste de inventario</p>                           |
| Cambio de estado de inventario                            | Sí | N.º                           |
| Ciclo de recuento y procesamiento de discrepancias de recuento | Sí | Sí                           |
| Reimpresión de etiqueta (impresión de matrícula)             | Sí | Sí                          |
| Creación de matrícula de entidad de almacén                                | Sí | N.º                           |
| Interrupción de matrícula de entidad de almacén                                | Sí | N.º                           |
| Empaquetar en matrículas de entidad de almacén anidadas                                | Sí | N.º                           |
| Registro de entrada del conductor                                    | Sí | N.º                           |
| Registro de salida del conductor                                   | Sí | N.º                           |
| Cambiar código de disposición de lote                      | Sí | Sí                          |
| Mostrar lista de trabajo abierta                             | Sí | Sí                          |
| Consolidar matrículas de entidad de almacén                         | Sí | N.º                           |
| Procesamiento de reabastecimiento del umbral de zona y mínimo y máximo| Sí <p>La recomendación es no incluir las mismas ubicaciones como parte de las consultas</p>| Sí                          |
| Procesamiento de reabastecimiento de slotting                  | Sí  | Sí<p>Tenga en cuenta que la configuración debe realizarse en la unidad de escalado</p>                           |
| Bloquear y desbloquear trabajo                             | Sí | Sí                          |
| Cambiar usuario                                        | Sí | Sí                          |
| Cambiar grupo de trabajo en trabajo                           | Sí | Sí                          |
| Cancelar trabajo                                        | Sí | Sí                          |

### <a name="production"></a>Producción

La siguiente tabla resume qué escenarios de producción de gestión de almacenes se admiten en las cargas de trabajo de la unidad de escalado actualmente.

| Proceso | Concentrador | Carga de trabajo de ejecución de almacén en una unidad de escala |
|---------|-----|------------------------------|
| Ubicación de bienes terminados y notificados como terminados | Sí | Sí |
| Ubicación de coproducto y producto derivado | Sí | Sí |
| <p>Todos los demás procesos de gestión de almacenes están relacionados con la producción, incluyendo:</p><li>Liberar al almacén</li><li>Procesamiento de oleadas de producción</li><li>Picking de materia prima</li><li>Ubicación de kanban</li><li>Picking de kanban</li><li>Iniciar pedido de producción</li><li>Residuo de producción</li><li>Último pallet de producción</li><li>Registrar lista de selección</li><li>Vaciar kanban</li></ul> | Sí | N.º |
| Reabastecimiento de materias primas | N.º | N.º |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>Mantener unidades de escalado para la ejecución de almacén

Varios trabajos por lotes se ejecutan tanto en el concentrador como en las unidades de escala.

En la implementación del concentrador, puede mantener manualmente los trabajos por lotes. Puede gestionar los siguientes trabajos por lotes en **Gestión de almacenes \> Tareas periódicas \> Gestión de la carga de trabajo de back-office**:

- Procesador de mensajes de unidad de escalado a centro
- Registrar recepciones de pedido de origen
- Completar pedidos de almacén

En la carga de trabajo, en unidades de escalado, puede gestionar los siguientes trabajos por lotes en **Gestión de almacenes \> Tareas periódicas \> Gestión de la carga de trabajo**:

- Procesar registros de tabla de oleada
- Procesador de mensajes del centro de almacén a la unidad de escalado
- Procesar solicitudes de actualización de cantidad para líneas de pedido de almacén

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
