---
title: "Configurar el proceso de importación avanzada de conciliación bancaria"
description: "La característica Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 for Operations. En este artículo se explica cómo configurar la funcionalidad de importación para los extractos bancarios."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 106853
ms.assetid: 45dae275-ea45-4c7e-b38f-89297c7b5352
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eab840b2974f4e9e8cf542c146482ba8e4239079
ms.openlocfilehash: acf7bacf6e95725024ff0a542a059349593d01a0
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-the-advanced-bank-reconciliation-import-process"></a>Configurar el proceso de importación avanzada de conciliación bancaria

La característica Conciliación bancaria avanzada le permite importar extractos bancarios electrónicos y conciliarlos automáticamente con transacciones bancarias en Microsoft Dynamics 365 for Operations. En este artículo se explica cómo configurar la funcionalidad de importación para los extractos bancarios. 

La configuración de la importación del extracto bancario varía en función del formato de su extracto bancario electrónico. Microsoft Dynamics 365 para el listo para usar de los formatos del extracto bancario del soporte de las tres operaciones: ISO20022, MT940, y BAI2.

## <a name="sample-files"></a>Archivo de muestra
Para los tres formatos, debe tener archivos que traduzcan el extracto bancario electrónico de formato original a un formato que Dynamics 365 para las operaciones pueda usar. Encontrará los archivos los recursos necesarios en el nodo **Recursos** de Application Explorer de Microsoft Visual Studio. Tras encontrar los archivos, cópielos en una única ubicación conocida, para que pueda cargarlos más fácilmente durante el proceso de instalación.

| Nombre del recurso                                           | Nombre de archivo                            |
|---------------------------------------------------------|--------------------------------------|
| BankStmtImport\_BAI2CSV\_al xslt\_\_BAI2XML              | BAI2CSV-to-BAI2XML.xslt              |
| BankStmtImport\_BAI2XML\_al xslt\_\_conciliación\_       | BAI2XML-to-Reconciliation.xslt       |
| BankStmtImport BankReconciliation\_\_al xslt compuesto\_\_ | BankReconciliation-to-Composite.xslt |
| BankStmtImport\_ISO20022XML\_al xslt\_\_conciliación\_   | ISO20022XML-to-Reconciliation.xslt   |
| BankStmtImport\_MT940TXT\_al xslt\_\_MT940XML            | MT940TXT-to-MT940XML.xslt            |
| BankStmtImport\_MT940XML\_al xslt\_\_conciliación\_      | MT940XML-to-Reconciliation.xslt      |
| Xml de BankStmtImport\_\_SampleBankCompositeEntity          | SampleBankCompositeEntity.xml        |

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Ejemplos de diseños técnicos y formatos de extracto bancario
A continuación se presentan los ejemplos de las definiciones de técnicas diseño del archivo de importación avanzado de conciliación bancaria y tres ejemplo de archivos relacionados del extracto bancario: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts  

| Definición de diseño técnico                             | Archivo de ejemplo de extracto bancario          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout                                   | MT940StatementExample                |
| DynamicsAXISO20022Layout                                | ISO20022StatementExample             |
| DynamicsAXBAI2Layout                                    | BAI2StatementExample                 |

 

## <a name="set-up-the-import-of-iso20022-bank-statements"></a>Configuración de la importación de los extractos bancarios ISO20022
En primer lugar, debe definir el grupo de procesamiento del formato de extractos bancarios para los extractos bancarios ISO20022 mediante el marco de entidades de datos.

1.  ** Vaya a las áreas de trabajo ** &gt; ** gestión de datos **.
2.  Click **Import**.
3.  Escriba un nombre para el formato, como **ISO20022**.
4.  Establezca el campo **Formato de datos de origen** en **Elemento XML**.
5.  Establezca el campo **Nombre de entidad** en **Extractos bancarios**.
6.  Para cargar los archivos de importación, haga clic en **Cargar**y, a continuación, busque y seleccione el archivo **SampleBankCompositeEntity.xml** que guardó anteriormente.
7.  Cuando se cargue la entidad Extractos bancarios y se complete la asignación, haga clic en la **Ver mapa** para la entidad.
8.  La entidad de extractos bancarios es una entidad compuesta que consta de cuatro entidades independientes. En la lista, seleccione **BankStatementDocumentEntity** y, a continuación, haga clic en la acción **Ver mapa**.
9.  En la ficha **Transformaciones**, haga clic en **Nueva**.
10. Para el número de secuencia 1, haga clic en **Cargar archivo**y seleccione el archivo** ISO20022XML-to-Reconciliation.xslt** que guardó anteriormente. ** Nota: ** Las Dynamics 365 para los archivos de transformación de las operaciones se generan para el formato estándar. Dado que los bancos divergen a menudo de este formato, es posible que actualizar el archivo de transformación para asignar a su formato del extracto bancario. <!-- For details about the expected format for ISO20022, see [Dynamics AX ISO20022 Layout](./media/dynamicsaxiso20022layout1.xlsx).-->
11. Click **New**.
12. Para el número de secuencia 2, haga clic en **Cargar archivo**y seleccione el archivo **BankReconciliation-to-Composite.xslt** que guardó anteriormente.
13. Haga clic en **Aplicar transformaciones**.

