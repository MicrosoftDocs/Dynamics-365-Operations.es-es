---
title: Visión general del estado de ciclo de vida de producto
description: El estado del ciclo de vida de un producto documenta el estado de ciclo de vida de un producto liberado o una variante del producto.
author: cvocph
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: c3674442dfec11afc26881f3e5c442ba05a4821b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813555"
---
# <a name="product-lifecycle-state-overview"></a>Visión general del estado de ciclo de vida de producto

[!include [banner](../includes/banner.md)]

El estado del ciclo de vida de un producto documenta el estado de ciclo de vida de un producto liberado o una variante del producto. Los estados del ciclo de vida de un producto están definidos por el usuario, normalmente administrador de producto o administrador de datos de producto maestro. Los procesos empresariales específicos, como planificación maestra, pueden verse afectados por una estado de ciclo de vida específico.   

Un producto liberado o una variante del producto se puede asociar con un estado de ciclo de vida del producto que documente en qué estado del ciclo de vida está un producto o una variante específica actualmente. Puede definir cualquier número de estados del ciclo de vida del producto asignando un nombre y una descripción al estado. Puede seleccionar un estado de ciclo de vida como el estado predeterminada para nuevos productos liberados. Las variantes del producto liberado heredan su estado del ciclo de vida del producto de su producto maestro liberado en el momento de la creación. Al cambiar el estado del ciclo de vida en un producto maestro liberado, puede elegir actualizar todas las variantes existentes que tengan el mismo estado original.  

## <a name="create-a-new-product-lifecycle-state"></a>Crear un nuevo estado de ciclo de vida de producto 

- Para crear un nuevo estado del ciclo de vida de un producto, reproduzca o lea la guía de tareas **Crear un nuevo estado del ciclo de vida de producto**. 

-  Para crear un estado del ciclo de vida de un producto predeterminado, reproduzca o lea la guía de tareas **Crear un estado del ciclo de vida de producto predeterminado**.   

## <a name="associate-product-lifecycle-states-to-released-products"></a>Asociar estados del ciclo de vida del producto a los productos liberados  

Existen diferentes métodos para asociar un estado del ciclo de vida de producto a los productos liberados o las variantes de producto.

-  En la creación de un nuevo producto liberado, el **Estado del ciclo de vida del producto** predeterminado se asigna automáticamente. 
-  En la liberación de un producto a una entidad jurídica, el **Estado del ciclo de vida del producto** predeterminado se asigna automáticamente. 
-  En la liberación de una variante del producto a una entidad jurídica, el **Estado del ciclo de vida del producto** asociado al producto maestro liberado en esta entidad jurídica se asigna automáticamente una variante nueva. 

Puede actualizar manualmente el estado del ciclo de vida del producto mediante: 

-    La página de lista de **Productos liberados** o **Vista de detalles**. 
-  La página de lista de **Variantes de productos liberados** o **Vista de detalles**. 
-  Busque los productos o las variantes de producto obsoleto basados en demanda y asocie un estado de ciclo de vida.  

Para obtener información detallada sobre cómo asociar a estados del ciclo de vida del producto, reproduzca o lea las dos siguientes guías de tareas.

-  Para asociar un estado de ciclo de vida del producto a un producto maestro liberado, reproduzca o lea la guía de tareas **Asignar un estado de ciclo de vida del producto a un producto maestro liberado**. 

-  Para asociar un estado de ciclo de vida del producto a un producto liberado, reproduzca o lea la guía de tareas **Asignar un estado de ciclo de vida del producto a un producto liberado**. 

## <a name="impact-on-master-planning"></a>Impacto en la planificación maestra 

El estado del ciclo de vida de producto sólo tiene una marca de control: **Está activo para la planificación**. De forma predeterminada, el campo se establece en **Sí** para todos los estados del ciclo de vida de producto creados, pero se puede cambiar a **No**. Cuando esté establecido en **No**, los productos liberados asociados o las variantes del producto liberado están: 

-  Excluidos de la planificación maestra. 
-  Excluidos del cálculo a nivel de LM. 

Para obtener información detallada sobre cómo usar el estado de ciclo de vida del producto para excluir productos de la planificación maestra y del cálculo a nivel de LM, reproduzca o lea la guía de tareas **Crear un estado de ciclo de vida del producto para excluir productos de la planificación maestra**.

> [!NOTE]
> Por motivos de rendimiento, se recomienda asociar todos los productos liberados o variantes del producto obsoletos, especialmente al trabajar con variantes de la configuración de productos no reutilizables , con un estado del ciclo de vida del producto que se desactive para la planificación maestra.  

