---
title: Automatizar pruebas con informes electrónicos
description: En este tema se explica cómo puede utilizar la funcionalidad de línea base del marco de informes electrónicos (ER) para automatizar la prueba de funcionalidades.
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatBaselineTable, ERFormatMappingRunLogTable, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 503d4ca562df5c60ee7c475ac146dffbe0edc0c9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569054"
---
# <a name="automate-testing-with-electronic-reporting"></a>Automatizar pruebas con informes electrónicos

[!include[banner](../includes/banner.md)]

En este tema se explica cómo puede utilizar el marco de informes electrónicos (ER) para automatizar la prueba de alguna funcionalidad. El ejemplo de este tema muestra cómo automatizar la prueba de procesamiento de pagos a proveedores.

La aplicación utiliza el marco de ER para generar los archivos de pago y los documentos correspondientes durante el procesamiento de pagos a proveedores. El marco de ER consta de un modelo de datos, asignaciones de modelo y componentes del formato que respaldan el procesamiento de pagos para distintos tipos de pago y la generación de documentos en distintos formatos. Estos componentes se pueden descargar desde Microsoft Dynamics Lifecycle Services (LCS) e importar en la instancia.

También puede personalizar cada componente de Microsoft y utilizarlo como la base de su propio componente personalizado. Al crear una versión personalizada, puede realizar cambios que admitean determinados requisitos. Por ejemplo, puede ajustar el modelo de datos de ER y la asignación de modelo de ER para acceder a los datos de la aplicación específicos del usuario, o bien puede cambiar un formato de ER para modificar el diseño de un documento generado.

Puede utilizar formatos de ER personalizados para procesar archivos de pago que generan pagos de proveedor y también para procesar informes de control. El control de versiones se admite en componentes de ER. Por lo tanto, Microsoft puede proporcionar versiones actualizadas de soluciones de ER para el procesamiento de pago a proveedores. También puede combinar automáticamente la versión actualizada con su componente personalizado reorganizándola. Sin embargo, debe probar la versión reorganizada para asegurarse de que funciona como espera.

Los modelos de datos de ER y las asignaciones de modelo de ER son comunes para muchos formatos de ER que se emplean para procesar pagos de diferentes tipos y para generar documentos de pago específicas de un país/región. Por lo tanto, es muy aconsejable automatizar la prueba de aceptación e integración del usuario para que se realice automáticamente en varias empresas, pero tiene en cuenta el contexto del país/región de cada empresa de destino, utiliza distintos conjuntos de datos, etc.

Para obtener más información sobre cómo crear una versión personalizada de un formato basado en el formato que recibió de un proveedor de configuración, consulte [ER Actualizar el formato adoptando una nueva versión de base de ese formato](./tasks/er-upgrade-format.md).

## <a name="key-concepts"></a>Conceptos clave

Los usuarios avanzados funcionales pueden crear la prueba de aceptación e integración del usuario sin tener que escribir código fuente.

- Utilice la característica de la línea base de ER para comparar documentos generados en copias maestras. Para obtener información, consulte [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md).
- Utilice el grabador de tareas para grabar casos de prueba, e incluya la evaluación de línea base. Para obtener más información, consulte [Recursos del grabador de tareas](../user-interface/task-recorder.md).
- Agrupe casos de prueba para los escenarios de prueba requeridos. Para obtener más información, consulte [Crear y automatizar pruebas de aceptación del usuario](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md).

    - Utilice el Modelador de procesos empresariales (BPM) en LCS para crear bibliotecas para las pruebas de aceptación de usuario.
    - Utilice bibliotecas de prueba de BPM para crear un plan de prueba y conjuntos de prueba en Microsoft Azure DevOps Services (Azure DevOps).

Los usuarios avanzados funcionales pueden ejecutar pruebas de aceptación e integración del usuario.

- Utilice la Regression Suite Automation Tool (RSAT) para ejecutar casos de prueba del conjunto de pruebas deseado.
- Informe de los resultados de la prueba a Azure DevOps, y utilice este servicio para investigar esos resultados.

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar las tareas en este tema, debe completar los siguientes requisitos previos:

