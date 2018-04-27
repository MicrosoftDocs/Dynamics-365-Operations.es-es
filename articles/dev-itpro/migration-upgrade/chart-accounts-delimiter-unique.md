---
title: "El delimitador de plan de cuentas debe ser único"
description: "En Dynamics 365 for Finance and Operations, no puede tener el mismo delimitador para el plan de cuentas y los valores de dimensión. Debe cambiar los valores del delimitador tras la actualización."
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c9728714944b54f3bff1e2a8b43c7adcf5200f08
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="chart-of-accounts-delimiter-must-be-unique"></a>El delimitador de plan de cuentas debe ser único

[!INCLUDE [banner](../includes/banner.md)]

En Microsoft Dynamics AX 2012, puede utilizar el mismo delimitador para el plan de cuentas y los valores de dimensión. En Dynamics 365 for Finance and Operations, no puede tener el mismo delimitador para el plan de cuentas y los valores de dimensión. Si hay un delimitador duplicado, puede cambiarlo tras la actualización. 

Esta característica está disponible en:
- Dynamics 365 for Finance and Operations versión 8.0
- Dynamics 365 for Finance and Operations versión 7.1, KB 4094701 no puede especificar las dimensiones financieras cuando los valores de dimensión contienen el delimitador del plan de cuentas
- Dynamics 365 for Finance and Operations versión 7.2, KB 4092967 no puede elegir subproyecto como dimensión cuando el formato de subproyecto contiene el delimitador de la dimensión

## <a name="update-delimiter"></a>Actualizar el delimitador
Si existe conflicto con el plan de cuentas, se puede cambiar el delimitador del plan de cuentas y el formato de id. del proyecto o del subproyecto. Ningún otro delimitador de dimensión se puede modificar. 
- Puede cambiar el delimitador del plan de cuentas después de la actualización a Finance and Operations en **Parámetros de contabilidad general** > **Plan de cuentas y dimensiones** > **Cambiar delimitador**. 
- Si el único conflicto está en el formato de Id. de proyecto/subproyecto, es posible cambiar el valor en **Gestión de proyectos y parametros de contabilidad** > **General** > **Modificar el formato de subproyecto**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Cómo determinar si el entorno requiere delimitadores actualizados 
Si los delimitadores en el entorno actualizado están en conflicto, es posible que se produzca inestabilidad al especificar valores en un control de entrada segmentado o control de entrada de dimensiones. Esto significa que deberá usar siempre búsquedas o un menú desplegable al especificar combinaciones de cuenta y dimensión.

