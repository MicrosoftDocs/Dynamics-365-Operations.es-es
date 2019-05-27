---
title: Modificar formatos para generar documentos que tengan datos de la aplicación
description: 'Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER Generar documentos con la actualización de datos de la aplicación (Parte 3: Modificar el modelo y la asignación)".'
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
ms.openlocfilehash: a095d0326835b0ae7322d5d58307216ee828649e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544550"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>Modificar formatos para generar documentos que tengan datos de la aplicación

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de los datos de la aplicación (Parte 3: Modificar el modelo y la asignación)".

Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico y actualizar los datos de la aplicación. En este procedimiento, se modificarán las configuraciones de ER para que no se usen solo para generar documentos electrónicos, sino también para actualizar los datos de la aplicación. Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de DEMF.


## <a name="modify-format-to-collect-details-of-reporting"></a>Modificar el formato para obtener los detalles del informe
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Intrastat (modelo)".
3. En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".
4. Haga clic en Diseñador.
5. En el árbol, expanda "Archivo".
6. En el árbol, expanda "Archivo\Declaración".
7. En el árbol, expanda "Archivo\Declaración\Datos"
8. En el campo de Multiplicidad, seleccione "Uno o varios".
    * Configurar el elemento de formato para almacenar los detalles del proceso de generación de informes de Intrastat. Este elemento representa el registro de encabezado del archivo.  
9. En el árbol, expanda "Archivo\Declaración\Datos"
10. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento"
11. En el campo de Multiplicidad, seleccione "Cero o varios".
    * Configurar el elemento de formato para almacenar los detalles del proceso de generación de informes de Intrastat. Este elemento representará la lista de líneas almacenadas.  
12. En el árbol, expanda "Archivo\Declaración\Datos\Elemento".
13. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim1"
14. Seleccione Sí en el campo Excluido.
    * No se guardarán estos datos, por lo que puede excluir este elemento del formato del origen de datos de los detalles de generación de informes de Intrastat.  
15. En el árbol, expanda "Archivo\Declaración\Datos\Elemento\Dim1"
16. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim1\propiedad".
17. Seleccione Sí en el campo Excluido.
18. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento,\Dim1\fecha".
19. Seleccione Sí en el campo Excluido.
20. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim2"
21. Seleccione Sí en el campo Excluido.
22. En el árbol, expanda "Archivo\Declaración\Datos\Elemento\Dim2"
23. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim2\propiedad".
24. Seleccione Sí en el campo Excluido.
25. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim2\código".
26. Seleccione Sí en el campo Excluido.
27. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim3"
    * Varios elementos de formato pueden tener el mismo nombre. Por ejemplo, "Dim". No puede reconocerlos explícitamente cuando se usa este formato como origen de datos para almacenar los detalles de la generación de informes de Intrastat, por lo que es necesario definir nombres alternativos para esos elementos de formato.   
28. En el campo Nombre, escriba "Importe".
    * Importe  
29. En el campo de Multiplicidad, seleccione "Exactamente uno".
30. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento\Dim4"
31. En el campo Nombre, escriba "Artículo".
    * Artículo  
32. En el campo de Multiplicidad, seleccione "Exactamente uno".
    * Además de los elementos de formato de diseño, los siguientes detalles de generación de informes de Intrastat se deben almacenar: identificación de registro única de cada elemento de material registrado y nombre de archivo generado. Dado que este datos no se rellenará en el informe de Intrastat, debe agregar el formato que está relacionado con estos elementos de detalle como elementos de origen de datos.  
33. En el árbol, expanda "Archivo\Declaración\Datos"
34. Haga clic en Agregar para abrir el cuadro desplegable.
35. En el árbol, seleccione "Origen de datos\Elemento".
36. En el campo Nombre, introduzca "Nombre de archivo".
    * Nombre de archivo  
37. En el campo Tipo de datos, seleccione "Cadena".
38. Haga clic en Aceptar
39. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento"
40. Haga clic en Agregar elemento.
41. En el campo Nombre, escriba “Id. de reg. de materiales”.
    * Id. de reg de mercancías  
