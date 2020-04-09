---
title: Agregar un cálculo a un modelo de configuración de producto
description: Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55f8fcfdafb2d5fb5a4d4800221fabf4b2111f86
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150272"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Agregar un cálculo a un modelo de configuración de producto

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos. Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios. El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.


## <a name="add-a-calculation"></a>Agregar un cálculo

## <a name="create-calculation-expression"></a>Crear expresión de cálculo
1. Haga clic en Editar expresión.
2. En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".
3. Haga clic en Validar.
4. Haga clic en Cerrar.
5. Haga clic en Aceptar

