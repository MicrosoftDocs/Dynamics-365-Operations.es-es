---
title: Ciclo de vida de administración de modelos (vista previa)
description: Este tema describe formas de mantener los modelos de aprendizaje automático de su organización para optimizar las predicciones que generan.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: d5566bde97a2e60d050f4a7b499b554df4848bf9
ms.sourcegitcommit: f6050b444e636ba662c00d0443c94a99f8ea0b0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309799"
---
# <a name="model-management-lifecycle-preview"></a>Ciclo de vida de administración de modelos (vista previa)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema describe formas de mantener los modelos de aprendizaje automático de su organización para optimizar las predicciones que generan.

Le recomendamos que entrene el modelo de IA en un entorno de espacio aislado y luego utilice soluciones administradas para implementarlo en un entorno de producción. Este enfoque ayuda a garantizar que se implementen los controles correctos para administrar el ciclo de vida del modelo.

Debido a que el modelo de inteligencia artificial se basa en la factura disponible y los datos del cliente, es importante que el entorno de la zona de pruebas tenga una copia reciente de los datos de producción. Puede comenzar a entrenar su modelo siguiendo los pasos en [Utilice las predicciones de pago del cliente](use-customer-payment-predictions.md). Después de que el modelo haya sido reentrenado, evalúe los resultados como se describe en [Evaluar el modelo de predicción de pagos del cliente inicial](evaluate-payment-prediction.md). Utilice la información en [Mejorar el modelo de predicción](improve-model.md) para experimentar con combinaciones de funciones y filtros que pueden ayudar a mejorar el modelo.

Cuando esté satisfecho con los resultados del entrenamiento, siga los pasos en [Distribuya su modelo de IA](https://docs.microsoft.com/ai-builder/distribute-model) para realizar la transición del modelo a su entorno de producción.
