---
title: Buscar variantes de producto obsoletas
description: Este procedimiento muestra cómo encontrar los productos liberados obsoletos o las variantes de producto y cómo asociar un estado de ciclo de vida del producto a los productos obsoletos.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 807297a87a7f0e59023d80fbd371bffbf2b086bd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808001"
---
# <a name="find-obsolete-product-variants"></a>Buscar variantes de producto obsoletas 

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo encontrar los productos liberados obsoletos o las variantes de producto y cómo asociar un estado de ciclo de vida del producto a los productos obsoletos. Requisito previo: Es necesario definir el menos un estado de ciclo de vida del producto que esté inactivo para realizar la planificación antes de que se pueda reproducir esta guía de la tarea.


## <a name="run-a-simulation"></a>Ejecutar una simulación
1. Vaya a Gestión de información de productos > Tareas periódicas > Cambiar estado de ciclo de vida para productos obsoletos.
2. En el campo Nuevo estado de ciclo de vida de producto, especifique o seleccione un valor.
3. Seleccione Sí en el campo Ejecutar simulación sin actualizar datos de producto.
4. En el campo Excluir productos creados dentro de este número de días, escriba un número.
5. En el campo Excluir productos usados en transacciones (en número de días), escriba un número.
6. Expanda la sección Registros que incluir.
7. Haga clic en Filtro.
8. En la lista, marque la fila seleccionada.
9. En el campo Criterios, escriba un valor.
10. Haga clic en Aceptar
11. Haga clic en Aceptar

> [!NOTE]
> Se recomienda ejecutar la simulación en lotes si espera buscar un gran número de productos. Además, asegúrese de que la simulación no se ejecute durante el período laborable más activo de la empresa.  

## <a name="review-the-simulation-results"></a>Revise los resultados de simulación
1. Vaya a Gestión de información de productos > Consultas e informes > Historial de mantenimiento de estado del ciclo de vida del producto.
   
> [!NOTE]
> En esta página puede revisar los resultados de simulación y evaluar la cantidad de productos y variantes de producto que se asociarán a un estado del ciclo de vida del nuevo producto al ejecutar la actualización sin la simulación.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Ejecute la actualización del estado del ciclo de vida de producto para los productos obsoletos
1. Cierre la página.
2. Vaya a Gestión de información de productos > Tareas periódicas > Cambiar estado de ciclo de vida para productos obsoletos.
3. Expanda la sección Registros que incluir.

> [!NOTE]
> Observe que se ha guardado la última selección.  

4. Seleccione No en el campo Ejecutar simulación sin actualizar datos de producto.
5. Expanda la sección Ejecutar en segundo plano.

> [!NOTE]
> En función de la cantidad de productos y variantes de producto se vean afectadas, considere ejecutar este trabajo por lotes. Compruebe que no se ejecuta un trabajo de actualización grande durante el horario laboral más activo de la empresa.  

6. Haga clic en Aceptar
7. Vaya a Gestión de información de productos > Consultas e informes > Historial de mantenimiento de estado del ciclo de vida del producto.

> [!NOTE]
> Revise los productos emitidos y las variantes de producto cambiados.  

8. En la lista, busque y seleccione el registro deseado.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]