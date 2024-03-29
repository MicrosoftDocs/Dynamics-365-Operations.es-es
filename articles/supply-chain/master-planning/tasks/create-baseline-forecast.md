---
title: 'Guía: Crear una previsión de línea base'
description: Un planificador de producción puede crear una previsión de línea base usando modelos de previsión de series temporales o copiando la demanda histórica.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eb2450f0e86eb4aa9a69c9c651ab1648ca0172b
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469600"
---
# <a name="guide-create-a-baseline-forecast"></a>Guía: Crear una previsión de línea base

[!include [banner](../../includes/banner.md)]

Un planificador de producción puede crear una previsión de línea base usando modelos de previsión de series temporales o copiando la demanda histórica. Este procedimiento muestra cómo copiar una demanda histórica para crear una previsión de línea base para todos los productos mediante una clave de asignación de artículos.

## <a name="set-up-an-item-allocation-key"></a>Configurar clave de asignación de artículos

1. Vaya a **Planificación maestra > Configuración > Grupos de planificación de empresas vinculadas**.
2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro en el campo *Nombre* con un valor de *10*.
    * La previsión de demanda se aplica a distintas entidades jurídicas. Esta es la razón por la que necesita configurar todas las empresas para las que desea generar previsiones en un grupo de planificación de empresas vinculadas.  
3. En la lista, busque y seleccione el registro deseado.
4. Seleccionar **Clave de asignación de artículos**.
    * Seleccione todas las claves de asignación de artículos para las que desea crear previsiones.  
5. En la lista, marque la fila seleccionada.
    * Seleccione la clave de asignación de artículos D_Aloc.  
6. Seleccionar **>**.
7. Cierre la página.
8. Cierre la página.

## <a name="set-up-the-demand-forecasting-parameters"></a>Configuración de parámetros de previsión de demanda

1. Vaya a **Planificación maestra > Configuración > Previsión de demanda > Parámetros de previsión de la demanda**.
2. Expanda la sección **Parámetros de algoritmo de previsión**.
3. En el campo **Estrategia de generación de previsión**, seleccione **Copiar sobre demanda histórica**.
4. Seleccione **Guardar**.

## <a name="create-a-baseline-forecast"></a>Crear una previsión de línea base

1. Vaya a **Planificación maestra > Previsión > Previsión de demanda > Generar previsión estadística de línea base**.
2. En el campo **Fecha inicial**, escriba una fecha.
    * Si tiene pedidos de ventas que comiencen a partir del 1 de enero de 2015, especifique esta fecha. Si no, especifique la fecha más temprana de sus pedidos de ventas.  
3. En el campo **Fecha final**, especifique una fecha.
    * Escriba la última fecha de sus pedidos de ventas, por ejemplo, *31-03-2015*.  
4. En el campo **Fecha inicial**, escriba una fecha.
    * Especifique *01-04-2015*. Esta fecha se calcula automáticamente como la fecha inicial del siguiente de depósito de previsión.  
5. Expanda la sección **Registros que incluir**.
6. Seleccione **Filtro**.
7. En la lista, marque la fila seleccionada.
    * Marque la fila en la que **Campo** = *Grupo de planificación de empresas vinculadas*.  
8. En el campo **Criterios**, escriba un valor.
    * Escriba el grupo de planificación de empresas vinculadas (por ejemplo, *10*), que usó en la primera tarea.  
9. En la lista, busque y seleccione el registro deseado.
    * Seleccione la fila en la que **Campo** = *Clave de asignación de artículos*.  
10. En el campo **Criterios**, escriba un valor.
11. Seleccione **Aceptar**.
12. Expanda la sección **Parámetros avanzados**.
13. En el campo **Depósito de previsión**, seleccione *Mes*.
14. En el campo **Horizonte de previsión**, indique *3*.
15. En el campo **Congelar límite de tiempo**, indique *1*.
16. Seleccione **Aceptar**.

## <a name="visualize-the-demand-forecast"></a>Visualización de la previsión de demanda

1. Vaya a **Planificación maestra > Previsión > Previsión de demanda > Previsión de la demanda ajustada**.
2. En la tabla de vista agregada, seleccione la celda de la fila 1, columna 2. Este es el segundo mes para el que ha creado previsión.
3. Defina **QtyCell** en *400*.
    * En la celda, especifique un número distinto al previsto, por ejemplo, 400.  
4. Ha realizado un ajuste manual en la previsión. Observe la indicación gráfica en el siguiente paso.
5. Seleccione **Detalles de línea de previsión**.
    * En esta página puede ver los valores de precisión, la demanda histórica y la previsión. También puede modificar la previsión.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]