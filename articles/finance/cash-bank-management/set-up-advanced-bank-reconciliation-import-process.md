---
title: Configurar el proceso de importación avanzada de conciliación bancaria
description: La característica de conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 Finance. En este artículo se explica cómo configurar la funcionalidad de importación para los extractos bancarios.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70a12148ca324e1e7e1f90d29d46f68cb4144438
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995324"
---
# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Configurar el proceso de importación avanzada de conciliación bancaria

[!include [banner](../includes/banner.md)]

La característica de conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Dynamics 365 Finance. En este artículo se explica cómo configurar la funcionalidad de importación para los extractos bancarios. 

La configuración de la importación del extracto bancario varía en función del formato de su extracto bancario electrónico. Finance admite de serie tres formatos de extractos bancarios: ISO20022, MT940 y BAI2.

## <a name="set-time-zone-preference"></a>Establecer preferencia de zona horaria
Cuando configure los valores de importación del extracto bancario, puede ser importante considerar la zona horaria de los datos de fecha y hora dentro de los archivos de extracto bancario que se importarán. El valor predeterminado es asumir que los valores de fecha y hora ya están en la hora universal coordinada (UTC) así que no se aplicará ninguna conversión de la zona horaria al importar los datos. 

Hay una opción disponible para especificar la zona horaria a utilizar para importar datos. Esta opción está disponible en el campo **Preferencia de la zona horaria** en cada página **Detalles sobre el formato de datos de origen** (ficha desplegable **Gestión de datos del espacio de trabajo > Configurar orígenes de datos > Seleccionar un formato de fecha > Configuración regional**). Esta preferencia de zona horaria que especifique se aplicará a todas las importaciones que usan dicho formato de datos de origen. Puede crear tantos formatos del origen de datos según sea necesario para importar datos de varias zonas horarias.  

Esta zona horaria puede no ser igual a una zona horaria del usuario o de la empresa, por lo que esté seguro de aclarar qué zona horaria están usando los datos. Recomendamos que tenga en cuenta los puntos siguientes al establecer una preferencia de zona horaria. 

 - La preferencia de zona horaria se aplicará a todas las importaciones que usan dicho formato de datos de origen. Puede crear tantos formatos del origen de datos según sea necesario para gestionar el importar datos de varias zonas horarias. 
 
 - La preferencia de la zona horaria debe ser la zona horaria local de los datos de fecha y hora en el archivo de importación. 
 
 - La zona horaria de los datos de fecha y hora no puede ser el mismo que una zona horaria del usuario o de la empresa.
 
 - Los usuarios pueden ajustar su propia zona horaria mediante sus **Opciones de usuario**.

Tenga en cuenta que las acciones siguientes pueden ayudar a minimizar posibles conflictos de fecha y hora al importar extractos bancarios. 

 - Impida cambiar las preferencias de la zona horaria para cualquier cuenta bancaria que haya realizado ya instrucciones importadas. Cambiar la preferencia de la zona horaria podría afectar a realizar un pedido desde las instrucciones existentes en relación con las nuevas instrucciones debido el ajuste de la zona horaria. 
 
 - Revise todas importaciones que usen el formato del origen de datos seleccionado. La preferencia de la zona horaria especificada para el formato se aplicarán a todas la importación proyectos que el uso que da formato. Verifique que la preferencia de la zona horaria es apropiada para el formato que se aplicarán a todas la importación proyectos que el uso que da formato.

## <a name="sample-files"></a>Archivo de muestra
Para los tres formatos, debe tener archivos que traduzcan la instrucción bancaria electrónica del formato original a un formato que Finance puede usar. Encontrará los archivos los recursos necesarios en el nodo **Recursos** de Application Explorer de Microsoft Visual Studio. Tras encontrar los archivos, cópielos en una única ubicación conocida, para que pueda cargarlos más fácilmente durante el proceso de instalación.

| Nombre del recurso                                           | Nombre de archivo                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_to\_Reconciliation\_xslt       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport\_BankReconciliation\_to\_Composite\_xslt | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_to\_Reconciliation\_xslt      | MT940XML-to-Reconciliation.xslt      |
| BankStmtImport\_SampleBankCompositeEntity\_xml          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Ejemplos de diseños técnicos y formatos de extracto bancario
A continuación se presentan ejemplos de diseño técnico de archivo de importación de conciliación bancaria avanzada y tres archivos de ejemplo de extracto bancario relacionados: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Definición de diseño técnico                             | Archivo de ejemplo de extracto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |



## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Configuración de la importación de los extractos bancarios ISO20022
En primer lugar, debe definir el grupo de procesamiento del formato de extractos bancarios para los extractos bancarios ISO20022 mediante el marco de entidades de datos.

