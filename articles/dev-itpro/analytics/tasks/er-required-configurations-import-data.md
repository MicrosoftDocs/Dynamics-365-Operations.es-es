--- 
title: "Crear las configuraciones necesarias para importar datos de un archivo externo para informes electrónicos (ER)"
description: "En los siguientes pasos se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede diseñar configuraciones de informes electrónicos (ER) para importar datos a la aplicación de Dynamics 365 for Finance and Operations, Enterprise edition, desde un archivo externo."
author: NickSelin
manager: AnnBe
ms.date: 02/22/2017
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
ms.openlocfilehash: c0d9636fe8a8d5230859da8fe557fe11a9513ba0
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-required-configurations-to-import-data-from-an-external-file-for-electronic-reporting-er"></a>Crear las configuraciones necesarias para importar datos de un archivo externo para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los siguientes pasos se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede diseñar configuraciones de informes electrónicos (ER) para importar datos a la aplicación de Dynamics 365 for Finance and Operations, Enterprise edition, desde un archivo externo. En este ejemplo, creará las configuraciones necesarias de ER para la empresa del ejemplo, Litware, Inc. Para completar estos pasos, primero debe completar los pasos en la guía de la tarea, "ER crea un proveedor de la configuración y marcarlo como activo". Estos pasos se pueden completar mediante el conjunto de datos de USMF. También debe descargar y guardar los archivos siguientes localmente mediante vínculos desde el tema Visión general de los informes electrónicos (https://go.microsoft.com/fwlink/?linkid=852550): 1099model.xml, 1099format.xml, 1099entries.xml, 1099entries.xlsx.

    * ER ofrece a los usuarios de empresas la posibilidad de configurar el proceso de importar archivos de datos externos a las tablas en Dynamics 365 for Finance and Operations, Enterprise edition en formato .XML o .TXT. En primer lugar, se debe diseñar un modelo de datos abstracto y una configuración del modelo de datos de ER para representar los datos que está importando. A continuación, es necesario definir la estructura del archivo que está importando y el método que se utilizará para trasladar los datos del archivo al modelo de datos abstracto. La configuración del formato de ER que se asigna al modelo de datos diseñado debe crearse para ese modelo de datos abstracto. A continuación, la configuración del modelo de datos debe ampliarse con una asignación que describa cómo se conservan los datos importados como datos de un modelo de datos abstractos y cómo se usa para actualizar las tablas en Dynamics 365 for Finance and Operations, Enterprise edition.  La configuración del modelo de datos de ER se debe anexar con una nueva asignación de modelo que describa el enlace del modelo de datos con los destinos de la aplicación.  
    * La siguiente situación muestra las capacidades de importación de datos de ER. Esto incluye las transacciones de proveedor que se siguen externamente y luego se importan a Dynamics 365 for Finance and Operations, Enterprise edition, para notificarse más adelante en el acuerdo del proveedor para 1099.   

## <a name="add-a-new-er-model-configuration"></a>Añada una nueva configuración para el modelo ER
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
    * Compruebe que el proveedor de configuración de la empresa de ejemplo, Litware, Inc. está disponible y marcado como activo. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".    
2. Haga clic en Configuraciones de informes.
    * En lugar de crear desde un modelo nuevo para admitir la importación de datos, cargue el archivo, 1099model.xml, que ha descargado previamente. Este archivo contiene el modelo de datos personalizado de las transacciones de los proveedores. Este modelo de datos se asigna a Dynamics 365 for Finance and Operations, Enterprise edition, los componentes de datos que se encuentran en la entidad de datos del AOT.   
3. Haga clic en Intercambiar.
4. Haga clic en Cargar desde un archivo XML.
    * Haga clic en Explore y navegue hasta el archivo 1099model.xml file que ha descargado previamente.  
5. Haga clic en Aceptar
6. En el árbol, seleccione "Modelo de pagos 1099".

