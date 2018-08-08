--- 
title: "Usar el diario de existencias de seguridad para actualizar la cobertura mínima"
description: "Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d278b20724006ec3b3aa557738e8b130ca2bba15
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Usar el diario de existencias de seguridad para actualizar la cobertura mínima

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas. Esto se hace usando el diario de existencias de seguridad. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Esta tarea está pensada para el planificador de producción, para ayudar a mantener una cobertura mínima.


## <a name="create-a-new-safety-stock-journal-name"></a>Puede crear un nuevo nombre de diario de existencias de seguridad.
1. Vaya a Nombres de diario de existencias de seguridad.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba "Material".
4. En el campo Descripción, escriba "Material".
5. Cierre la página.

## <a name="create-a-safety-stock-journal"></a>Crear un diario de existencias de seguridad
1. Vaya a Cálculo de existencias de seguridad.
2. Haga clic en Nuevo.
3. En el campo Nombre, especifique o seleccione un valor.
    * Seleccione el nombre del diario de las existencias de seguridad que ha creado, por ejemplo, Material.  
4. Haga clic en Crear líneas.
5. En el campo Fecha inicial, escriba una fecha.
    * Establezca la fecha en "02-01-2015".  
6. Especifique una fecha en el campo Fecha final.
    * Establezca la fecha en "30-12-2015".  
7. Haga clic en Aceptar
    * Esto creará líneas para las dimensiones que tienen transacciones de inventario.  

## <a name="calculate-proposal"></a>Calcular propuesta
1. Haga clic en Calcular propuesta.
2. Seleccione la opción Usar el promedio de emisión durante el plazo.
3. Establezca el factor de multiplicación en "10".
    * El factor Multiplicar se utiliza para ajustar la propuesta. Dado que los datos de demostración solo tienen algunas transacciones, deberá establecer el factor para conseguir una propuesta realista.  
4. Haga clic en Aceptar
    * Desplácese hacia abajo para encontrar M0002 y M0003. Vea la columna Cantidad mínima calculada.   

## <a name="update-minimum-quantity"></a>Actualizar cantidad mínima
1. En el campo Nueva cantidad mínima, escriba un número.
    * Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada. Si el mínimo calculado es cero, puede escribir el valor futuro deseado. Por ejemplo, usted puede especificar la Cantidad mínima calculada en este campo para M0002 que tiene el almacén 12.  
2. En la lista, busque y seleccione el registro deseado.
    * Por ejemplo, puede seleccionar M0002 que tiene el almacén 12.  
3. En el campo Nueva cantidad mínima, escriba un número.
    * Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada. Si el mínimo calculado es cero, puede escribir el valor futuro deseado.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Publicar la nueva cantidad mínima y validar el resultado
1. Haga clic en Registrar.
2. Haga clic en Aceptar
3. Haga clic para seguir el vínculo en el campo Número de artículo.
4. Haga clic para seguir el vínculo en el campo Número de artículo.
5. En el panel de acciones, haga clic en Plan.
6. Haga clic en Cobertura de artículos.
    * Observe que se ha actualizado la Cantidad mínima con la nueva cantidad mínima del diario de existencias de seguridad.  


