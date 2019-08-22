---
title: Dividir un activo fijo
description: Esta guía de la tarea va a dividir un porcentaje de un libro de activos a un nuevo libro de activos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8e5fdc8a7b326daca1fc0f0962c69bb8fb1ff64
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839722"
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