42. En el campo Tipo de dato, seleccione "Int64".
43. Haga clic en Aceptar
44. Haga clic en la ficha Asignación.
45. En el árbol, seleccione "Archivo\Declaración\Datos\Nombre de archivo".
46. Haga clic en Enlazar.
47. En el árbol , expanda "modelo".
48. En el árbol, expanda "modelo\Transacciones".
49. En el árbol, seleccione "Archivo\Declaración\Datos\Elemento = modelo.Transacciones\Id. de reg. de producto".
50. En el árbol, seleccione "modelo\Transacciones\Id. de reg. de producto".
51. Haga clic en Enlazar.
52. Haga clic en Guardar.

## <a name="modify-format-to-memorize-details-of-reporting"></a>Modificar el formato para memorizar los detalles del informe
1. Haga clic en Asignar formato a modelo.
2. Haga clic en Nuevo.
3. En el campo de Definición, especifique o seleccione el elemento raíz “Para la actualización de datos de la aplicación".
    * Para la actualización de los datos de la aplicación  
4. En el campo Nombre, escriba "Asignación a datos de actualización".
    * Asignación para actualizar datos  
5. Haga clic en Guardar.
    * Esta asignación define cómo los detalles del informe de Intrastat se obtienen en el modelo de datos, la estructura que especifica el elemento raíz seleccionado “Para la actualización de datos de la aplicación”. Estos detalles, la asignación de modelo con el mismo elemento raíz “Para la actualización de datos de la aplicación” y la dirección "A destino" se utilizará par la actualización de los datos de la aplicación. La actualización de los datos de la aplicación comienza inmediatamente después de que se genera el informe de Intrastat saliente. Tenga en cuenta que la actualización de los datos de la aplicación se puede saltar en el tiempo de ejecución, pero el modelo de datos debe estar vacío (con la lista de registro vacía).   
6. Haga clic en Diseñador.
    * Tenga en cuenta que el formato de informe de Intrastat saliente se agrega de forma predeterminada como origen de datos para esta asignación de modelo.  
    * Vincule los elementos del informe diseñado (presentado como origen de datos) a los elementos del modelo de datos, que se filtra según el elemento raíz del modelo seleccionado.  
7. En el árbol, expanda "Encabezado de archivo".
8. En el árbol, expanda "Encabezado de archivo\Líneas de archivo".
9. En el árbol, expanda "formato".
10. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)".
11. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)".
12. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..* (Elemento)".
13. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..* (Elemento)\Dim3: Elemento XML 1..1 (Importe)".
14. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..* (Elemento)\Dim4: Elemento XML 1..1 (Elemento)".
15. En el árbol, seleccione "Encabezado de archivo\Número de líneas".
16. Haga clic en Editar.
17. En el árbol, seleccione "Lista\COUNT".
18. Haga clic en Agregar función.
19. En el árbol, expanda "formato".
20. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)".
21. En el árbol, expanda "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)".
22. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..* (Elemento)".
23. Haga clic en Agregar origen de datos.
24. En el campo Fórmula, escriba "COUNT(format.Declaration.Data.Item)".
    * RECUENTO (formato.Declaración.Datos.Elemento)  
25. Haga clic en Guardar.
26. Cierre la página.
27. En el árbol, seleccione "Encabezad de archivo\Nombre de archivo".
28. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Nombre de archivo: Cadena de elemento(Nombre de archivo)".
29. Haga clic en Enlazar.
30. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..* (Elemento)\Dim4: Elemento XML 1..1 (elemento)\número: Cadena(número)".
31. En el árbol, seleccione "Encabezado de archivo\Líneas de archivo\Número de elemento".
32. Haga clic en Enlazar.
33. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..*(Elemento)\Dim3: Elemento XML 1..1 (Importe)\valor: Numérico real(valor)".
34. En el árbol, seleccione "Encabezado de archivo\Líneas de archivo\Importe".
35. Haga clic en Enlazar.
36. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..*(Elemento)\Id. de reg. de materiales: Elemento Int64(Id. de reg. de materiales)".
37. En el árbol, seleccione "Encabezado de archivo\Líneas de archivo\Id. de reg. de materiales".
38. Haga clic en Enlazar.
39. En el árbol, seleccione "Encabezado de archivo\Líneas de archivo".
40. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)\Elemento: Elemento XML 0..* (Elemento)".
41. Haga clic en Enlazar.
42. En el árbol, seleccione "Encabezado de archivo".
43. En el árbol, seleccione "formato\Declaración: elemento XML(Declaración)\Datos: Elemento XML 1..* (Datos)".
44. Haga clic en Enlazar.
45. Haga clic en Guardar.
46. Cierre la página.
47. Cierre la página.
48. Cierre la página.

