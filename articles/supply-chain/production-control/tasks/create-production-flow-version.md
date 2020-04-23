---
title: Crear una versión de flujo de producción
description: Este procedimiento se centra en crear una nueva versión de flujo de producción.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da3b77ed459f42ef91d64066b18b07fece9efc8f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212144"
---
# <a name="create-a-production-flow-version"></a>Crear una versión de flujo de producción

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en crear una nueva versión de flujo de producción. Para este procedimiento, deben definirse los parámetros de producción de lean manufacturing y las unidades de medida para la clase de tiempo. Debe definir también un flujo de valor y un grupo de producción. Para obtener más información acerca de los flujos de producción y las actividades de lean manufacturing (producción ajustada), consulte la documentación al respecto de Microsoft Dynamics AX. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-production-flow"></a>Crear flujos de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione una unidad operativa de tipo Flujo de valor. Un flujo de valor es una unidad operativa que abarca todas las actividades y los flujos del flujo de valor. En esta fase, las unidades operativas se limitan a una entidad jurídica y no tienen más funcionalidad.  
7. En el campo Grupo de producción, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione un grupo de producción para el flujo de producción. Los grupos de producción permiten definir las cuentas de trabajo en curso, material y manos de obra para un proceso de producción. Para asociar el contexto de contabilidad a un flujo de producción, debe seleccionarse un grupo de producción.  
9. Haga clic en Guardar.

## <a name="create-a-production-flow-version"></a>Crear una versión de flujo de producción
1. Haga clic en Agregar.
2. En el campo Fecha de vencimiento, especifique una fecha y una hora.
    * Si procede, defina una fecha de vencimiento para la versión. Puede actualizarla en un cualquier momento, incluso las versiones activas. Puede utilizarla para planificar la finalización de una versión.  
3. Haga clic en Aceptar
4. En la lista, marque la fila seleccionada.
5. En el campo Unidad, escriba un valor.
6. Resuelva los cambios en la unidad de producción.
7. En campo Ritmo de producción promedio, escriba un número.
    * Defina el ritmo de producción promedio de la versión. Para el control de producción de la versión de flujo de producción, defina un ritmo de producción promedio objetivo. El ritmo de producción se define como cantidad por período de tiempo. En el ejemplo, el ritmo de producción es 0,2 horas por 10 piezas. Por un horario de trabajo de 8 horas, esto se corresponde con una capacidad de rendimiento diario de 400 piezas.  
8. En el campo Cantidad por ciclo, especifique un número.
    * Defina la cantidad por el ciclo relacionado con el ritmo de producción promedio.  
9. Expanda la sección Detalles de versión.
10. En campo Ritmo de producción mínimo, escriba un número.
    * Defina el ritmo de producción mínimo. El ritmo de producción mínimo debe ser inferior o igual al ritmo de producción promedio.  
11. En campo Ritmo de producción máximo, escriba un número.
    * El ritmo de producción máximo debe ser superior o igual al ritmo de producción promedio.  
12. Escriba un número en el campo Período para tiempo de ciclo real (días).
    * Escriba un número de días en el período para tiempo de ciclo real. El período para el tiempo de ciclo real es el número de días que los trabajos se agregan a partir del minuto real y hacia atrás, para calcular el tiempo de ciclo real. El valor se puede cambiar en cualquier momento y solo se usa para calcular los tiempos de ciclo reales.  
13. Haga clic en Guardar.

