---
title: Atributos de lote
description: "Este artículo proporciona información acerca de los atributos de lote. Los atributos de lote son características de las materias primas y los productos terminados que componen los lotes de inventario. El artículo también explica cómo asignar atributos de lote y cómo puede buscar en ellos al reservar lotes."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f23040177394558e95a13d16885814e83e5ebf99
ms.lasthandoff: 03/31/2017


---

# <a name="batch-attributes"></a>Atributos de lote

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de los atributos de lote. Los atributos de lote son características de las materias primas y los productos terminados que componen los lotes de inventario. El artículo también explica cómo asignar atributos de lote y cómo puede buscar en ellos al reservar lotes.

Los atributos de lote son características de las materias primas y los productos terminados que componen los lotes de inventario. Los atributos de lote pueden variar en función de diversos factores, como las condiciones ambientales, la calidad de las materias primas usadas para producir el lote o el resultado del producto terminado. El número y los tipos de atributos de lote usados pueden variar mucho de una industria a otra. A continuación se muestran dos ejemplos de cómo usar los atributos de lote:

-   En la industria del queso, la leche, que es una de las materias primas usadas en la fabricación del queso, puede tener atributos como contenido graso y porcentaje en peso. El queso fabricado a partir de la leche puede tener otros atributos, como humedad y solera.
-   En la industria del acero, el hierro que se fabrica puede tener atributos como los porcentajes de contenido de magnesio, contenido de plata y contenido de cinc.

Para gestionar mejor la cantidad y los tipos de atributos, puede utilizar grupos de atributos de lote. De esta manera, no es necesario agregar cada atributo de manera individual.

## <a name="assign-batch-attributes"></a>Asignar atributos de lote
Puede asignar atributos de lote a productos individuales incluidos en lotes de inventario o puede asignarlos a productos asociados a clientes específicos. Para poder asignar un artículo de atributo de lote en el nivel de cliente, debe asignarlo primero en el nivel de producto. El producto debe tener la dimensión de lote configurada como **Activa** en el grupo de dimensiones de seguimiento. Para asignar un atributo de lote a un producto individual, use la página específica del producto. Si el atributo es específico de un producto para un cliente, use la página específica del cliente. Al agregar un atributo a un producto, también define otros parámetros. A continuación se incluyen algunos ejemplos:

-   Los intervalos mínimo y máximo de un atributo de tipo **Entero** o **Fracción**.
-   Las acciones de tolerancia para un atributo de tipo **Entero** o **Fracción**. Si el valor del atributo no está entre el mínimo y el máximo, la acción puede ser un mensaje de advertencia o un mensaje de error.
-   Es el valor de destino del atributo. Este valor es el valor óptimo del atributo y se aplica a todos los tipos de atributo.

Puede obtener acceso a las páginas de los productos que seleccione en la página **Productos emitidos** en Gestión de información de productos. Tras asignar atributos de lote a un producto, puede agregar valores específicos a los atributos en la página **Atributos de lote de inventario**.

## <a name="reserve-batches"></a>Reservar lotes
Puede buscar en atributos de lote al realizar las reservas de lote para un pedido de ventas para completar el pedido de un cliente o cuando selecciona y reserva lotes para un pedido de producción. Esta búsqueda ayuda a localizar un lote de inventario que contiene el producto con el atributo de lote que desea. Una vez localizado el lote o los lotes, puede reservar el producto en la línea de transacción de inventario de origen.




