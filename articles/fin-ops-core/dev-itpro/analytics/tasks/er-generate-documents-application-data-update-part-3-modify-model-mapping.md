---
title: Modificar modelos y asignaciones para generar documentos que tengan datos de la aplicación
description: 'Este tema describe cómo diseñar las configuraciones de los informes para generar un documento electrónico y actualizar datos de la aplicación. (Parte 2: generar documentos).'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64bcf885fe2f5fca6b91589171b5e539eff2c3e5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567101"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a>Modificar modelos y asignaciones para generar documentos que tengan datos de la aplicación

[!include [banner](../../includes/banner.md)]

Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de datos de la aplicación (Parte 2: Generar documentos)". 

Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico y actualizar los datos de la aplicación. En este procedimiento, se modificarán las configuraciones de ER para comenzar a utilizarlas para generar documentos electrónicos y actualizar los datos de la aplicación. Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de DEMF.


## <a name="modify-data-model"></a>Modificar modelos de datos
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, seleccione "Intrastat (modelo)".
    * Ampliará cómo se usa el modelo de datos. Además de usarlo como origen de datos para generar el informe de Intrastat, el modelo de datos se usará para obtener detalles sobre el proceso de generación de informes de Intrastat. Los detalles se usarán después para actualizar los datos de la aplicación.   
3. Haga clic en Diseñador.
4. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
5. En el campo "Nuevo nodo como", escriba "Raíz del modelo".
6. En el campo Nombre, escriba "Para actualizar datos de la aplicación".
    * Para la actualización de los datos de la aplicación  
7. Haga clic en Agregar.
8. En el árbol, seleccione “Para actualizar datos de la aplicación".
    * Este nuevo elemento raíz se agrega para especificar el flujo de datos para desplazar datos del informe de Intrastat (usado como origen de datos) a las tablas de la aplicación (el destino de la actualización). Tenga en cuenta que los distintos elementos raíz se deben utilizar para obtener los datos que se envían al documento de salida y para recopilar datos del documento que se usa para actualizar los datos de la aplicación.   
9. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
10. En el campo Nombre, escriba "Encabezado de archivo".
    * Encabezado de archivo  
11. En el campo Tipo de artículo, seleccione Lista de registros.
12. Haga clic en Agregar.
    * Dado que creará un registro para cada informe de Intrastat que se genere, debe crear un elemento nuevo para eso.  
13. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
14. En el campo Nombre, introduzca "Nombre de archivo".
    * Nombre de archivo  
15. En el campo Tipo de artículo, seleccione Cadena.
16. Haga clic en Agregar.
17. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
18. En el campo Nombre, escriba "Número de líneas".
    * Número de líneas  
19. En el campo Tipo de artículo, seleccione "Entero".
20. Haga clic en Agregar.
    * Agregue este artículo para representar el número de transacciones de Intrastat que se registran durante el proceso actual de generación de informes.  
21. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
22. En el campo Nombre, escriba "Líneas de archivo".
    * Líneas de archivo  
23. En el campo Tipo de artículo, seleccione Lista de registros.
24. Haga clic en Agregar.
    * Agregue este artículo para representar la lista de transacciones de Intrastat que se registran durante el proceso actual de generación de informes.  
25. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
26. En el campo Nombre, escriba "Importe".
    * Importe  
27. En el campo Tipo de artículo, seleccione Real.
28. Haga clic en Agregar.
29. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
30. En el campo Nombre, escriba “Id. de reg. de materiales”.
    * Id. de reg de mercancías  
31. En el campo Tipo de artículo, seleccione "Int64".
32. Haga clic en Agregar.
33. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
34. En el campo Nombre, escriba "Número de elemento".
    * código de artículo  
35. En el campo Tipo de artículo, seleccione Cadena.
36. Haga clic en Agregar.
37. Haga clic en Guardar.
38. Cierre la página.

## <a name="modify-model-mapping"></a>Modificar asignación de modelos
1. En el árbol, expanda "Intrastat (modelo)".
2. En el árbol, seleccione "Intrastat (modelo)\Intrastat (asignación)".
    * Permite modificar la asignación del modelo existente para comenzar a utilizarlo para la actualización de los datos de la aplicación y para archivar los detalles de informes de Intrastat.  
3. Haga clic en Diseñador.
4. Haga clic en Nuevo.
5. En el campo Nombre, escriba "Actualizar archivado".
    * Actualizar archivo  
6. En el campo Dirección, seleccione "A destino".
7. Haga clic en Guardar.
    * Esta nueva asignación especifica el flujo de datos para desplazar datos (detalles del informe de Intrastat) desde el modelo de datos a las tablas de la aplicación (el destino de la actualización). Tenga en cuenta que los diferentes elementos raíz del modelo se deben utilizar para recopilar datos de la aplicación para el proceso de generación de informes y después usar los datos del modelo para la actualización de los datos de la aplicación.   
