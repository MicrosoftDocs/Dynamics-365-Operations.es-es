---
title: Validar un flujo de producción y una versión
description: Este procedimiento muestra cómo crear un nuevo flujo de producción y una primera versión de lean manufacturing.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5dfd5655ecdfa74d75490b0915c4cea609baebe3
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146519"
---
# <a name="validate-a-production-flow-and-version"></a>Validar un flujo de producción y una versión

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un nuevo flujo de producción y una primera versión de lean manufacturing. Requisitos previos: deben definirse los parámetros de producción de lean manufacturing y las unidades de medida para la clase de tiempo. Debe definir un flujo de valor y un grupo de producción. Consulte las notas del producto sobre lean manufacturing para familiarizarse con los conceptos de flujos de producción y actividades. Este procedimiento hace referencia a la entidad jurídica USMF en los datos de demostración. Sin embargo, si se supone que se configura la entidad jurídica para lean manufacturing, se pueden usar otras entidades jurídicas.


## <a name="create-a-production-flow"></a>Crear flujos de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Un flujo de valor es una unidad operativa que abarca todas las actividades y los flujos del flujo de valor.   En esta fase, las unidades operativas se limitan a una entidad jurídica y no tienen más funcionalidad.  
7. En el campo Grupo de producción, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Los grupos de producción permiten definir las cuentas de trabajo en curso, material y manos de obra para un proceso de producción. Para asociar el contexto de contabilidad a un flujo de producción, debe seleccionarse un grupo de producción.  
9. Haga clic en Guardar.

## <a name="create-a-production-flow-version"></a>Crear una versión de flujo de producción
1. Haga clic en Agregar.
2. En el campo Fecha de vencimiento, especifique una fecha y una hora.
    * Puede actualizar la fecha de vencimiento de la versión en cualquier momento dado, incluso para las versiones activas. Use el vencimiento de la versión para planear la retirada de una versión.  
3. Haga clic en Aceptar
4. En la lista, marque la fila seleccionada.
5. En el campo Unidad, escriba un valor.
6. Seleccione la unidad de producción.
7. En campo Ritmo de producción promedio, escriba un número.
    * Para el control de producción de la versión de flujo de producción, defina un ritmo de producción promedio objetivo.   El ritmo se define como cantidad por período de tiempo.  En el ejemplo determinado, el ritmo de producción es 0,2 horas por 10 piezas. Por un horario de trabajo de 8 horas, esto se corresponde con una capacidad de rendimiento diario de 400 piezas.  
8. En el campo Cantidad por ciclo, especifique un número.
9. Expanda o contraiga la sección Detalles de versión.
10. En campo Ritmo de producción mínimo, escriba un número.
    * El ritmo de producción mínimo debe ser inferior o igual al ritmo de producción promedio.  
11. En campo Ritmo de producción máximo, escriba un número.
    * El ritmo de producción máximo debe ser superior o igual al ritmo de producción promedio.  
12. Escribir un número de días en el Período para tiempo de ciclo real
    * El período para el tiempo de ciclo real es el número de días que los trabajos se agregan a partir del minuto real y hacia atrás, para calcular el tiempo de ciclo real. El valor se puede cambiar en cualquier momento y solo se usa para calcular los tiempos de ciclo reales.  
13. Haga clic en Guardar.

