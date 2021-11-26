---
title: Diseñe expresiones de ER para abrir métodos de clase de aplicación
description: Este tema describe cómo volver a usar la lógica de aplicación existente en las configuraciones de informes electrónicos llamando a los métodos necesarios de clases de aplicación.
author: NickSelin
ms.date: 11/02/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81fae8d3603677afd7dd4b09b9073805f73582b4
ms.sourcegitcommit: e6b4844a71fbb9faa826852196197c65c5a0396f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "7751715"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Diseñe expresiones de ER para abrir métodos de clase de aplicación

[!include [banner](../../includes/banner.md)]

Esta tema describe cómo volver a usar la lógica de aplicación existente en las configuraciones de [informes electrónicos (ER)](../general-electronic-reporting.md) llamando a los métodos necesarios de clases de aplicación en expresiones de ER. Los valores de los argumentos para las clases de llamada se pueden definir dinámicamente en tiempo de ejecución. Por ejemplo, los valores se pueden basar en la información del documento de análisis para garantizar su corrección.

Por el ejemplo de este tema, diseñe un proceso que analice los extractos bancarios de entrada para una actualización de los datos de la aplicación. Recibirá los extractos bancarios entrantes como archivos de texto (.txt) que contienen códigos de número de cuenta bancaria internacional (IBAN). Como parte del proceso de importación de extractos bancarios, debe validar la corrección del código de IBAN mediante la lógica que esté ya disponible.

## <a name="prerequisites"></a>Requisitos previos

Los procedimientos de este tema se ha creado para los usuarios a los que se ha asignado el rol de **Administrador del sistema** o **Desarrollador de informes electrónicos**.

El procedimiento se puede completar mediante cualquier conjunto de datos.