## <a name="default-migration-import-and-export"></a>Migración, exportación e importación predeterminados 

Las entidades de datos no admiten los estados del ciclo de vida del producto y el estado del ciclo de vida no se puede establecer en un estado variable a través de las entidades de datos del producto liberado.

-  En la migración de las versiones anteriores, el estado del ciclo de vida de todos los productos y las variantes de producto estarán en blanco.  
-  Al importar los productos liberados a través de una entidad de datos, se aplicará estado del ciclo de vida predeterminado en la creación.  
-  Al importar variantes de producto liberado a través de una entidad de datos, se importará el estado del ciclo de vida del producto del producto maestro liberado.   

## <a name="find-obsolete-products-and-products-variants"></a>Busque los productos y las variantes de productos obsoletos 

Puede ejecutar un análisis de simulación para encontrar los productos liberados o las variantes de producto obsoletos y actualice su estado del ciclo de vida de producto. Para encontrar porductos obsoletos, reproduzca o lea la guía de tareas **Buscar productos liberados o las variantes de producto obsoletos y asignar un estado del ciclo de vida de producto**. Esta guía de tareas muestra cómo encontrar los productos liberados obsoletos o las variantes de producto y cómo asociar un estado de ciclo de vida del producto a los productos obsoleto. También muestra cómo ver los resultados de la simulación y evalua la cantidad de productos y variantes de producto se asociarán con un estado del ciclo de vida del nuevo producto al ejecutar la actualización sin la simulación.  

Al ejecutar el análisis en modo de simulación, los productos y las variantes de producto identificados como obsoletos se muestran en un formulario específico, donde se pueden revisar fácilmente. Las búsquedas de análisis para transacciones y datos maestros específicos para identificar los productos que no tienen ninguna demanda dentro de un período variable y ningún dato maestro que pueda resultar en demanda. Los nuevos productos liberados en un período variable se pueden excluir del análisis. Cuando la simulación de análisis devuelve el resultado esperado, el usuario puede ejecutar el análisis y establecer un estado del ciclo de vida del producto a todos los productos identificados como obsoletos por el análisis.  

> [!NOTE]
> Tenga en cuenta que todos los análisis y actualizaciones se deben hacer dentro de la misma entidad jurídica.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Criterios para seleccionar y actualizar productos liberados o variantes del producto 

Use los siguientes criterios para seleccionar y actualizar los productos liberados o variantes del producto: 

-    El estado del ciclo de vida de producto del producto o la variante del producto debe ser diferente deñ nuevo estado deseado. 
-  El producto o la variante del producto se ha creado hace algunos días basado en el número de días que se ha especificado en el cuadro de diálogo de selección. 
-  No hay pedidos de producción abiertos (= estado < terminado) del producto o la variante del producto. 
-  No existen transacciones de inventario abiertas (= problema del estado ReservPhysical a QuotationIssue o estado de recepción Registrered a QuotationReceipt) del producto o la variante del producto. 
-  No hay transacciones de inventario dentro del último número de días del producto o la variante del producto. 
-  No hay demanda futura o previsión de suministro del producto o la variante del producto.  
-  No se ha establecido ningún nivel mínimo de existencias en la cobertura de artículos para el producto o la variante del producto. 
-  Ninguna regla kanban de cantidad fija activa para el producto o la variante del producto.  
-  Ninguna línea de pedido de servicio para el producto o la variante del producto. 
-  No existen líneas de acuerdos de compra o ventas activos o futuros para el producto o la variante del producto. 
-  El producto o la variante del producto no se usa en una lista de materiales que esté asociada a una versión aprobada no caducada de lista de materiales para un producto o una variante que esté activo para la planificación.

## <a name="related-topics"></a>Temas relacionados

-  [Crear un nuevo estado de ciclo de vida de producto](tasks/new-product-lifecycle-state.md)
-  [Crear un estado predeterminado de ciclo de vida de producto](tasks/default-product-lifecycle-state.md)
-  [Asignar un estado de ciclo de vida de producto a un producto maestro liberado](tasks/product-lifecycle-state-released-product-master.md)
-  [Asignar un estado de ciclo de vida de producto a un producto liberado](tasks/product-lifecycle-state-released-product.md)
-  [Buscar las variantes de producto obsoletas y asignar un estado de ciclo de vida del producto](tasks/obsolete-product-variants.md)
-  [Crear un estado de ciclo de vida del producto para excluir productos de planificación maestra](tasks/exclude-products-master-planning.md)