## <a name="review-data-model-settings"></a>Revise la configuración del modelo de datos
1. Haga clic en Diseñador.
    * Este modelo se ha diseñado para representar las transacciones de los proveedores desde el punto de vista de la empresa, y está a parte de la implementación de Dynamics 365 for Finance and Operations, Enterprise edition.   
2. En el árbol, expanda el ''1099-MISC".
3. En el árbol, seleccione "1099-MISC\Transacciones".
4. En el árbol, expanda "1099-MISC\Transacciones".
    * El elemento Transacciones de este modelo representa las transacciones individuales. Los elementos secundarios se utilizan para especificar los detalles necesarios, como cuenta de proveedor y fecha de transacción, para cada transacción.   
5. Cierre la página.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Añada una nueva configuración del formato de ER que permita la importación de datos
    * Los pasos en esta subtarea le muestran cómo se puede crear una nueva configuración de formato para administrar la importación de datos de archivos externos.   
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nuevo, especifique "Formato basado en el modelo de datos del modelo de Pagos 1099".
3. Seleccione Sí en el campo Admite la importación de datos.
4. Pulse la tecla ESC para cerrar esta página.
    * En lugar de crear un formato nuevo para admitir la importación de datos, cargue el archivo 1099format.xml que ha descargado previamente. Este archivo contiene la estructura definida de archivo que está importando y la asignación de la estructura al modelo de datos personalizado de las transacciones de los proveedores.   
5. Haga clic en Intercambiar.
6. Haga clic en Cargar desde un archivo XML.
    * Haga clic en Examinar y desplácese hasta el archivo 1099format.xml que ha descargado previamente.  
7. Haga clic en Aceptar
8. En el árbol, expanda el "Modelo de pagos 1099".
9. En el árbol, seleccione “Modelo de pagos 1099\Formato para la importación de transacciones de proveedores".

## <a name="review-format-settings"></a>Configuración del formato de revisión
1. Haga clic en Diseñador.
2. Active "Mostrar detalles".
3. Haga clic en Expandir/Contraer.
4. Haga clic en Expandir/Contraer.
    * El formato diseñado representa la estructura esperada del archivo externo. Este archivo debe estar en formato XML y tener el elemento raíz de la liquidación. Cada transacción de proveedor se representa mediante un elemento de transacción que se define como si tuviera una multiplicidad de cero a varios. Esto significa que el archivo de entrada puede contener desde cero hasta múltiples transacciones. Los elementos anidados del elemento "transacción" representan los atributos de una sola transacción. Tenga en cuenta que todos los atributos, excepto el país, están marcados como obligatorios, lo que significa que es necesario tenerlos en el archivo a importar.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Revise la configuración de la asignación de formato para el modelo de datos
1. Haga clic en Asignar formato a modelo.
    * La asignación “Transacciones de proveedores para importar" contiene las reglas de transferencia de datos desde el archivo XML de entrada hasta la parte seleccionada del modelo de datos personalizado, que se define seleccionando la definición de the1099-MISC.  
2. Haga clic en Diseñador.
3. Active "Mostrar detalles".
4. En el árbol, expanda "formato: Registro".
5. En el árbol, seleccione "formato: Registro".
    * Tenga en cuenta que el formato diseñado se presentará aquí como un componente del origen de datos.  
6. En el árbol, expanda "formato:Registro\*liquidación: Elemento XML 1..1 (liquidación): Registro".
7. En el árbol, expanda "formato: Registro\*liquidación:Elemento 1..1 XML (liquidación): Registro\transacción: Elemento XML. 0.. * (transacción): Lista de registro".
8. En el árbol, expanda "formato: Registro\*liquidación: Elemento XML 1..1 (liquidación): Registro\transacción: Elemento XML. 0.. * (transacción): Lista de registro\*proveedor: Elemento XML 1..1 (proveedor): Registro”.
9. En el árbol, expanda "formato: Registro\*liquidación: Elemento XML 1..1 (liquidación): Registro\transacción: Elemento XML. 0.. * (transacción): Lista de registro\país: Elemento XML 0..1 (país): Registro”.
10. En el árbol, seleccione "formato: Registro\*liquidación: Elemento XML 1..1 (liquidación): Registro\transacción: Elemento XML. 0.. * (transacción): Lista de registro\*proveedor: Elemento XML 1..1 (proveedor): Registro”.
    * Tenga en cuenta que la presentación de los elementos de formato obligatorios y optativos es diferente en el componente predefinido del origen de datos “formato”.  