Para completarlos, debe descargar y guardar el archivo siguiente: [SampleIncomingMessage.txt](https://download.microsoft.com/download/8/0/a/80adbc89-f23c-46d9-9241-e0f19125c04b/SampleIncomingMessage.txt).

En este tema, creará las configuraciones de ER necesarias para la empresa de ejemplo, Litware, Inc. Por tanto, antes de que pueda completar los procedimientos en este tema, debe completar los siguientes pasos:

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, compruebe que está disponible el proveedor de la configuración para la empresa de ejemplo **Litware, Inc.** y que se ha marcado como activo. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento [Creación de proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-a-new-er-model-configuration"></a>Importe una nueva configuración para el modelo ER

1. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione la ventana del proveedor de configuración **Microsoft**.
2. Seleccione **Repositorios**.
3. En la página **Repositorios de localización**, seleccione **Mostrar filtros**.
4. Para seleccionar el registro del repositorio global, agregue un campo de filtro **Nombre**.
5. En el campo **Nombre**, especifique **Global**. Luego seleccione operador de filtro **contiene**.
6. Seleccionar **Aplicar**.
7. Seleccione **[Abrir](../er-download-configurations-global-repo.md#open-configurations-repository)** para revisar la lista de configuraciones de ER del repositorio seleccionado.
8. En la página **Repositorio de configuraciones**, en el árbol de configuraciones, seleccione **Modelo de pago**.
9. En la pestaña desplegable **Versiones**, si está disponible el botón **Importar**, seleccione **Sí**.

    Si el botón **Importar** no está habilitado, ya ha importado la versión seleccionada de la configuración de ER del **Modelo de pago**.

10. Cierre la página **Repositorio de configuraciones** y luego cierre la página **Repositorios de localización**.

## <a name="add-a-new-er-format-configuration"></a>Añada una nueva configuración para el formato de ER

Agregar un nuevo formato de ER para analizar los extractos bancarios de entrada en el formato de TXT.

1. En la página **Configuraciones de localización**, seleccione la ventana **Configuraciones de informes**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Modelo de pago**.
3. Seleccionar **Crear configuración**. 
4. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el campo **Nuevo**, especifique **Formato basado en modelo de datos PaymentModel**.
    2. En el campo **Nombre**, escriba **Formato de importación de extracto bancario (muestra)**.
    3. Seleccione **Sí** en el campo **Admite la importación de datos**.
    4. Seleccione **Crear configuración** para terminar de crear la configuración.

## <a name="design-the-er-format-configuration--format"></a>Diseñar la configuración del formato de ER - Formato

Diseñe el formato de ER que representa la estructura esperada del archivo externo en formato TXT.

1. Para la configuración de formato **Formato de importación de extracto bancario (muestra)** que agregó, seleccione **Diseñador**.
2. En la página **Diseñador de formatos**, en el árbol de estructura de formato del panel izquierdo, seleccione **Agregar raíz**.
3. En el cuadro de diálogo que aparece, siga estos pasos:

    1. En el árbol, seleccione **Texto\\Secuencia** para agregar un componente de formato **Secuencia**.
    2. En el campo **Nombre**, especifique **Raíz**.
    3. En el campo **Caracteres especiales**, seleccione **Línea nueva - Windows (CR LF)**. Basándose en esta configuración, cada línea en el archivo de análisis se considerará un registro individual.
    4. Seleccione **Aceptar**.

4. Seleccione **Agregar**.
5. En el cuadro de diálogo que aparece, siga estos pasos:

    1. En el árbol, seleccione **Texto\\Secuencia**.
    2. En el campo **Nombre**, escriba **Filas**.
    3. En el campo de **Multiplicidad**, seleccione **Uno o varios**. En base a este valor, se espera que el menos una línea esté presente en el archivo del análisis.
    4. Seleccione **Aceptar**.

6. En el árbol, seleccione **Raíz\\Filas** y luego seleccione **Agregar secuencia**.
7. En el cuadro de diálogo que aparece, siga estos pasos:

    1. En el campo **Nombre**, especifique **Campos**.
    2. En el campo **Multiplicidad**, seleccione **Exactamente uno**.
    3. Seleccione **Aceptar**.

8. En el árbol, seleccione **Raíz\\Filas\\Campos** y luego seleccione **Agregar**.
9. En el cuadro de diálogo que aparece, siga estos pasos:

    1. En el árbol, seleccione **Texto\\Cadena**.
    2. En el campo **Nombre**, escriba **IBAN**.
    3.. Seleccione **Aceptar**.

10. Seleccione **Guardar**.

La configuración está ahora establecida para que cada línea del archivo de análisis contenga solo el código de IBAN.

![Configuración del formato de importación del extracto bancario (muestra) en la página de diseñador de formato.](../media/design-expressions-app-class-er-01.png)

## <a name="design-the-er-format-configuration--mapping-to-a-data-model"></a>Diseñar la configuración del formato de ER – asignación a un modelo de datos

Diseñe una asignación de formato de ER que use información del archivo de análisis para completar un modelo de datos.

1. En la página **Diseñador de formato** en el Panel acciones, seleccione **Asignar formato a modelo**.
2. En la página **Asignación de modelo a origen de datos** en el Panel acciones, seleccione **Nuevo**.
3. En el campo **Definición**, seleccione **BankToCustomerDebitCreditNotificationInitiation**.
4. En el campo **Nombre**, escriba **Asignación a modelo de datos**.
5. Seleccione **Guardar**.
6. Seleccione **Diseñador**.
7. En la página **Diseñador de asignación de modelo**, en el árbol **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Clase**.
8. En la sección **Orígenes de datos**, seleccione **Agregar raíz** para agregar un origen de datos que llame a la lógica de la aplicación existente para la validación de códigos IBAN.
9. En el cuadro de diálogo que aparece, siga estos pasos:

    1. En el campo **Nombre**, especifique **Check\_codes**.
    2. En el campo **Clase**, especifique o seleccione **ISO7064**.
    3. Seleccione **Aceptar**.

10. En el árbol **Tipos de orígenes de datos**, siga estos pasos:

    1. Amplíe el origen de datos **format**.
    2. Expanda **format\\Root: Sequence(Root)**.
    3. Expanda **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**.
    4. Expanda **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)**.

11. En el árbol **Modelo de datos**, siga estos pasos:

    1. Amplíe el campo **Pagos** del modelo de datos.
    2. Expanda **Payments\\Creditor Account(CreditorAccount)**.
    3. Expanda **Payments\\Creditor Account(CreditorAccount)\\Identification**.
    4. Expanda **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN**.

12. Siga estos pasos para vincular componentes del formato configurado a los campos del modelo de datos:

    1. Seleccione **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)**.
    2. Seleccione **Pagos**.
    3. Seleccione **Enlazar**. Basándose en esta configuración, cada línea en el archivo de análisis se considerará un pago único.
    4. Seleccione **format\\Root: Sequence(Root)\\Rows: Sequence 1..\* (Rows)\\Fields: Sequence 1..1 (Fields)\\IBAN: String(IBAN)**.
    5. Seleccione **Payments\\Creditor Account(CreditorAccount)\\Identification\\IBAN**.
    6. Seleccione **Enlazar**. Basado en este ajuste, el campo **IBAN** del modelo de datos se completará con el valor del archivo de análisis.

    ![El enlace de componentes de formato con campos del modelo de datos en la página Diseñador de asignación de modelo.](../media/design-expressions-app-class-er-02.png)

13. En la pestaña **Validaciones**, siga estos pasos para agregar una regla de [validación](../general-electronic-reporting-formula-designer.md#Validation) que muestra un mensaje de error para cualquier línea del archivo de análisis que contenga un código IBAN no válido:

    1. Seleccione **Nuevo** y luego seleccione **Editar condición**.
    2. En la página **Diseñador de fórmula**, en el árbol **Origen de datos**, expanda el origen de datos **Check\_codes** que representa la clase de aplicación **ISO7064** para ver los métodos disponibles de esta clase.
    3. Seleccione **Check\_codes\\verifyMOD1271\_36**.
    4. Seleccione **Agregar origen de datos**.
    5. En el campo **Fórmula**, introduzca la siguiente [expresión](../general-electronic-reporting-formula-designer.md#Binding): **Check\_codes.verifyMOD1271\_36(format.Root.Rows.Fields.IBAN)**.
    6. Haga clic en **Guardar** y, a continuación, cierre la página.
    7. Seleccione **Editar mensaje**.
    8. En la página **Diseñador de fórmulas**, en el campo **Fórmula**, entre **CONCATENATE("Se ha encontrado un código IBAN no válido:&nbsp;", format.Root.Rows.Fields.IBAN)**.
    9. Haga clic en **Guardar** y, a continuación, cierre la página.

    En base a esta configuración, la condición de validación devolverá *[FALSE](../er-formula-supported-data-types-primitive.md#boolean)* para todo código IBAN no válido llamando al método existente **verifyMOD1271\_36** de la clase de aplicación **ISO7064**. Tenga en cuenta que el valor del código IBAN se define de forma dinámica en el tiempo de ejecución como argumento del método de llamada basándose en el contenido del archivo de texto de análisis.

    ![Regla de validación en la página del diseñador de asignación de modelo.](../media/design-expressions-app-class-er-03.png)

14. Seleccione **Guardar**.
15. Cierre la página **Diseñador de asignación de modelo** y luego cierre la página **Asignación de modelo a origen de datos**.

## <a name="run-the-format-mapping"></a>Ejecute la asignación de formato

Para comprobar, ejecute la asignación de formato mediante el archivo SampleIncomingMessage.txt que descargó anteriormente. La salida generada incluirá datos que se importan desde el archivo de texto seleccionado y se trasladan al modelo de datos personalizado durante la importación real.

1. En la página **Asignación de modelo a origen de datos**, seleccione **Ejecutar**.
2. En la página **Parámetros de informes electrónicos**, seleccione **Navegar**, busque el archivo **SampleIncomingMessage.txt** que descargó y selecciónelo.
3. Seleccione **Aceptar**.
4. Observe que la página **Asignación de modelo a origen de datos** muestra un mensaje de error sobre un código IBAN no válido.

    ![Resultado de ejecutar la asignación de formato en la página Asignación de modelo a origen de datos.](../media/design-expressions-app-class-er-04.png)

5. Revise la salida en formato XML que representa los datos que se han importado del archivo seleccionado y se han trasladado al modelo de datos. Observe que solo se procesaron sin errores tres líneas del archivo de texto importado. El código IBAN en línea 4 no es válido y se omitió.

    ![Salida XML.](../media/design-expressions-app-class-er-05.png)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
