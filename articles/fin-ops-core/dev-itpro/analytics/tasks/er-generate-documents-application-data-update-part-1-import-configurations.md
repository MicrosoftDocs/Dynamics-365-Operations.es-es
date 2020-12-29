---
title: Importar configuraciones para generar documentos que tengan datos de la aplicación
description: 'Para completar los pasos de este procedimiento, primero debe completar los pasos del procedimiento, "ER: Crear un proveedor de configuraciones y marcarlo como activo".'
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f919d953c3aa0c8d16366167a12e52d35f32cdf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684628"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>Importar configuraciones para generar documentos que tengan datos de la aplicación

[!include [banner](../../includes/banner.md)]

Para completar los pasos de este procedimiento, primero debe completar los pasos del procedimiento, "ER: Crear un proveedor de configuraciones y marcarlo como activo".

Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico. En este procedimiento, importará las configuraciones de ER necesarias que se han creado para la empresa de ejemplo, Litware, Inc. y las usará para generar documentos electrónicos. Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de DEMF. Antes de empezar, descargue y guardar los archivos que aparecen en el tema de Ayuda, “Generar documentos electrónicos y actualizar los datos de las aplicaciones mediante la herramienta de informes electrónicos” (generate-electronic-documents-update-application-data/). Los archivos son Intrastat (model).xml, Intrastat (mapping).xml y Intrastat (format).xml.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo. Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".  
    * Los pasos de este procedimiento muestran cómo usar capacidades de ER para completar una actualización de datos de la aplicación y cómo generar un informe Intrastat. Los detalles del proceso de generación de informes se almacenan en las tablas de la aplicación. Actualmente, cuando el proceso de generación de informes de Intrastat se activa desde el formulario Intrastat, el archivado se realiza en función de la lógica programada en el código fuente existente. En este procedimiento, no configurará una lógica similar pero simplificada de los datos de la aplicación utilizando solamente el marco de ER. No se realizarán cambios en el código fuente.   

## <a name="import-er-configurations"></a>Importar configuraciones de ER
1. Haga clic en Configuraciones de informes.
2. Haga clic en Intercambiar.
3. Haga clic en Cargar desde un archivo XML.
    * Importe la configuración del modelo de ER que contenga un modelo de datos que se designe para usarlo como el origen de datos para la generación de informes de ER. Más tarde, se ampliará esta definición del modelo de datos para utilizarlo para que una actualización de datos de la aplicación almacene los detalles del proceso de generación de informes de Intrastat.   
    * Haga clic en Examinar y seleccione el archivo Intrastat (model).xml.  
4. Haga clic en Aceptar
5. En el árbol, seleccione "Intrastat (modelo)".
6. Haga clic en Diseñador.
7. En el árbol, expanda "Para el documento de salida".
8. En el árbol, expanda "Para el documento de salida\Transacciones".
    * Revisar la estructura del modelo de datos importado. Tenga en cuenta que el artículo de la raíz “para el documento de salida” se ha definido para especificar el flujo de datos para recopilar datos de la aplicación y utilizarlos como origen de datos para generar el informe Intrastat. Las "transacciones (lista de registro)" se utilizan para representar la lista de transacciones Intrastat que deben crear un informe. Dado que se guardarán los códigos de producto del informe, el identificador único de un código de producto "Id. de inf de producto (Int64)" es necesario en este flujo de datos.   
9. Cierre la página.
10. Haga clic en Intercambiar.
11. Haga clic en Cargar desde un archivo XML.
    * Importe la configuración de la asignación de ER que especifica el flujo de datos para recopilar datos de la aplicación y después utilizarlos para generar el informe de Intrastat. Más tarde, se ampliará esta definición de asignación del modelo para obtener datos del informe de Intrastat y utilizarlos la actualización de datos de la aplicación para almacene los detalles del proceso de generación de informes de Intrastat.   
    * Haga clic en Examinar y seleccione el archivo Intrastat (mapping).xml  
12. Haga clic en Aceptar
13. En el árbol, expanda "Intrastat (modelo)".
14. En el árbol, seleccione "Intrastat (modelo)\Intrastat (asignación)".
15. Haga clic en Diseñador.
    * Tenga en cuenta que la asignación de modelo actual contiene el valor “Para modelo" en el campo Dirección. Esto significa que esta asignación de modelo se ha diseñado para recopilar datos de la aplicación y almacenarlos en el modelo de datos.  
16. Haga clic en Diseñador.
17. En el árbol, expanda "Lista".
18. En el árbol, expanda "Transacciones = Lista".
    * Revise la estructura de la asignación modelo que usa el modelo de datos que se filtra según el artículo de la raíz, “para el documento de salida.” Tenga en cuenta que el origen de datos agregado, "lista", proporciona acceso a los datos de la aplicación necesarios, que es la lista de registros de la tabla Intrastat.  
19. Cierre la página.
20. Cierre la página.
21. Haga clic en Intercambiar.
22. Haga clic en Cargar desde un archivo XML.
    * Importe la configuración del formato de ER que especifica el diseño del informe Intrastat y el proceso de rellenar datos para el informe. Más tarde, se ampliará esta definición de formato para pasar los datos del informe de Intrastat al modelo de datos y después usarlos para actualizar los datos de la aplicación para guardar los detalles del proceso de generación de informes de Intrastat.   
    * Haga clic en Examinar y seleccione el archivo Intrastat (format).xml.  
23. Haga clic en Aceptar
24. En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".
25. Haga clic en Diseñador.
26. Haga clic en Expandir/Contraer.
27. En el árbol , seleccione "Archivo\Declaración".
28. Haga clic en la ficha Asignación.
29. En el árbol, seleccione "Archivo".
    * Revise la estructura del formato que se usa para generar el informe de Intrastat. Tenga en cuenta que está diseñado para generar un archivo XML rellenando datos desde el modelo de datos, que se basa en el elemento raíz “Para el documento de salida”. Compruebe que el nombre para el archivo generado se haya definido en el formulario del cuadro de diálogo del usuario (el origen de datos “fn” se utiliza para eso).   
30. Cierre la página.

