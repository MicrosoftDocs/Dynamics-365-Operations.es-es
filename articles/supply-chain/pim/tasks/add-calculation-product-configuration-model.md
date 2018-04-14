--- 
title: "Agregar un cálculo a un modelo de configuración de producto"
description: "Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2db8fb922b085a7f118822ef4fd974ac338f4d99
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Agregar un cálculo a un modelo de configuración de producto

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos. Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios. El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.


## <a name="add-a-calculation"></a>Agregar un cálculo

## <a name="create-calculation-expression"></a>Crear expresión de cálculo
1. Haga clic en Editar expresión.
2. En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".
3. Haga clic en Validar.
4. Haga clic en Cerrar.
5. Haga clic en Aceptar


