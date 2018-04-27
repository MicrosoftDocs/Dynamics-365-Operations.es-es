--- 
title: "Diseñar una configuración para importar datos desde un archivo externo en formato CSV (ER)"
description: "Use este procedimiento para diseñar configuraciones de informes electrónicos (ER) para importar datos a Dynamics 365 for Finance and Operations, desde un archivo externo en formato CSV."
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
ms.openlocfilehash: f6bfa9f7c0638b0eaacf1a49bcd7d84ffab3acbf
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---
# <a name="design-a-configuration-to-import-data-from-an-external-file-in-csv-format-er"></a>Diseñar una configuración para importar datos desde un archivo externo en formato CSV (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Use este procedimiento para diseñar configuraciones de informes electrónicos (ER) para importar datos a Dynamics 365 for Finance and Operations, desde un archivo externo en formato CSV. En este procedimiento, creará las configuraciones necesarias de ER para la empresa del ejemplo, Litware, Inc. Para completar estos pasos, primero debe completar los pasos en el procedimiento, "ER crea un proveedor de la configuración y marcarlo como activo". 

Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante el conjunto de datos de USMF. 

También debe descargar y guardar los siguientes archivos localmente: (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Puede configurar un proceso para importar archivos externos en formato XML, TXT o CSV a las tablas en la aplicación Dynamics 365 for Finance and Operations. En primer lugar, debe crear un modelo de datos abstracto para representar los datos importados, desde un punto de vista de la empresa; se crea una configuración del modelo de datos de ER para esto. A continuación, defina una estructura del archivo importado que se asigne al modelo de datos diseñado como forma de ir a los datos de puerto desde el archivo al modelo de datos abstracto; una configuración del formato de ER se crea para esto. A continuación, la configuración del modelo de datos de ER debe ampliarse con una asignación de modelos nueva que describa cómo se utilizan los datos del archivo importado y los datos persistentes del modelo de datos abstracto para actualizar las tablas de aplicación o las entidades de datos.  
    * Los pasos siguientes muestran cómo las transacciones de los proveedores con seguimiento externo se importan desde el archivo CSV externo para su uso posterior en el acuerdo del proveedor para los formularios 1099.   
    * Compruebe que el proveedor de configuración de la empresa de ejemplo, Litware, Inc., está disponible y marcado como activo. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".  
2. Haga clic en Configuraciones de informes.
3. Aplique el filtro "Modelo de pagos 1099”. Si ya ha completado el procedimiento, “ER Crear las configuraciones necesarias para importar datos de un archivo externo para informes electrónicos” y la configuración "Modelo de pagos 1099” están disponibles en el árbol de configuración, omita todos los pasos de la subtarea siguiente.   

## <a name="add-a-new-er-model-configuration"></a>Añada una nueva configuración para el modelo ER
1. En lugar de crear un modelo nuevo para admitir la importación de datos, cargue el archivo 1099model.xml que ha descargado previamente. Este archivo contiene el modelo de datos personalizado de las transacciones de los proveedores. Este modelo de datos ya está asignado a los componentes de datos necesarios.  
2. Haga clic en Intercambiar.
3. Haga clic en Cargar desde un archivo XML.
4. Haga clic en Explore y navegue hasta el archivo 1099model.xml file que ha descargado previamente.  
5. Haga clic en Aceptar

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Añada una nueva configuración del formato de ER que permita la importación de datos
1. En el árbol, seleccione "Modelo de pagos 1099".
2. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
3. En el campo Nuevo, especifique "Formato basado en el modelo de datos del modelo de Pagos 1099".
4. Seleccione Sí en el campo Admite la importación de datos.
5. Pulse la tecla ESC para cerrar esta página.
    * En lugar de crear un formato de ER nuevo para admitir la importación de datos, cargue el archivo 1099formatcsv.xml que ha descargado previamente. Este archivo contiene el formato de ER requerido que define la estructura del archivo CSV entrante y la asignación de esta estructura al modelo de datos de las transacciones de los proveedores.   
6. Haga clic en Intercambiar.
7. Haga clic en Cargar desde un archivo XML.
    * Haga clic en Examinar y desplácese hasta el archivo 1099formatcsv.xml que ha descargado previamente.  
8. Haga clic en Aceptar
9. En el árbol, expanda el "Modelo de pagos 1099".
10. En el árbol, seleccione '1099 Payments model\For importing vendors' transactions (CSV)'.

## <a name="review-format-settings"></a>Configuración del formato de revisión
1. Haga clic en Diseñador.
2. Haga clic en Expandir/Contraer.
3. Active "Mostrar detalles".
    * El formato diseñado representa la estructura esperada del archivo externo en formato CSV.  
4. En el árbol, seleccione 'Incoming: File\Root: Sequence'.
    * Para el elemento Root del tipo SEQUENCE, la opción “Línea nueva: Windows (CR LF)” se ha seleccionado en el campo “caracteres especiales”. Basándose en esta configuración, cada línea en el archivo de análisis debe considerarse un registro individual.   
5. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* '.
    * Para el elemento Root\Line del tipo SEQUENCE, se ha seleccionado la opción “Uno o varios” en el campo “multiplicidad”. En base a este valor, al menos una línea se visualizará en el archivo del análisis.   
6. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case'.
    * Tenga en cuenta que el elemento Root\Line\Types del tipo CASE se ha agregado como elemento anidado de la secuencia Root\Line. Dado que este elemento CASE contiene 3 elementos en secuencia anidados, este valor presupone que esperamos encontrar 3 tipos de línea diferentes en el archivo del análisis.   
7. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Header: Sequence 1..1 '.
    * El elemento Root\Line\Types\Header del tipo SEQUENCE contiene el elemento STRING anidado cuyo valor ha sido definido como el valor de cadena fijo. Esta secuencia analizará la línea de encabezado del archivo de análisis.   
8. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)'.
    * El elemento Root\Line\Types\Record del tipo SEQUENCE se ha configurado para analizar las líneas de transacción. Tenga en cuenta que la opción de carácter “delimitador personalizado” se ha configurado en una coma. Esto significa que la coma se usará como separador de campos para este tipo de línea en el archivo del análisis.   
    * Tenga en cuenta que varios elementos anidados de diferentes tipos de datos se han agregado para el elemento Root\Line\Types\Record para analizar las líneas de transacción como campos independientes. Tenga en cuenta que la opción “Solicitud de presupuesto” se ha configurado como “Ninguno”. Esto significa que en el archivo de análisis, se considerará que ninguno de los campos de este tipo tiene caracteres incluidos.   
9. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\TransactionDate: DateTime'.
    * Por ejemplo, el elemento Root\Line\Types\Record\TransactionDate del tipo DATETIME se ha configurado para obtener el valor de fecha y hora de la transacción de archivo de análisis en el formato de M/d/aaaa.   
10. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\CountryCode: String 0..1 '.
    * Tenga en cuenta que el elemento Root\Line\Types\Record\CountryCode del tipo STRING se ha configurado como si tuviera la opción "Cero o uno" en el campo “multiplicidad”. Este valor considera el valor del campo de CountryCode en la línea de análisis como opcional.   
11. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\Remark: Sequence 1..1 (,)'.
    * Tenga en cuenta que el elemento Root\Line\Types\Record\Remark del tipo SEQUENCE se ha configurado como si tuviera la opción “Todos” en el campo "Solicitud de presupuesto" y el carácter de comillas dobles en el campo "Comillas". Significa que se considerará que todos los campos de este tipo de líneas del archivo de análisis (descrito por los artículos anidadas: texto del tipo STRING) están entre comillas dobles.  
12. En el árbol, seleccione 'Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Unparsed: Sequence 1..1 '.
    * El elemento Root\Line\Types\Unparsed del tipo SEQUENCE se ha configurado para analizar las líneas de transacción de la estructura que no coincide con la estructura descrita arriba en el elemento CASE principal.   

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Revise la configuración de la asignación de formato para el modelo de datos
1. Haga clic en Asignar formato a modelo.
    * La asignación de modelo “asignación para modelar desde formato CSV” describe el flujo de datos de la transferencia de datos del archivo CSV de entrada al modelo de datos.   
2. Haga clic en Diseñador.
3. En el árbol, expanda "formato".
    * Tenga en cuenta que el formato diseñado se presentará aquí como un componente del origen de datos.  
4. En el árbol, expanda 'format\Incoming: File(Incoming)'.
5. En el árbol, expanda 'format\Incoming: File(Incoming)\Root: Sequence(Root)'.
6. En el árbol, expanda 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)'.
7. En el árbol, expanda 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)'.
8. En el árbol, expanda 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)'.
9. En el árbol, expanda 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data'.
10. En el árbol, expanda 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\CountryCode: String 0..1 (CountryCode)'.
11. En el árbol, seleccione 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\TransactionDate: DateTime(TransactionDate)'.
    * Tenga en cuenta que los elementos de formato necesarios y opcionales como TransactionDate y CountryCode parecen diferentes en el componente de origen de datos “formato” predefinido.   
12. En el árbol, expanda 'Transactions = '$both''.
    * Tenga en cuenta que los elementos del formato que define la estructura del archivo importado están vinculados a los elementos del modelo de datos. En función de estos vínculos, el contenido del archivo CSV importado se almacenará al tiempo de ejecución en el modelo de datos existente. Preste atención al vínculo del elemento CountryRegion. En el caso de elementos de transacción en el archivo de entrada que no tengan un valor de código de país especificado, el código de país predeterminado será “EE.UU.” y se rellenará en el modelo de datos.   
13. Active "Mostrar detalles".
14. Haga clic en la pestaña Validaciones.
15. Haga clic en Buscar.
16. Escriba "vend" en el campo Buscar.
17. Haga clic en Buscar siguiente.
    * Esta asignación de formato puede contener una lógica definida por el usuario para validar la precisión de los datos importados desde una perspectiva empresarial. Por ejemplo, según el valor, por toda línea del archivo de importación cuya estructura no coincida ni con la estructura de la línea de encabezado ni con la línea de transacción, se generará un mensaje de advertencia en el registro de información que informe al usuario acerca de este caso e indique el número de secuencia de la transacción en el archivo.   
18. Cierre la página.

## <a name="run-the-format-mapping"></a>Ejecute la asignación de formato
Para comprobar, ejecute la asignación de formato mediante el archivo 1099entriescsv.csv que descargó anteriormente. La salida generada presentará datos que se importarán desde el archivo CSV seleccionado y se rellenarán en el modelo de datos personalizado durante la importación real.   
1. Haga clic en Ejecutar.
    * Haga clic en Examinar y desplácese hasta el archivo 1099entriescsv.csv que ha descargado previamente.  
2. Haga clic en Aceptar
    * Tenga en cuenta los mensajes de advertencia relativos a las líneas que no se aceptan. La línea 4 contiene el valor de los ingresos que se muestra en el formato no aceptable mientras que la línea 7 no contiene el texto de nota de la transacción en dobles comillas.   
    * Revise la salida en formato XML que representa los datos que se han importado del archivo seleccionado y se han trasladado al modelo de datos. Tenga en cuenta que todas las líneas 7 del archivo CSV importado se procesaron. La línea 1 de los cargos de los campos contenedores se saltó, 4 se transacciones se analizaron correctamente y 2 transacciones se reconocieron como no válidas.   
3. Cierre la página.
4. Cierre la página.


