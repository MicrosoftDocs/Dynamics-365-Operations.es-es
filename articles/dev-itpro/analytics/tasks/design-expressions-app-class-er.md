--- 
title: "Diseñe expresiones para abrir métodos de clase de aplicación (ER)"
description: "Esta guía proporciona información acerca de cómo volver a usar la lógica de aplicación existente en las configuraciones de informes electrónicos (ER) llamando a los métodos necesarios de clases de aplicación en expresiones de ER."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 631fa7bae808856efb8b95700fd2a85e6d5f8725
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---
# <a name="design-expressions-to-call-application-class-methods-er"></a>Diseñe expresiones para abrir métodos de clase de aplicación (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Esta guía proporciona información acerca de cómo volver a usar la lógica de aplicación existente en las configuraciones de informes electrónicos (ER) llamando a los métodos necesarios de clases de aplicación en expresiones de ER. Los valores de los argumentos para llamar a clases se pueden definir de forma dinámica en tiempo de ejecución: por ejemplo, en función de la información en el documento de análisis para proteger su corrección. En esta guía, creará las configuraciones de ER necesarias para la empresa de muestra, Litware, Inc. Este procedimiento se crea para los usuarios con el rol asignado de Administrador del sistema o de Desarrollador de informes electrónicos. 

Estos pasos se pueden completar mediante cualquier conjunto de datos. También debe descargar y guardar el archivo siguiente localmente: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

Para completar estos pasos, primero debe completar los pasos del procedimiento "ER Creación y activación de un proveedor de configuraciones".

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Compruebe que el proveedor de configuración de la empresa de ejemplo, Litware, Inc., está disponible y marcado como activo. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".   
    * Supongamos que está diseñando un proceso para analizar los extractos bancarios de entrada para una actualización de los datos de la aplicación. Recibirá los extractos bancarios entrantes como archivos TXT que incluyen los códigos de IBAN. Como parte del proceso de importación del extracto bancario, debe validar la corrección de los códigos de este IBAN mediante la lógica que esté ya disponible en Dynamics 365 for Finance and Operations.   

## <a name="import-a-new-er-model-configuration"></a>Importe una nueva configuración para el modelo ER
1. En la lista, busque y seleccione el registro deseado.
    * Seleccione el mosaico del proveedor de Microsoft.  
2. Haga clic en Repositorios.
3. Haga clic en Mostrar filtros.
4. Añada un campo de filtro "Nombre de tipo". En el campo Nombre, especifique el valor “recursos”, seleccione el operador del filtro "contiene" y haga clic en Aplicar.
5. Haga clic en Abrir.
6. En el árbol, seleccione "Modelo de pago".
    * Si el botón de la importación de las ficha desplegable Versiones no está habilitado, ya ha importado la versión 1 del “modelo de pago” de la configuración de ER. Puede omitir los pasos del resto de esta subtarea.   
7. Haga clic en Importar.
8. Haga clic en Sí.
9. Cierre la página.
10. Cierre la página.

## <a name="add-a-new-er-format-configuration"></a>Añada una nueva configuración para el formato de ER
1. Haga clic en Configuraciones de informes.
    * Agregar un nuevo formato de ER para analizar los extractos bancarios de entrada en el formato de TXT.  
2. En el árbol, seleccione "Modelo de pago".
3. Haga clic en Crear configuración para abrir el menú del cuadro de diálogo.
4. En el campo Nuevo, especifique "Formato basado en modelo de datos PaymentModel".
5. En el campo Nombre, escriba “formato de importación de extracto bancario (muestra)”.
    * Formato de importación del extracto bancario (muestra)  
6. Seleccione Sí en el campo Admite la importación de datos.
7. Haga clic en Crear configuración.

## <a name="design-the-er-format-configuration---format"></a>Diseñar la configuración del formato de ER - format
1. Haga clic en Diseñador.
    * El formato diseñado representa la estructura esperada del archivo externo en formato TXT.  
2. Haga clic en Agregar para abrir el menú del cuadro de diálogo.
3. En el árbol, seleccione "Texto\Secuencia".
4. Escriba "Raíz" en el campo Nombre.
    * Raíz  
5. En el campo Caracteres especiales, seleccione "Línea nueva - Windows (CR LF)".
    * La opción seleccione "Línea nueva - Windows (CR LF)" se ha seleccionado en el campo "Caracteres especiales". Basándose en esta configuración, cada línea en el archivo de análisis se considera un registro individual.  
6. Haga clic en Aceptar
7. Haga clic en Agregar para abrir el cuadro desplegable.
8. En el árbol, seleccione "Texto\Secuencia".
9. En el campo Nombre, escriba "Rows".
    * Filas  
10. En el campo de Multiplicidad, seleccione "Uno o varios".
    * La opción “Uno o varios” se ha seleccionado en el campo “Multiplicidad”. En base a este valor, se espera que el menos una línea se visualizará en el archivo del análisis.  
