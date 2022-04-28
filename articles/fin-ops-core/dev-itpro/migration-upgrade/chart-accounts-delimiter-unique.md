---
title: Hacer único el delimitador del plan de cuentas
description: Este tema explica cómo no puede tener el mismo delimitador para el plan contable y los valores de dimensión. Debe cambiar los valores del delimitador tras la actualización.
author: panolte
ms.date: 04/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6081a62077f1fc6b6920991ed6faae667c25a47c
ms.sourcegitcommit: e8a2a1e34fa48a42afac9724828f4ec72b6d7085
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8573629"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Hacer único el delimitador del plan de cuentas

[!include [banner](../includes/banner.md)]

En Microsoft Dynamics AX 2012, puede utilizar el mismo delimitador para el plan de cuentas y los valores de dimensión. En las versiones actuales de finanzas y operaciones, no puede tener el mismo delimitador para el plan de cuentas y los nombres o valores de dimensión. Si hay un delimitador duplicado, puede cambiarlo tras la actualización. 

## <a name="update-delimiter"></a>Actualizar el delimitador
Si existe conflicto con el plan de cuentas, se puede cambiar el delimitador del plan de cuentas y el formato de id. del proyecto o del subproyecto. Ningún otro delimitador de dimensión se puede modificar. 
- Puede cambiar el delimitador del plan de cuentas después de la actualización en **Parámetros de contabilidad general** > **Plan de cuentas y dimensiones** > **Cambiar delimitador**. 
- Si el único conflicto está en el formato de Id. de proyecto/subproyecto, es posible cambiar el valor en **Gestión de proyectos y parametros de contabilidad** > **General** > **Modificar el formato de subproyecto**. 

### <a name="other-considerations"></a>Otras consideraciones
Al igual que el ID de proyecto/subproyecto, cualquier otro registro de datos maestros que se use como dimensiones financieras (como proveedores o clientes) no debe tener valores de ID de cuenta que usen el mismo carácter que el delimitador del plan de cuentas. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Cómo determinar si el entorno requiere delimitadores actualizados 
Si los delimitadores en el entorno actualizado están en conflicto, es posible que se produzca inestabilidad al especificar valores en un control de entrada segmentado o control de entrada de dimensiones. Esto significa que deberá usar siempre búsquedas o un menú desplegable al especificar combinaciones de cuenta y dimensión.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
