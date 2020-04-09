---
title: Transferencia del inventario físico en el almacén
description: Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 899701413814ce38a4367618ed72d1039eca0bf8
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148179"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Transferencia del inventario físico en el almacén

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra. Antes de comenzar, necesita tener configurado un nombre de diario de inventario para las transferencias de inventario. Puede revisar este procedimiento en la empresa de demostración USMF con los valores de ejemplo mostrados o puede usar sus propios datos si tiene productos y ubicaciones configurados. Estas tareas las realizará normalmente el empleado del almacén.


## <a name="create-an-inventory-transfer-journal"></a>Creación de un diario de transferencias de inventario
1. En el **Panel de exploración**, vaya a **Gestión de inventarios > Movimientos del diario > Artículos > Transferencia**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, especifique o seleccione un valor.
4. Haga clic en **Aceptar**. Existe la opción de especificar las dimensiones "De" y "A" para cada línea de diario. Estas son esenciales para este tipo de diario. Puede transferir los artículos a las ubicaciones mediante distintas reglas. En este ejemplo transferiremos un artículo dentro del mismo almacén, de una ubicación controlada mediante matrícula de entidad de almacén a una ubicación que no se controla mediante matrículas de entidad de almacén.   

## <a name="create-journal-lines"></a>Crear líneas de diario
1. En la **Ficha desplegable Líneas de diario**, haga clic en **Nuevo**.
2. En el campo **Número de artículo**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "A0001".  
3. En el campo **Sitio de origen**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "2".  
4. En el campo **Sitio de destino**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "2".  
5. En el campo **Almacén de origen**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "24".  
6. En el campo **Almacén de destino**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "24".  
7. En el campo **Ubicación de origen**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "FL-001".  
8. En el campo **Ubicación de destino**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "BULK-001".  
9. En el campo **Cantidad**, especifique un número.
10. En la ficha desplegable **Detalles de línea**, haga clic en la pestaña **Dimensiones de inventario**.
11. En **Desde dimensiones de inventario**, en el campo **Matrícula**, especifique o seleccione un valor. Si está usando USMF, puede seleccionar "24".  
12. Haga clic en **Guardar**.

## <a name="post-the-inventory-transfer-journal"></a>Registrar el diario de transferencias de inventario
1. En el **panel de acciones**, haga clic en **Publicar**.
2. Haga clic en **Aceptar**.

## <a name="view-inventory-transactions"></a>Ver transacciones de inventario
1. Haga clic en **Inventario**.
2. Haga clic en **Transacciones**. Aquí puede ver las transacciones creadas al registrar el diario.  

