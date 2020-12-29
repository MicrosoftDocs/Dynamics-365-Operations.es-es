---
title: Mejoras en el seguimiento de los resultados de informes de ER generados y su comparación con valores de línea base
description: En este tema se proporciona información sobre cómo se ha mejorado la característica de la línea base de ER en la versión 10.0.3 de Microsoft Dynamics 365 for Finance and Operations (junio de 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
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
ms.openlocfilehash: 55e821b27f80383d8a8dc7a2d46f87e17c554078
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682856"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>Mejoras en el seguimiento de los resultados de informes de ER generados y su comparación con valores de línea base

[!include[banner](../includes/banner.md)]

En este tema se describe el primer conjunto de mejoras que se han hecho en la característica de línea base del marco de informes electrónicos (ER). Estas mejoras están disponibles en la versión 10.0.3 de Microsoft Dynamics 365 for Finance and Operations (junio de 2019) y posteriores.

## <a name="automate-the-setting-of-baseline-rules"></a>Automatizar la configuración de reglas de línea base

En el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md) se explica cómo configurar el marco de ER para recopilar información sobre ejecuciones del formato de ER y evaluar los resultados de esas ejecuciones. El ejemplo de este tema muestra los pasos que se debe completar.

Estos son algunos de estos pasos:

- Ejecutar un formato de ER para generar un archivo de salida y para almacenar localmente el archivo.
- Agregar el archivo almacenado localmente como adjunto de la línea base que se agregó para un formato de ER.
- Configurar la regla de línea base para la línea base agregada. Esta configuración incluye los siguientes pasos:

    - Especificar un elemento del formato de ER que se utiliza para generar un archivo de salida.
    - Seleccionar el archivo adjunto que hace referencia al archivo de salida generado.

> [!NOTE]
> Estos pasos debe realizarse manualmente, aunque las nuevas funcionalidades de ER permiten su automatización. Para obtener más información acerca de esta característica, complete el siguiente ejemplo.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Ejemplo: Automatizar la configuración de reglas de línea base

Para completar los pasos de este ejemplo, primero debe completar los pasos del ejemplo en el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md), a través de la sección "Agregar una nueva línea base para un formato de ER designado".

### <a name="review-added-baseline"></a>Revisar línea base agregada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Líneas base**.

    > [!NOTE]
    > El botón **Líneas base** en el panel de acciones solo está disponible cuando el parámetro de usuario de ER **Ejecutar en modo depuración** está activado para la empresa actual.

Se ha agregado la línea base para el formato seleccionado **Formato para aprender líneas base de ER**, pero las reglas de línea base aún no se han agregado para esta línea base.

