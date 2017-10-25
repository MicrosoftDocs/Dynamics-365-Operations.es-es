---
title: "Espacio de trabajo de administración de activos fijos"
description: "Este tema proporciona información acerca del espacio de trabajo Activo fijo. Este espacio de trabajo muestra la información relacionada con los activos fijos que se especifican en el sistema. Incluye una vista resumida y una vista de análisis."
author: saraschi
manager: AnnBe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c87cd29f46acb44faddaf5552de21fb8f4c5c71d
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-management-workspace"></a>Espacio de trabajo de administración de activos fijos

[!include[banner](../includes/banner.md)]

El espacio de trabajo **Administración de activos fijos** muestra la información relacionada con los activos fijos que se especifican en el sistema. Este espacio de trabajo incluye una vista de resumen y una vista de análisis. La pestaña **Mi trabajo** muestra fichas del resumen, detalles de activos fijos e información relacionada sobre los activos fijos en la empresa actual. También puede agregar análisis a la sección de análisis de Power BI directamente en el espacio de trabajo. Las pestaña **Análisis de todas las empresas** usa las capacidades de Microsoft Power BI para mostrar las representaciones visuales relacionadas con los activos fijos en todas las empresas.

## <a name="my-work"></a>Mi trabajo

### <a name="summary"></a>Resumen

Las fichas en la sección **Resumen** ofrecen una visión general de los activos fijos. La información incluye métricas sobre los activos que aún no se adquirieron, los activos que se han adquirido durante el año actual y los activos que se han cancelado durante el año actual. La sección **Resumen** también tiene exploración rápida a la página de la lista de los **Activos fijos**, la propuesta de depreciación de lote y el diario de activos fijos.

### <a name="find-fixed-assets"></a>Buscar activos fijos

La sección **Buscar activos fijos** permite buscar rápidamente los activos especificando el número de activo fijo, el grupo, el nombre, la ubicación o la persona responsable. Todos los activos que coincidan con los criterios de búsqueda aparecerán en la lista.

En la lista, puede ver las siguientes páginas:

 - La página **Detalles** para el activo fijo
 - La página **Libros** para todos los libros asociados al activo fijo
 - La página **Evaluación de activos fijos**

### <a name="valuations"></a>Valoraciones

La página **Evaluación del activo fijo** permite ver, en una página, la información más importante sobre un activo fijo, así como los detalles de todos los libros que están asociados al activo fijo. La opción **Saldos** en la parte superior izquierda de la página muestra la evaluación actual para cada libro que está asociada al activo fijo. Puede explorar desde los valores para ver las transacciones detalladas que forman el valor de resumen. La opción **Perfil** en la parte superior izquierda de la página muestra el programa de depreciación para cada libro que está asociada al activo fijo.

Puede obtener acceso a la página **Evaluación de activos fijos** en espacio de trabajo **Administración de activos fijos** o la página de lista de **Activo fijo**.

### <a name="related-information"></a>Información relacionada

Puede navegar directamente a la página **Configuración de libros**, la página **Consulta de las transacciones de activos fijos** y a varios informes mediante los vínculos de la sección **Información relacionada** del espacio de trabajo.

### <a name="analytics--all-companies"></a>Análisis de todas las empresas

La página **Análisis** proporciona métricas importante sobre activos fijos en todas las entidades jurídicas del sistema. El acceso a esta ficha se controla mediante la opción Ver el análisis de los activos fijos para el privilegio de seguridad de todas las empresas.

En la tabla siguiente se muestran las visualizaciones que se encuentran disponibles en cada página de informe.

| Página de informes            | Visualización        |
|------------------------|----------------------|
| Evaluación de activos fijos | Valor neto total en los libros |
| Evaluación de activos fijos | Los valores netos en los libros por grupo de activo fijo |
| Evaluación de activos fijos | Valores de adquisición |
| Evaluación de activos fijos | Valores de cancelación |
| Evaluación de activos fijos | Detalles de activo fijo |
| Mapas de valoraciones        | Valor neto total en los libros |
| Mapas de valoraciones        | Ubicaciones de activos fijos |
| Mapas de valoraciones        | Detalles de activo fijo |

Para ver la analítica con datos, primero debe actualizar la medición de agregado AssetTransactionMeasure en la página **Almacén de entidades** .
