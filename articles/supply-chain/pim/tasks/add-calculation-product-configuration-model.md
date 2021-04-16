---
title: Agregar un cálculo a un modelo de configuración de producto
description: Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 268baa4b518f6df52d4393f7278a79cbe1733844
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812692"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]