Después de configurar el grupo de procesamiento de formato, el siguiente paso es definir las reglas de formato de instrucciones bancarias para extractos bancarios ISO20022.

1.  Retroceda ** efectivo y bancos ** &gt; ** la configuración ** &gt; ** conciliación bancaria avanzado configurar ** &gt; ** formato del extracto bancario **.
2.  Click **New**.
3.  Especifique un formato de instrucción, como **ISO20022**.
4.  Escriba un nombre para el formato.
5.  Establezca el campo **Grupo de procesamiento** en el grupo que ha definido anteriormente, como **ISO20022**.
6.  Active la casilla **Archivo XML**.

El último paso es habilitar Conciliación bancaria avanzada y establecer el formato de la instrucción en la cuenta bancaria.

1.  ** Van efectivo y bancos ** &gt; ** las cuentas bancarias **.
2.  Seleccione la cuenta bancaria y ábrala para ver los detalles.
3.  En la pestaña **Conciliación**, establezca la opción **Conciliación bancaria avanzada **en **Sí**.
4.  Establezca el campo **Formato de extracto** en el formato que ha creado anteriormente, como **ISO20022**.

## <a name="set-up-the-import-of-mt940-bank-statements"></a>Configuración de la importación de los extractos bancarios MT940
En primer lugar, debe definir el grupo de procesamiento del formato de extractos bancarios para los extractos bancarios MT940 mediante el marco de entidades de datos.

1.  ** Vaya a las áreas de trabajo ** &gt; ** gestión de datos **.
2.  Click **Import**.
3.  Escriba un nombre para el formato, como **MT940**.
4.  Establezca el campo **Formato de datos de origen** en **Elemento XML**.
5.  Establezca el campo **Nombre de entidad** en **Extractos bancarios**.
6.  Para cargar los archivos de importación, haga clic en **Cargar**y, a continuación, busque y seleccione el archivo **SampleBankCompositeEntity.xml** que guardó anteriormente.
7.  Cuando se cargue la entidad Extractos bancarios y se complete la asignación, haga clic en la **Ver mapa** para la entidad.
8.  La entidad de extractos bancarios es una entidad compuesta que consta de cuatro entidades independientes. En la lista, seleccione **BankStatementDocumentEntity** y, a continuación, haga clic en la acción **Ver mapa**.
9.  En la ficha **Transformaciones**, haga clic en **Nueva**.
10. Para el número de secuencia 1, haga clic en **Cargar archivo**y seleccione el archivo **MT940TXT-to-MT940XML.xslt** que guardó anteriormente.
11. Haga clic en **Nuevo**.
12. Para el número de secuencia 2, haga clic en **Cargar archivo**y seleccione el archivo** MT940XML-to-Reconciliation.xslt** que guardó anteriormente. ** Nota: ** Las Dynamics 365 para los archivos de transformación de las operaciones se generan para el formato estándar. Dado que los bancos divergen a menudo de este formato, es posible que actualizar el archivo de transformación para asignar a su formato del extracto bancario. <!--- For details about the expected format for MT940, see [Dynamics AX MT940 Layout](./media/dynamicsaxmt940layout1.xlsx)-->
13. Click **New**.
14. Para el número de secuencia 3, haga clic en **Cargar archivo**y seleccione el archivo **BankReconciliation-to-Composite.xslt** que guardó anteriormente.
15. Haga clic en **Aplicar transformaciones**.

Después de configurar el grupo de procesamiento de formato, el siguiente paso es definir las reglas de formato de instrucciones bancarias para extractos bancarios MT940.

1.  Retroceda ** efectivo y bancos ** &gt; ** la configuración ** &gt; ** conciliación bancaria avanzado configurar ** &gt; ** formato del extracto bancario **.
2.  Click **New**.
3.  Especifique un formato de instrucción, como **MT940**.
4.  Escriba un nombre para el formato.
5.  Establezca el campo **Grupo de procesamiento** en el grupo que ha definido anteriormente, como **MT940**.
6.  Establezca el campo **Tipo de archivo** en **txt**.

El último paso es habilitar Conciliación bancaria avanzada y establecer el formato de la instrucción en la cuenta bancaria.

1.  ** Van efectivo y bancos ** &gt; ** las cuentas bancarias **.
2.  Seleccione la cuenta bancaria y ábrala para ver los detalles.
3.  En la pestaña **Conciliación**, establezca la opción **Conciliación bancaria avanzada **en **Sí**.
4.  Cuando se le pida que confirme la selección y habilite Conciliación bancaria avanzada, haga clic en **Aceptar**.
5.  Establezca el campo **Formato de extracto** en el formato que ha creado anteriormente, como **MT940**.

