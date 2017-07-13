---
title: "Visión general del proceso de producción"
description: "Este artículo ofrece una visión general de los procesos de producción. Describe las distintas etapas de pedidos de producción, de pedidos de lote y de kanbans, desde la creación de pedidos al cierre del período financiero."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgProdStatusListPage, JmgShopSupervisorWorkspace, Kanban, ProdTable, ProdTableOverview
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19832
ms.assetid: 0e83c7ea-feba-4ed6-8717-8b48a3b8804a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: b73ec05442c8b089435d5813ea93b997c473cbb4
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Visión general del proceso de producción
<a id="production-process-overview" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este artículo ofrece una visión general de los procesos de producción. Describe las distintas etapas de pedidos de producción, de pedidos de lote y de kanbans, desde la creación de pedidos al cierre del período financiero. 

La producción de productos, un proceso también conocido como el ciclo de vida de producción, sigue los pasos específicos necesarios para completar la fabricación de un artículo. El ciclo de vida comienza con la creación del pedido de producción, el pedido de lote o kanban. Finaliza con un artículo manufacturado terminado listo para el cliente o para otra fase de producción. Cada paso del ciclo de vida requiere diferentes tipos de información para terminar el proceso. Cuando termina cada paso, el pedido de producción, el pedido de lote o el kanban refleja esto cambiando el estado de producción. Distintos tipos de productos requieren diferentes procesos de fabricación.  

El módulo **Control de producción** está vinculado a otros módulos, como **Gestión de información de productos**, **Gestión de inventarios**, **Contabilidad general**, **Administración de almacenes**, **Contabilidad de proyectos** y **Administración de la organización**. Esta integración permite el flujo de información necesario para completar la fabricación de un artículo terminado.  

El proceso de producción se ve influenciado normalmente por los métodos de validación de inventario y contabilidad de costes que se eligen para un proceso de producción específico. Finance and Operations admite ambos métodos, el de coste real (primero en entrar, primero en salir \[FIFO\]; último en entrar, primero en salir \[LIFO\]; promedio móvil; y media ponderada periódica) y el de coste estándar. La Lean manufacturing se implementa en función del principio de la contabilización previa de los costes.  

La opción de los métodos de medición del coste también define los requisitos para informar sobre el consumo de material y recursos durante el proceso de producción. Normalmente, los métodos de coste real requieren un informe exacto en el nivel de trabajo, mientras que los métodos de costes periódicos permiten disponer de informes menos granulares sobre el consumo de materiales y recursos.

## Fabricación en modo mixto
<a id="mixed-mode-manufacturing" class="xliff"></a>
Los distintos productos y topologías de producción que requieren la aplicación de distintos tipos de pedido. Finance and Operations puede aplicar los distintos tipos de pedido de modo mezclado. En otras palabras, se pueden producir todos los tipos de pedidos durante el proceso de completo de producir un producto terminado.

-   **Pedido de producción**: este es el tipo de pedido clásico para producir un producto o una variante del producto específico de una cantidad concreta en una fecha específica. Los pedidos de producción se basan en listas de materiales y rutas.
-   **Pedido de lote**: este tipo de pedido se usa para industrias de proceso y procesos discretos donde la conversión de fabricación se basa en una fórmula, o donde los coproductos y productos derivados pueden ser productos finales, o en lugar del producto principal. Los pedidos de lote usan listas de materiales y rutas de tipo **Fórmula**.
-   **Kanban**: los kanbans se usan para señalar procesos repetitivos de lean manufacturing (producción ajustada) que se basan en flujos de producción, reglas kanban y listas de materiales.
-   **Proyecto**: un proyecto de la fabricación combina productos y servicios con una programación y un presupuesto dados. La parte de fabricación de un proyecto se puede entregar a través de los otros tipos de pedido.

## Principios de fabricación
<a id="manufacturing-principles" class="xliff"></a>
Para seleccionar el principio de fabricación que se aplica mejor a un determinado producto y un mercado relacionado, debe tener en cuenta los requisitos de producción y logística, y también las expectativas del cliente acerca de los plazos de entrega.

