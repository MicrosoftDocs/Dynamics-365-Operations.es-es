---
title: Variables de prueba de gestión de calidad
description: Este tema describe cómo crear variables de prueba, de modo que se puedan usar para pruebas cualitativas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4495c3d3f8df9f07ec079d8e497a17979abbe3ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575881"
---
# <a name="quality-management-test-variables"></a>Variables de prueba de gestión de calidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear variables de prueba, de modo que se puedan usar para pruebas cualitativas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.

Para cada prueba cuallitativa que se define en la página **Pruebas**, debe definir una variable de prueba y sus posibles resultados (resultados). (Para las pruebas cualitativas, el campo **Tipo** de la página **Pruebas** se establece en *Opción*).

Utilice la página **Variables de prueba** para configurar, editar y visualizar los resultados posibles de una variable de prueba asociada a una prueba cualitativa. Para cada resultado, asigna un estado de resultado de *Pasar* o *Fallar*, para indicar si la prueba se supera o no cuando se selecciona ese resultado como resultado de la prueba. Utilice la página **Grupos de prueba** para asignar una variable de prueba y un resultado predeterminado de esta en una prueba cualitativa individual.

Para cada variable de prueba, recomendamos que definan al menos dos resultados: uno que tenga un estado de resultado de *Pasar* y uno que tenga un estado de resultado de *Fallar*. No hay límite en el número total de variables o resultados que se pueden definir. Además, varias pruebas pueden utilizar las mismas variables de prueba para registrar los resultados.

## <a name="examples-of-test-variables"></a>Ejemplos de variables de prueba

### <a name="example-1"></a>Ejemplo 1

Una empresa de fabricación realiza dos pruebas en materiales fabricados. En una prueba, el nivel de pH está asociado con una tira de color. Los niveles de pH aceptables están en colores más claros y los niveles de pH inaceptables están en colores más oscuros. En otra prueba, se realizan múltiples inspecciones visuales y los trabajadores de calidad usan su juicio para determinar si el artículo pasa o no la inspección visual.

### <a name="example-2"></a>Ejemplo 2

Una fábrica de galletas utiliza una prueba de inspección para el producto terminado. Esta prueba de inspección tiene varias variables. Una variable es el gusto y sus posibles resultados son bueno y malo. Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.

## <a name="create-a-test-variable"></a>Crear una variable de prueba

Siga estos pasos para crear una variable de prueba.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Variables de prueba**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Variable**: introduzca un id. o nombre único para la variable.
    - **Descripción**: escriba una descripción detallada de la variable.

1. Mientras la nueva fila aún está seleccionada, seleccione **Resultados** en el panel de acciones.
1. En la página **Resultados de variable de prueba**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Resultado**: introduzca un id. o nombre único para el resultado.
    - **Descripción**: escriba una descripción detallada del resultado.
    - **Estado del resutado**: seleccione *Pasa* o *Falla*, para indicar si la prueba se supera o no cuando se selecciona ese resultado como resultado de la prueba.

1. Repita el paso anterior para cada resultado adicional. Asegúrese de que al menos un resultado tenga un estado de resultado de *Pasa* y al menos uno tenga un estado de resultado de *Falla*.
1. Cierre las páginas.

## <a name="additional-resources"></a>Recursos adicionales

- [Instrumentos de prueba de gestión de calidad](quality-test-instruments.md)
- [Pruebas de gestión de calidad](quality-tests.md)
- [Grupos de pruebas de gestión de calidad](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
