--- 
title: Dividir un activo fijo
description: "Esta guía de la tarea va a dividir un porcentaje de un libro de activos a un nuevo libro de activos."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="split-a-fixed-asset"></a>Dividir un activo fijo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea va a dividir un porcentaje de un libro de activos a un nuevo libro de activos.  Usa el rol de contable y los datos de prueba de USMF.


## <a name="create-a-new-fixed-asset"></a>Crear un activo fijo nuevo
1. Vaya a Activos fijos > Activos fijos > Activos fijos.
2. Haga clic en Nuevo.
3. En el campo Grupo de activos fijos, escriba o seleccione un valor.
4. Anote el número de activo fijo que se va a usar en el proceso de división más adelante.
5. En el campo Nombre, escriba un valor.
6. Cierre el formulario.

## <a name="split-a-fixed-asset"></a>Dividir un activo fijo
1. En la lista, busque y seleccione el activo fijo para dividir.
2. En la lista, haga clic en el vínculo de la fila seleccionada.
3. Haga clic en Libros.
    * Seleccione el libro para dividir el nuevo activo.  
4. Haga clic en Funciones.
5. Haga clic en Dividir activo fijo.
6. En el campo Hasta activo fijo, escriba o seleccione un valor.
7. En el campo Al libro, haga clic en el botón desplegable para abrir la búsqueda.
8. En el campo Fecha de transacción, especifique una fecha.
9. En el campo Porcentaje, especifique un número.
10. En el campo Nombre del diario, especifique o seleccione un valor.
11. Haga clic en Aceptar

## <a name="post-the-journal-transaction"></a>Registrar la transacción de diario
1. Vaya a Activos fijos > Movimientos de diario > Diario de activos fijos.
2. En la lista, seleccione el diario creado con el proceso de la división.
3. Haga clic en Líneas.
    * Compruebe las líneas de diario creadas.  Se creó una transacción de ajuste de adquisición para que el activo original reduzca el valor en el porcentaje especificado durante el proceso de la división.  Se crea una transacción de adquisición del nuevo activo para el mismo importe.  
4. Haga clic en Registrar.