-   **Para existencias**: este es el principio clásico de fabricación, donde los productos se producen para existencias, en función de la previsión o del reabastecimiento de la de existencias mínimo (este último se calcula normalmente en función de la previsión o de consumo histórico).
-   **Hacer para pedir**: los productos estándar se realizan por petición o se terminan por petición. Aunque la preproducción se puede hacer mediante el principio de Hacer para existencias, los pasos costosos de la cadena de valor o los pasos que crean variantes se accionan por medio de un pedido de ventas o un pedido de transferencia.
-   **Configurar a pedido**: en cuanto al principio Hacer para pedir, las operaciones finales de la cadena de valor se hacen por pedido. La variante del producto real que se produce no está predefinida, sino que se crea en el momento de introducir los pedidos, según el modelo de configuración del producto de ventas. El principio Configurar a pedido requiere un nivel determinado de unificación del proceso para una línea determinada de producto.
-   **Diseñar a pedido**: los procesos de diseño a pedido se gestiona normalmente por medio de un proyecto y suelen empezar normalmente con la fase de ingeniería. Durante la fase de ingeniería, se diseñan y se describen los productos reales necesarios para satisfacer el pedido. Los pedidos de producción, los pedidos de lote o los kanbans se pueden crear continuación para producir los productos.

## Visión general del ciclo de vida de producción
<a id="overview-of-the-production-life-cycle" class="xliff"></a>
Se pueden dar los siguientes pasos en el ciclo de vida de producción para todos los tipos de pedido de fabricación en modo mixto. Sin embargo, no todos están representadas como estados de pedido explícitos.

1.  **Creado**: puede crear un pedido de producción, un pedido de lote, o un kanban manualmente, o puede configurar el sistema para generarlos basándose en distintas señales de la demanda. La planificación maestra crea pedidos de producción, pedidos de lote o kanbans poniendo el firme los pedidos planificados. Otras señales de demanda son pedidos de ventas o señales de suministro fijado desde otros pedidos de producción o kanbans. Para kanbans de cantidad fija, se generan señales de demanda cuando los kanbans se registran como vacíos.
2.  **Estimado**: puede calcular estimaciones para el material y el consumo de recursos. La estimación genera transacciones de inventario para las materias primas con estado **En pedido**. Las recepciones de productos principales, coproductos y productos derivados principales se generan cuando se estiman pedidos de producción o pedidos de lote. Si la lista de materiales contiene líneas del tipo **Suministro asegurado**, se generan pedidos de compra para los materiales o servicios de operación subcontratados y adjuntan al pedido de producción o de lote. Los artículos o pedidos se reservan en función de la estrategia de reserva del pedido de producción, y el precio de los productos terminados se calcula en función de la configuración de parámetros.
3.  **Programado**: puede programar la producción basándose en operaciones, trabajos individuales o ambos.
    -   **Programación de operaciones**: este método de programación proporciona un plan estimado a largo plazo. Mediante este método, puede asignar las fechas de inicio y finalización a los pedidos de producción. Si los pedidos de producción están vinculados a las operaciones de ruta, puede asignarlos a los grupos de centro de coste.
    -   **Programación de trabajos**: este método de programación proporciona un plan detallado. Cada operación se desglosa en trabajos individuales que tienen fechas, horas y recursos de operaciones asignados. Si se usa la capacidad limitada, los trabajos se asignan a los recursos de operaciones en función de su disponibilidad. Puede ver y cambiar la programación en un gráfico de Gantt.
    -   **Programación kanban**: los trabajos kanban se programan en el tablero de programación kanban o se programan automáticamente según la configuración automática de la planificación de las reglas kanban.