![Página de líneas base del formato de los informes electrónicos](media/GER-BaselineSample-AddBaseline2.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")

### <a name="make-a-new-baseline-rule"></a>Crear una nueva regla de línea base

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En el árbol, expanda **Modelo para aprender líneas base de ER**.
3. En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.
4. En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
5. En el campo **Introducir id.**, introduzca **1**.
6. Establezca la opción **Crear archivos de línea base** en **Sí**.
7. Seleccione **Aceptar**.
8. Seleccione **Líneas base**.

    ![Página de líneas base del formato de los informes electrónicos](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")

    El archivo de salida generado se ha adjuntado automáticamente a la línea base del formato de ER ejecutado. La regla de línea base se ha agregado automáticamente a esta línea base y también contiene la referencia al archivo adjunto.

9. En el campo **Nombre**, especifique **Línea base 1**.
10. En el campo **Máscara de nombre de archivo**, introduzca **.xml**.
11. Seleccione **Guardar**.

### <a name="run-the-format"></a>Ejecutar el formato

Ya está listo para completar el resto de pasos del ejemplo del tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md), empezando por la sección "Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados".

> [!NOTE]
> Cuando elimine la regla de línea base agregada automáticamente en la ficha desplegable **Líneas base**, los archivos adjuntos a los que se hace referencia no se eliminan automáticamente.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Configurar la línea base de modo que ignore constantemente las partes que cambian de la salida de ER

Cuando un formato de ER se haya diseñado para contener información que se cambia cuando se ejecuta el formato, el formato debe requerir el uso de la característica de la línea base de ER para comparar los resultados generados con valores de línea base. Por ejemplo, puede que la información sea la fecha y la hora de procesamiento o el identificador único de un documento generado en distintos formatos (identificador único global \[GUID\], etc.). Las nuevas funcionalidades de ER le permiten configurar la regla de línea base de modo que ignore los elementos que pueden cambiarse de un formato de ER cuando el formato se ejecute con el propósito de comparar valores de línea base con los resultados de la ejecución del formato. Para obtener más información acerca de esta característica, complete el siguiente ejemplo.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Ejemplo: Configurar la línea base de modo que ignore constantemente las partes que cambian de la salida de ER

Para completar los pasos de este ejemplo, primero debe completar los pasos del ejemplo en el tema [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md).

### <a name="modify-a-configured-er-format"></a>Modificar un formato de ER configurado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En el árbol, expanda **Modelo para aprender líneas base de ER**.
3. En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.
4. Seleccione **Diseñador**.
5. En el árbol, seleccione **Salida\\Documento**.
6. Seleccione **Agregar**.
7. En el cuadro de diálogo desplegable, en el árbol, seleccione **XML\\Atributo**.
8. En el campo **Nombre**, introduzca **ProcessingDateTime**.
9. Seleccione **Aceptar**.
10. En la pestaña **Asignación**, en el árbol, seleccione **Salida\\Documento\\ProcessingDateTime**.
11. Seleccione **Editar fórmula**.
12. En el campo **Fórmula**, introduzca la expresión siguiente: **DATETIMEFORMAT(NOW(), "O")**
13. Seleccione **Guardar** y, a continuación, seleccione **Prueba**.
14. Seleccione **Prueba** de nuevo para volver a probar la expresión configurada.

    ![Página del diseñador de fórmulas](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Captura de pantalla de la página del diseñador de fórmulas")

    > [!NOTE]
    > La pestaña **Resultado de prueba** muestra que la expresión configurada devuelve un valor de fecha y hora diferente cada vez que se invoca.

15. Cierre la página **Diseñador de fórmula** y seleccione **Guardar**.

    ![Página de diseñador de formato](media/GER-BaselineSample-FormatMappingDesign2.PNG "Captura de pantalla de la página del diseñador de formatos")

16. Cierre la página **Diseñador de formato**.

### <a name="remove-an-existing-baseline-rule"></a>Eliminar una regla de línea base existente

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Líneas base**.
3. En la lista de líneas base, seleccione la línea base configurada para el formato **Formato para aprender líneas base de ER**.
4. En la ficha desplegable **Líneas base**, seleccione **Eliminar** para eliminar la regla de línea base que configuró anteriormente.

![Página de líneas base del formato de los informes electrónicos](media/GER-BaselineSample-AddBaseline3.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>Definir sustituciones para los enlaces de formato de ER diseñado

1. En la página **Configuraciones**, en la ficha desplegable **Sustituciones**, seleccione **Seleccionar componentes**.
2. En el árbol de componentes del formato, expanda **Salida**, expanda **Salida\\Documento** y active la casilla para **Salida\\Documento\\ProcessingDateTime**.
3. Seleccione **Aceptar**.

![Página de líneas base del formato de los informes electrónicos](media/GER-BaselineSample-AddBaseline4.PNG "Captura de pantalla de la página de líneas base del formato de los informes electrónicos")

Se ha agregado el componente del formato de ER seleccioando a la lista de componentes en la ficha desplegable **Sustituciones**. Cuando el formato de ER de la base se ejecuta en modo de depuración, el enlace del formato para cada componente se sustituirá por el enlace que se muestra en la columna **Enlace** . Para cambiar el enlace predeterminado para un componente que se muestra en la ficha desplegable **Sustituciones**, seleccione **Editar**.

### <a name="make-a-new-baseline-rule"></a>Crear una nueva regla de línea base

Siga los pasos de la sección "Ejemplo: Automatizar la configuración de reglas de línea base" descrita anteriormente en este tema. Una notificación le advierte que el archivo de salida se ha generado mediante el uso de la configuración de línea base, y que se ha producido una sustitución forzada de los enlaces de formato.

![Notificación en la página de configuración](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Captura de pantalla de la notificación en la página Configuraciones")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>Suprimir avisos sobre la sustitución de enlaces de formato

Al configurar determinados parámetros de ER, puede suprimir las notificaciones que advierten sobre la sustitución de enlaces de formato. Esta supresión puede resultar útil cuando los enlaces de formato se reemplazan en un modo desatendido mediante el uso de la Regression Suite Automation Tool. En este caso, el aviso se puede considerar un error del caso de prueba que se está ejecutando.

1. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, seleccione **Parámetros de usuario**.
2. Establezca la opción **Suprimir avisos de línea base** en **Sí** y seleccione **Aceptar**.

### <a name="review-the-generated-baseline-file"></a>Revisar el archivo de línea base generado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Líneas base**.
3. Seleccione **Archivos adjuntos**.
    > [!NOTE]
    > El archivo generado contiene texto de fecha y hora de procesamiento (**"#"**) del enlace que se configuró en la regla de línea base agregada, no del enlace del formato.
    
4. Cierre la página **Archivos adjuntos**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Ejecutar el formato de ER diseñado y revisar el registro para analizar los resultados

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En el árbol, expanda **Modelo para aprender líneas base de ER**.
3. En el árbol, seleccione **Modelo para aprender líneas base de ER\\Formato para aprender líneas base de ER**.
4. En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
5. En el campo **Introducir id.**, escriba **1**.
6. Seleccione **Aceptar**.
7. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configurar registros de depuración**.

El registro de ejecución contiene información sobre los resultados de la comparación del archivo generado con la línea base configurada. El registro indica que el archivo generado y la línea base son iguales, aunque el formato ejecutado contiene el enlace para introducir un valor de fecha y hora que cambia constantemente en el archivo de salida.

> [!NOTE]
> Aunque el archivo de salida se haya generado mediante el uso de la configuración de línea base que fuerza la sustitución de los enlaces del formato, no recibe ningún aviso sobre la sustitución.

## <a name="exchange-baseline-settings-between-environments"></a>Intercambiar configuración de línea base entre entornos

### <a name="export-baseline-settings"></a>Exportar configuración de línea base

Las nuevas funcionalidades de ER le permiten exportar la configuración de línea base para el formato de ER seleccionado desde el entorno actual y almacenarla como archivos XML. 

Para exportar la configuración de línea base, en la página **Líneas base del formato de informes electrónicos**, seleccione **Exportar**.

### <a name="import-baseline-settings"></a>Importar configuración de línea base

La configuración de línea base exportada se puede importar en un entorno diferente. El entorno se debe importar primero como formato de ER. Posteriormente, puede importar la configuración de línea base.

Para importar la configuración de línea base desde un archivo XML almacenado localmente, en la página **Líneas base del formato de informes electrónicos**, seleccione **Importar** y seleccione **Examinar** para seleccionar el archivo XML.

![Importar el cuadro de diálogo de la configuración de la línea base](media/GER-BaselineSample-ImportBaseline1.PNG "Captura de pantalla del cuadro de diálogo Importar configuración de líneas de base")

Para importar la configuración de línea base de un archivo XML almacenado en Microsoft SharePoint Server, según la configuración actual Administración de documentos y el tipo de documento seleccionado, en la página **Líneas base del formato de informes electrónicos**, seleccione **Importar desde origen**. A continuación, seleccione el tipo de documento y el archivo XML. El tipo de documento requerido para acceder a la carpeta de SharePoint deben configurarse con antelación.

![Importación del cuadro de diálogo de origen](media/GER-BaselineSample-ImportBaseline2.PNG "Captura de pantalla del cuadro de diálogo Importar del origen")

> [!NOTE]
> Puede utilizar el Grabador de tareas para registrar los pasos a fin de seleccionar el tipo de documentos requerido y el nombre de archivo en el cuadro de diálogo **Importar desde origen**. De esta manera, puede conservar la configuración de línea base requerida en SharePoint Server e importarla automáticamente mediante la reproducción de una grabación de tareas cuando ejecute pruebas automatizadas usando la Regression Suite Automation Tool.

## <a name="additional-resources"></a>Recursos adicionales

- [Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base](er-trace-reports-compare-baseline.md)
- [Recursos del Grabador de tareas](../user-interface/task-recorder.md)
