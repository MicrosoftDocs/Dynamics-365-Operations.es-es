--- 
title: "Corrección de información de seguimiento de inventario"
description: "Este procedimiento le muestra el proceso de crear y registrar un diario de transferencia de inventario para corregir la información de seguimiento de inventario."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: caf8c67d315666edfffe86e459bc7a4478697f07
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="correct-inventory-tracking-information"></a>Corrección de información de seguimiento de inventario

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra el proceso de crear y registrar un diario de transferencia de inventario para corregir la información de seguimiento de inventario. En este ejemplo, actualizaremos la información de un artículo controlado por lote cambiando un lote registrado incorrectamente por otro lote. Puede revisar este procedimiento con los datos de prueba de la empresa USPI o utilizar sus propios datos. Si utiliza sus propios datos, debe tener un artículo habilitado para lotes y no debe estar controlado por ubicación. También necesita tener configurado un nombre de diario de inventario para las transferencias de inventario. Estas tareas las realizará normalmente el empleado del almacén.


## <a name="create-an-inventory-transfer-journal"></a>Creación de un diario de transferencias de inventario
1. Vaya a Transferir.
2. Haga clic en Nuevo.
3. En el campo Nombre, especifique o seleccione un valor.
4. Haga clic en Aceptar

## <a name="create-journal-lines"></a>Creación de líneas de diario
1. Haga clic en Nuevo.
2. En el campo Número de artículo, especifique o seleccione un valor.
    * Si utiliza USPI, seleccione el artículo M5003.  
3. En el campo Cantidad, especifique un número.
4. Haga clic en la ficha Dimensiones de inventario.
5. En el campo Número de lote, especifique o seleccione un valor.
6. En el campo Sitio, especifique o seleccione un valor.
7. En el campo Almacén, especifique o seleccione un valor.
8. En el campo Número de lote, especifique o seleccione un valor.

## <a name="post-the-journal"></a>Registrar el diario
1. Haga clic en Registrar.
2. Haga clic en Aceptar

## <a name="check-tracing-information"></a>Comprobar la información de seguimiento
1. Haga clic en Inventario.
2. Haga clic en Seguimiento.
3. Haga clic en Aceptar
    * Con esta información de seguimiento puede rastrear desde qué lote corrigió el inventario.  También puede usar la página Seguimiento de artículos para ver esta información.  
4. Cierre la página.

## <a name="check-inventory-transactions"></a>Comprobar las transacciones del inventario
1. Haga clic en Inventario.
2. Haga clic en Transacciones.
    * Aquí puede ver las transacciones creadas al registrar el diario.   