1.  Vaya a **Espacios de trabajo** &gt; **Administración de datos**.
2.  Haga clic en **Importar**.
3.  Escriba un nombre para el formato, como **ISO20022**.
4.  Establezca el campo **Formato de datos de origen** en **Elemento XML**.
5.  Establezca el campo **Nombre de entidad** en **Extractos bancarios**.
6.  Para cargar los archivos de importación, haga clic en **Cargar** y, a continuación, busque y seleccione el archivo **SampleBankCompositeEntity.xml** que guardó anteriormente.
7.  Cuando se cargue la entidad Extractos bancarios y se complete la asignación, haga clic en la **Ver mapa** para la entidad.
8.  La entidad de extractos bancarios es una entidad compuesta que consta de cuatro entidades independientes. En la lista, seleccione **BankStatementDocumentEntity** y, a continuación, haga clic en la acción **Ver mapa**.
9.  En la ficha **Transformaciones**, haga clic en **Nueva**.
10. Para el número de secuencia 1, haga clic en **Cargar archivo** y seleccione el archivo **ISO20022XML-to-Reconciliation.xslt** que guardó anteriormente. **Nota:** los archivos de transformación se crean para el formato estándar. Debido a que los bancos a menudo se apartan de este formato, puede tener que actualizar el archivo de transformación para asignarlo al formato del extracto bancario. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Haga clic en **Nuevo**.
12. Para el número de secuencia 2, haga clic en **Cargar archivo** y seleccione el archivo **BankReconciliation-to-Composite.xslt** que guardó anteriormente.
13. Haga clic en **Aplicar transformaciones**.

Después de configurar el grupo de procesamiento de formato, el siguiente paso es definir las reglas de formato de instrucciones bancarias para extractos bancarios ISO20022.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Configuración** &gt; **Configuración de conciliación bancaria avanzada** &gt; **Formato de extracto bancario**.
2.  Haga clic en **Nuevo**.
3.  Especifique un formato de instrucción, como **ISO20022**.
4.  Escriba un nombre para el formato.
5.  Establezca el campo **Grupo de procesamiento** en el grupo que ha definido anteriormente, como **ISO20022**.
6.  Active la casilla **Archivo XML**.

El último paso es habilitar Conciliación bancaria avanzada y establecer el formato de la instrucción en la cuenta bancaria.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Cuentas bancarias**.
2.  Seleccione la cuenta bancaria y ábrala para ver los detalles.
3.  En la pestaña **Conciliación**, establezca la opción **Conciliación bancaria avanzada** en **Sí**.
4.  Establezca el campo **Formato de extracto** en el formato que ha creado anteriormente, como **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Configuración de la importación de los extractos bancarios MT940
En primer lugar, debe definir el grupo de procesamiento del formato de extractos bancarios para los extractos bancarios MT940 mediante el marco de entidades de datos.

1.  Vaya a **Espacios de trabajo** &gt; **Administración de datos**.
2.  Haga clic en **Importar**.
3.  Escriba un nombre para el formato, como **MT940**.
4.  Establezca el campo **Formato de datos de origen** en **Elemento XML**.
5.  Establezca el campo **Nombre de entidad** en **Extractos bancarios**.
6.  Para cargar los archivos de importación, haga clic en **Cargar** y, a continuación, busque y seleccione el archivo **SampleBankCompositeEntity.xml** que guardó anteriormente.
7.  Cuando se cargue la entidad Extractos bancarios y se complete la asignación, haga clic en la **Ver mapa** para la entidad.
8.  La entidad de extractos bancarios es una entidad compuesta que consta de cuatro entidades independientes. En la lista, seleccione **BankStatementDocumentEntity** y, a continuación, haga clic en la acción **Ver mapa**.
9.  En la ficha **Transformaciones**, haga clic en **Nueva**.
10. Para el número de secuencia 1, haga clic en **Cargar archivo** y seleccione el archivo **MT940TXT-to-MT940XML.xslt** que guardó anteriormente.
11. Haga clic en **Nuevo**.
12. Para el número de secuencia 2, haga clic en **Cargar archivo** y seleccione el archivo **MT940XML-to-Reconciliation.xslt** que guardó anteriormente. **Nota:** los archivos de transformación se crean para el formato estándar. Debido a que los bancos a menudo se apartan de este formato, puede tener que actualizar el archivo de transformación para asignarlo al formato del extracto bancario. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Haga clic en **Nuevo**.
14. Para el número de secuencia 3, haga clic en **Cargar archivo** y seleccione el archivo **BankReconciliation-to-Composite.xslt** que guardó anteriormente.
15. Haga clic en **Aplicar transformaciones**.

Después de configurar el grupo de procesamiento de formato, el siguiente paso es definir las reglas de formato de instrucciones bancarias para extractos bancarios MT940.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Configuración** &gt; **Configuración de conciliación bancaria avanzada** &gt; **Formato de extracto bancario**.
2.  Haga clic en **Nuevo**.
3.  Especifique un formato de instrucción, como **MT940**.
4.  Escriba un nombre para el formato.
5.  Establezca el campo **Grupo de procesamiento** en el grupo que ha definido anteriormente, como **MT940**.
6.  Establezca el campo **Tipo de archivo** en **txt**.

