---
title: "Visión general de lean manufacturing"
description: "Este artículo proporciona una visión general y una descripción de las funciones de producción ajustada de Dynamics 365 for Finance and Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob, KanbanBoardWorkCell, KanbanJobSchedulingListPage, LeanProductionFlow
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19371
ms.assetid: 026c5605-6be7-4fdb-a6f2-8e37a806796c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 376b521a7527b4f60bc01c080f8eabb5cb231b30
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# <a name="lean-manufacturing-overview"></a>Visión general de lean manufacturing

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general y una descripción de las funciones de producción ajustada de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

Lean manufacturing ofrece herramientas que puede usar para modelar las operaciones lean. Estas herramientas apoyan y promueven los siguientes conceptos y actividades empresariales:
-   Crear una fundación de lean manufacturing modelando procesos de fabricación y logística como flujos de producción.
-   Implementar un sistema de extracción lean mediante el uso de kanbans para indicar los requisitos de la demanda.
-   Supervisión y mantenimiento de trabajos kanban

La arquitectura de lean manufacturing de Finance and Operations consta de flujos de producción, actividades y reglas kanban. Estas estructuras se integran completamente con los procesos de Finance and Operations. Puede usar el lean manufacturing en un entorno de fabricación mixto que combine distintas estrategias de suministro, producción y abastecimiento. Estas estrategias incluyen pedidos de producción, de lote para los sectores de procesamiento, de compra y de transferencia.
| **Importante**                                                                                                                                                                                                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Puede usar Finance and Operations para permitir implementar lean manufacturing (producción ajustada) con kanbans. Sin embargo, la correcta implementación de los principios lean dependerá de los procesos empresariales internos que utilice y de las condiciones y el entorno real de la producción. |

## <a name="modeling-manufacturing-and-logistics-processes-as-production-flows"></a>Modelo de fabricación y procesos de logística durante el flujo de producción
Para crear una fundación de lean manufacturing, modele los procesos de fabricación y logística como flujos de producción. Esta actividad consta de las siguientes tareas:
1.  Identifique los procesos para los que desea implementar una estrategia de reabastecimiento lean y, a continuación, modele esos procesos como flujos de producción. De esta manera, podrá analizar y agilizar los procesos. Uno de los objetivos de la implementación de lean es reducir los deshechos mejorando el flujo de materiales e información.
2.  Defina un flujo de producción como una secuencia de actividades que describa el flujo de materiales. Una actividad de transferencia define el movimiento de uno o varios producto de una ubicación a otra. Una actividad de proceso define una operación de valor añadido que se aplica a un producto.
3.  Cree una versión del flujo de producción que defina los requisitos para el ritmo de producción. Estos requisitos se utilizan para calcular los tiempos de ciclo de todas las actividades del flujo de producción. Se pueden crear varias versiones de los flujos de producción y utilizarlas posteriormente para mejorar los procesos.

## <a name="using-kanbans-to-signal-demand-requirements"></a>Uso de los kanbans para indicar los requisitos de la demanda
Un sistema de extracción produce mercancías solo cuando son necesarias. Esta práctica reduce los plazos de entrega y el exceso de inventario. Puede usar kanbans para planear, seguir y procesar los requisitos basados en los flujos de producción. Para crear un marco de kanban, cree las reglas kanban que definen cuando se crean kanbans y cómo se cumplen los requisitos. Se pueden crear dos tipos de reglas kanban. Las reglas de fabricación crean trabajos kanban de proceso y las reglas kanban de retirada crean trabajos kanban de transferencia. Se pueden configurar las siguientes estrategias de reabastecimiento:
-   Las reglas kanban de **cantidad fija** están relacionadas con un número fijo de unidades de gestión de material, lo que significa que los números de kanbans activos son constantes. Cuando todos los productos de un kanban se consumen y las unidades de gestión de material se vacían manualmente, se crea un nuevo kanban del mismo tipo. Al crear las reglas kanban de cantidad fija, puede calcular las cantidades óptimas de kanban y de producto que se usan. El cálculo tiene en cuenta la previsión, la demanda real de pedidos abiertos, el plazo de reabastecer los artículos y las demandas históricas.
-   Las reglas kanban **programadas** reabastecen los requisitos calculados por la planificación maestra. La planificación maestra genera kanbans planificados que se pueden poner en firme en kanbans.
-   Las reglas kanban de **evento** reabastecen los requisitos que se originan de las líneas de pedidos de ventas, las líneas de listas de materiales, las de kanban o la configuración mínima de inventario. Cuando se generan los kanbans de evento, se fijan a los requisitos de origen.

Cuando se crean los kanbans, se generan uno o más trabajos kanban según las actividades de flujo kanban definidas en las reglas de éstos.

## <a name="monitoring-and-maintaining-kanban-jobs"></a> Supervisión y mantenimiento de trabajos kanban
Lean manufacturing proporciona visibilidad al estado actual de las actividades de fabricación y logística gobernadas por las reglas kanban. De esta manera, podrá planificar y dar prioridad a las tareas siguientes:

-   Obtener una visión general de la programación actual del trabajo kanban.
-   Planear y reprogramar los trabajos kanban.
-   Realice un seguimiento del estado de los trabajos kanban y regístrelo.

En la siguiente lista se describen los tableros kanban especializados:
-   Programación de trabajos kanban: proporciona una visión general de los trabajos kanban. El tablero muestra los trabajos kanban y sus estados para una o varias celdas de trabajo. Los trabajos se listan en función de los períodos de planificación (días o semanas) definidos en el modelo de flujo de producción. El tablero también muestra el consumo de capacidad de cada período de planificación, de manera que pueda supervisar la carga programada. Puede cambiar el estado de los trabajos kanban, reprogramarlos en períodos de planificación diferentes y realizar otras tareas.
-   Tablero kanban para trabajos de transferencia: este tablero proporciona una visión general de los trabajos de transferencia actual. Puede actualizar y registrar listas de selección, iniciar y finalizar trabajos de transferencia y realizar otras tareas.
-   Tablero kanban para trabajos de proceso: este tablero se ha diseñado para admitir el flujo de producción normal y para proporcionar una descripción general de la situación actual en una o varias celdas de trabajo. En este tablero se pueden priorizar, seleccionar o fabricar kanbans. Este tablero también se ha diseñado para poder escanear códigos de barras para generar informes de kanbans.

## <a name="kanban-jobs-and-integration-with-finance-and-operations-processes"></a>Trabajos kanban e integración con procesos de Finance and Operations
Los trabajos kanban se integran completamente con los procesos actuales de las transacciones de inventario de Finance and Operations.
-   Puede realizar las actividades de picking para reabastecer el material utilizado para satisfacer los requisitos de los trabajos kanban.
-   Puede imprimir tarjetas kanban, tarjetas kanban de circulación y listas de picking para apoyar el uso de kanban. Estos documentos se usan para representar, seguir y registrar trabajos kanban en el almacén y en la planta de producción.
-   Puede registrar el picking y las actividades de transferencia de inventario mediante el escaneo de los códigos de barras.

Además, lean manufacturing apoya los procesos de compra y de facturación de los servicios a los que hacen referencia las actividades subcontratadas.
-   Puede asignar servicios y líneas de acuerdo de compra a las actividades subcontratadas.
-   Puede crear pedidos de compra y avisos de recepción periódicos para apoyar la compra y la facturación de los servicios.






