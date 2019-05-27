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
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9754c46010e7bbdb2edef0d6e68162f344bb1257
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570420"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Agregar un cálculo a un modelo de configuración de producto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos. Muestra cómo puede crear una expresión lógica mediante el operador "If" para establecer una altura de altavoz en 10 para los altavoces blancos y 15 para todos los demás acabados de armarios. El procedimiento usa el componente Altavoz superior en la empresa de demostración USMF.


## <a name="add-a-calculation"></a>Agregar un cálculo

## <a name="create-calculation-expression"></a>Crear expresión de cálculo
1. Haga clic en Editar expresión.
2. En el campo ConstraintBody, especifique "If[CabinetFinish=="White", 10, 15]".
3. Haga clic en Validar.
4. Haga clic en Cerrar.
5. Haga clic en Aceptar

