--- 
title: "Ejecutar un informe que use dimensiones financieras como origen de datos para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5d4f57ae2a309d9e15c1afe60c3e91d7d7eb3870
ms.openlocfilehash: c5aefc44adc24f9d216f9470e4307a3723690173
ms.contentlocale: es-es
ms.lasthandoff: 11/02/2017

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a>Ejecutar un informe que use dimensiones financieras como origen de datos para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER. Estos pasos se pueden llevar a cabo en la empresa DEMF.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)". También debe configurar tipos de documento predeterminados en la página Parámetros de informes electrónicos. Los tipos de documento predeterminados también se especifican al descarga e importar cualquier configuración del ER. 


## <a name="run-report"></a>Ejecutar informe
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".
3. En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras\Informe del diario contable".
4. Haga clic en Ejecutar.
5. En el campo Nombre de dimensión, especifique o seleccione un valor.
    * Para seleccionar todas las dimensiones de la empresa actual, introduzca lo siguiente: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
6. Expanda la sección Registros que incluir.
7. Haga clic en Filtro.
8. Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.
9. En el campo Criterios, escriba "00057".
10. Haga clic en Aceptar
11. Haga clic en Aceptar
    * Revise la salida generada. Tenga en cuenta que para cada transacción del lote seleccionado, se incluyen las dimensiones financieras del conjunto de dimensiones correspondientes. Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionadas o el número de dimensiones configuradas para esta instancia de Dynamics 365 for Finance and Operations, Enterprise edition.  


