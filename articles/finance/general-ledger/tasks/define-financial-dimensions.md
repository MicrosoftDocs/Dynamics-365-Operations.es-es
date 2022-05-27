---
title: Definir dimensiones financieras
description: Este procedimiento muestra la forma de agregar una dimensión financiera respaldada por la entidad y una dimensión financiera personalizada.
author: aprilolson
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails,  DimensionAttributeTableExtensionActivate, DimensionValueDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10a991938f68c0ade19999e48a02f032c92a6779
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716954"
---
# <a name="define-financial-dimensions"></a>Definir dimensiones financieras

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra la forma de agregar una dimensión financiera respaldada por la entidad y una dimensión financiera personalizada. La guía usa la empresa de demostración de USMF.

## <a name="create-an-entity-backed-financial-dimension"></a>Crear una dimensión financiera respaldada por entidad
1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Plan contable > Dimensiones > Dimensiones financieras**.
2. Haga clic en **Nuevo**.
3. En el campo **formulario de alores del usuario**, seleccione una entidad definida por el sistema en la que desea basar la dimensión financiera. 
4. En el campo **Nombre de dimensión**, escriba un valor para describir la dimensión financiera. El nombre puede ser diferente de la entidad definida por el sistema pero no puede contener espacios ni caracteres especiales.
5. Haga clic en **Activar**. La activación de la dimensión financiera actualiza la tabla con el nombre de la dimensión financiera y quita las dimensiones eliminadas. Puede especificar valores de dimensión para activar una dimensión financiera, pero no se puede usar una dimensión financiera hasta que esté activada.  
6. Haga clic en **Cerrar** en el mensaje de activación.
7. Haga clic en **Activar**. La activación de la dimensión se puede programar para ejecutarse por lote en una fecha y una hora específicas.  
8. En el **panel de acciones**, haga clic en **Valores de dimensión**. Algunos valores de dimensión son específicos de la empresa. Puede comprobar si son específicos de la empresa si el nombre de la empresa se muestra en la lista de valores de dimensión.  

## <a name="create-a-custom-financial-dimension"></a>Crear una dimensión financiera personalizada
1. Haga clic en **Nuevo**.
2. En el campo **Usar valores de**, seleccione **Dimensión personalizada**.
3. En el campo **Nombre de dimensión**, escriba un valor para describir la dimensión financiera.
    - El nombre no puede contener espacios o caracteres especiales.  
    - También puede especificar una máscara de cuenta para limitar el importe y el tipo de información que puede especificar para valores de dimensión.   
    - Puede especificar los caracteres que permanecen iguales para cada valor de dimensión, como letras o un guión. También puede especificar signos de número (#) y ampersands (&) como marcadores de posición para las letras y los números que se modificarán cada vez que se cree un valor de dimensión. Use un signo de número (#) como indicador de posición para un número y un ampersand (&) como indicador de posición para una letra.  Ejemplo: Para limitar el valor de dimensión a letras CC, un guión y tres números, debe especificar CC-### como la máscara de formato.  
4. Haga clic en **Activar**. La activación de la dimensión financiera actualiza la tabla con el nombre de la dimensión financiera y quita las dimensiones eliminadas. Puede especificar valores de dimensión para activar una dimensión financiera, pero no se puede usar una dimensión financiera hasta que esté activada.     
5. Haga clic en **Activar**. La activación de la dimensión se puede programar para ejecutarse por lote en una fecha y una hora específicas.      
6. En el **panel de acciones**, haga clic en **Valores de dimensión**.
7. Haga clic en **Nuevo**.
8. En el campo **Valor de dimensión**, escriba un nombre para describir el valor de la dimensión financiera.
9. En el campo **Descripción**, escriba una descripción del valor de la dimensión financiera.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