11. En el árbol, expanda "Transacciones: Lista de registro = format.settlement.'$enumerated''.
    * Tenga en cuenta que los elementos del formato que define la estructura del archivo importado están vinculados a los elementos del modelo de datos personalizado. En función de estos vínculos, el contenido del archivo XML importado se almacenará al tiempo de ejecución en el modelo de datos existente. Preste atención al vínculo del elemento de país. En el caso de elementos de transacción en el archivo de entrada que no tengan dicho elemento, el código de país predeterminado será “EE.UU.” y se rellenará en el modelo de datos.  
12. Haga clic en la pestaña Validaciones.
    * Esta asignación de formato puede contener una lógica definida por el usuario para validar la precisión de los datos importados desde una perspectiva empresarial. Por ejemplo, en función de la configuración, en el caso de las transacciones en el archivo a importar que no tenga un código de país definido, se generará un mensaje de advertencia en el registro de información que indica al usuario el caso y el número de secuencia de la transacción.  
13. Cierre la página.

## <a name="run-the-format-mapping-to-the-data-model"></a>Ejecute la asignación de formato para el modelo de datos
    * Ejecute esta asignación de formato para realizar pruebas. Utilice el archivo 1099entries.xml que ha descargado previamente. Ahora puede exportar este archivo desde el libro 1099entries.xlsx que se utiliza para gestionar las transacciones de proveedor. La salida generaad se importará desde el archivo XML seleccionado y rellenará el modelo de datos personalizado a tiempo real.  
1. Haga clic en Ejecutar.
    * Haga clic en Examinar y desplácese hasta el archivo 1099entries.xml que ha descargado previamente.  
2. Haga clic en Aceptar
    * Observe el mensaje de advertencia que le indica que falta un código de país para una transacción en el archivo importado.  
    * Revise la salida en formato XML, que representa los datos que se han importado del archivo seleccionado y se han trasladado al modelo de datos.   
3. Cierre la página.
4. Cierre la página.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>Revise la configuración de la asignación del modelo para los destinos
1. En el árbol, seleccione "Modelo de pagos 1099".
2. Haga clic en Diseñador.
3. Haga clic en Asignar modelo a origen de datos.
    * La asignación Para la importación de transacciones manuales 1099 se ha definido mediante el tipo de dirección A. Lo cual significa que se ha introducido para admitir la importación de datos y contiene la configuración de reglas que definen cómo se utiliza el archivo externo importado y cómo se conservan los datos importados como datos de un modelo de datos abstractos para actualizar tablas en la aplicación Dynamics 365 for Finance and Operations, Enterprise edition.  
4. Haga clic en Diseñador.
5. En el árbol, expanda "modelo: Modelo de datos 1099 Modelo de pagos".
6. En el árbol, expanda "modelo: Modelo de datos 1099 Modelo de pagos\Transacciones: Lista de registros".
    * Tenga en cuenta que el modelo diseñado se presentará aquí como un elemento del origen de datos. En tiempo de ejecución, contendrá los datos que se importen del archivo externo. Se agregaron varias tablas como elementos del origen de datos para garantizar que los datos importados son compatibles con los datos de la aplicación actual, tanto si la cuenta del proveedor de la transacción que importa está disponible en el sistema, como si ya existe la combinación de los códigos del país y del estado importador, etc.  
