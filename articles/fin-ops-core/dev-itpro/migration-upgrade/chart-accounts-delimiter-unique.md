---
title: Hacer único el delimitador del plan de cuentas
description: Este tema explica cómo no puede tener el mismo delimitador para el plan contable y los valores de dimensión. Debe cambiar los valores del delimitador tras la actualización.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 2ce91557334a4342fa85848fc1b746b6b12c8992
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688536"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Hacer único el delimitador del plan de cuentas

[!include [banner](../includes/banner.md)]

En Microsoft Dynamics AX 2012, puede utilizar el mismo delimitador para el plan de cuentas y los valores de dimensión. En las versiones actuales de Finance and Operations, no puede tener el mismo delimitador para el plan de cuentas y los valores de dimensión. Si hay un delimitador duplicado, puede cambiarlo tras la actualización. 

Esta función está disponible en las versiones siguientes:
- Finance and Operations versión 8.0
- Finance and Operations versión 7.1, KB 4094701 no puede especificar las dimensiones financieras cuando los valores de dimensión contienen el delimitador del plan de cuentas
- Finance and Operations versión 7.2, KB 4092967 no puede elegir subproyecto como dimensión cuando el formato de subproyecto contiene el delimitador de la dimensión

## <a name="update-delimiter"></a>Actualizar el delimitador
Si existe conflicto con el plan de cuentas, se puede cambiar el delimitador del plan de cuentas y el formato de id. del proyecto o del subproyecto. Ningún otro delimitador de dimensión se puede modificar. 
- Puede cambiar el delimitador del plan de cuentas después de la actualización en **Parámetros de contabilidad general** > **Plan de cuentas y dimensiones** > **Cambiar delimitador**. 
- Si el único conflicto está en el formato de Id. de proyecto/subproyecto, es posible cambiar el valor en **Gestión de proyectos y parametros de contabilidad** > **General** > **Modificar el formato de subproyecto**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Cómo determinar si el entorno requiere delimitadores actualizados 
Si los delimitadores en el entorno actualizado están en conflicto, es posible que se produzca inestabilidad al especificar valores en un control de entrada segmentado o control de entrada de dimensiones. Esto significa que deberá usar siempre búsquedas o un menú desplegable al especificar combinaciones de cuenta y dimensión.
