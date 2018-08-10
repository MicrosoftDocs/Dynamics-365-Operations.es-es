--- 
title: "Crear criterios de selección de precios de venta"
description: "Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos."
author: ShylaThompson
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 59f6a4131f6a27c0089a1259e3f849f91a47bc87
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-price-selection-criteria"></a>Crear criterios de selección de precios de venta

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un criterio de selección del precio de ventas para los modelos de precio de ventas basados en atributos. Este procedimiento requiere que haya al menos un modelo de precio de ventas disponible. Este ejemplo usa el modelo de precio para el modelo de precio de ventas de la solución Altavoz en la empresa de los datos de demostración USMF. Normalmente, un responsable de productos utiliza este procedimiento.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Agregue un nuevo criterio para un modelo de precio de ventas existente
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Modelos de configuración del producto.
3. En la lista, seleccione la fila del modelo de producto de la solución Altavoz, pero no haga clic en el vínculo del nombre del modelo.
4. En el panel de acciones, haga clic en Modelo.
5. Haga clic en Criterios de modelo de precio.
6. Haga clic en Nuevo.
7. En el campo Nombre, escriba "Grupo de clientes 10".
    * El nombre del criterio del modelo de precios se usa para ayudar a identificar los criterios de selección subyacentes.  
8. En el campo Modelo de precio, especifique o seleccione un valor.
9. En el campo Tipo de pedido, seleccione Pedido de compra.
    * El tipo de pedido determina los campos de base de datos que estarán disponibles para la consulta de selección.  
10. Especifique una fecha en el campo Válido desde.
11. En el campo Vence el, especifique una fecha.
12. Haga clic en Guardar.

## <a name="create-the-query-for-the-selection-criteria"></a>Cree la consulta para los criterios de selección
1. Haga clic en Editar.
2. En el campo Tabla, seleccione Clientes. 
3. Seleccione Grupo de clientes en el campo Campo.
    * En este ejemplo, utilizaremos un grupo de clientes específico para los criterios de selección.  
4. En el campo Criterios, seleccione Grupo de clientes 10. 
5. Haga clic en Aceptar


