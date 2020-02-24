---
title: Generar documentos que tengan datos de la aplicación
description: Para completar los pasos de este procedimiento, debe completar primero el procedimiento, "ER Generar documentos con la actualización de datos de la aplicación (Parte 4 . Modificar formato)".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6af7113031fd77a0a7e06ec23a149a3fa7ad0012
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026072"
---
# <a name="generate-documents-that-have-application-data"></a>Generar documentos que tengan datos de la aplicación

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de los datos de la aplicación (Parte 4: Modificar formato)".



Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico y actualizar los datos de la aplicación. En este procedimiento, ejecuta la configuración del formato de ER para generar el informe de Intrastat y actualizar los datos de la aplicación para los detalles de almacenamiento del proceso de generación de informes.



Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de DEMF. Antes de comenzar, asegúrese de que el contexto del país para la empresa de DEMF sea Bélgica (BEL).


## <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior
1. Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.
2. Haga clic en la ficha Secuencias numéricas.
    * Para archivar los detalles del proceso de generación de informes de Intrastat, necesitamos identificar los registros de cada archivo que creamos. Una secuencia numérica especial se debe configurar para eso.  
3. Seleccione la referencia "Id. de archivo de Intrastat”.
4. En el campo Código de secuencia numérica, escriba un valor.
    * En el campo "Código de secuencia numérica", especifique o seleccione el valor "Fore_2".  
5. ResolveChanges, el código de secuencia de Número.
6. Haga clic en Guardar.
7. Cierre la página.

## <a name="run-modified-er-format"></a>Ejecutar el formato de ER modificado
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Intrastat (modelo)".
3. En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".
4. Haga clic en Ejecutar.
5. En el campo Especificar nombre de archivo, escriba“intrastat2.xml".
    * intrastat2.xml  
6. Haga clic en Aceptar

## <a name="review-er-format-executions-results"></a>Revisar los resultados de la ejecución del formato de ER
Revise el archivo XML generado.  
1. Cierre la página.
2. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.
    * Abra este formulario que contiene las transacciones de Intrastat que se incluyen en el documento electrónico generado.  
3. Haga clic en de archivo de Intrastat.
    * Dado que el formato de informe electrónico ejecutado contiene ahora valores para la actualización de los datos de la aplicación, los detalles del informe de Intrastat completado no se han almacenado. En este formulario, puede ver el registro de encabezados del archivo creado.  
4. Haga clic en Detalles.
    * En este formulario, puede ver los detalles del archivo creado.  
5. Cierre la página.
6. Cierre la página.
7. Cierre la página.

