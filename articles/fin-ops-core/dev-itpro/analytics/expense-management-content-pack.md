---
title: Contenidos de gestión de gastos de Power BI
description: Este tema describe lo que se incluye en el paquete de contenido de gestión de gasto de Power BI.
author: RyanSand
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: TrvExpenseWorkspace, ExpenseWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 0dcb6114544b3817d8b80122a32759e67ad8dc94
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181712"
---
# <a name="expense-management-power-bi-content"></a>Contenidos de gestión de gastos de Power BI

[!include [banner](../includes/banner.md)]

Este tema describe lo que se incluye en el contenido de gestión de gasto de Power BI. 

## <a name="overview"></a>Información general
Hay dos paquetes de contenido de Power BI disponibles para su uso con la gestión de gasto en la versión 8.1 y posterior. 
- Hay un panel personal diseñado para los empleados que envían informes de gastos. 

  El panel está adaptado para proporcionar información clave a individuos sobre importes no enviado y enviados, así como historial y penetraciones en el historial de transacciones de gastos. El panel personal es una sola página que contiene la información más importante para el usuario.

- Hay un panel de administración diseñado para los empleados administrativos y los administradores de los proveedores. El panel está adaptado hacia el seguimiento y generación de informes sobre gastos totales del empleado. Proporciona datos clave de gastos, como importes no enviado de los gastos, de kilometraje e informes de gastos medios. Usa datos transaccionales y ofrece las vistas globales de administración de gasto en todas las empresas. También proporciona un desglose por empleado, con la opción para agregar datos de la dimensión financiera. El contenido de análisis de gastos de administración incluye: 
  - Una página de visión general con medidas clave sobre importes de gastos e informaciones sobre borradores, en proceso e informes de gastos completados. 
  - Una página de contabilidad del empleado para revisar los detalles individuales sobre un empleado según tiempo, tipo de coste y grupo de estadísticas. 
  - Una página de comparación del empleado para comparar a varios empleados en el tiempo. 

Todos los importes se muestran en la divisa de la empresa. Se muestran los datos de todas las empresas, pero si es necesario, puede agregar un filtro de empresa. 

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
Puede encontrar los contenidos del Expense Admin Dashboard.pbix y Expense Personal Dashboard.pbix Power BI en la bibilioteca de activos compartidos en Microsoft Dynamics Lifecycle Services (LCS). Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte Contenido de [Power BI en LCS en Microsoft y sus socios](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/12/12/power-bi-content-from-microsoft-and-your-partners/).
El contenido está disponible en el área de trabajo de gestión de gastos como contenido incrustado de Power BI. Cualquier propietario de gastos puede tener acceso a gastos personales para ellos mismos, mientras que sólo los vendedores y los administradores de los proveedores pueden acceder al contenido de la gestión de casos para ver los datos de gastos de todo el usuario.

## <a name="refreshing-the-power-bi-content"></a>Actualizar el contenido de Power BI
El contenido de gestión de gastos de Power BI requiere actualizar la medida de TrvBiExpenseMeasurement y BudgetActivityMeasure desde el almacén de entidades. 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido incluye un conjunto de páginas de informe. Cada página consta de un conjunto de métricas que se visualizan como gráficos, mosaicos y tablas. La tabla siguiente proporciona información general de las visualizaciones del contenido de Power BI.

**Análisis de gastos personales**

| Página de informes | Visualización                             |
|-------------|-------------------------------------------|
| Mis gastos | Importe de kilometraje                         |
|             | Informes de gastos en proceso                |
|             | N. º de los gastos no enviados               |
|             | Gastos personales a ser pagados              |
|             | Importe no enviado                        |
|             | Importe enviado                          |
|             | Importe esperando reembolso             |
|             | Informes de gastos con importes y estado   |
|             | Informes de gastos enviados pero no aprobados  |
|             | Tipo de coste de gastos                     |
|             | Gastos por comerciante                      |
|             | Gastos por gastos procesados            |
|             | Gastos por proyecto                       |
|             | Importe total de la transacción en el tiempo        |

**Análisis de gastos administrativos**

| Página de informes         | Visualización                           |           
|---------------------|-----------------------------------------|
| Visión general de gastos    | Borrador del importe de los gastos                   |
|                     | Número de líneas del borrador de gasto           |
|                     | Líneas del borrador de gasto                     |
|                     | Informe de gastos de infracciones de directiva        |
|                     | Importe pendiente                      |
|                     | Gastos enviados pero no aprobados       |
|                     | Gastos aprobados                       |
|                     | Importe total de gastos                    |
|                     | Resumen de informe de gastos                |
|                     | Tipo de coste de gastos                   |
|                     | Gastos por comerciante                    |
|                     | Gastos por empleados                   |
|                     | Gastos frente proyecto                     |
| Comparación de empleado | Importes de gastos                         |
|                     | Importes de gastos en el tiempo por empleado   |
| Estadísticas del empleado | Informes de gasto por tipo de coste            |
|                     | Gastos personales                       |
|                     | Informes de gasto por grupo de estadísticas     |
