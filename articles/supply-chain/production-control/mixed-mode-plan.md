---
title: "Planificación modo mezcla: combinar abastecimiento producción ajustada, proceso y discreto"
description: "Este tema proporciona información acerca de la planificación modo mezcla."
author: cvocph
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 52931
ms.assetid: 2e8b5fd1-cee9-45da-a3ae-6961fb020b89
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bb8fa816d48ee808b92a5bf80c2c39c51f33a195
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="mixed-mode-planning---combine-discrete-process-and-lean-sourcing"></a>Planificación modo mezcla: combinar abastecimiento producción ajustada, proceso y discreto

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de la planificación modo mezcla. En la planificación modo mezcla, puede modelar la cadena de suministros en función del flujo de materiales. Microsoft Dynamics 365 for Finance and Operations garantiza que el flujo de materiales siga sus modelos, independientemente de la directiva de suministro seleccionada (kanbans, pedidos de producción, pedidos de compra, pedidos de lote o pedidos de transferencia). 

Puede seleccionar la estrategia completa para suministrar un producto, independientemente de la estructura de producto.  

Por ejemplo, puede tener control de kanban en el ensamblado, donde los materiales se abastecen para la zona de montaje por pedidos de producción, kanban, transferencias, pedidos de lote o cualquier combinación que sea adecuada para las características de la cadena de suministro, pero puede seguir teniendo visibilidad completa de los suministros. Esta capacidad conduce a procesos de cadena de suministro optimizados y la visibilidad en la cadena de suministro aumenta.  

La granularidad de las directivas de suministro que se usan en la programación maestra depende de las dimensiones de almacenamiento que se habilitan como dimensiones de cobertura. Para permitir que la programación maestra controle el reabastecimiento y el suministro de distintos tipos de ubicaciones (por ejemplo, separando la planta de producción para distintas unidades de producción o separando diferentes tipos de materiales y almacenes de mercancías terminadas), se recomienda que habilite el sitio y el almacén como dimensiones de cobertura. De manera alternativa, el almacén se puede anular como dimensión de cobertura. En ese caso, cuando se usa la gestión de almacenes avanzada, todos los movimientos dentro de un almacén se controlan por el trabajo del almacén, mientras que todos los movimientos de un almacén a otro pueden ser controlados por kanban de retirada.

## <a name="supply-policies"></a>Directivas de suministro
La planificación modo mezcla de Finance and Operations controla el modo de suministrar un producto y, en función del suministro, el modo de emisión de los requisitos derivados (consumo de artículos de una lista de materiales \[L. MAT\]). Según el tipo de pedido, el sistema automáticamente suministra materiales para que coincidan con los requisitos.  

Las directivas de suministro se pueden definir en el nivel de producto o en cualquier granularidad que admita sus requisitos. La granularidad de las directivas de suminsitro se definen en la página **Configuración de pedido predeterminada**.  

Las directivas de suministro pueden ser controladas por producto, dimensiones de artículo (configuración, color y tamaño), sitio y almacén. Esta configuración se realiza en la página **Cobertura de artículos**.  

El tipo de pedido predeterminado controla lo que genera la planificación maestra del pedido.  

Independientemente de cómo se modele de la cadena de suministro, Finance and Operations admite la combinación de directivas de suministro. Puede tener pedidos de producción que se suministran desde kanbans. Como alternativa, puede tener un pedido de lote que requiera que un producto se suministre por transferencias o por kanbans.  

Finance and Operations garantiza que el flujo de material siga el modelo.  

El almacén para seleccionar el material se asigna dinámicamente en el tiempo de ejecución, después de que se haya definido la directiva de suminsitro.  

Normalmente, los kanbans no se crean para fechas futuras, ya que un kanban tiene un ciclo de vida corto. Para mantener visibilidad completa en la cadena de suministro, hemos introducido el nuevo concepto de planificación de un “kanban planificado,” que se usa para calcular los requisitos derivados y ayuda a garantizar que los requisitos se suministran en base a la misma lógica que se usa cuando se crea el kanban real.  

La misma lógica está presente para el resto de los tipos de directivas de suministro. Por lo tanto, la planificación a largo plazo de los materiales se basa en la misma lógica que espera ejecutar con los pedidos reales después de a aprobación de la producción y el suministro.

## <a name="materials-allocation-cross-supply-policy--resource-consumption-on-boms"></a>Directiva de suministros cruzados de la asignación de los materiales: consumo de recursos de L. MAT.
El consumo de recursos es una funcionalidad importante. El consumo de recursos permite seleccionar dinámicamente un almacén para seleccionar materiales, en función de la directiva de suministros (tipo de pedido), y también hace que el mantenimiento de datos base sea más fácil.  

El consumo de recursos requiere que el almacén en el que se seleccionan los materiales se asigne en base a la forma en que se suministra el producto. Es decir, en el tiempo de ejecución, el sistema encuentra los recursos que se usarán para la fabricación. Swgún estos recursos, el sistema encuentra el almacén de selección.  

Para el trabajo que es independiente de una directiva de suministro, no es necesario modificar la información en la L. MAT. si se cambia el suministro. Para los cambios ad hoc, Finance and Operations garantiza que los materiales se suministren del almacén adecuado.

## <a name="process-manufacturing--the-production-type"></a>Fabricación en procesos: el tipo de producción
Para una flexibilidad completa en modo mezcla, se recomienda usar las L. MAT. del tipo de producción para todos los productos. Puede usar pedidos de producción, kanbans, pedidos de transferencia o pedidos de compra para el suministro de un producto. Para la fabricación de procesos, debe usar un tipo de proceso de **Fórmula**, **Coproducto**, **Producto derivado** o **Artículo de planificación**. Los kanbans y los pedidos de producción no se pueden usar para estos tipos de producción.




