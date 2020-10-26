---
title: Asociación de un índice de combustible con un transportista como cargo adicional
description: Este procedimiento muestra cómo crear una asignación de cargos adicionales, un cargo adicional de transportista y cargos adicionales maestros por recargo por combustible, y cómo asociar un índice de combustible de transportista con un transportista.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bfecdbd8ca2d6124906ef664493602a1d0ac0baf
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981930"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Asociación de un índice de combustible con un transportista como cargo adicional

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear una asignación de cargos adicionales, un cargo adicional de transportista y cargos adicionales maestros por recargo por combustible, y cómo asociar un índice de combustible de transportista con un transportista. Es necesario haber configurado un índice de combustible de transportista antes de ejecutar este procedimiento. Puede usar el procedimiento "Configuración de un índice de combustible de transportista". Estas tareas de configuración las realiza normalmente el administrador de logística. Los datos de demostración utilizados para crear este procedimiento son los de la empresa USMF.


## <a name="create-an-accessorial-master"></a>Creación de un cargo maestro adicional
1. Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales maestros.
2. Haga clic en Nuevo.
3. En el campo Cargos adicionales maestros, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. Haga clic en Guardar.

## <a name="create-a-carrier-accessorial-charge"></a>Creación de un cargo adicional de transportista
1. Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales del transportista.
2. Haga clic en Nuevo.
3. En el campo Id. de cargos adicionales del transportista, escriba un valor.
4. En el campo Transportista de envío, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
    * En este ejemplo, elija el transportista por camión.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. En el campo Servicio de transportista, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Cargos adicionales maestros, haga clic en el botón desplegable para abrir la búsqueda.
10. En la lista, busque y seleccione el registro deseado.
    * En este ejemplo, elija los cargos adicionales maestros recién creados.  
11. Haga clic en Guardar.

## <a name="create-an-accessorial-assignment"></a>Creación de una asignación de cargos adicionales
1. Haga clic en Asignaciones de cargos adicionales.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. Expanda la sección Criterios.
    * En los criterios puede elegir aplicar siempre un suplemento por combustible o, para este ejemplo, elija que se aplique solo dentro de determinada región.  
5. En el campo Valor inicial de código postal, escriba un valor.
6. En el campo Valor final de código postal, escriba un valor.
7. Expanda la sección Cálculo.
    * En la sección de cálculo, puede especificar la manera de calcular el recargo por combustible. Este cálculo depende de la unidad adicional que haya elegido como base para el cálculo.  
8. En el campo Tipo de tasas de cargos adicionales, seleccione Suplemento por combustible.
9. En el campo Unidad adicional, seleccione Kilometraje.
10. En el campo Región, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
12. Haga clic en Guardar.

## <a name="update-the-carrier-rating-profile"></a>Actualización del perfil de clasificación de transportista
1. Vaya a Administración de transporte > Configuración > Transportistas > Transportistas de envío.
2. En la lista, busque y seleccione el registro deseado.
3. Expanda la sección Perfiles de clasificación.
4. Haga clic en Editar.
5. En el campo Índice de combustible del transportista, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Haga clic en Guardar.

