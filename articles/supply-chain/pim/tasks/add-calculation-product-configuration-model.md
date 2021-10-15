---
title: Agregar un cálculo a un modelo de configuración de producto
description: Este procedimiento muestra cómo agregar un nuevo cálculo a un modelo de configuración de productos.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d201061ff47203f09f96dc08ff6fc8ac437a6f9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570666"
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