## <a name="set-up-the-import-of-bai2-bank-statements"></a>Configuración de la importación de los extractos bancarios BAI2
En primer lugar, debe definir el grupo de procesamiento del formato de extractos bancarios para los extractos bancarios BAI2 mediante el marco de entidades de datos.

1.  ** Vaya a las áreas de trabajo ** &gt; ** gestión de datos **.
2.  Click **Import**.
3.  Escriba un nombre para el formato, como **BAI2**.
4.  Establezca el campo **Formato de datos de origen** en **Elemento XML**.
5.  Establezca el campo **Nombre de entidad** en **Extractos bancarios**.
6.  Para cargar los archivos de importación, haga clic en **Cargar**y, a continuación, busque y seleccione el archivo **SampleBankCompositeEntity.xml** que guardó anteriormente.
7.  Cuando se cargue la entidad Extractos bancarios y se complete la asignación, haga clic en la **Ver mapa** para la entidad.
8.  La entidad de extractos bancarios es una entidad compuesta que consta de cuatro entidades independientes. En la lista, seleccione **BankStatementDocumentEntity** y, a continuación, haga clic en la acción **Ver mapa**.
9.  En la ficha **Transformaciones**, haga clic en **Nueva**.
10. Para el número de secuencia 1, haga clic en **Cargar archivo**y seleccione el archivo **BAI2CSV-to-BAI2XML.xslt** que guardó anteriormente.
11. Haga clic en **Nuevo**.
12. Para el número de secuencia 2, haga clic en **Cargar archivo**y seleccione el archivo** BAI2XML-to-Reconciliation.xslt** que guardó anteriormente. ** Nota: ** Las Dynamics 365 para los archivos de transformación de las operaciones se generan para el formato estándar. Dado que los bancos divergen a menudo de este formato de, y es posible que actualizar el archivo de transformación para asignar a su formato del extracto bancario. <!--- For details about the expected format for BAI2, see [Dynamics AX BAI2 Layout](./media/dynamicsaxbai2layout1.xlsx).-->
13. Click **New**.
14. Para el número de secuencia 3, haga clic en **Cargar archivo**y seleccione el archivo **BankReconciliation-to-Composite.xslt** que guardó anteriormente.
15. Haga clic en **Aplicar transformaciones**.

Después de configurar el grupo de procesamiento de formato, el siguiente paso es definir las reglas de formato de instrucciones bancarias para extractos bancarios BAI2.

1.  Retroceda ** efectivo y bancos ** &gt; ** la configuración ** &gt; ** conciliación bancaria avanzado configurar ** &gt; ** formato del extracto bancario **.
2.  Click **New**.
3.  Especifique un formato de instrucción, como **BAI2**.
4.  Escriba un nombre para el formato.
5.  Establezca el campo **Grupo de procesamiento** en el grupo que ha definido anteriormente, como **BAI2**.
6.  Establezca el campo **Tipo de archivo** en **txt**.

El último paso es habilitar Conciliación bancaria avanzada y establecer el formato de la instrucción en la cuenta bancaria.

1.  ** Van efectivo y bancos ** &gt; ** las cuentas bancarias **.
2.  Seleccione la cuenta bancaria y ábrala para ver los detalles.
3.  En la pestaña **Conciliación**, establezca la opción **Conciliación bancaria avanzada **en **Sí**.
4.  Cuando se le pida que confirme la selección y habilite Conciliación bancaria avanzada, haga clic en **Aceptar**.
5.  Establezca el campo **Formato de extracto** en el formato que ha creado anteriormente, como **BAI2**.

## <a name="test-the-bank-statement-import"></a>Probar la importación del extracto bancario
El paso final es probar que puede importar el extracto bancario.

1.  ** Van efectivo y bancos ** &gt; ** las cuentas bancarias **.
2.  Seleccione la cuenta bancaria para la que está habilitada la funcionalidad Conciliación bancaria avanzada.
3.  En la pestaña **Conciliar** , haga clic en **Extractos bancarios**.
4.  En la página **Extracto bancario**, haga clic en **Importar extracto**.
5.  Establezca el campo **Cuenta bancaria** en la cuenta bancaria seleccionada. El campo **Formato de extracto** se establecerá automáticamente, en función de la configuración de la cuenta bancaria.
6.  Haga clic en **Examinar** y seleccione el archivo de extracto bancario electrónico.
7.  Haga clic en **Cargar**.
8.  Haga clic en **Aceptar**.

Si la importación es correcta, recibirá un mensaje que indica que se importó la instrucción. Si la importación no fue correcta, en el espacio de trabajo **Administración de datos**, en la sección **Historial de trabajos**, encuentre el trabajo. Haga clic en **Detalles de ejecución** para que el trabajo abra la página **Resumen de ejecución** y, a continuación, haga clic en **Ver registro de ejecución** para ver los errores de importación.


