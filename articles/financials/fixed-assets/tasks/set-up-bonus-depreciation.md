--- 
title: "Configuración de la depreciación de bonificación"
description: "Este procedimiento muestra cómo crear un método de amortización por depreciación especial y asociarlo con un libro de activos fijos."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus, AssetGroup, AssetGroupBookSetup, AssetGroupSetupBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7e6ebb13084626b477b6e0b24acdc09e2c0d3d6d
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

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


