---
title: Modelar una organización eficiente
description: El artículo proporciona información sobre los conceptos clave en los modelos de una organización lean.
author: cvocph
manager: tfehr
ms.date: 09/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, KanbanFlowSelection, KanbanFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 960ba8851810ff528581144ad863772f18f9fa79
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985898"
---
# <a name="modeling-a-lean-organization"></a>Modelar una organización eficiente

[!include [banner](../includes/banner.md)]

El artículo proporciona información sobre los conceptos clave en los modelos de una organización lean. 

Normalmente, una situación de lean manufacturing suele ser superior a únicamente una colección de reglas kanban o de directivas de suministro de material sin relación. El flujo de materiales y productos en las celdas de trabajo y las ubicaciones para una situación de producción o de suministro específicas se pueden describir como una secuencia o pequeña red de proceso o de actividades de transferencia. Esta secuencia o red se conoce como flujo de producción.

## <a name="production-flows-in-lean-manufacturing"></a>Flujos de producción en lean manufacturing
En las situaciones de producción que se basan en pedidos de producción, el material se emite a un pedido de producción específico. Durante una secuencia de operaciones que se basan una lista de materiales (L. Mat) y las rutas, los productos se crean y finalmente se reciben en la ubicación proporcionada. El tiempo de capacidad de proceso de pedidos de producción varía de minutos a semanas. Todo el coste, material y trabajo relacionado se acumula en el pedido de producción. 

Para reducir el plazo de entrega y el exceso de inventario entre los centros de trabajo que causa la producción de lote, la lean manufacturing coloca el reabastecimiento de kanban y los supermercados en el reabastecimiento del almacén y la fabricación. Normalmente, estas características interrumpen normalmente la producción de ciclos parcialmente independientes de kanban. El reabastecimiento de un kanban para un producto semiterminado ya no se activa por un pedido para un producto terminado. 

Para restablecer el contexto de producción y de coste para las distintas situaciones de kanban que se proponen, los flujos de producción basados en actividad que se han introducido como la espina dorsal de lean manufacturing. Todas las reglas kanban hacen referencia a esta estructura predefinida. El modelo basado en la actividad admite la configuración de una gran variedad de escenarios. Sin embargo, este modelo no agrega complejidad para los trabajadores de planta, porque todas las situaciones usan la mismo interfaz de usuario basada en actividades.

## <a name="semi-finished-products-non-bom-levels"></a>Productos semiterminados (no a niveles de L. MAT)
La lean manufacturing integra kanbans para los productos a los que se le ha realizado un inventario y productos semiterminados en un único período, y por tanto ofrece una experiencia unificada de usuario para todos los casos. Debido a la arquitectura, ya no se tienen que introducir los niveles adicionales de L. MAT para permitir que se usen los kanbans para productos semiterminados. Esta arquitectura también ayuda a reducir las transacciones de inventario al mínimo.

## <a name="products-and-material-in-work-in-progress"></a>Productos y materiales en el trabajo en curso
La reducción de los tamaños de lote al estado ideal de un único flujo de la parte de lean manufacturing (producción ajustada) puede provocar un aumento dramático de las transacciones de inventario si cada proceso de selección o registro de kanban provoca transacciones para los artículos consumidos. La arquitectura del flujo de producción permite la transferencia de material al flujo de producción junto con los kanbans de retirada en tamaños de la unidad de gestión de material de transporte o almacenamiento. El valor del material enviado se agrega a la cuenta de trabajo en curso relacionada con el flujo de producción. Este comportamiento es similar al comportamiento del material que se emite a un pedido de producción. El mismo principio se puede aplicar a productos y productos semiterminados. A menos que se creen, se transfieran o se consuman estos productos dentro de un flujo de producción, las transacciones de inventario son opcionales. Una vez que los productos se registran en el inventario, el trabajo en curso para el flujo de producción se reduce deduciendo el coste estándar relacionado.

## <a name="value-streams-and-value-stream-mapping"></a>Flujos de valor y asignación del flujo de valor
La arquitectura de lean manufacturing está inspirada en los cinco principios Lean formulados por Womack y Jones: valor del cliente, flujo de valor, flujo, extracción y perfección. Un método aprobado para implementar soluciones de lean manufacturing en el mundo físico de la fabricación es la asignación del flujo de valor (VSM). Este método lo introdujeron Rother y Shook en su publicación “Aprender a ver” en el instituto de lean manufacturing. 

El flujo de valor en estado futuro se puede modelar como una versión del flujo de producción. Todos los procesos del flujo de valor se modelan como actividades de proceso. Los movimientos o transferencias se pueden modelar como actividades de transferencia si se debe registrar el estado de la transferencia o si se necesita una integración con la selección de inventario o envíos consolidados. 

El flujo de valor en sí se modela como unidad operativa. Por lo tanto, el flujo de valor se puede usar como dimensión financiera.

Para obtener más información sobre cómo crear unidades operativas, vea [Crear una unidad operativa](../../fin-and-ops/organization-administration/tasks/create-operating-unit.md).

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>Gestión de costes de lean manufacturing en función del flujo de producción
La consolidación periódica del coste para un flujo de producción corrige la cuenta relacionada de trabajo en curso y habilita la determinación de las desviaciones de los productos que se proporcionan por el flujo de producción.

## <a name="continuous-improvement"></a>Actualización continua
Para mejorar la actualización continua, los flujos de producción se ejecutan en versiones de tiempo de vigencia. Por tanto, una versión de flujo de producción existente, junto con todas las reglas kanban relacionadas, se pueden copiar en una versión futura del flujo de producción. Además, el flujo de producción de estado futuro se puede modelar antes de validarse y activarse para producción. Para ayudar a garantizar un flujo de material constante en la fecha de la transición y más allá, los kanbans existentes de versiones anteriores del flujo de producción están relacionados automáticamente con la nueva versión.

## <a name="simplicity"></a>Simplicidad
Para la implementación de lean manufacturing (producción ajustada), hemos elegido el flujo de producción y el de la actividad que permite modelar situaciones simples y complejas de producción en una sola arquitectura escalable. Un análisis más detallado del concepto de actividad revela una nueva simplicidad para los usuarios que realmente la necesitan: los trabajadores de planta y de logística. Notificando con trabajos basados en actividad en lugar de transacciones de inventario, una interfaz de usuario unificada para todas las variantes de lean manufacturing (producción ajustada) transfiere la complejidad de negocio de la interfaz de usuario al que pertenece: el flujo de producción como la espina dorsal de lean manufacturing (producción ajustada).