4.  **Liberado**: puede liberar el pedido de producción o de lotes cuando termine la programación y el material quede disponible para ser seleccionado o prepararse. La comprobación de disponibilidad de material ayuda al supervisor de planta a evaluar la disponibilidad del material para los pedidos de producción o los pedidos de lote. También puede imprimir documentos de pedido de producción, como las listas de selección, tarjeta de trabajo, tarjeta de ruta y trabajo de ruta. Cuando se libera el pedido de producción, el estado del pedido cambia para indicar que la producción puede iniciarse. Si se usa la gestión de almacenes, al liberar el pedido de producción o el pedido de lote se liberan las líneas de lista de materiales de producción hacia la gestión de almacenes. Entonces se generan oleadas de almacén y trabajo de almacén según la configuración de almacén.
5.  **Preparado**/**Seleccionado**: cuando se hayan almacenado provisionalmente todos los materiales y recursos en la ubicación de producción, las líneas de lista de materiales o las líneas de kanban se actualizan al estado **Seleccionado**. Los pedidos asegurados y el trabajo relacionado de almacén se suelen completar en esta fase. Hacen falta tarjetas kanban o tarjetas de trabajo para informar del progreso de producción en caso de asignarse e imprimirse.
6.  **Iniciado**: cuando se inicia un pedido de producción, un pedido de lote o un kanban, se puede notificar el material y el consumo del recurso con el pedido. El sistema se puede configurar para registrar automáticamente el consumo de material y de recursos asignados al pedido cuando se inicia el pedido. Esta asignación se conoce como contabilización hacia atrás, contabilización hacia delante o autoconsumo. Puede asignar manualmente materiales a los pedidos de producción o los pedidos de lote creando diarios adicionales de lista de selección. También puede asignar manualmente los costes de mano de obra y otros de ruta al pedido. Si usa la programación de operaciones, puede asignar estos costes creando un diario de tarjeta de ruta. Si usa la programación de trabajos, puede asignar los costes creando un diario de tarjeta de trabajo. Los pedidos de producción o los pedidos de lote se pueden comenzar por lotes de la cantidad final solicitada. Dentro de un pedido de producción, un pedido de lote o uno de kanban, los trabajos creados se pueden iniciar y notificar por separado a través de diarios, la terminal de ejecución de fabricación (terminal MES) o los tableros kanban.
7.  Informar progreso/**Completar** trabajos: use el terminal MES, los diarios de producción, los tableros kanban o las capacidades de escaneado móvil para informar del progreso de producción por trabajo o por recurso. El material y el consumo de recursos se registrarán y el estado de los kanbans, los pedidos de producción y los pedidos de lote relacionados podrán actualizarse a **Recibido** a o **Notificado como terminado**. Se puede generar trabajo de guardado para el almacén, en función de la configuración de almacén.
8.  **Notificado como terminado** (la recepción del producto): cuando un pedido de producción o de lote se notifica como terminado, la cantidad de productos terminados que se haya completado se actualiza en el inventario. Esta cantidad incluye la cantidad de coproductos y productos derivados relevantes. Si utiliza contabilidad de trabajo en proceso (WIP), se genera un diario contable para reducir las cuentas de trabajo en curso y para aumentar el inventario de productos terminados. Cuando se calcula el coste de un pedido de producción, se registra el coste real de la producción. Si los costes de materiales y de mano de obra que están asociados a una producción ya no están asignados en un diario o flujo invertido, pueden asignarse automáticamente mediante contabilización hacia atrás. La asignación mediante contabilización hacia atrás implica la posterior deducción de los procesos de la transacción de inventario. Si el pedido de producción se completa, seleccione la casilla de verificación **Cierre final** para cambiar el estado restante a **Finalizado**. De lo contrario, deje el campo en blanco para permitir informar las cantidades adicionales producidas.
9.  **Evaluación de calidad**: una recepción de producto puede desencadenar la creación de pedidos de calidad, en función de la configuración de los procesos de prueba y las reglas de calidad establecidas para los productos específicos. Puesto que un pedido de calidad puede actualizar el estado de inventario o los atributos de lote de los productos probados, la evaluación de calidad es un proceso obligatorio en muchas industrias.
10. **Ubicación** y **Enviar a pedido**: tras la recepción del producto y su evaluación de calidad, el trabajo opcional de guardado dirige los productos recibidos al siguiente punto de consumo, a un almacén de productos terminados o a una zona de envío si hay requisitos de envío a pedido.
11. **Finalizado**: antes de que se complete la producción, los costes reales se calculan para la cantidad producida. Todos los costes estimados de material, mano de obra y gastos generales se invierten y sustituyen por los costes reales. Si activa la casilla de verificación **Cierre final** al ejecutar el cálculo de costes, el estado de pedido de producción cambia a **Finalizado**. Este estado evita que los costes adicionales se registren para un pedido de producción finalizado.
12. **Cierre de período**: algunos principios de contabilidad de costes, como media periódica, costes de contabilización previa, FIFO o LIFO, requieren actividades periódicas para cerrar el inventario o el período financiero. Normalmente, el sistema intenta informar de todo el material y los recurso consumidos, y también las correcciones del inventario y los residuos, antes de cerrar los períodos. Estos informes se realizan normalmente mediante los diarios de movimientos de inventario o los diarios de ajuste. El objetivo es evaluar el rendimiento económico de unidades operativas por período. En algunos casos, cuando se usan pedidos de producción duraderos que abarcan los períodos de informes financieros, los diarios de producción se usan para notificar sobre el progreso de producción y el consumo de recursos para el final del período.


Consulte también
<a id="see-also" class="xliff"></a>
--------

[Comentarios de producción](production-feedback.md)

[Modelos de configuración del producto](../pim/product-configuration-models.md)

[Lean manufacturing (producción ajustada)](lean-manufacturing-overview.md)




