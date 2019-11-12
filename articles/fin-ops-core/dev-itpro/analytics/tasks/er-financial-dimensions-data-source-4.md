---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)'
description: En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27498fb8290fa18abd64d7f306e9c0bf4713a72f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550143"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)

[!include [task guide banner](../../includes/task-guide-banner.md)]

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
    * Revise la salida generada. Tenga en cuenta que para cada transacción del lote seleccionado, se incluyen las dimensiones financieras del conjunto de dimensiones correspondientes. Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionado o el número de dimensiones configurado para esta instancia.  