11. Haga clic en Aceptar
12. En el árbol, seleccione 'Root\Rows'.
13. Haga clic en Agregar secuencia.
14. En el campo Nombre, escriba "Fields".
    * Campos  
15. En el campo de Multiplicidad, seleccione "Exactamente uno".
16. Haga clic en Aceptar
17. En el árbol , seleccione 'Root\Rows\Fields'.
18. Haga clic en Agregar para abrir el cuadro desplegable.
19. En el árbol, seleccione "Texto\Cadena".
20. En el campo Nombre, escriba "IBAN".
    * IBAN  
21. Haga clic en Aceptar
    * Se ha configurado que cada línea del archivo de análisis contenga el único código de IBAN.  
22. Haga clic en Guardar.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>Diseñar la configuración del formato de ER – asignación al modelo de datos
1. Haga clic en Asignar formato a modelo.
2. Haga clic en Nuevo.
3. En el campo Definición, escriba "BankToCustomerDebitCreditNotificationInitiation".
    * BankToCustomerDebitCreditNotificationInitiation  
4. ResolveChanges la Definición.
5. En el campo Nombre, escriba "Asignar a modelo de datos".
    * Asignación del modelo de datos  
6. Haga clic en Guardar.
7. Haga clic en Diseñador.
8. En el árbol, seleccione 'Dynamics 365 for Operations\Class'.
9. Haga clic en Agregar raíz.
    * Agregar un nuevo origen de datos para llamar a la lógica de aplicación existente para obtener la validación de los códigos de IBAN.  
10. En el campo Nombre, escriba "check codes".
    * comprobar códigos  
11. En el campo Clase, escriba ''ISO7064".
    * ISO7064  
12. Haga clic en Aceptar
13. En el árbol, expanda "formato".
14. En el árbol, amplíe 'format\Root: Sequence(Root)'.
15. En el árbol, seleccione 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)'.
16. Haga clic en Enlazar.
17. En el árbol, amplíe 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)'.
18. En el árbol, amplíe 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)'.
19. En el árbol, seleccione 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)'.
20. En el árbol, amplíe 'Payments = format.Root.Rows'.
21. En el árbol, amplíe 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)'.
22. En el árbol, amplíe 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification'.
23. En el árbol, seleccione 'Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification\IBAN'.
24. Haga clic en Enlazar.
25. Haga clic en la pestaña Validaciones.
26. Haga clic en Nuevo.
    * Agregar una nueva regla de validación que muestre un error para cualquier línea del archivo de análisis que contenga un código de IBAN no válido.  
27. Haga clic en Editar condición.
28. En el árbol, amplíe 'check_codes'.
29. En el árbol, seleccione 'check_codes\verifyMOD1271_36'.
30. Haga clic en Agregar origen de datos.
31. En el campo Fórmula, escriba 'check_codes.verifyMOD1271_36('.
    * check_codes.verifyMOD1271_36(  
32. En el árbol, expanda "formato".
33. En el árbol, amplíe 'format\Root: Sequence(Root)'.
34. En el árbol, amplíe 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)'.
35. En el árbol, amplíe 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)'.
36. En el árbol, seleccione 'format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)'.
37. Haga clic en Agregar origen de datos.
38. En el campo de fórmula, introduzca 'check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)'.
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Haga clic en Guardar.
40. Cierre la página.
    * La condición de validación se ha configurado para devolver FALSE para todo código IBAN no válido llamando al método existente “verifyMOD1271_36” de la clase de aplicación “ISO7064”. Tenga en cuenta que el valor del código IBAN se define de forma dinámica en el tiempo de ejecución como argumento del método de llamada basándose en el contenido del archivo TXT de análisis.   
41. Haga clic en Editar mensaje.
42. En el campo de fórmula, entre 'CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)'.
    * CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)  
43. Haga clic en Guardar.
44. Cierre la página.
45. Haga clic en Guardar.
46. Cierre la página.

## <a name="run-the-format-mapping"></a>Ejecute la asignación de formato
Para comprobar, ejecute la asignación de formato mediante el archivo SampleIncomingMessage.txt que descargó. La salida generada incluye datos que importarán desde el archivo TXT seleccionado y se rellenarán en el modelo de datos personalizado durante la importación real.   
1. Haga clic en Ejecutar.
    * Haga clic en Examinar y desplácese hasta el archivo SampleIncomingMessage.txt que ha descargado previamente.  
2. Haga clic en Aceptar
    * Revise la salida en formato XML que representa los datos que se han importado del archivo seleccionado y se han trasladado al modelo de datos. Tenga en cuenta que solo las líneas 3 del archivo TXT importado se procesaron. El código de IBAN de la línea 4 que no es válida se saltó y se proporcionó un mensaje de error en el registro de información.  


