--- 
title: "Crear una configuración de formato para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 04817d1f1851e43679995641e8b0ff99edaa83ad
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a>Crear una configuración de formato para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o de desarrollador de informes electrónicos puede crear una configuración de formato para realizar informes electrónicos. Esta configuración del formato definirá el formato de los documentos electrónicos que se usan para procesar pagos. En este ejemplo, creará una configuración del formato para la empresa de demostración, Litware, Inc. Para completar estos pasos, debe completar primero los pasos del procedimiento "Asignación de modelos a orígenes de datos seleccionados".


## <a name="create-a-new-format-configuration"></a>Creación de una configuración de formato nueva
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, seleccione Pagos (modelo simplificado).
4. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
5. En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".
6. En el campo Nombre, escriba "BACS (ficticio Reino Unido)".
    * BACS (ficticio Reino Unido)  
7. En el campo Descripción, escriba "Formato de pago de proveedor BACS (ficticio Reino Unido)".
    * Formato de pago de proveedor BACS (ficticio Reino Unido)  
    * El proveedor de configuraciones activo se especifica automáticamente aquí. Este proveedor podrá mantener esta configuración. Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.  
    * Se puede definir un formato concreto de documento electrónico. Deje este campo en blanco si desea seleccionar un formato en el tiempo de ejecución.  
8. En el campo definición del modelo de Datos, introduzca o seleccione un valor.
9. Haga clic en Crear configuración.
    * Se ha creado una nueva configuración. La versión de borrador se puede usar para almacenar el formato de diseño para gestionar documentos electrónicos.  

## <a name="design-format-of-electronic-document"></a>Diseño del formato de los documentos electrónicos
1. Haga clic en Diseñador.
2. Haga clic en Agregar raíz para abrir el cuadro de diálogo desplegable.
3. En el árbol, seleccione Común\Archivo.
4. En el campo Nombre, escriba "Xml".
    * XML  
5. En el campo Codificación, escriba "UTF-8".
    * UTF-8  
6. Haga clic en Aceptar
7. Haga clic en Agregar para abrir el cuadro desplegable.
8. En el árbol, seleccione XML\Elemento.
9. En el campo Nombre, escriba "Mensaje".
    * Mensaje  
10. Haga clic en Aceptar
11. En el árbol, seleccione 'Xml\Mensaje'.
12. Haga clic en Agregar elemento.
13. En el campo Nombre, escriba "ProcessingDate".
    * ProcessingDate  
14. Haga clic en Aceptar
15. Haga clic en Agregar elemento.
16. En el campo Nombre, escriba "MessageId".
    * MessageId  
17. Haga clic en Aceptar
18. Haga clic en Agregar elemento.
19. En el campo Nombre, escriba "Pagos".
    * Pagos  
20. Haga clic en Aceptar
21. En el árbol, seleccione 'Xml\Mensaje\Pagos'.
22. Haga clic en Agregar elemento.
23. En el campo Nombre, escriba "Artículo".
    * Artículo  
24. Haga clic en Aceptar
25. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".
26. Haga clic en Agregar para abrir el cuadro desplegable.
27. En el árbol, seleccione XML\Atributo.
28. En el campo Nombre, escriba "Id".
    * Id.  
29. Haga clic en Aceptar
30. Haga clic en Agregar para abrir el cuadro desplegable.
31. En el árbol, seleccione XML\Elemento.
32. En el campo Nombre, escriba "Proveedor".
    * Proveedor  
33. Haga clic en Aceptar
34. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor".
35. Haga clic en Agregar elemento.
36. En el campo Nombre, escriba "Nombre".
    * Nombre  
37. Haga clic en Aceptar
38. Haga clic en Agregar elemento.
39. En el campo Nombre, escriba "Banco".
    * Banco  
40. Haga clic en Aceptar
41. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco".
42. Haga clic en Agregar elemento.
43. En el campo Nombre, especifique "RoutingNumber".
    * RoutingNumber  
44. Haga clic en Aceptar
45. Haga clic en Agregar elemento.
46. En el campo Nombre, escriba "AccountNumber".
    * AccountNumber  
47. Haga clic en Aceptar
48. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor".
49. Haga clic en Copiar.
50. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".
51. Haga clic en Pegar.
52. En el campo Nombre, escriba "Pagador".
    * Pagador  
53. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".
54. Haga clic en Agregar elemento.
55. En el campo Nombre, escriba "Divisa".
    * Divisa  
56. Haga clic en Aceptar
57. Haga clic en Agregar elemento.
58. En el campo Nombre, escriba "Descripción".
    * Descripción  
59. Haga clic en Aceptar
60. Haga clic en Agregar elemento.
61. En el campo Nombre, escriba "TransDate".
    * TransDate  
62. Haga clic en Aceptar
63. Haga clic en Agregar elemento.
64. En el campo Nombre, escriba "Importe".
    * Importe  
65. Haga clic en Aceptar

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Preparación de los componentes de formato que asignar a los elementos del modelo de datos
1. En el árbol, seleccione "Xml\Mensaje\ProcessingDate".
2. Haga clic en Agregar para abrir el cuadro desplegable.
3. En el árbol, seleccione "Texto\DateTime".
4. En el campo Formato, escriba "aaaa-MM-dd".
    * dd/mm/aaaa  
5. Haga clic en Aceptar
6. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\TransDate".
7. Haga clic en DateTime.
8. En el campo Formato, escriba "aaaa-MM-dd".
    * dd/mm/aaaa  
9. En el campo tipo DateTime, seleccione "Fecha".
10. Haga clic en Aceptar
11. En el árbol, seleccione "Xml\Mensaje\MessageId".
12. Haga clic en Agregar para abrir el cuadro desplegable.
13. En el árbol, seleccione "Texto\Cadena".
14. Haga clic en Aceptar
15. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Nombre".
16. Haga clic en Agregar cadena.
17. Haga clic en Aceptar
18. En el árbol, seleccione 'Xml\Mensaje\Pagos\Artículo\Proveedor\RoutingNumber".
19. Haga clic en Agregar cadena.
20. Haga clic en Aceptar
21. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\AccountNumber".
22. Haga clic en Agregar cadena.
23. Haga clic en Aceptar
24. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Nombre".
25. Haga clic en Agregar cadena.
26. Haga clic en Aceptar
27. En el árbol, seleccione 'Xml\Mensaje\Pagos\Artículo\Pagador\RoutingNumber".
28. Haga clic en Agregar cadena.
29. Haga clic en Aceptar
30. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Banco\AccountNumber".
31. Haga clic en Agregar cadena.
32. Haga clic en Aceptar
33. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Moneda".
34. Haga clic en Agregar cadena.
35. Haga clic en Aceptar
36. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Descripción".
37. Haga clic en Agregar cadena.
38. Haga clic en Aceptar
39. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Importe".
40. Haga clic en Agregar cadena.
41. Haga clic en Aceptar
42. Haga clic en Guardar.
43. Cierre la página.