- Implementar una topología que admita la automatización de la prueba. Debe tener acceso a la instancia de esta topología para el rol **Administrador del sistema**. Esta topología debe contener los datos de prueba que se usarán en este ejemplo. Para obtener más información, consulte [Implementar y usar un entorno que admita la automatización continua de la compilación y la prueba](../perf-test/continuous-build-test-automation.md).
- Para ejecutar pruebas de aceptación e integración de usuario, debe instalar RSAT en la topología que está utilizando y configurarla de la forma adecuada. Para obtener información sobre cómo instalar y configurar RSAT y configurarlo para trabajar con aplicaciones Finance and Operations y Azure DevOps, consulte [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357). Preste atención a los requisitos previos para usar la herramienta. En la siguiente ilustración se muestra un ejemplo de la configuración de RSAT. El rectángulo azul incluye los parámetros que especifican el acceso a Azure DevOps. El rectángulo verde incluye los parámetros que especifican el acceso a la instancia.

    ![Configuración de RSAT](media/GER-Configure.png "Captura de pantalla del cuadro de diálogo Configuración de RSAT")

- Para organizar casos de prueba en conjuntos para ayudar a garantizar la secuencia de ejecución correcta, de modo que pueda recopilar registros de ejecuciones de pruebas para la generación de informes y la investigación, debe tener acceso a Azure DevOps desde la topología implementada.
- Para completar el ejemplo en este tema, le recomendamos que descargue [ER uso para pruebas de RSAT](https://go.microsoft.com/fwlink/?linkid=874684). Este archivo zip contiene las siguientes guías de tareas:

    | Contenido                                           | Nombre y ubicación del archivo |
    |---------------------------------------------------|------------------------|
    | Grabación de tareas de ejemplo para preparar datos para pruebas | Prepare\\Recording.xml |
    | Grabación de tareas de ejemplo para procesar pagos a proveedores   | Process\\Recording.xml |

## <a name="prepare-the-accounts-payable-module-to-process-vendor-payments"></a>Preparar el módulo Proveedores para procesar pagos a proveedores

1. Iniciar sesión en su instancia.
2. Descargue las siguientes configuraciones de ER desde LCS. Para obtener instrucciones, consulte [ER Importar una configuración de Lifecycle Services](./tasks/er-import-configuration-lifecycle-services.md).

    - **Modelo de pago** Modelo de configuración de ER
    - **Asignación de modelo de pago 1611** Configuración de la asignación del modelo de ER
    - **BACS (Reino Unido)** Configuración de formato de ER

    ![Configuraciones de informes electrónicos](media/GER-Configurations.png "Captura de pantalla de Configuraciones en informes electrónicos")

3. Seleccione la empresa de los datos de demostración **GBSI**, que tiene un contexto de país/región en Gran Bretaña.
4. Configure los parámetros de Proveedores:

    1. Vaya a **Proveedores \> Configuración de pagos \> Formas de pago**.
    2. Seleccione el método de pago **Electrónico**.
    3. Configure el método de pago seleccionado de modo que utilice el formato de ER **BACS (Reino Unido)** que descargó antes para el procesamiento de pagos a proveedores:

        1. En la ficha desplegable **Formatos de archivo**, establezca la opción **Formato de exportación electrónica genérica** en **Sí**.
        2. En el campo **Configuración de formato de exportación**, seleccione **BACS (Reino Unido)**.

    ![Página Formas de pago](media/GER-APParameters.png "Captura de pantalla de la página Formas de pago")

    > [!NOTE]
    > Si tiene la versión derivada de este formato de ER que se creó para admitir personalizaciones, puede seleccionar esta configuración en el método de pago **Electrónico**.

5. Crea un pago a proveedor de ejemplo:

    1. Vaya a **Proveedores \> Pagos \> Diario de pagos**.
    2. Asegúrese de que no haya registro el diario de pagos.

        ![Página Diario de pagos](media/GER-APJournal.png "Captura de pantalla de la página Diario de pagos")

    3. Seleccione **Líneas** e introduzca una línea que tenga la siguiente información.

        | Campo               | Valor de ejemplo   |
        |---------------------|-----------------|
        | Nombre del proveedor         | GB\_SI\_000001  |
        | Débito               | 1,000.00        |
        | Divisa            | GBP             |
        | Tipo de cuenta de contrapartida | Banco            |
        | Cuenta de contrapartida      | GBSI OPER       |
        | Forma de pago   | Electrónica      |

    ![Página Pagos a proveedores](media/GER-APJournalLines.png "Captura de pantalla de la página Pagos a proveedores")

## <a name="prepare-the-er-framework-to-test-vendor-payment-processing"></a>Preparar el marco de ER para probar el procesamiento de pago a proveedor

### <a name="configure-er-parameters"></a>Configurar los parámetros de ER

1. Vaya a **Administración de la organización \> Informes electrónicos \> Parámetros de informes electrónicos**.
2. En la pestaña **Archivos adjuntos**, en el campo **Línea base**, seleccione **Archivo** como el tipo de documento que el marco Administración de documentos (DM) emplea para mantener los documentos relacionados con la característica de línea base como archivos adjuntos de DM.

    ![Página de parámetros de informes electrónicos](media/GER-ERParameters.png "Captura de pantalla de página Parámetros de informes electrónicos")

### <a name="generate-baseline-copies-of-vendor-paymentrelated-documents"></a>Generar copias de línea base de documentos relacionados con el pago a proveedor

1. Vaya a **Proveedores \> Pagos \> Diario de pagos**.
2. Seleccionar **Líneas**.
3. Seleccione **Generar pagos**.
4. Seleccione el método de pago **Electrónico**.
5. Seleccionar la cuenta bancaria **GBSI OPER**.
6. Establezca la opción **Imprimir informe de control** en **Sí**.
7. Descargue la salida generada como archivo zip.
8. Abra el archivo descargado.
9. Extraiga los siguientes archivos del archivo descargado:

    - **Archivo** archivo de pago en formato de texto
    - **ERVendOutPaymControlReport** archivo de informe de control en formato XLSX

    ![Archivos extraídos](media/GER-APJournalProcessed.png "Captura de pantalla de los nombres de archivos extraídos en el explorador de Windows")

### <a name="turn-on-the-er-baseline-feature"></a>Activar la característica de línea base de ER

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. En el panel de acciones, en la pestaña **Configuraciones**, seleccione **Parámetros de usuario**.
3. Establezca la opción **Ejecutar en modo depuración** en **Sí**.

Al activar en el parámetro **Ejecutar en modo de depuración**, obliga al marco de ER a realizar las siguientes acciones después de la ejecución de cualquier formato de ER que genere documentos de salida:

1. Determine si una línea base se configuró para cualquiera de los componentes del formato de ER ejecutado.
2. Determine si cada línea base configurada es aplicable en las condiciones actuales (código de empresa de la empresa que inició sesión, nombre del archivo y extensión del nombre del archivo de la salida generada, etc.).
3. Para cada línea base aplicable, realice las siguientes acciones:

    1. Compare la salida que se genera durante la ejecución del formato de ER con la línea base correspondientes.
    2. Almacene los resultados de la comparación en el registro de depuración de configuraciones de ER.

### <a name="configure-er-baselines-for-vendor-payment-processing"></a>Configurar las líneas base de ER para el procesamiento de pago a proveedor

1. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
2. Seleccione **Líneas base**.
3. Seleccione **Nuevo**.
4. En el campo **Referencia**, seleccione el formato **BACS (Reino Unido)**.
5. Seleccione **Archivos adjuntos**.
6. Agregue una nueva línea base para el archivo de pago a proveedor:

    1. Seleccione **Nuevo**.
    2. En el campo **Tipo**, seleccione el tipo de documento de DM **Archivo** que configuró en los parámetros de ER para almacenar artefactos de línea base.
    3. Examine para seleccionar el archivo de pago guardado localmente **Archivo** en formato de texto.
    4. En el campo **Descripción**, introduzca **Archivo TXT de pago**.

7. Agregue una nueva línea base para el informe de control para el pago a proveedor:

    1. Seleccione **Nuevo**.
    2. En el campo **Tipo**, seleccione el tipo de documento de DM **Archivo** que configuró en los parámetros de ER para almacenar artefactos de línea base.
    3. Examine para seleccionar el archivo de control guardado localmente **ERVendOutPaymControlReport** en formato XLSX.
    4. En el campo **Descripción**, introduzca **Informe de control XLSX de pago**.

    ![Líneas base para el archivo de pago a proveedor e informe de control](media/GER-BaselineAttachments.png "Captura de pantalla de la página Configuraciones con el informe de control XLSX de pago seleccionado")

8. Cierre la página.
9. En la ficha deplegable **Líneas base**, seleccione **Nueva** para configurar una línea base para el archivo de pago:

    1. Asigne un nombre a la línea **Configuración de línea base para archivo de pago**.
    2. En el campo **Nombre de componente de archivo**, seleccione **archivo** para aplicar esta línea base a la salida del formato de ER que genera el archivo de pago en formato de texto BACS (Reino Unido).
    3. En el campo **Empresas**, seleccione **GBSI** para aplicar esta línea base cuando el formato de ER **BACS (Reino Unido)** se ejecute en la empresa GBSI.
    4. En el campo **Máscara de nombre de archivo**, introduzca **\*.TXT** para aplicar esta línea base solo a salidas del componente de formato de **archivo** con la extensión del nombre de archivo **.txt** .
    5. En el campo **Línea base**, seleccione **Archivo TXT de pago** para que esta línea base se utilice para compararla con la salida generada.

10. Seleccione **Nuevo** para configurar una línea base para el informe de control:

    1. Asigne un nombre a la línea **Configuración de línea base para informe de control**.
    2. En el campo **Nombre de componente de archivo**, seleccione **ERVendOutPaymControlReport** para aplicar esta línea base a la salida del formato de ER que genera el informe de control.
    3. En el campo **Empresas**, seleccione **GBSI** para aplicar esta línea base cuando el formato de ER **BACS (Reino Unido)** se ejecute en la empresa GBSI.
    4. En el campo **Máscara de nombre de archivo**, introduzca **\*.XLSX** para aplicar esta línea base solo a salidas del componente de formato de **ERVendOutPaymControlReport** con la extensión del nombre de archivo **.xslx** .
    5. En el campo **Línea base**, seleccione **Informde control XLSX de pago** para que esta línea base se utilice para compararla con la salida generada.

    ![Ficha desplegable de líneas base en la página Configuraciones](media/GER-BaselineRules.png "Captura de pantalla de la ficha desplegable Líneas base en la página Configuraciones")

## <a name="record-tests-to-validate-vendor-payment-processing"></a>Grabar pruebas para validar el procesamiento de pago a proveedor

Como usuarios avanzado funcional, puede grabar sus propios pasos para probar el procesamiento de pagos a proveedor. Le recomendamos que reproduzca (y edite, según sea necesario) la grabación de tareas **Prepare\\Recording.xml** que descargó anteriormente. Esta grabación se utiliza para establecer todos los datos de prueba en el estado correcto. Se requiere ese paso porque la prueba se puede realizar muchas veces, y cada prueba debe usar los datos que se encuentran en el mismo estado.

### <a name="reset-user-settings"></a>Restablecer configuración de usuario

1. Abra el panel predeterminado.
2. Seleccione el botón **Configuración** (el símbolo de engranaje).
3. Seleccione **Opciones de usuario**.
4. Seleccione **Datos de uso**.
5. Seleccione **Restablecer**.
6. Seleccione **Sí** para confirmar que desea restablecer los datos de uso.
7. Cierre la página.

### <a name="record-the-steps-to-prepare-data-for-testing"></a>Grabar los pasos para preparar los datos para la prueba

1. Seleccione el botón **Configuración** (el símbolo de engranaje).
2. Seleccione **Grabación de tareas**.
3. Seleccione **Reproducir grabación**.
4. Seleccione **Abrir desde PC**.
5. Seleccione **Examinar** y seleccione el archivo guardado localmente **Prepare\\Recording.xml**.
6. Seleccione **Inicio**.
7. Siga seleccionando **Reproducir siguiente paso pendiente** hasta que se hayan reproducido todos los pasos de la grabación.

Esta grabación de tareas realiza las siguientes acciones:

1. Establezca el estado de la línea de pago procesada a **Ninguno**.

    ![Pasos 3 a 4 de la grabación de tareas](media/GER-Recording1Review1.png "Captura de pantalla de los pasos 3 a 4 de la grabación de tareas")

2. Active el parámetro de usuario de ER **Ejecutar en modo de depuración**.

    ![Pasos 9 a 10 de la grabación de tareas](media/GER-Recording1Review2.png "Captura de pantalla de los pasos 9 a 10 de la grabación de tareas")

3. Limpie el registro de depuración de ER que contiene los resultados de la comparación de archivos generados con las líneas base.

    ![Pasos 13 a 15 de la grabación de tareas](media/GER-Recording1Review3.png "Captura de pantalla de los pasos 13 a 15 de la grabación de tareas")

### <a name="record-the-steps-to-test-vendor-payment-processing"></a>Grabar los pasos para probar el procesamiento de pago a proveedor

Le recomendamos que reproduzca (y edite, según sea necesario) la grabación de tareas **Process\\Recording.xml** que descargó anteriormente. Esta grabación se utiliza para procesar pagos a proveedor y para validar los resultados de la comparación de documentos generados con las líneas base correspondientes.

1. Seleccione el botón **Configuración** (el símbolo de engranaje).
2. Seleccione **Grabación de tareas**.
3. Seleccione **Reproducir grabación**.
4. Seleccione **Abrir desde PC**.
5. Seleccione **Examinar** y seleccione el archivo guardado localmente **Process\\Recording.xml**.
6. Seleccione **Inicio**.
7. Siga seleccionando **Reproducir siguiente paso pendiente** hasta que se hayan reproducido todos los pasos de la grabación.

Esta grabación de tareas realiza las siguientes acciones:

1. Inicie el procesamiento de pago a proveedor.
2. Seleccione los parámetros de tiempo de ejecución correctos y active la generación de un informe de control.

    ![Pasos 3 a 8 de la grabación de tareas](media/GER-Recording2Review1.png "Captura de pantalla de los pasos 3 a 8 de la grabación de tareas")

3. Acceda al registro de depuración de ER para grabar los resultados de la comparación de salidas generadas con las líneas base correspondientes.

    En el registro de depuración de ER, los resultados de la comparación aparecen en el campo **Texto generado**. Los campos **Componente de formato** y **Ruta del formato que provocó una entrada de registro** hacen referencia al componente del archivo para el que se ha comparado la salida generada con la línea base.

    ![Entradas en la página registros de ejecución de informes electrónicos](media/GER-ERDebugLog.png "Captura de pantalla de entradas en la página Registros de ejecución de informes electrónicos")

4. La comparación de la salida actual con la línea base se graba usando la opción del grabador de tareas **Validar** y seleccionando **Valor actual**.

    ![Uso de la opción Validar para compararla con el valor actual](media/GER-TRRecordValidation.png "Captura de pantalla del uso de la opción Validar para compararla con el valor actual")

    La siguiente ilustración muestra el aspecto de los pasos de validación grabados en la grabación de tareas.

    ![Pasos 13 y 15 de la grabación de tareas](media/GER-Recording2Review2.png "Captura de pantalla de los pasos 13 y 15 de la grabación de tareas")

## <a name="add-the-recorded-tests-to-azure-devops"></a>Agregar las pruebas grabadas en Azure DevOps

1. Abra el entorno de Azure DevOps.
2. Seleccione el proyecto que definió en los parámetros de RSAT cuando [configuró la herramienta](#prerequisites).
3. Seleccione el plan de prueba que definió en los parámetros de RSAT cuando [configuró la herramienta](#prerequisites).
4. Cree un caso de prueba nuevo para el plan de prueba seleccionado:

    1. Asigne un nombre al caso de prueba **Preparar datos para probar el procesamiento de pago electrónico del proveedor**.
    2. Adjunte el archivo **Recording.xml** de la carpeta **Preparar** que descargó anteriormente.

5. Cree un caso de prueba nuevo para el plan de prueba seleccionado:

    1. Asigne un nombre al caso de prueba **Probar procesamiento de pagos a proveedor usando el formato de ER BACS (Reino Unido)**.
    2. Adjunte el archivo **Recording.xml** de la carpeta **Procesar** que descargó anteriormente.

    ![Nuevos casos de prueba para el plan de prueba seleccionado](media/GER-RSAT-DevOps-Tests-Passed.png "Captura de pantalla de los nuevos casos de prueba para el plan de prueba seleccionado")

> [!NOTE]
> Preste atención al orden de ejecución correcto de las pruebas que se agregan.

## <a name="prepare-rsat-to-run-the-recorded-tests"></a>Preparar RSAT para ejecutar las pruebas grabadas

### <a name="load-the-tests-from-azure-devops-to-rsat"></a>Cargar las pruebas de Azure DevOps a RSAT

1. Abra la aplicación de RSAT local en la topología actual.
2. Seleccione **Cargar** para cargar las pruebas que residen actualmente en Azure DevOps en RSAT.

    ![Pruebas cargadas en RSAT](media/GER-RSAT-RSAT-Tests-Loaded.png "Captura de pantalla de las pruebas cargadas en RSAT")

### <a name="create-automation-and-parameters-files"></a>Crear archivos de automatización y parámetros

1. En RSAT, seleccione las pruebas que cargó de Azure DevOps.
2. Seleccione **Nuevo** para crear archivos de automatización y parámetros de RSAT.

    ![Archivos de automatización y parámetros de RSAT creados en RSAT](media/GER-RSAT-RSAT-Tests-Initiated.png "Captura de pantalla de los archivos de automatización y parámetros de RSAT creados en RSAT")

### <a name="modify-the-parameters-files"></a>Modificar los archivos de parámetros

1. En RSAT, seleccione el caso de prueba **Preparar datos para probar el procesamiento de pago electrónico del proveedor**.
2. Seleccione **Editar**.
3. En el libro de Microsoft Excel que se abre, en la hoja de cálculo **General**, cambie el código de empresa a **GBSI** ya que esta empresa se utilizará para la ejecución de la prueba.
4. En RSAT, seleccione el caso de prueba **Probar procesamiento de pagos a proveedor usando el formato de ER BACS (Reino Unido)**.
5. Seleccione **Editar**.
6. En el libro de Excel que se abre, en la hoja de cálculo **General**, cambie el código de empresa a **GBSI**.
7. En la hoja de cálculo **ERFormatMappingRunLogTable**, tenga en cuenta que las celdas A:3 y C:3 contienen el texto de los campos en la tabla de registro de depuración de ER que se utilizan para validar los resultados de la comparación de la salida a la línea base. Estos textos se utilizarán para evaluar registros de depuración de ER que se crean durante la ejecución de la prueba.

    ![Hoja de cálculo de ERFormatMappingRunLogTable](media/GER-RSAT-RSAT-ExcelParameters.png "Captura de pantalla de la hoja de cálculo de ERFormatMappingRunLogTable")

## <a name="run-the-tests-and-analyze-the-results"></a>Ejecutar las pruebas y analizar los resultados

### <a name="run-the-tests-in-rsat"></a>Ejecutar las pruebas en RSAT

1. En RSAT, seleccione las pruebas cargadas.
2. Seleccione **Ejecutar**.

Tenga en cuenta que los casos de prueba se ejecutan automáticamente en la aplicación mediante un explorador web.

### <a name="analyze-the-results-of-test-execution"></a>Analizar los resultados de la ejecución de la prueba

Los resultados de la ejecución de la prueba se almacenan en RSAT. Tenga en cuenta que ambas pruebas fueron correctas.

![Pruebas que fueron correctas en RSAT](media/GER-RSAT-RSAT-Tests-Passed.png "Captura de pantalla de pruebas que fueron correctas en RSAT")

Tenga en cuenta que los resultados de la ejecución de la prueba también se envían a Azure DevOps para poder realizar un análisis adicional.

![Resultados de la ejecución de la prueba en Azure DevOps](media/GER-RSAT-DevOps-Tests-Added.png "Captura de pantalla de los resultados de la ejecución de la prueba en Azure DevOps")

### <a name="simulate-a-situation-where-tests-fail"></a>Simular una situación en la que las pruebas son incorrectas

Este conjunto de pruebas debe ser incorrecto cuando al menos una de las salidas generadas no coincide con la línea base correspondiente. Para lograr esta situación, puede utilizar su versión derivada del formato **BACS (Reino Unido)** que generará un archivo de pago que tiene contenido diferente al de la línea base correspondiente. Para simular esta situación, puede utilizar el mismo formato **BACS (Reino Unido)** pero cambiar el importe del pago en la línea de pago procesada.

1. Abra la aplicación y vaya a **Proveedores \> Pagos \> Diario de pagos**.
2. Seleccionar **Líneas**.
3. Seleccione la línea de pago y, a continuación, seleccione **Estado de pago \> Ninguno**.
4. En el campo **Débito**, cambie el valor de **1000,00** a **2000,00**.
5. Seleccione **Guardar** para guardar los cambios.

### <a name="run-the-tests-in-rsat"></a>Ejecutar las pruebas en RSAT

1. En RSAT, seleccione las pruebas cargadas.
2. Seleccione **Ejecutar**.

Tenga en cuenta que los casos de prueba se ejecutan automáticamente en la aplicación mediante un explorador web.

### <a name="analyze-the-results-of-test-execution"></a>Analizar los resultados de la ejecución de la prueba

Los resultados de la ejecución de la prueba se almacenan en RSAT. Tenga en cuenta que la segunda prueba fue incorrecta durante la segunda ejecución.

![Resultados de prueba incorrecta en RSAT](media/GER-RSAT-RSAT-Tests-Failed.png "Captura de pantalla de los resultados de prueba incorrecta en RSAT")

Tenga en cuenta que los resultados de la ejecución de la prueba también se envían a Azure DevOps para poder realizar un análisis adicional.

![Resultados de prueba incorrecta en Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed.png "Captura de pantalla de los resultados de prueba incorrecta en Azure DevOps")

Puede acceder al estado de cada prueba. También puede acceder al reigstro de ejecución para analizar los motivos en caso de fallo. En la siguiente ilustración, el registro de ejecución muestra que se produjo el fallo debido a la diferencia en contenido entre el archivo de pago generado y su línea base.

![Registro de ejecución para analizar un fallo en Azure DevOps](media/GER-RSAT-DevOps-Tests-Failed-Log.png "Captura de pantalla del registro de ejecución para analizar un fallo en Azure DevOps")

Por lo tanto, como ya ha visto, el funcionamiento de cualquier formato de ER se puede evaluar automáticamente mediante el uso de la RSAT como la plataforma de prueba y mediante el uso de casos de prueba basados en el grabador de tareas que utilizan la característica de línea base de ER.

## <a name="additional-resources"></a>Recursos adicionales

- [Recursos del Grabador de tareas](../user-interface/task-recorder.md)
- [Regression Suite Automation Tool](https://www.microsoft.com/download/details.aspx?id=57357)
- [Crear y automatizar pruebas de aceptación del usuario](../lifecycle-services/using-task-guides-and-bpm-to-create-user-acceptance-tests.md)
- [Implementar y usar un entorno que admita la automatización continua de la compilación y la prueba](../perf-test/continuous-build-test-automation.md)
- [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md)
- [ER Actualizar el formato adoptando una nueva versión de base de ese formato](tasks/er-upgrade-format.md)
- [ER Importar una configuración de Lifecycle Services](tasks/er-import-configuration-lifecycle-services.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]