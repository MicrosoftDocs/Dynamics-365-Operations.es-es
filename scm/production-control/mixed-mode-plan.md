---
title: El modo mixto planificados - combine discreto, el proceso, y la compra de componentes lean
description: "Este artículo proporciona información acerca de la planificación modo mezcla. En la planificación modo mezcla, puede modelar la cadena de suministros en función del flujo de materiales. El Microsoft Dynamics 365 para las operaciones se asegura de que el flujo de material siga los modelos, independientemente de la directiva de suministro seleccionada (los kanbans, los pedidos de producción, pedidos de compra, pedidos de lote, o pedidos de transferencia)."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d635421112f6d1e79a47090de3ffc4178b36b132
ms.lasthandoff: 03/31/2017


---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>El modo mixto planificados - combine discreto, el proceso, y la compra de componentes lean

Este artículo proporciona información acerca de la planificación modo mezcla. En la planificación modo mezcla, puede modelar la cadena de suministros en función del flujo de materiales. El Microsoft Dynamics 365 para las operaciones se asegura de que el flujo de material siga los modelos, independientemente de la directiva de suministro seleccionada (los kanbans, los pedidos de producción, pedidos de compra, pedidos de lote, o pedidos de transferencia). 

Puede seleccionar la estrategia completa para suministrar un producto, independientemente de la estructura de producto.  

Por ejemplo, puede tener control de kanban en el ensamblado, donde los materiales se abastecen para la zona de montaje por pedidos de producción, kanban, transferencias, pedidos de lote o cualquier combinación que sea adecuada para las características de la cadena de suministro, pero puede seguir teniendo visibilidad completa de los suministros. Esta capacidad conduce a procesos de cadena de suministro optimizados y la visibilidad en la cadena de suministro aumenta.  

La granularidad de las directivas de suministro que se usan en la programación maestra depende de las dimensiones de almacenamiento que se habilitan como dimensiones de cobertura. Para permitir que la programación maestra controle el reabastecimiento y el suministro de distintos tipos de ubicaciones (por ejemplo, separando la planta de producción para distintas unidades de producción o separando diferentes tipos de materiales y almacenes de mercancías terminadas), se recomienda que habilite el sitio y el almacén como dimensiones de cobertura. De manera alternativa, el almacén se puede anular como dimensión de cobertura. En ese caso, cuando se usa la gestión de almacenes avanzada, todos los movimientos dentro de un almacén se controlan por el trabajo del almacén, mientras que todos los movimientos de un almacén a otro pueden ser controlados por kanban de retirada.

## <a name="supply-policies"></a>Directivas de suministro
Dinámica 365 de los controles de planificación de modo mixto de las operaciones cómo se proporciona un producto y, en función de la fuente, cómo se emiten los requisitos derivados (consumo de artículos de una lista de materiales \[\]MAT). Según el tipo de pedido, el sistema automáticamente suministra materiales para que coincidan con los requisitos.  

Las directivas de suministro se pueden definir en el nivel de producto o en cualquier granularidad que admita sus requisitos. La granularidad de las directivas de suminsitro se definen en la página **Configuración de pedido predeterminada **.  

Las directivas de suministro pueden ser controladas por producto, dimensiones de artículo (configuración, color y tamaño), sitio y almacén. Esta configuración se realiza en la página **Cobertura de artículos **.  

El tipo de pedido predeterminado controla lo que genera la planificación maestra del pedido.  

Independientemente de cómo se de modelo la cadena de suministro, Dynamics 365 para las operaciones admite la combinación de directivas de suministro. Puede tener pedidos de producción que se suministran desde kanbans. Como alternativa, puede tener un pedido de lote que requiera que un producto se suministre por transferencias o por kanbans.  

La Dynamics 365 para las operaciones se asegura de que el flujo de material siga el modelo.  

El almacén para seleccionar el material se asigna dinámicamente en el tiempo de ejecución, después de que se haya definido la directiva de suminsitro.  

Normalmente, los kanbans no se crean para fechas futuras, ya que un kanban tiene un ciclo de vida corto. Para mantener visibilidad completa en la cadena de suministro, hemos introducido el nuevo concepto de planificación de un “kanban planificado,” que se usa para calcular los requisitos derivados y ayuda a garantizar que los requisitos se suministran en base a la misma lógica que se usa cuando se crea el kanban real.  

La misma lógica está presente para el resto de los tipos de directivas de suministro. Por lo tanto, la planificación a largo plazo de los materiales se basa en la misma lógica que espera ejecutar con los pedidos reales después de a aprobación de la producción y el suministro.

## <a name="materials-allocation-crosssupply-policy--resource-consumption-on-boms"></a>Desde el material de la asignación directiva crosssupply – consumo de recursos en las listas de materiales
El consumo de recursos es una función importante. El consumo de recursos permite seleccionar dinámicamente un almacén para seleccionar materiales, en función de la directiva de suministros (tipo de pedido), y también hace que el mantenimiento de datos base sea más fácil.  

El consumo de recursos requiere que el almacén en el que se seleccionan los materiales se asigne en base a la forma en que se suministra el producto. Es decir, en el tiempo de ejecución, el sistema encuentra los recursos que se usarán para la fabricación. Swgún estos recursos, el sistema encuentra el almacén de selección.  

Para el trabajo que es independiente de una directiva de suministro, no es necesario modificar la información en la L. MAT. si se cambia el suministro. Para los cambios ad hoc, Dynamics 365 para las operaciones garantiza que los materiales se originario de almacén derecho.

## <a name="process-manufacturing--the-production-type"></a>Fabricación en procesos: el tipo de producción
Para mayor flexibilidad completa en modo mixto, recomendamos que utilice el tipo de producción MAT para todos los productos. Puede utilizar pedidos de producción, kanban, pedidos de transferencia, pedidos de compra o de suministrar un producto. Para la fabricación de procesos, debe usar un tipo de proceso de **Fórmula**, **Coproducto**, **Producto derivado** o **Artículo de planificación**. Los kanbans y los pedidos de producción no se pueden usar para estos tipos de producción.


