---
title: Ciclo de vida de la administración de modelos
description: Este tema describe formas de mantener los modelos de aprendizaje automático de su organización para optimizar las predicciones que generan.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 0b16cfdce801e8a63b47397526b47995018b99c9
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2021
ms.locfileid: "7594840"
---
# <a name="model-management-lifecycle"></a>Ciclo de vida de la administración de modelos

[!include [banner](../includes/banner.md)]

Este tema describe formas de mantener los modelos de aprendizaje automático de su organización para optimizar las predicciones que generan.

Le recomendamos que entrene el modelo de IA en un entorno de espacio aislado y luego utilice soluciones administradas para implementarlo en un entorno de producción. Este enfoque ayuda a garantizar que se implementen los controles correctos para administrar el ciclo de vida del modelo.

Debido a que el modelo de inteligencia artificial se basa en la factura disponible y los datos del cliente, es importante que el entorno de la zona de pruebas tenga una copia reciente de los datos de producción. Puede comenzar a entrenar su modelo siguiendo los pasos en [Utilice las predicciones de pago del cliente](use-customer-payment-predictions.md). Después de que el modelo haya sido reentrenado, evalúe los resultados como se describe en [Evaluar el modelo de predicción de pagos del cliente inicial](evaluate-payment-prediction.md). Utilice la información en [Mejorar el modelo de predicción](improve-model.md) para experimentar con combinaciones de funciones y filtros que pueden ayudar a mejorar el modelo.

Cuando esté satisfecho con los resultados del entrenamiento, siga los pasos en [Distribuya su modelo de IA](/ai-builder/distribute-model) para realizar la transición del modelo a su entorno de producción.
