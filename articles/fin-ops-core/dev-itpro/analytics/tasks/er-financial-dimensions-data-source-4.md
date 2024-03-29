---
title: 'ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)'
description: Este artículo describe cómo configurar un modelo de informes electrónicos (ER) para usar dimensiones financieras como origen de datos para informes ER. (Parte 4)
author: kfend
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, SysQueryForm
ms.openlocfilehash: d0fca8b1a6139b71782af05531d9494c968ef9f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290766"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Usar dimensiones financieras como origen de datos (Parte 4: Ejecución del informe)

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario asignado al rol de administrador del sistema o desarrollador de informes electrónicos puede configurar un modelo de informes electrónicos (ER) para que use las dimensiones financieras como origen de datos de informes ER. Estos pasos se pueden llevar a cabo en la empresa DEMF.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Usar dimensiones financieras como origen de datos (Parte 3: Diseño del informe)". También debe configurar tipos de documento predeterminados en la página Parámetros de informes electrónicos. Los tipos de documento predeterminados también se especifican al descarga e importar cualquier configuración del ER. 


## <a name="run-report"></a>Ejecutar informe
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Modelo de ejemplo de las dimensiones financieras".
3. En el árbol, seleccione "Modelo de ejemplo de las dimensiones financieras\Informe del diario contable".
4. Haga clic en Ejecutar.
![Página de configuraciones de ER.](../media/er-financial-dimensions-guides-run1.png)
5. En el campo nombre de Dimensión, especifique o seleccione un valor.
    * Para seleccionar todas las dimensiones de la empresa actual, introduzca la siguiente información: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![Los parámetros del informe electrónico se deslizan hacia afuera, menú desplegable Nombre de la dimensión.](../media/er-financial-dimensions-guides-run2.png)
6. Expanda la sección Registros que incluir.
7. Haga clic en Filtro.
8. Seleccione la fila de la tabla de diario contable y el campo Número de lote del diario.
9. En el campo Criterios, escriba "00057".
10. Haga clic en Aceptar.
11. Haga clic en Aceptar.
![Los parámetros del informe electrónico se deslizan hacia afuera, sección Informes para incluir.](../media/er-financial-dimensions-guides-run3.png)
    * Revise la salida generada. Para cada transacción del lote seleccionado, se presentan las dimensiones financieras del conjunto de dimensiones correspondiente. Ejecute este informe y seleccione diferentes dimensiones para ver que el informe no depende del número de dimensiones seleccionado o el número de dimensiones configurado para esta instancia.  
![Las configuraciones de ER generaron resultados.](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
