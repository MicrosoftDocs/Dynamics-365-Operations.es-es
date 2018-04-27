---
title: "Importar datos de las plantillas de la entidad de los datos de Excel con varias hojas de cálculo"
description: "Este tema describe cómo importar datos mediante las plantillas de la entidad de los datos de Excel en Microsoft Dynamics 365 for Finance and Operations."
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 2aefea9373df20bd3e99026e30aed096dcea9814
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="excel-templates-with-multiple-worksheets"></a>Plantillas de Excel con varias hojas de cálculo

[!INCLUDE [banner](../includes/banner.md)]

La administración de datos en Microsoft Dynamics 365 for Finance and Operations admite las plantillas basadas en Microsoft Excel para entidades de datos. Estas plantillas pueden contener una o varias hojas de cálculo. Las plantillas con varias hojas de cálculo se utilizan a menudo cuando es conveniente administrar datos en un solo archivo e importarlos a múltiples entidades de datos. Un ejemplo serían sitios y almacenes.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Cargar un archivo una vez y asígnarlo a todas las entidades
Tomemos un ejemplo en el que exista un archivo de Excel con las hojas de cálculo denominadas **Sitios** y **Almacenes**. Para configurar el proyecto de la importación de datos, agregaría la primera entidad de datos, **Sitios** y después cargaría el archivo. Podrá seleccionar **Sitios** como la hoja de cálculo que se utilizará para esta entidad.

Si agrega la segunda entidad **Almacenes** sin salir del formulario **Agregar archivo** , la búsqueda de la hoja de cálculo le permitirá seleccionar la hoja de cálculo **Almacenes** sin tener que cargar el archivo de nuevo. El único motivo para cargar un nuevo archivo sería si los datos **Almacenes** figuraban en un archivo diferente.

![Varias hojas de cálculo](./media/AddFileMultipleWorkSheets.png) 

## <a name="fix-worksheet-to-entity-mapping"></a>Corregir hoja de cálculo para la asignación de la entidad

La asignación de la hoja de cálculo a una entidad de datos en el trabajo de importación se puede corregir desde la cuadrícula. La columna **Hoja de cálculo** en la cuadrícula muestra las hojas de cálculo del archivo que se ha asignado. Puede elegir otra hoja de cálculo del menú desplegable. Si la hoja de cálculo seleccionada ya está asignada a una entidad en el proyecto de los datos, el sistema le pedirá que confirme el cambio. Recomendamos que corrija todas las asignaciones en la cuadrícula.

![Actualizar la asignación de hoja de cálculo](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Volver a asignar a un nuevo archivo

En casos en los que una versión nueva del mismo archivo o un archivo completamente nuevo se deba cargar para las entidades existentes en un proyecto de datos, debe usar la experiencia **Agregar archivo** y agregar las entidades de nuevo como si las agregara por primera vez. El sistema confirmará que desea sobrescribir las entidades existentes del proyecto de datos antes de continuar. Las entidades que no están agregadas de nuevo (o sobrescritas) continuarán llevando a cabo las asignaciones anteriores del archivo anterior.

## <a name="upload-a-file-using-run-project"></a>Cargar archivo mediante Ejecutar proyecto

Puede cargar un archivo de Excel mediante la opción **Ejecutar proyecto** para ejecutar un proyecto de importación. Debe tener cuidado de cargar solo los archivos con las mismas hojas de cálculo que las asignaciones existentes en entidades de datos en los proyectos de datos. Si una hoja de cálculo no se encuentra en el archivo recién cargado, el sistema muestra un error y detendrá la importación. Si la asignación a la hoja de cálculo debe cambiarse para una entidad, las asignaciones del proyecto de datos se deben actualizar primero desde el proyecto de datos antes de utilizar el archivo en la experiencia **Ejecutar proyecto**.


