---
title: ER Asignar componentes del formato creado a los elementos del modelo de datos (noviembre de 2016)
description: El procedimiento siguiente muestra cómo un usuario con rol de Administrador del sistema o de Desarrollador de informes electrónicos puede asignar elementos del modelo de datos a componentes de la configuración de informes electrónicos (ER) creada, lo que define un formato de documento electrónico para el dominio de pagos de la empresa.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 548f16034ebdf7e0f29e8e89d85aac880f6323a1
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026249"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>ER Asignar componentes del formato creado a los elementos del modelo de datos (noviembre de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

El procedimiento siguiente muestra cómo un usuario con rol de Administrador del sistema o de Desarrollador de informes electrónicos puede asignar elementos del modelo de datos a componentes de la configuración de informes electrónicos (ER) creada, lo que define un formato de documento electrónico para el dominio de pagos de la empresa. Este formato se utilizará después para generar documentos electrónicos para el procesamiento de pagos. En este ejemplo, usted creará una configuración de formato para la empresa de muestra "Litware, Inc". Estos pasos se pueden realizar con cualquier empresa, ya que las configuraciones de informes electrónicos se comparten en todas las empresas. Para finalizar estos pasos, primero debe completar los pasos en la guía de tareas "Creación de una configuración de formato".


## <a name="select-a-format-configuration"></a>Seleccione una configuración de formato
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Configuraciones de informes.
3. En el árbol, expanda "Pagos (modelo simplificado)".
4. En el árbol, seleccione "Pagos (modelo simplificado\BACS (ficticio Reino Unido)".
5. Haga clic en Diseñador.

## <a name="map-format-components-to-data-model-elements"></a>Asignación de los componentes de formato a los elementos del modelo de datos
1. Haga clic en Expandir/Contraer.
2. Haga clic en la ficha Asignación.
3. En el árbol , expanda "modelo".
4. En el árbol, seleccione 'Xml\Mensaje\ProcessingDate\DateTime".
5. En el árbol, seleccione "modelo\ProcessingDateTime".
6. Haga clic en Enlazar.
7. En el árbol, seleccione "'Xml\Mensaje\MessageId\Cadena".
8. En el árbol, seleccione "modelo\MessageIdentification".
9. Haga clic en Enlazar.
10. En el árbol, expanda modelo\Pagos.
11. En el árbol, seleccione "Xml\Mensaje\Pagos\Importe\Cadena".
12. En el árbol, seleccione "modelo\Pagos\InstructedAmount".
13. Haga clic en Enlazar.
14. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\TransDate\DateTime".
15. En el árbol, seleccione "modelo\Pagos\TransactionDate".
16. Haga clic en Enlazar.
17. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Descripción\Cadena".
18. En el árbol, seleccione modelo\Pagos\Descripción.
19. Haga clic en Enlazar.
20. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Divisa\Cadena".
21. En el árbol, seleccione "modelo\Pagos\Divisa".
22. Haga clic en Enlazar.
23. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Id.".
24. En el árbol, seleccione "modelo\Pagos\End2EndID".
25. Haga clic en Enlazar.
26. En el árbol, expanda modelo\Pagos\Acreedor.
27. En el árbol, expanda modelo\Pagos\Acreedor\Cuenta.
28. En el árbol, expanda modelo\Pagos\Acreedor\Agente.
29. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Cadena".
30. En el árbol, seleccione modelo\Pagos\Acreedor\Nombre.
31. Haga clic en Enlazar.
32. En el árbol, seleccione 'Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\RoutingNumber\Cadena".
33. En el árbol, seleccione "modelo\Pagos\Acreedor\Agente\RoutingNumber".
34. Haga clic en Enlazar.
35. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Proveedor\Banco\AccountNumber\Cadena".
36. En el árbol, seleccione modelo\Pagos\Acreedor\Cuenta\Número.
37. Haga clic en Enlazar.
38. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Nombre\Cadena".
39. En el árbol, expanda modelo\Pagos\Deudor.
40. En el árbol, expanda modelo\Pagos\Deudor\Cuenta.
41. En el árbol, expanda modelo\Pagos\Deudor\Agente.
42. En el árbol, seleccione modelo\Pagos\Deudor\Nombre.
43. Haga clic en Enlazar.
44. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Banco\RoutingNumber\Cadena".
45. En el árbol, seleccione "modelo\Pagos\Deudor\Agente\RoutingNumber".
46. Haga clic en Enlazar.
47. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo\Pagador\Banco\AccountNumber\Cadena".
48. En el árbol, seleccione modelo\Pagos\Deudor\Cuenta\Número.
49. Haga clic en Enlazar.
50. En el árbol, seleccione "Xml\Mensaje\Pagos\Artículo".
51. En el árbol, seleccione modelo\Pagos.
52. Haga clic en Enlazar.
53. Haga clic en Guardar.

## <a name="validate-format-mapping"></a>Validación de la asignación de formato
1. Haga clic en Validar.
    * Valide la nueva asignación para garantizar que todos los enlaces son aceptables.  
2. Cierre la página.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>Cambio del estado de la versión actual de la configuración del formato
En los siguientes pasos, usted cambiará el estado de la configuración del formato de Borrador a Completado para que esté disponible para la generación de documentos de pago.  
1. Haga clic en Cambiar estado.
2. Haga clic en Completar.
3. En el campo Descripción, escriba un valor.
    * Para ver un ejemplo, "versión 1".  
4. Haga clic en Aceptar
5. Seleccione la versión completada de la configuración actual.
    * Tenga en cuenta que la configuración se guarda como una versión 1.1 completa: versión 1 del formato basado en la versión 1 del modelo de datos.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Definición de la fecha de vigencia para la versión finalizada del formato
Cada versión del formato se puede configurar como disponible para su uso a partir de una fecha concreta. Cuando haya más de una versión de formato activa en una fecha concreta, se seleccionará para su uso el formato más reciente (según el número de versión). El valor de fecha de sesión se usa para seleccionar la versión adecuada.  

## <a name="restrict-access-to-created-format-from-companies"></a>Restricción del acceso al formato creado desde empresas
1. Expanda la sección Códigos ISO de país/región.
    * Los accesos a los formatos se pueden restringir identificando países o regiones aplicables. Si la lista de países o regiones para el formato concreto está vacía, el formato se puede usar en cualquier empresa. Si se insertan códigos de país o región ISO en la lista de países o regiones, el formato solo se puede usar en empresas si su sede principal se encuentra ubicada en dicho país o región.  