7. En el árbol, seleccione "modelo: Modelo de datos 1099 Modelo de pagos\Transacciones: Lista de registro\$fallido: Campo calculado = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boleano".
8. Haga clic en Editar.
9. Haga clic en Editar fórmula.
    * Cuando como mínimo falle una validación para una sola transacción importada, esta transacción se marcará como fallida mediante el atributo “$failed” del origen de datos.  
10. Cierre la página.
11. Haga clic en Cancelar.
12. En el árbol, seleccione “tax1099trans: Tabla “registros VendSettlementTax1099' = model.Validated'
13. Haga clic en Editar destino.
    * Este destino de ER se ha agregado para especificar cómo los datos importados actualizarán las tablas de la aplicación. En este caso, se ha seleccionado la tabla de datos VendSettlementTax1099. Dado que se ha seleccionado la acción del registro Insertar, las transacciones importadas se insertarán en la tabla VendSettlementTax1099. Tenga en cuenta que una sola asignación de modelo puede contener varios destinos. Esto significa que los datos importados se pueden utilizar para actualizar varias tablas de la aplicación al mismo tiempo. Las tablas, las vistas y las entidades de datos se pueden usar como destinos de ER.   
    * Si la asignación va a ser llamada desde un punto en la aplicación Dynamics 365 for Finance and Operations, Enterprise edition (como un botón o un elemento del menú) que ha sido diseñado específicamente para esta acción, el destino de ER se debe marcar como el punto de integración. En este ejemplo es el punto ERTableDestination#VendSettlementTax1099.  
14. Haga clic en Cancelar.
15. Haga clic en Mostrar todo.
16. Haga clic en Mostrar solo los asignados.
17. En el árbol, expanda “tax1099trans: Tabla “registros VendSettlementTax1099' = model.Validated'
    * Tenga en cuenta que el elemento del origen de datos que contiene las únicas transacciones validadas está vinculado al destino creado. Usted puede filtrar las transacciones importadas para ignorar las que son incompatibles con los datos de las aplicaciones.  
18. En el árbol, seleccione “erróneo: Tabla 'VendSettlementTax1099Entity' registros = model.Failed'
19. Haga clic en la pestaña Validaciones.
    * Esta asignación de modelo puede contener una lógica definida por el usuario para validar la corrección de los datos importados desde los datos de aplicación existentes. Por ejemplo, en función de la configuración actual, en el caso de transacciones en el archivo importado con una cuenta de proveedor que no esté en el sistema, se generará un mensaje de advertencia para informar al usuario e indicar el código de cuenta de proveedor incorrecto.  
    * Tenga en cuenta que la opción de acción de validación Registrar se puede usar para cada validación, para especificar si el proceso de importación debe continuar o detenerse, así como si las inserciones o actualizaciones ya efectuadas se pueden mantener o deshacer.  
20. Haga clic en Mostrar solo los asignados.
21. Haga clic en Mostrar todo.
22. Cierre la página.
    * Ejecute esta asignación de modelo para probar el formato diseñado y las asignaciones del modelo. Use el archivo 1099entries.xml. Los datos del archivo seleccionado se importarán en el sistema.  
23. Haga clic en Ejecutar.
    * Tenga en cuenta que el cuadro de diálogo no contiene preguntas adicionales sobre la asignación del formato que se debe usar para analizar el archivo importado y después trasladar los datos al modelo de datos. Esto se debe a que actualmente solo existe un formato que utiliza este modelo, que se marca como diseñado para admitir la importación de datos.  
    * Define el identificador del asiento para distinguir las transacciones importadas de otras transacciones que podrían haberse importado ya o especificado manualmente.  
24. En el campo Especifique identificador de asiento, introduzca “IMPORT-001”.
    * Examine para obtener el archivo “1099entries.xml”.  
25. Haga clic en Aceptar
    * La lista de advertencias generadas proporciona información acerca de las cuentas de proveedor incorrectas, un código incorrecto del cuadro de impuestos 1099, los códigos de país que faltan, etc. Compara esta lista de advertencias al contenido que se incluye en el archivo XML de ejecución.  
