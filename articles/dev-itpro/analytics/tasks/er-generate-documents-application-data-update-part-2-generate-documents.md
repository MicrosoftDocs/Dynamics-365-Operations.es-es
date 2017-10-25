--- 
title: "Generar documentos con actualización de datos de aplicaciones para informes electrónicos (ER)"
description: "Para completar los pasos de este procedimiento, primero debe completar el procedimiento, ER Generar documentos con la actualización de los datos de la aplicación (Parte 1: Configuraciones de importación)\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: c724ce3c39ed7097a5a842b44a095628dcdfa131
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="generate-documents-with-application-data-update-for-electronic-reporting-er"></a>Generar documentos con actualización de datos de aplicaciones para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de los datos de la aplicación (Parte 1: Configuraciones de importación)".



Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico. En este procedimiento, ejecute la configuración del formato importado de ER que se ha creado para la empresa de ejemplo, Litware, Inc. para generar documentos electrónicos.



Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de DEMF. 



Antes de comenzar, cambie el contexto del país para la empresa de DEMF de Alemania (DEU) al Bélgica (BEL). Haga clic en Administración de organizaciones > Organizaciones > Entidades jurídicas para actualizar el código de país en la dirección principal de la entidad jurídica DEMF. Reinicie la aplicación.


## <a name="run-imported-er-format"></a>Ejecutar formato de ER importado
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Intrastat (modelo)".
3. En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".
4. Haga clic en Ejecutar.
    * Ejecute la versión de borrador de la configuración del formato de ER para generar el informe de Intrastat.  
5. En el campo Especificar nombre de archivo, escriba“intrastat.xml”.
    * Especifique el nombre del archivo.  
6. Haga clic en Aceptar
    * Revise el archivo XML generado.  
7. Cierre la página.
8. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.
    * Abra este formulario para ver las transacciones de Intrastat que se incluyen en el documento electrónico generado.  
9. Haga clic en de archivo de Intrastat.
    * Dado que el formato de informe electrónico ejecutado no contiene ningún valor para la actualización de los datos de la aplicación, los detalles del informe de Intrastat completado no se han almacenado.  
10. Cierre la página.
11. Cierre la página.

