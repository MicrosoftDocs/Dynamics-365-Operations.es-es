--- 
title: "Mantener L. MAT. para un modelo de configuración de producto"
description: "La ejecución de este procedimiento requiere un modelo de configuración de producto existente."
author: BibiSp
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 645d748235935ae67867295a87a84a6539710ab0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Mantener L. MAT. para un modelo de configuración de producto

[!include[task guide banner](../../includes/task-guide-banner.md)]

La ejecución de este procedimiento requiere un modelo de configuración de producto existente. El modelo Altavoz superior de la empresa de demostración USMF se usa para crear este procedimiento.


## <a name="add-a-bom-line"></a>Adición de una línea de L. MAT
1. Haga clic en Definición de modelo de variante del producto.
2. Haga clic en Modelos de configuración del producto.
3. En la lista, busque y seleccione el registro deseado.
    * Seleccione el Altavoz superior para este procedimiento.  
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Expanda la sección Líneas de L. MAT.
6. Haga clic en Agregar.
7. En el campo Nombre, escriba un valor.
8. En el campo Descripción, escriba un valor.
9. Haga clic en Guardar.

## <a name="add-bom-line-details"></a>Agregar detalles de línea de L. MAT
1. Haga clic en Detalles de línea de L. MAT.
2. En el campo Número de artículo, especifique o seleccione un valor.
    * Por ejemplo, puede seleccionar el artículo M0055.  
    * Para cada propiedad de la línea de L. MAT, puede seleccionar si toma un valor fijo o se asigna a un atributo.  
3. Active la casilla Establecer.
4. Seleccione Sí en el campo Cálculo.
    * La configuración de la propiedad Cálculo en Sí garantiza que se incluye la línea de L. MAT en los cálculos de coste.  
5. Haga clic en la pestaña Configurar.
6. Active la casilla Establecer.
7. En el campo Cantidad, especifique un número.
    * El campo de cantidad determina qué cantidad del artículo se incluirá en la L. MAT. Esto podría ser un candidato obvio para una asignación de atributos.  
8. Haga clic en la ficha Dimensión.
    * Compruebe si cualquiera de las dimensiones del producto está activas y, por tanto, debe tener un valor o atributo asignado.  
9. Haga clic en Aceptar

