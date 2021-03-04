---
title: Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base
description: En este tema se explica cómo puede comparar los resultados de los informes electrónicos (ER) generados con los valores del informe de línea base.
author: NickSelin
manager: AnnBe
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: d89922bd10b6db17d3fee22409137d6ec966858b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682832"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base

[!include[banner](../includes/banner.md)]

Puede realizar un seguimiento de los resultados de los formatos de informes electrónicos (ER) que generan documentos electrónicos salientes. Cuando está activada la generación de seguimiento (mediante el uso del parámetro del usuario de ER **Ejecutar en modo de depuración**), se genera un nuevo registro de ejecución del formato de ER cada vez que se ejecuta un informe de ER. Los siguientes detalles se almacenan en cada seguimiento que se genera:

- Todas las advertencias que se generaron mediante reglas de validación
- Todos los errores que se generaron mediante reglas de validación
- Todos los archivos generados que se almacenan como archivos adjuntos del registro de seguimiento

Puede almacenar los archivos de aplicación individuales de línea base para cualquier formato de ER. Los archivos se consideran archivos de línea base cuando describen los resultados esperados de los informes que se ejecutan. Si un archivo de línea base está disponible para un formato de ER que se ejecuta mientras está activada la generación de seguimiento, el seguimiento almacena, además de los detalles que se mencionaron anteriormente, el resultado de la comparación del documento electrónico generado con el archivo de línea base. En un clic, también puede obtener el documento electrónico generado y su archivo de línea base en un único archivo zip. A continuación, puede hacer comparación detallada mediante una herramienta externa como WinDiff.

Puede evaluar el seguimiento para analizar si los documentos electrónicos que se crean generan incluyen el contenido esperado. Puede hacer esta evaluación en un entorno de prueba de aceptación del usuario (UAT) cuando ha cambiado la base de código (por ejemplo, cuando migró a una nueva instancia de la aplicación, paquetes de revisión instalados o modificaciones de código implementadas). De este modo, puede asegurarse de que la evaluación no afecta a la ejecución de informes de ER que se usan. Para muchos informes de ER, la evaluación se puede realizar en modo desatendido.

Para obtener más información acerca de esta función, reproduzca las guías de tareas **ER Generar informes y comparar los resultados (Parte 1)** y **ER Generar informes y comparar los resultados (Parte 2)**, que forman parte del proceso empresarial **7.5.4.3 Probar soluciones y servicios de TI (10679)** y se puede descargar del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Estas guías de tareas le guían por el proceso de configuración del marco de ER para utilizar los archivos de línea base para evaluar documentos electrónicos generados.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Ejemplo: Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base

En este procedimiento se explica cómo configurar el marco de ER para recopilar información sobre ejecuciones del formato de ER y evaluar después los resultados de esas ejecuciones. Como parte de esa evaluación, los documentos generados se comparan con sus archivos de línea base. En este ejemplo, creará las configuraciones de ER necesarias para la empresa de ejemplo, Litware, Inc. Este procedimiento se ha creado para los usuarios con los roles de Administrador del sistema o Desarrollador de informes electrónicos asignados. Estos pasos se pueden completar mediante cualquier conjunto de datos.

