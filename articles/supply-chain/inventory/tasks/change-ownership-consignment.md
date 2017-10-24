---
title: "Cambiar la propiedad del inventario de entrega en base a la demanda de la producción"
description: "Este procedimiento muestra cómo cambiar el propietario del inventario de entrega del proveedor a su entidad jurídica cuando hay demanda del inventario en producción."
author: perlynne
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5925f5423d596adc4326dfff4734de2afd80b5a8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Cambiar la propiedad del inventario de entrega en base a la demanda de la producción

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo cambiar el propietario del inventario de entrega del proveedor a su entidad jurídica cuando hay demanda del inventario en producción. Este cambio de propiedad se hace creando y registrando un diario de cambio de propiedad del inventario. Las líneas de diario de cambio de propiedad se pueden crear manualmente o, tal como se muestra en este registro, en función de la demanda existente de la producción. Normalmente, un supervisor de planta realiza esta tarea. Puede utilizar este procedimiento en la empresa de demostración USMF o en sus propios datos. Si utiliza sus propios datos, asegúrese de que tiene los requisitos previos siguientes: un nombre de diario de inventario que se ha configurado para el cambio de propiedad de inventario, artículos disponibles propiedad del proveedor registrados físicamente y una o más líneas de pedido de producción del material. Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="create-an-inventory-ownership-journal"></a>Crear un diario de propiedad de inventario
1. Ir a Gestión del inventario > Entradas de diario > Artículos > Cambio de propiedad de inventario.
2. Haga clic en Nuevo.
    * El diario de cambio de propiedad de inventario se usa para cambiar el propietario del inventario de entrega del proveedor a la entidad jurídica actual. Este cambio de propiedad se hace liberando el inventario disponible propiedad del proveedor y posteriormente recibiendo ese inventario en la entidad jurídica actual.  
3. En el campo Nombre, especifique o seleccione un valor.
    * Solo puede seleccionar los nombres de diarios de inventario que tengan el tipo de diario Cambio de propiedad.  
4. Haga clic en Aceptar
5. Haga clic en Funciones.
6. Haga clic en Crear líneas de diario a partir de pedidos de producción.
    * Puede iniciar el proceso de cambio de propiedad si consulta todas las líneas de producción que tienen demanda de consumo de materias primas.  
7. En el campo Estados de emisión de inventario que incluir, seleccione una opción.
    * Esta opción permite filtrar por el estado de emisión de las transacciones de inventario. Por ejemplo, puede crear líneas de diario para el inventario con los estados Seleccionado y Física reservada.  
8. Expanda la sección Registros que incluir.
    * Esta sección le permite aplicar filtrado adicional. Por ejemplo, puede seleccionar una fecha específica de la materia prima.  
9. Haga clic en Aceptar

## <a name="post-the-inventory-ownership-change-journal"></a>Registrar el diario de cambio de propiedad de inventario
1. Haga clic en Registrar.
    * Cuando se registra el diario, el inventario propiedad del proveedor se libera usando la referencia "Cambio de propiedad". El inventario se recibe como disponible usando una transacción de inventario que se actualiza con una recepción de producto del pedido de compra. Tenga en cuenta que sólo se crean las transacciones relacionadas con el diario registrado. No se crean transacciones de inventario previstas.  
2. Haga clic en Aceptar
3. Cierre la página.

