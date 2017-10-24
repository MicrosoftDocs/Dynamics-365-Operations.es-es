---
title: "Transferencia del inventario físico en el almacén"
description: "Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bfba69731a4897906d08ff9fb9ce69e79121efeb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a>Transferencia del inventario físico en el almacén

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra. Antes de comenzar, necesita tener configurado un nombre de diario de inventario para las transferencias de inventario. Puede revisar este procedimiento en la empresa de demostración USMF con los valores de ejemplo mostrados o puede usar sus propios datos si tiene productos y ubicaciones configurados. Estas tareas las realizará normalmente el empleado del almacén.


## <a name="create-an-inventory-transfer-journal"></a>Creación de un diario de transferencias de inventario
1. Vaya a Transferir.
2. Haga clic en Nuevo.
3. En el campo Nombre, especifique o seleccione un valor.
4. Haga clic en Aceptar
    * Existe la opción de especificar las dimensiones "De" y "A" para cada línea de diario. Estas son esenciales para este tipo de diario. Puede transferir los artículos a las ubicaciones mediante distintas reglas. En este ejemplo transferiremos un artículo dentro del mismo almacén, de una ubicación controlada mediante matrícula de entidad de almacén a una ubicación que no se controla mediante matrículas de entidad de almacén.   

## <a name="create-journal-lines"></a>Creación de líneas de diario
1. Haga clic en Nuevo.
2. En el campo Número de artículo, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "A0001".  
3. En el campo Sitio de origen, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "2".  
4. En el campo Sitio de destino, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "2".  
5. En el campo Desde almacén, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "24".  
6. En el campo Hasta almacén, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "24".  
7. En el campo Desde ubicación, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "FL-001".  
8. En el campo Ubicación de destino, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "BULK-001".  
9. En el campo Cantidad, especifique un número.
10. Haga clic en la ficha Dimensiones de inventario.
11. En el campo Número de licencia, especifique o seleccione un valor.
    * Si está usando USMF, puede seleccionar "24".  
12. Haga clic en Guardar.

## <a name="post-the-inventory-transfer-journal"></a>Registrar el diario de transferencias de inventario
1. Haga clic en Registrar.
2. Haga clic en Aceptar

## <a name="view-inventory-transactions"></a>Ver transacciones de inventario
1. Haga clic en Inventario.
2. Haga clic en Transacciones.
    * Aquí puede ver las transacciones creadas al registrar el diario.  

