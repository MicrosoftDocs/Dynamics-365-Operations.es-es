--- 
title: "Ejecutar un formato que use intervalos horizontalmente ensanchables para agregar columnas de forma dinámica en Excel para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4b859151edd28e39c1f97b2f600da6e304b1d065
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a>Ejecutar un formato que use intervalos horizontalmente ensanchables para agregar columnas de forma dinámica en Excel para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos, puede configurar un formato electrónico (ER) para generar informes mientras que los archivos de las hojas de cálculo de Excel (OPENXML) en los que las columnas necesarias se pueden crear de forma dinámica como intervalos horizontalmente ensanchables. Estos pasos se pueden llevar a cabo en la empresa DEMF.

Para completar estos pasos, primero debe completar los pasos en el “ER Uso de los intervalos horizontalmente ensanchables para agregar columnas de manera dinámica en informes de Excel (Parte 1: Diseño de formato)”.

Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="find-created-format"></a>Busque el formato creado
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".
3. En el árbol, seleccione "Modelo de ejemplo de dimensiones financieras\Ejemplo de muestra con intervalos horizontalmente ensanchables".

## <a name="execute-format-to-create-excel-output"></a>Ejecute el formato para crear un resultado en formato Excel
1. Haga clic en Ejecutar.
2. En el campo Nombre de dimensión, introduzca “BusinessUnit;CostCenter;Departament”.
    * En el campo nombre de Dimensión, especifique o seleccione un valor.  Para seleccionar todas las dimensiones para la empresa actual, especifique lo siguiente: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. Expanda la sección Registros que incluir.
4. Haga clic en Filtro.
5. Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.
6. En campo Criterios, introduzca '00057..00058'.
    * 00057..00058  
7. Haga clic en Aceptar
8. Haga clic en Aceptar
    * Revise la salida generada. Tenga en cuenta que el archivo de Excel recién creado contiene el mismo número de columnas que han sido seleccionadas para las dimensiones financieras. El encabezado del informe en las columnas representa los nombres de las dimensiones financieras. Las líneas de transacciones en las columnas representan las dimensiones financieras. Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionadas o el número de dimensiones configuradas para esta instancia de Dynamics 365 for Finance and Operations, Enterprise edition.  