26. Cierre la página.
27. Cierre la página.
28. Cierre la página.
29. Cierre la página.
30. Vaya a Proveedores > Tareas periódicas > Impuesto 1099 > Liquidación del proveedor por 1099s.
    * Este formulario muestra las transacciones acumulativas en la tabla Tax1099Summary que se han creado en función de las transacciones importadas.  
31. En el campo Fecha inicial, defina la fecha en "2000-01-01".
32. Haga clic en Transacciones manuales de 1099.
    * Este formulario contiene la lista de transacciones que se agregaron manualmente y las que acabamos de importar.  
33. Abra el filtro de columna Asiento.
34. Introduzca un valor de filtro "IMPORT-001" en el campo "Asiento" mediante el operador de filtro "empieza por".

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Revise la relación entre el modelo y las asignaciones de formato
1. Cierre la página.
2. Cierre la página.
3. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
4. Haga clic en Configuraciones de informes.
5. En el árbol, seleccione "Modelo de pagos 1099".
    * Supongamos que desea admitir la importación de los mismos datos pero de un formato de archivo de .TXT.   
6. Haga clic en Crear configuración para abrir el cuadro de diálogo. 
7. En el campo Nuevo, especifique "Formato basado en el modelo de datos del modelo de Pagos 1099".
8. En el campo Nombre, introduzca "Importar datos de un archivo TXT".
9. Seleccione Sí en el campo Admite la importación de datos.
10. Haga clic en Crear configuración.
11. Haga clic en Diseñador.
12. Haga clic en Asignar formato a modelo.
13. Haga clic en Nuevo.
14. En el campo Definición, especifique o seleccione un valor.
    * Seleccione la opción "1099-MISC".  
15. En el campo Nombre, introduzca "Importar datos de un archivo TXT".
16. En el campo Descripción, introduzca "Importar datos de un archivo TXT".
17. Haga clic en Guardar.
18. Cierre la página.
19. Cierre la página.
20. Haga clic en Editar.
    * Si ha instalado el hotfix "soporte de KB 4012871 de las asignaciones de modelo GER en distintas configuraciones con una capacidad de especificar distintos tipos de requisitos previos para implementarlos en diferentes versiones de Dynamics 365 for Finance and Operations, Enterprise edition" (https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 ), ejecute el siguiente paso “Activar el indicador ‘Asignación modelo predeterminada’" en la configuración de formato introducida. En caso contrario, omita el siguiente paso.  
21. Seleccione Sí en el campo Valor predeterminado de la asignación de modelo.
22. En el árbol, seleccione "Modelo de pagos 1099".
23. Haga clic en Diseñador.
24. Haga clic en Asignar modelo a origen de datos.
25. Haga clic en Ejecutar.
    * Si ha instalado el hotfix, soporte de KB 4012871 de las asignaciones modelo GER en distintas configuraciones con capacidad de especificar distintos tipos de requisitos previos para implementarlos en diferentes versiones de Dynamics 365 for Finance and Operations, Enterprise edition, (https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871), seleccione la asignación modelo preferida en el campo de búsqueda. Si aún no ha instalado el reemplazo vaya al paso siguiente, ya que la asignación ha sido seleccionada por la definición de la configuración del formato predeterminado.  
    * Si no ha instalado el reemplazo, 4012871 KB, observe que el cuadro de diálogo contiene una pregunta adicional sobre el modelo de asignación que se usa para analizar el archivo que está importando. Los datos se del trasladan del cuadro de diálogo al modelo de datos. Actualmente, usted puede elegir qué formato de asignación se debe usar en función del tipo de archivo que pretende importar.  
    * Si pretende llamar esta asignación modelo desde un punto de Dynamics 365 for Finance and Operations, Enterprise edition, que especialmente designado para la acción, el destino de ER y la asignación de formato se deben marcar como parte de la integración.  
26. Haga clic en Cancelar.
27. Cierre la página.
28. Cierre la página.


