---
title: Configuración de libros depreciación (mayo de 2016)
description: Esta guía de la tarea creará un nuevo libro de amortización y lo asociará a un grupo de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6840e211847494598a81cd3228dbd3796447e18c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839866"
---
# <a name="set-up-depreciation-books-may-2016"></a>Configuración de libros depreciación (mayo de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de la tarea creará un nuevo libro de amortización y lo asociará a un grupo de activos fijos.  Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.


## <a name="create-a-depreciation-book"></a>Crear un libro de amortización
1. Vaya a Activos fijos > Configuración > Libros amortización.
2. Haga clic en Nuevo.
3. En el campo Libro amortización, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Active o desactive la casilla Calcular depreciación.
6. En el campo Método de depreciación, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el método de depreciación deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Método de depreciación alternativo, haga clic en el botón desplegable para abrir la búsqueda.
10. En la lista, seleccione el método de depreciación deseado.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
    * El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales. Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.  
12. Active o desactive la casilla Crear ajustes de depreciación con ajustes de base.
13. En el campo Calendario, haga clic en el botón desplegable para abrir la búsqueda.
14. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Asociar el libro de amortización con un grupo de activos fijos
1. Haga clic en Grupos de activos fijos.
2. En el campo Grupo de activos fijos, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Convención de amortizaciones, seleccione una opción.
6. En el campo Tiempo de vida, especifique un número.
    * Tenga en cuenta que el valor del campo Períodos de depreciación se calcula después de definir el tiempo de vida.  

