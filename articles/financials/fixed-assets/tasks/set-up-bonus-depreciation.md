---
title: Configuración de la depreciación de bonificación
description: Este procedimiento muestra cómo crear un método de amortización por depreciación especial y asociarlo con un libro de activos fijos.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6bbd6b78d05fcc9d95f6e6409db2619a210ad760
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "339220"
---
# <a name="set-up-bonus-depreciation"></a>Configuración de la depreciación de bonificación

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo crear un método de amortización por depreciación especial y asociarlo con un libro de activos fijos. Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.


## <a name="create-a-special-depreciation-allowance"></a>Crear un método de amortización por depreciación especial
1. Vaya a Activos fijos > Configuración > Método de amortización por depreciación especial.
2. Haga clic en Nuevo.
3. En el campo Método de amortización por depreciación especial, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Porcentaje, especifique un número.
    * Defina un importe si no se ha indicado ningún porcentaje.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Asociar un método de amortización por depreciación especial con un libro del grupo de activos fijos
1. Vaya a Activos fijos > Configuración > Grupos de activos fijos.
2. En la lista, seleccione el grupo de activos fijos que se asociará con el método de amortización por depreciación especial.
3. Haga clic en Libros.
4. En la lista, seleccione el libro asociado al método de amortización por depreciación especial.
5. Haga clic en Método de amortización por depreciación especial.
6. Haga clic en Nuevo.
7. En el campo Método de amortización por depreciación especial, escriba o seleccione un valor.
    * El porcentaje o el importe predeterminado proviene de la configuración del método de amortización por depreciación especial.  
8. En el campo Prioridad, especifique un número.