El último paso es habilitar Conciliación bancaria avanzada y establecer el formato de la instrucción en la cuenta bancaria.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Cuentas bancarias**.
2.  Seleccione la cuenta bancaria y ábrala para ver los detalles.
3.  En la pestaña **Conciliación**, establezca la opción **Conciliación bancaria avanzada** en **Sí**.
4.  Cuando se le pida que confirme la selección y habilite Conciliación bancaria avanzada, haga clic en **Aceptar**.
5.  Establezca el campo **Formato de extracto** en el formato que ha creado anteriormente, como **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Configuración de la importación de los extractos bancarios BAI2
En primer lugar, debe definir el grupo de procesamiento del formato de extractos bancarios para los extractos bancarios BAI2 mediante el marco de entidades de datos.

1.  Vaya a **Espacios de trabajo** &gt; **Administración de datos**.
2.  Haga clic en **Importar**.
3.  Escriba un nombre para el formato, como **BAI2**.
4.  Establezca el campo **Formato de datos de origen** en **Elemento XML**.
5.  Establezca el campo **Nombre de entidad** en **Extractos bancarios**.
6.  Para cargar los archivos de importación, haga clic en **Cargar** y, a continuación, busque y seleccione el archivo **SampleBankCompositeEntity.xml** que guardó anteriormente.
7.  Cuando se cargue la entidad Extractos bancarios y se complete la asignación, haga clic en la **Ver mapa** para la entidad.
8.  La entidad de extractos bancarios es una entidad compuesta que consta de cuatro entidades independientes. En la lista, seleccione **BankStatementDocumentEntity** y, a continuación, haga clic en la acción **Ver mapa**.
9.  En la ficha **Transformaciones**, haga clic en **Nueva**.
10. Para el número de secuencia 1, haga clic en **Cargar archivo** y seleccione el archivo **BAI2CSV-to-BAI2XML.xslt** que guardó anteriormente.
11. Haga clic en **Nuevo**.
12. Para el número de secuencia 2, haga clic en **Cargar archivo** y seleccione el archivo **BAI2XML-to-Reconciliation.xslt** que guardó anteriormente. **Nota:** los archivos de transformación se crean para el formato estándar. Debido a que los bancos a menudo se apartan de este formato, puede tener que actualizar el archivo de transformación para asignarlo al formato del extracto bancario. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Haga clic en **Nuevo**.
14. Para el número de secuencia 3, haga clic en **Cargar archivo** y seleccione el archivo **BankReconciliation-to-Composite.xslt** que guardó anteriormente.
15. Haga clic en **Aplicar transformaciones**.

Después de configurar el grupo de procesamiento de formato, el siguiente paso es definir las reglas de formato de instrucciones bancarias para extractos bancarios BAI2.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Configuración** &gt; **Configuración de conciliación bancaria avanzada** &gt; **Formato de extracto bancario**.
2.  Haga clic en **Nuevo**.
3.  Especifique un formato de instrucción, como **BAI2**.
4.  Escriba un nombre para el formato.
5.  Establezca el campo **Grupo de procesamiento** en el grupo que ha definido anteriormente, como **BAI2**.
6.  Establezca el campo **Tipo de archivo** en **txt**.

El último paso es habilitar Conciliación bancaria avanzada y establecer el formato de la instrucción en la cuenta bancaria.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Cuentas bancarias**.
2.  Seleccione la cuenta bancaria y ábrala para ver los detalles.
3.  En la pestaña **Conciliación**, establezca la opción **Conciliación bancaria avanzada** en **Sí**.
4.  Cuando se le pida que confirme la selección y habilite Conciliación bancaria avanzada, haga clic en **Aceptar**.
5.  Establezca el campo **Formato de extracto** en el formato que ha creado anteriormente, como **BAI2**.

## <a name="test-the-bank-statement-import"></a>Probar la importación del extracto bancario
El paso final es probar que puede importar el extracto bancario.

1.  Vaya a **Gestión de efectivo y bancos** &gt; **Cuentas bancarias**.
2.  Seleccione la cuenta bancaria para la que está habilitada la funcionalidad Conciliación bancaria avanzada.
3.  En la pestaña **Conciliar** , haga clic en **Extractos bancarios**.
4.  En la página **Extracto bancario**, haga clic en **Importar extracto**.
5.  Establezca el campo **Cuenta bancaria** en la cuenta bancaria seleccionada. El campo **Formato de extracto** se establecerá automáticamente, en función de la configuración de la cuenta bancaria.
6.  Haga clic en **Examinar** y seleccione el archivo de extracto bancario electrónico.
7.  Haga clic en **Cargar**.
8.  Haga clic en **Aceptar**.

Si la importación es correcta, recibirá un mensaje que indica que se importó la instrucción. Si la importación no fue correcta, en el espacio de trabajo **Administración de datos**, en la sección **Historial de trabajos**, encuentre el trabajo. Haga clic en **Detalles de ejecución** para que el trabajo abra la página **Resumen de ejecución** y, a continuación, haga clic en **Ver registro de ejecución** para ver los errores de importación.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]