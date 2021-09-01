---
title: Usar el diario de existencias de seguridad para actualizar la cobertura mínima
description: Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas.
author: ChristianRytt
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 022ec17d0fdc8b1ee204280ecaac40d75e9c1a44974f2bd4a9bb49fa0aa7878e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759440"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a>Usar el diario de existencias de seguridad para actualizar la cobertura mínima

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo calcular las propuestas de cobertura mínima basadas en transacciones históricas y, a continuación, actualizar la cobertura del artículo con las propuestas. Esto se hace usando el diario de existencias de seguridad. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Esta tarea está pensada para el planificador de producción, para ayudar a mantener una cobertura mínima.


## <a name="create-a-new-safety-stock-journal-name"></a>Puede crear un nuevo nombre de diario de existencias de seguridad.
1. En el **Panel de exploración**, vaya a **Planificación maestra > Configuración > Nombres de diario de existencias de seguridad**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, escriba "Material".
4. En el campo **Descripción**, escriba "Material".
5. Cierre la página.

## <a name="create-a-safety-stock-journal"></a>Crear un diario de existencias de seguridad
1. En el **Panel de exploración**, vaya a **Planificación maestra > Planificación maestra > Ejecutar > Cálculo de existencias de seguridad**.
2. Haga clic en **Nuevo**.
3. En el campo **Nombre**, especifique o seleccione un valor. Seleccione el nombre del diario de las existencias de seguridad que ha creado, por ejemplo, Material.  
4. Haga clic en **Crear líneas**.
5. En el campo **Fecha inicial**, escriba una fecha.  
6. En el campo **Fecha final**, especifique una fecha.
7. Haga clic en **Aceptar**. Esto creará líneas para las dimensiones que tienen transacciones de inventario.  

## <a name="calculate-proposal"></a>Calcular propuesta
1. Haga clic en **Calcular propuesta**.
2. Seleccione la opción **Usar el promedio de emisión durante el plazo**.
3. Establezca **Factor de multiplicación** en "10". El factor Multiplicar se utiliza para ajustar la propuesta. Dado que los datos de demostración solo tienen algunas transacciones, deberá establecer el factor para conseguir una propuesta realista.  
4. Haga clic en **Aceptar**. Desplácese hacia abajo para encontrar M0002 y M0003. Vea la columna **Cantidad mínima calculada**.   

## <a name="update-minimum-quantity"></a>Actualizar cantidad mínima
1. En el campo **Nueva cantidad mínima**, escriba un número. Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada. Si el mínimo calculado es cero, puede escribir el valor futuro deseado. Por ejemplo, usted puede especificar la Cantidad mínima calculada en este campo para M0002 que tiene el almacén 12.  
2. En la lista, busque y seleccione el registro deseado. Por ejemplo, puede seleccionar M0002 que tiene el almacén 12.  
3. En el campo **Nueva cantidad mínima**, escriba un número. Actualice la Nueva cantidad mínima para que coincida con el valor de la Cantidad mínima calculada. Si el mínimo calculado es cero, puede escribir el valor futuro deseado.  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Publicar la nueva cantidad mínima y validar el resultado
1. Haga clic en **Registrar**.
2. Haga clic en **Aceptar**.
3. Haga clic para seguir el vínculo en el campo **Número de artículo**.
4. Haga clic para seguir el vínculo en el campo **Número de artículo**.
5. En el **panel acciones**, haga clic en Plan.
6. Haga clic en **Cobertura de artículos**. Observe que se ha actualizado la **Cantidad mínima** con la nueva cantidad mínima del diario de existencias de seguridad.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]