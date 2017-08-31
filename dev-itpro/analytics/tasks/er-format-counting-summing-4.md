--- 
title: "Ejecutar el formato para realizar recuentos y sumas para informes electrónicos (ER)"
description: "Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada."
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 90a0dc0fc32a448d859fbb0933ea6f12ea16668f
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="run-the-format-to-do-counting-and-summing-for-electronic-reporting-er"></a>Ejecutar el formato para realizar recuentos y sumas para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Los pasos siguientes explican cómo un usuario asignado al administrador del sistema o al rol de desarrollador de informes electrónicos puede configurar un formato de informe electrónico (ER) para que realice el recuento y calcule en función de los datos de la salida de texto ya generada. Estos pasos se pueden llevar a cabo en la empresa DEMF.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Configurar el formato para contar y sumar (Parte 3: Uso de los cálculos para crear la salida)".

Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Pruebe esta configuración para la generación de los informes Intrastat
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, expanda "Intrastat modelo".
4. En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".
5. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".
6. En el panel de acciones, haga clic en Configuraciones.
7. Haga clic en Parámetros de usuario.
8. Seleccione Sí en el campo Parámetros de ejecución.
9. Haga clic en Aceptar
10. Haga clic en Editar.
11. Seleccione Sí en el campo Borrador de ejecución.
12. Haga clic en Guardar.
13. Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.
14. Expanda la sección Informes electrónicos.
15. Seleccione la configuración "Intrastat (DE) con recuento & suma".
16. Seleccione la configuración "Intrastat (DE) con recuento & suma".
17. Haga clic en Guardar.
18. Cierre la página.
19. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.
20. Haga clic en Salida.
21. Haga clic en Informe.
    * Ejecute el proceso de generación de informes de Intrastat.  
22. En el campo Fecha inicial, defina la fecha en "2000-01-01".
    * Defina las fechas de inicio y fin del período de informes que incluye las existentes en las transacciones del formulario.  
23. En el campo Fecha final, defina la fecha en "2022-12-31".
    * Defina las fechas de inicio y fin del período de informes que incluye las existentes en las transacciones del formulario.  
24. En el campo Dirección, seleccione "Llegadas".
25. Seleccione Sí en el campo Generar archivo.
26. Haga clic en Aceptar
    * Revise la salida creada con las líneas de resumen al final.  
27. Haga clic en Nuevo.
28. En la lista, marque la fila seleccionada.
29. En el campo Dirección, seleccione "Distribuciones".
30. En el campo Número de artículo, especifique o seleccione un valor.
31. En el campo Código Intrastat de la mercancía, especifique o seleccione un valor.
32. Establezca un Peso de "10".
33. establezca un importe de Factura de "10000"
34. Establezca un Importe estadístico de "10000"
35. Haga clic en Salida.
36. Haga clic en Informe.
37. En el campo Dirección, seleccione "Distribuciones".
38. Haga clic en Aceptar
    * Revise la salida creada con las líneas de resumen al final. Observe que se ha cambiado en comparación con la primera ejecución.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>Ejecute esta configuración en modo depuración para revisar los datos recogidos de suma & recuento
1. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
2. En el árbol, expanda "Intrastat modelo".
3. En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".
4. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".
5. En el panel de acciones, haga clic en Configuraciones.
6. Haga clic en Parámetros de usuario.
7. Seleccione Sí en el campo Ejecutar en modo depuración.
8. Haga clic en Aceptar
9. Cierre la página.
10. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.
11. Haga clic en Salida.
12. Haga clic en Informe.
13. Haga clic en Aceptar
14. Cierre la página.
15. Vaya a Administración de la organización > Informes electrónicos > Configuraciones.
16. En el árbol, expanda "Intrastat modelo".
17. En el árbol, expanda "Modelo de Intrastat\Intrastat (DE)".
18. En el árbol, seleccione "Modelo de Intrastat\Intrastat (DE)\Intrastat (DE) con recuento & suma".
19. Haga clic en los registros de Depuración.
    * Tenga en cuenta que se ha creado un registro de depuración para el proceso de ejecución de la configuración seleccionada.  
20. Haga clic en Vincular.
21. Haga clic en Abrir.
    * Revise el archivo XML creado que contiene los detalles de recuento y suma obtenidos durante la ejecución de la configuración seleccionada.  