8. Haga clic en Diseñador.
9. En el árbol, seleccione "Modelo de datos\Modelo de datos".
    * Agregar el origen de los datos necesario. Este es el modelo de datos que contiene los detalles de las transacciones de intrastat registradas que deben archivarse.  
10. Haga clic en Agregar raíz.
11. En el campo Nombre, escriba "Modelo".
    * modelo  
12. En el campo de Definición, especifique o seleccione el valor “Para la actualización de datos de la aplicación".
    * Para la actualización de los datos de la aplicación  
13. Haga clic en Aceptar.
14. En el árbol , expanda "modelo".
15. En el árbol, seleccione el apartado "Funciones\Campo calculado".
16. En el árbol, seleccione "modelo\Encabezado de archivo".
17. Haga clic en Agregar.
    * Dado que desea enumerar las transacciones de Intrastat registradas para archivar, el origen de datos adecuado se debe suma.  
18. En el campo Nombre, escriba "Líneas enumeradas".
    * Líneas enumeradas  
19. Haga clic en Editar fórmula.
20. En el árbol , seleccione "Lista\ENUMERAR".
21. Haga clic en Agregar función.
22. En el árbol , expanda "modelo".
23. En el árbol, expanda "modelo\Encabezado de archivo".
24. En el árbol, seleccione "modelo\Encabezado de archivo\Líneas de archivo".
25. Haga clic en Agregar origen de datos.
26. En el campo Fórmula, especifique "ENUMERATE(model.'Archive header'.'Archive lines')".
    * ENUMERE (modelo. “Encabezado de archivo”. “Líneas del archivo")  
27. Haga clic en Guardar.
28. Cierre la página.
29. Haga clic en Aceptar
30. Haga clic en Agregar destino.
    * Agregue las tablas de la aplicación como destinos requeridos que necesitan actualizaciones para archivar los detalles de las transacciones de Intrastat registradas.  
31. En el campo Nombre, escriba "Archivo".
    * Archivar  
32. En el campo Tabla, escriba "IntrastatArchiveGeneral".
    * IntrastatArchivoGeneral  
    * Conserve la acción de registro “Insertar” para poder agregar registros durante el archivado de detalles de cada proceso de generación de informes de Intrastat.  
33. Seleccione Sí en el campo Registrar en registro de información.
    * Seleccione Si para obtener información sobre los problemas con la actualización de los datos de la aplicación.  
34. Seleccione Sí en el campo Omitir validación de acciones del registro.
    * Seleccione Sí para suprimir errores de validación sobre campo vacío de "archivo Intrastat ID“. Esto se hace después de que se agreguen los registros, en función de la configuración del número de secuencia que esté configurado para esta tabla en el formulario de Parámetros de comercio exterior.  
35. Haga clic en Aceptar
    * Vincular elementos del origen de datos agregados (el modelo filtrado basado en el elemento raíz seleccionado) con los elementos de destino agregados.  
36. En el árbol, expanda "Archivo".
37. En el árbol, expanda "Archivo\<Relaciones".
38. En el árbol, expanda "Archivo\<Relaciones\DetalleArchivoIntrastat".
39. En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Cantidad(CantidadMST)".
40. En el árbol, expanda "modelo\Encabezado de archivo\Líneas enumeradas".
41. En el árbol, expanda "modelo\Encabezado de archivo\Líneas enumeradas\Valor".
42. En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Importe".
43. Haga clic en Enlazar.
44. En el árbol, seleccione “Archivo\<Relaciones\DetalleArchivoIntrastat\Productos(ProductosIntrastat)".
45. En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Producto Id reg".
46. Haga clic en Enlazar.
47. En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Numero de elemento(IdElemento)".
48. En el árbol, seleccione"modelo\Encabezado de archivo\Líneas enumeradas\Valor\Número de elemento".
49. Haga clic en Enlazar.
50. En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat\Numero de línea (NúmeroLínea)".
51. En el árbol, seleccione "modelo\Encabezado de archivo\Líneas enumeradas\Número".
52. Haga clic en Enlazar.
53. En el árbol, seleccione "Archivo\<Relaciones\DetalleArchivoIntrastat".
54. En el árbol, seleccione "modelo\Encabezado de archivo\Líneas enumeradas".
55. Haga clic en Enlazar.
56. En el árbol, seleccione "Archivo\Nombre de archivo(NombreArchivo)".
57. En el árbol, seleccione "modelo\Encabezado de archivo\Nombre de archivo".
58. Haga clic en Enlazar.
59. En el árbol, seleccione "Archivo\Número de líneas(NúmeroDeLíneas)".
60. En el árbol, seleccione "modelo\Encabezado de archivo\Número de líneas".
61. Haga clic en Enlazar.
62. En el árbol, seleccione "Archivo".
63. En el árbol, seleccione "modelo\Encabezado de archivo".
64. Haga clic en Enlazar.
65. Haga clic en Guardar.
66. Cierre la página.
67. Cierre la página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]