Para completar los pasos de este ejemplo, primero debe completar los pasos de [Crear y activar proveedores de configuración](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, compruebe que aparece el proveedor de la configuración para la empresa de ejemplo Litware, Inc. y que ha marcado como **Activo**. Si no ve a este proveedor de configuración, siga los pasos de [Crear y activar proveedores de configuración](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-document-management-parameters"></a>Confugurar los parámetros de gestión de documentos

1. Vaya **Administración de la organización** \> **Administración de documentos** \> **Tipos de documento** y cree un nuevo tipo de documento para almacenar los archivos de línea base.
2. En el campo **Clase**, introduzca **Adjuntar archivo**.
3. En el campo **Grupo**, introduzca **Archivo**.

![Página de tipos de documento](media/GER-BaselineSample-SetupDocumentType.PNG "Captura de pantalla de la página Tipos de documento")

> [!NOTE]
> Debe configurarse un nuevo tipo de documento que tiene el mismo nombre para cada conjunto de datos donde tiene previsto usar la característica de la línea base de ER.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Configurar parámetros de ER para empezar a usar la característica de la línea base

1. En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.

    ![Espacio de trabajo de los informes electrónicos](media/GER-BaselineSample-ERWorkspace.PNG "Captura de pantalla de página del espacio de trabajo de informes electrónicos")

2. En la pestaña **Archivos adjuntos**, en el campo **Línea base**, introduzca o seleccione el tipo de documento que acaba de crear.

    ![Pestaña de Archivos adjuntos para la página Parámetros de informes electrónicos](media/GER-BaselineSample-ERParameters.PNG "Captura de pantalla de página de los parámetros de informes electrónicos")

3. Selecione **Guardar** y cierre la página **Parámetros de informes electrónicos**.

### <a name="add-a-new-er-model-configuration"></a>Añada una nueva configuración para el modelo ER

1. En el espacio de trabajo **Informe electrónico**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
2. En el panel de acciones, seleccione **Crear configuración**.
3. En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Modelo para aprender líneas base de ER**.
4. Seleccione **Crear configuración** para confirmar la creación de una nueva entrada de modelo de datos de ER.

![Cuadro de diálogo desplegable Crear configuración](media/GER-BaselineSample-ModelAdd.PNG "Captura de pantalla del cuadro de diálogo desplegable de Crear configuración")

### <a name="design-a-data-model"></a>Diseñar un modelo de datos

1. En la página **Configuraciones**, en el panel de acciones, seleccione **Diseñador**.
2. Seleccione **Nuevo**.
3. En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Raíz**.
4. Seleccione **Agregar**.
5. Seleccione **Referencia raíz**.
6. Seleccione **Aceptar** y, a continuación, seleccione **Guardar**.
7. Cierre la página **Diseñador de modelo**.
8. Seleccione **Cambiar estado**.
9. Seleccione **Completar** y, a continuación, seleccione **Aceptar**.

![Página Configuraciones](media/GER-BaselineSample-ModelComplete.PNG "Captura de pantalla de la página Configuración")

### <a name="add-a-new-er-format-configuration"></a>Añada una nueva configuración para el formato de ER

1. En la página **Configuraciones**, en el panel de acciones, seleccione **Crear configuración**.
2. En el cuadro de diálogo desplegable, en el grupo del campo **Nuevo**, seleccione **Formato basado en modelo de datos Modelo para aprender líneas base de ER** .
3. En el campo **Nombre**, introduzca **Formato para aprender líneas base de ER**.
4. Seleccione **Crear configuración** para confirmar la creación de una nueva entrada de formato de ER.

![Cuadro de diálogo desplegable Crear configuración](media/GER-BaselineSample-FormatAdd.PNG "Captura de pantalla del cuadro de diálogo desplegable de Crear configuración")

### <a name="design-a-format"></a>Diseñar un formato

Para este ejemplo, creará un formato de ER simple para generar documentos XML.

1. En la página **Configuraciones**, en el panel de acciones, seleccione **Diseñador**.
2. Seleccione **Agregar raíz**.
2. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el árbol, seleccione **Común\\Archivo**.
    2. En el campo **Nombre**, especifique **Salida**.
    3. Seleccione **Aceptar**.

3. Seleccione **Agregar**.
4. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el árbol, seleccione **XML\\Elemento**.
    2. En el campo **Nombre**, especifique **Documento**.
    3. Seleccione **Aceptar**.

5. En el árbol, seleccione **Salida\\Documento**.
6. Seleccione **Agregar**.
7. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el árbol, seleccione **XML\\Atributo**.
    2. En el campo **Nombre**, escriba **Id**.
    3. Seleccione **Aceptar**.

    ![Página de diseñador de formato](media/GER-BaselineSample-FormatLayoutDesign.PNG "Captura de pantalla de la página del diseñador de formatos")

8. En la pestaña **Asignación**, seleccione **Eliminar**.
9. Seleccione **Agregar raíz**.
10. En el cuadro de diálogo desplegable, en el árbol, seleccione **General\\Parámetros de entrada de usuario** y, a continuación, siga estos pasos:

    1. En el campo **Nombre**, escriba **Id**.
    2. En el campo **Etiqueta**, introduzca **Id**.
    3. Seleccione **Aceptar**.

11. En el árbol, seleccione **Salida\\Documento\\Id**.
12. Seleccione **Enlazar** y, a continuación, seleccione **Guardar**.

![Página de diseñador de formato](media/GER-BaselineSample-FormatMappingDesign.PNG "Captura de pantalla de la página del diseñador de formatos")

A partir de la estructura diseñada, el formato configurado generará un archivo XML. Este XML contiene el elemento **Raíz** que tiene el atributo **Id.** que se establece en el valor que el usuario introduce en el cuadro de diálogo del tiempo de ejecución de ER.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Generar un nuevo archivo de línea base para un formato de ER diseñado

1. En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione **Ejecutar**.
2. En el campo **Introducir id.**, introduzca **1**.
3. Seleccione **Aceptar**.

    ![Cuadro de diálogo Parámetros de notificación electrónica](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "Captura de pantalla del cuadro de diálogo de los parámetros de los informes electrónicos")

4. Guarde una copia local del archivo **out.Admin.xml** que se genera, de modo que puede utilizarla más adelante como una línea base para este formato de ER.

    ![Notificación sobre el archivo generado en la página Configuraciones](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "Captura de pantalla de la notificación sobre el archivo generado en la página Configuraciones")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Configurar parámetros de ER para usar la característica de la línea base

1. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, seleccione **Parámetros de usuario**.
2. Establezca la opción **Ejecutar en modo depuración** en **Sí**.
3. Seleccione **Aceptar**.

![Cuadro de diálogo parámetros de usuario](media/GER-BaselineSample-ERUserParameters.PNG "Captura de pantalla del cuadro de diálogo de los parámetros del usuario")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Agregar una nueva línea base para un formato de ER diseñado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En el panel de acciones, haga clic en **Líneas base**.

    ![Botón de líneas base en la página Configuraciones](media/GER-BaselineSample-OpenBaselinePage.PNG "Captura de pantalla del botón Líneas base en la página Configuraciones")

3. En el panel de acciones, haga clic en **Nueva**.
4. Seleccione el formato de ER **Formato para aprender líneas base de ER** que diseñó anteriormente.
5. Seleccione **Guardar**.

![Página de líneas base del formato de los informes electrónicos](media/GER-BaselineSample-AddBaseline.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")

La línea base se agrega para el formato **Formato para aprender líneas base de ER** .

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Configurar una regla de línea base para la línea base agregada

1. En la página **Líneas base del formato de informes electrónicos**, en el panel de acciones, seleccione el botón **Archivos adjuntos** (el símbolo de clip de papel).
2. En el panel de acciones, seleccione **Nuevo** \> **Archivo**. En los parámetros de ER, debe haberse seleccionado previamente el tipo de documento **Archivo** como el tipo de documento que se utiliza para almacenar los archivos de línea base.
3. Seleccione **Examinar** y seleccione el archivo **out.Admin.xml** que se generó cuando se ejecutó el formato de ER configurado anteriormente.

    ![Página de Archivos adjuntos](media/GER-BaselineSample-UploadBaselineFile.PNG "Captura de pantalla de la página de Archivos adjuntos")

4. Cierre la página **Archivos adjuntos**.
5. En la ficha desplegable **Líneas base**, seleccione **Nueva**.
6. En el campo **Nombre**, especifique **Línea base 1**.
7. En el campo **Nombre de componente de archivo**, introduzca o seleccione **Salida**. Este valor indica que la línea base configurada se comparará con un archivo que se genere mediante el uso del elemento del formato **Salida**.
8. En el campo **Máscara de nombre de archivo**, introduzca **\*.xml**.

    > [!NOTE]
    > Puede definir la máscara del nombre de archivo. Cuando se define la máscara del nombre de archivo, el registro de línea base se utilizará para evaluar la salida generada solo cuando el nombre del archivo de salida que se genera satisface esa máscara.

9. Si la línea base configurada debe utilizarse solo cuando el formato de ER **Formato para aprender líneas base de ER** es ejecutado por usuarios que han iniciado sesión en determinadas empresas, seleccione esas empresas en el campo **Empresas**.
10. En el campo **Línea base**, introduzca o seleccione el archivo adjunto **outAdmin**.
11. Seleccione **Guardar**.

![Página de líneas base del formato de los informes electrónicos](media/GER-BaselineSample-SetupBaselineLine.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En el árbol, expanda **Modelo para aprender líneas base de ER** y seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.
3. En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
4. En el campo **Introducir id.**, introduzca **1**.
5. Seleccione **Aceptar**.
6. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configurar registros de depuración**.

    ![Página de registros de ejecución de informes electrónicos](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Captura de pantalla de página registros de ejecución de los informes electrónicos")

    > [!NOTE]
    > El registro de ejecución contiene información sobre los resultados de la comparación del archivo generado con la línea base configurada. En este ejemplo, el registro indica que el archivo generado y la línea base son iguales.

7. Seleccione **Eliminar todo**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En el árbol, expanda **Modelo para aprender líneas base de ER** y seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.
3. En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
4. En el campo **Introducir id.**, introduzca **2**.
5. Seleccione **Aceptar**.
6. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configurar registros de depuración**.

    ![Página de registros de ejecución de informes electrónicos](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Captura de pantalla de página registros de ejecución de los informes electrónicos")

    > [!NOTE]
    > El registro de ejecución contiene información sobre los resultados de la comparación del archivo generado con la línea base configurada. En este ejemplo, el registro indica que el archivo generado y la línea base son diferentes.

7. Seleccione **Comparar**.

> [!NOTE]
> El archivo generado y el archivo de línea base se proporcionan como archivo zip. Puede utilizar herramientas de comparación externas como WinDiff para comparar los archivos y revisar las diferencias.

## <a name="additional-resources"></a>Recursos adicionales

- [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]