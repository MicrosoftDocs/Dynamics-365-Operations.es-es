---
title: Tutorial de Regression Suite Automation Tool
description: En este tema se muestra cómo usar la Regression Suite Automation Tool (RSAT). Describe varias características y proporciona ejemplos que emplean secuencias de comandos avanzados.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: e2273aefb98880a1ae746ef7ec65b4f2262f3560
ms.sourcegitcommit: 49c97b0c94e916db5efca5672d85df70c3450755
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "8492931"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Tutorial de Regression Suite Automation Tool

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato pdf.

Este tutorial le muestra algunas de las características avanzadas de la Regression Suite Automation Tool (RSAT), incluye una asignación de demostración y describe la estrategia y los puntos de aprendizaje clave.

## <a name="notable-features-of-rsat-and-task-recorder"></a>Características notables de RSAT y Grabador de tareas

### <a name="validate-a-field-value"></a>Validar un valor del campo

RSAT le permite incluir pasos de validación dentro de su caso de prueba para validar los valores esperados. Para obtener información sobre esta característica, consulte el artículo [Validar valores esperados](rsat-validate-expected.md).

El siguiente ejemplo muestra cómo puede utilizar esta característica para validar si el inventario disponible es superior a 0 (cero).

1. En los datos de demostración en la empresa **USMF**, cree una grabación de tareas que tenga los siguientes pasos:

    1. Vaya a **Gestión de información de productos \> Productos \> Productos emitidos**.
    2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **1000** para el campo **Número de artículo**.
    3. Seleccione **Inventario disponible**.
    4. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **1** para el campo **Sitio**.
    5. En la lista, marque la fila seleccionada.
    6. Valide que el valor del campo **Total disponible** es **411,0000000000000000**.

2. Guarde la grabación de la tarea como **archivo de grabación** sin procesar y adjúntela a su caso de prueba en Azure DevOps.
3. Agregue el caso de prueba al plan de pruebas, y cargue el caso de prueba en RSAT.
4. Abra el archivo de parámetros de Excel y vaya a la pestaña **TestCaseSteps**.
5. Para validar si el inventario disponible siempre será más de **0**, vaya al paso **Validar total disponible** y cambie su valor de **411** a **0**. Cambie el valor del campo **Operador** de un signo igual (**=**) a un signo mayor que (**\>**).
6. Guarde y cierre el archivo de parámetros de Excel.
7. Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel en Azure DevOps.

Ahora, si es el valor del campo **Total disponible** para el artículo especificado en el inventario es superior a 0 (cero), las pruebas se aprobarán, independientemente del valor real del inventario disponible.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Variables guardadas y encadenamiento de casos de prueba

Una característica clave de RSAT es el encadenamiento de casos de prueba, es decir, la capacidad de una prueba para transferir variables a otras pruebas. Para más información, consulte el artículo [Copiar variables para encadenar casos de prueba](rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Caso de prueba derivado

RSAT le permite utilizar la misma grabación de tareas con múltiples casos de prueba, lo que permite que una tarea se ejecute con diferentes configuraciones de datos. Para más información consulte el articulo [Casos de prueba derivados](rsat-derived-test-cases.md).

### <a name="validate-notifications-and-messages"></a>Validar notificaciones y mensajes

Esta característica se puede utilizar para validar si se produjo una acción. Por ejemplo, cuando se crea, estima y inicia una orden de producción, la aplicación muestra un mensaje "Producción – Inicio" para notificarle que se ha iniciado el pedido de producción.

![Notificación Producción – Inicio.](./media/use_rsa_tool_05.png)

Puede validar este mensaje a través RSAT introduciendo el texto del mensaje en la pestaña **MessageValidation** del archivo de parámetros de Excel para la grabación adecuada.

![Pestaña Validación de mensaje.](./media/use_rsa_tool_06.png)

Una vez que se ejecute el caso de prueba, el mensaje del archivo de parámetros de Excel se compara con el mensaje que se muestra. Si los mensajes no coinciden, el caso de prueba fallará.

> [!NOTE]
> Puede introducir más de un mensaje en la pestaña **MessageValidation** en el archivo de parámetros de Excel. Los mensajes también pueden ser de error o de advertencia en lugar de mensajes informativos.

### <a name="snapshot"></a>Instantánea

Esta característica realiza capturas de pantalla de los pasos que se realizaron durante la grabación de tareas. Es útil para fines de auditoría o depuración.

- Para utilizar esta característica mientras ejecuta RSAT con la interfaz de usuario, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- Para utilizar esta característica mientras ejecuta RSAT por el CLI (por ejemplo, Azure DevOps), abra el archivo **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Cuando ejecute los casos de prueba, RSAT genera instantáneas (imágenes) de los pasos y las guarda en la carpeta de reproducción de los casos de prueba en el directorio de trabajo. En la carpeta de reproducción, se crea una subcarpeta separada llamada **StepSnapshots**. Esa carpeta contiene instantáneas de los casos de prueba que se ejecutan.

## <a name="assignment"></a>Asignación

### <a name="scenario"></a>Situación

1. El diseñador de productos crea un nuevo producto lanzado.
2. El director de producción inicia una orden de producción para llevar el nivel de existencias a dos piezas.
3. La fabricación comienza y termina con el pedido de producción, y verifica que la cantidad disponible es de dos piezas.
4. El equipo de ventas recibe un pedido para cuatro piezas del nuevo producto. Por lo tanto, el equipo de ventas actualia los requisitos netos a través del plan dinámico. Puesto que no hay capacidad adicional disponible, la directiva de pedidos predeterminada se establece en "comprar en lugar de fabricar". Por lo tanto, se crea un pedido de compra planificado.
5. El comprador agrega un proveedor, consolida el pedido de compra planificado y, a continuación, confirma el pedido de compra.
6. Cuando las mercancías que se adquirieron llegan el almacén, el operador de almacén busca el pedido de compra relacionado y recibe las mercancías. Puesto que el pedido está ahora completado, las mercancías se pueden seleccionar y empaquetar con el pedido de ventas.
7. Finance registra la factura de compra y la factura de ventas.

En la ilustración siguiente se muestra el flujo para este escenario.

![Flujo para el escenario de demostración.](./media/use_rsa_tool_14.png)

La siguiente ilustración muestra la jerarquía de procesos empresariales para este escenario en Modelador de procesos empresariales LCS.

![Procesos empresariales para el escenario de demostración.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Estrategia – Aprendizaje clave

### <a name="data"></a>Datos

- Asegúrese de que tiene volúmenes de datos representativos (una copia de los datos de configuración de producción/dorados más los datos migrados).
- Cuando genere nuevos datos mediante el grabador de tareas, cree nombres de pruebas que no entren en conflicto con nombres existentes (por ejemplo, utilice un prefijo como **RSATxxx**).
- Utilice la Restauración en un momento determinado de Azure para volver a ejecutar pruebas en entornos que no son del nivel 1.
- Aunque puede utilizar las características de Excel **ALEATORIO** y **AHORA** para generar una combinación única, el esfuerzo es considerablemente elevado. He aquí un ejemplo.

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Grabador de tareas

- Defina los escenarios antes de comenzar la grabación. Un proyecto bien gestionado tiene escenarios de prueba predefinidos. Para crear un caso de prueba, considere cómo de previsible es el resultado de esos escenarios de prueba.
- Divida las grabaciones si son realizadas por distintos roles, o si hay un tiempo de espera o un evento externo para el paso siguiente.
- Evite seleccionar valores en las listas. En su lugar, utilice formatos de texto, como **FIFO**, **AudioRM** y **SiteWH**. Cuando seleccione de una lista, se graba la posición del valor de la lista, no el valor en sí. Si los artículos se agregan a esa lista, el puesto de valor puede cambiar. Por lo tanto, su grabación utilizará un parámetro diferente, y el resto del escenario podría verse afectado.
- Piense en el comportamiento de varios usuarios. Por ejemplo, supongamos que su pedido de ventas recién creado no se seleccionará siempre automáticamente. En su lugar, utilice siempre el filtro para encontrar el orden correcto.
- Utilice la característica Copiar en el Grabador de tareas para guardar el nombre de un producto recién creado para que pueda usarse en casos de prueba encadenados.
- Use la característica Validar en el Grabador de tareas para establecer los puntos de control que verifiquen que los pasos se han ejecutado correctamente.

### <a name="rsat"></a>RSAT

- Para ejecutar la prueba en otra empresa, puede cambiar la empresa en la pestaña **General** del archivo de parámetros de Excel. Asegúrese de que la configuración y los datos estén disponibles en la empresa recién seleccionada.
- Puede cambiar el usuario de la prueba en la pestaña **General** del archivo de parámetros de Excel. Especifique el id. de correo electrónico del usuario que ejecutará el caso de prueba. De esta manera, el caso de prueba se puede ejecutar mediante los permisos de seguridad del usuario especificado.
- Para esperar antes de que se inicie la prueba, puede definir una pausa en la pestaña **General** del archivo de parámetros de Excel. Esta pausa se puede utilizar en un trabajo por lotes (por ejemplo, si un flujo de trabajo debe ejecutarse antes de que se realice el paso siguiente).

## <a name="advanced-scripting"></a>Secuencia de comandos avanzada

### <a name="cli"></a>CLI

RSAT se puede llamar desde una ventana del **Símbolo del sistema** o **PowerShell**.

> [!NOTE]
> Verifique que la variable de entorno **TestRoot** está establecida en la ruta de instalación de RSAT. (En Microsoft Windows, abra **Panel de control**, seleccione **Sistema y seguridad \> Sistema \> Configuración del sistema avanzado** y, a continuación, seleccione **Variables de entorno**).

1. Abra una ventana **Símbolo del sistema** o **PowerShell** como administrador.
2. Navegue al directorio de instalación de RSAT.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Enumere todos los comandos.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Enumera todos los comandos o muestra ayuda para un comando específico, junto con los parámetros disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: parámetros opcionales

`command`: Donde ``[command]`` es uno de los comandos de la lista anterior.

#### <a name="about"></a>acerca de

Muestra la versión de la RSAT instalada.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Borra la pantalla.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>descargar

Descarga adjuntos (archivos de parámetros, ejecución y grabación) para el caso de prueba especificado desde Azure DevOps hasta el directorio de salida. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles y usar cualquier valor de la primera columna como un parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>download: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de descarga esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.

##### <a name="download-required-parameters"></a>descargar: parámetros requeridos

+ `test_case_id`: representa la identificación del caso de prueba.

##### <a name="download-optional-parameters"></a>descargar: parámetros opcionales

+ `output_dir`: representa el directorio de trabajo de salida. El directorio debe existir. Se utilizará el directorio de trabajo desde la configuración si no se especifica este parámetro.

##### <a name="download-examples"></a>descargar: ejemplos

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>paquete de descargas

Descarga adjuntos (archivos de parámetros, ejecución y grabación) para todos los casos de prueba en el paquete de pruebas especificado desde Azure DevOps hasta el directorio de salida. Puede usar el comando ``listtestsuitenames`` para obtener todos los paquetes de prueba disponibles y usar cualquier valor como un parámetro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de descarga esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/byid`: este modificador indica que el paquete de pruebas deseado se identifica por su ID de Azure DevOps en lugar del nombre del paquete de pruebas.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite: parámetros requeridos

+ `test_suite_name`: representa el nombre del conjunto de prueba. Este parámetro es necesario si el modificador /byid **no** está especificado. Este nombre es el nombre del paquete de pruebas de Azure DevOps.
+ `test_suite_id`: representa la identificación del conjunto de prueba. Este parámetro es necesario si el modificador /byid **está** especificado. Este ID es el ID de Azure DevOps del paquete de pruebas.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite: parámetros opcionales

+ `output_dir`: representa el directorio de trabajo de salida. El directorio debe existir. Se utilizará el directorio de trabajo desde la configuración si no se especifica este parámetro.

##### <a name="downloadsuite-examples"></a>downloadsuite: ejemplos

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>editar

Le permite abrir el archivo de parámetros en el programa Excel y editarlo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>editar: parámetros necesarios

+ `excel_file`: debe contener una ruta completa a un archivo Excel existente.

##### <a name="edit-examples"></a>editar: ejemplos

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>generar

Genera archivos de ejecución y parámetros de prueba para el caso de prueba especificado en el directorio de salida. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generate: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de generación esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/dllonly`: generar solo archivos de ejecución de prueba. No regenerar el archivo de parámetros de Excel.
+ `/keepcustomexcel`: actualizar el archivo de parámetros existente. También regenere los archivos de ejecución.

##### <a name="generate-required-parameters"></a>generar: parámetros requeridos

+ `test_case_id`: representa la identificación del caso de prueba.

##### <a name="generate-optional-parameters"></a>generate: parámetros opcionales

+ `output_dir`: representa el directorio de trabajo de salida. El directorio debe existir. Se utilizará el directorio de trabajo desde la configuración si no se especifica este parámetro.

##### <a name="generate-examples"></a>generar: ejemplos

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

Genera un nuevo caso de prueba (caso de prueba secundario) derivado del caso de prueba proporcionado. El nuevo caso de prueba también se agrega al conjunto de pruebas especificado. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles y usar cualquier valor de la primera columna como un parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de generación esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.

##### <a name="generatederived-required-parameters"></a>generatederived: parámetros requeridos

+ `parent_test_case_id`: representa la identificación del caso de prueba primario.
+ `test_plan_id`: representa la identificación del plan de prueba.
+ `test_suite_id`: representa la identificación del conjunto de prueba.

##### <a name="generatederived-examples"></a>generatederived: ejemplos

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Genera solo los archivos de ejecución de pruebas para el caso de prueba especificado. No genera el archivo de parámetros de Excel. Los archivos se generan en el directorio de salida especificado. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles y usar cualquier valor de la primera columna como un parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de generación esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: parámetros requeridos

+ `test_case_id`: representa la identificación del caso de prueba.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly: parámetros opcionales

+ `output_dir`: representa el directorio de trabajo de salida. El directorio debe existir. Se utilizará el directorio de trabajo desde la configuración si no se especifica este parámetro.

##### <a name="generatetestonly-examples"></a>generatetestonly: ejemplos

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Genera los archivos de automatización de prueba para todos los casos de prueba en el conjunto de pruebas especificado. Puede usar el comando ``listtestsuitenames`` para obtener todos los paquetes de prueba disponibles y usar cualquier valor como un parámetro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de generación esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/dllonly`: generar solo archivos de ejecución de prueba. No regenerar el archivo de parámetros de Excel.
+ `/keepcustomexcel`: actualizar el archivo de parámetros existente. También regenere los archivos de ejecución.
+ `/byid`: este modificador indica que el paquete de pruebas deseado se identifica por su ID de Azure DevOps en lugar del nombre del paquete de pruebas.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: parámetros requeridos

+ `test_suite_name`: representa el nombre del conjunto de prueba. Este parámetro es necesario si el modificador /byid **no** está especificado. Este nombre es el nombre del paquete de pruebas de Azure DevOps.
+ `test_suite_id`: representa la identificación del conjunto de prueba. Este parámetro es necesario si el modificador /byid **está** especificado. Este ID es el ID de Azure DevOps del paquete de pruebas.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite: parámetros opcionales

+ `output_dir`: representa el directorio de trabajo de salida. El directorio debe existir. Se utilizará el directorio de trabajo desde la configuración si no se especifica este parámetro.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: ejemplos

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>ayuda

Idéntico a [?](#section) comando.

#### <a name="list"></a>lista

Enumera todos los casos de prueba disponibles en el plan de prueba actual.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Enumera todos los planes de prueba disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Enumera casos de prueba para el conjunto de pruebas especificado. Puede usar el comando ``listtestsuitenames`` para obtener todos los paquetes de prueba disponibles y usar cualquier valor de la lista como un parámetro **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: parámetros requeridos

+ `test_suite_name`: el nombre del conjunto deseado.

##### <a name="listtestsuite-examples"></a>listtestsuite: ejemplos

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Enumera casos de prueba para el conjunto de pruebas especificado.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid: parámetros requeridos

+ `test_suite_id`: el ID del conjunto deseado.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid: ejemplos

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Enumera todos los paquetes de prueba disponibles en el plan de prueba actual.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>reproducción

Reproduce el caso de prueba asociado con el archivo de parámetros de Excel especificado. Este comando usa archivos de automatización locales existentes y no descarga archivos de Azure DevOps. Este comando no es compatible con los casos de prueba de comercio de PDV.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>playback: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de reproducción esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/comments[="comment"]`: Proporcione una cadena de información personalizada que se incluirá en el campo **Comentarios** en las páginas de resumen y resultado de la prueba para las ejecuciones de casos de prueba en Azure DevOps.

##### <a name="playback-required-parameters"></a>playback: parámetros requeridos

+ `excel_parameter_file`: La ruta completa de un archivo de parámetros de Excel. El archivo debe existir.

##### <a name="playback-examples"></a>playback: ejemplos

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Reproduce múltiples casos de prueba a la vez. Los casos de prueba se identifican por su ID. Este comando descargará archivos de Azure DevOps. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles y usar cualquier valor de la primera columna como un parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a>playbackbyid: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de reproducción esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/comments[="comment"]`: Proporcione una cadena de información personalizada que se incluirá en el campo **Comentarios** en las páginas de resumen y resultado de la prueba para las ejecuciones de casos de prueba en Azure DevOps.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: parámetros requeridos

+ `test_case_id1`: ID del caso de prueba existente.
+ `test_case_id2`: ID del caso de prueba existente.
+ `test_case_idN`: ID del caso de prueba existente.

##### <a name="playbackbyid-examples"></a>playbackbyid: ejemplos

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Reproduce múltiples casos de prueba a la vez. Los casos de prueba se identifican mediante archivos de parámetros de Excel. Este comando usa archivos de automatización locales existentes y no descarga archivos de Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a>playbackmany: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de reproducción esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/comments[="comment"]`: Proporcione una cadena de información personalizada que se incluirá en el campo **Comentarios** en las páginas de resumen y resultado de la prueba para las ejecuciones de casos de prueba en Azure DevOps.

##### <a name="playbackmany-required-parameters"></a>playbackmany: parámetros requeridos

+ `excel_parameter_file1`: La ruta completa del archivo de parámetros de Excel. El archivo debe existir.
+ `excel_parameter_file2`: La ruta completa del archivo de parámetros de Excel. El archivo debe existir.
+ `excel_parameter_fileN`: La ruta completa del archivo de parámetros de Excel. El archivo debe existir.

##### <a name="playbackmany-examples"></a>playbackmany: ejemplos

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Reproduce todos los casos de prueba de uno o más de los conjuntos de pruebas especificados. Si se especifica el modificador /local, se utilizarán archivos adjuntos locales para la reproducción. De lo contrario, los archivos adjuntos se descargarán de Azure DevOps. Puede usar el comando ``listtestsuitenames`` para obtener todos los paquetes de prueba disponibles y usar cualquier valor de la primera columna como un parámetro **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite: modificadores opcionales

+ `/updatedriver`: si se especifica este modificador, el webdriver del navegador de Internet se actualizará según sea necesario antes de que se ejecute el proceso de reproducción.
+ `/local`: este modificador indica que los archivos adjuntos locales deben usarse para la reproducción en lugar de descargar archivos de Azure DevOps.
+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de reproducción esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/comments[="comment"]`: Proporcione una cadena de información personalizada que se incluirá en el campo **Comentarios** en las páginas de resumen y resultado de la prueba para las ejecuciones de casos de prueba en Azure DevOps.
+ `/byid`: este modificador indica que el paquete de pruebas deseado se identifica por su ID de Azure DevOps en lugar del nombre del paquete de pruebas.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: parámetros requeridos

+ `test_suite_name1`: representa el nombre del conjunto de prueba. Este parámetro es necesario si el modificador /byid **no** está especificado. Este nombre es el nombre del paquete de pruebas de Azure DevOps.
+ `test_suite_nameN`: representa el nombre del conjunto de prueba. Este parámetro es necesario si el modificador /byid **no** está especificado. Este nombre es el nombre del paquete de pruebas de Azure DevOps.
+ `test_suite_id1`: representa la identificación del conjunto de prueba. Este parámetro es necesario si el modificador /byid **está** especificado. Este ID es el ID de Azure DevOps del paquete de pruebas.
+ `test_suite_idN`: representa la identificación del conjunto de prueba. Este parámetro es necesario si el modificador /byid **está** especificado. Este ID es el ID de Azure DevOps del paquete de pruebas.

##### <a name="playbacksuite-examples"></a>playbacksuite: ejemplos

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

Ejecuta todos los casos de prueba del conjunto de pruebas Azure DevOps especificado.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>playbacksuitebyid: modificadores opcionales

+ `/retry[=seconds]`: si se especifica este modificador y los casos de prueba están bloqueados por otras instancias de RSAT, el proceso de reproducción esperará la cantidad de segundos especificada y luego intentará una vez más. El valor predeterminado para \[segundos\] es 120 segundos. Sin este modificador, el proceso se cancelará inmediatamente si se bloquean los casos de prueba.
+ `/comments[="comment"]`: Proporcione una cadena de información personalizada que se incluirá en el campo **Comentarios** en las páginas de resumen y resultado de la prueba para las ejecuciones de casos de prueba en Azure DevOps.
+ `/byid`: este modificador indica que el paquete de pruebas deseado se identifica por su ID de Azure DevOps en lugar del nombre del paquete de pruebas.

##### <a name="playbacksuitebyid-required-parameters"></a>playbacksuitebyid: parámetros requeridos

+ `test_suite_id`: Representa el ID del conjunto de pruebas tal y como existe en Azure DevOps.

##### <a name="playbacksuitebyid-examples"></a>playbacksuitebyid: ejemplos

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>quit

Cierra la aplicación. Este comando es útil solo cuando las aplicaciones se ejecutan en modo interactivo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>quit: ejemplos

`quit`

#### <a name="upload"></a>upload

Carga adjuntos (archivos de parámetros, ejecución y grabación) que pertenecen a un conjunto de pruebas específico o a casos de prueba de Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>upload: parámetros requeridos

+ `test_suite_name`: carga todos los archivos que pertenecen al conjunto de pruebas especificado.
+ `test_case_id1`: representa el primer ID de caso de prueba que debe cargarse. Use este parámetro solo cuando no se haya proporcionado un nombre de conjunto de pruebas.
+ `test_case_idN`: representa el último ID de caso de prueba que debe cargarse. Use este parámetro solo cuando no se haya proporcionado un nombre de conjunto de pruebas.

##### <a name="upload-examples"></a>upload: ejemplos

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Carga solo el archivo de grabación que pertenece a uno o más casos de prueba especificados en Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: parámetros requeridos

+ `test_case_id1`: representa el primer ID de caso de prueba para la grabación que debe cargarse en Azure DevOps.
+ `test_case_idN`: representa el último ID de caso de prueba para la grabación que debe cargarse en Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording: ejemplos

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>usage

Muestra los tres modos de uso de esta aplicación.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Ejecución de la aplicación en modo interactivo:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Ejecución de la aplicación especificando un comando:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Ejecución de la aplicación proporcionando un archivo de configuración:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Ejemplos de Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Ejecutar un caso de prueba en un bucle

Tiene una secuencia de comandos de prueba que crea un nuevo cliente. Mediante la secuencia de comandos, este caso de prueba se puede ejecutar en un bucle aleatorizando los siguientes datos antes de que se ejecute cada iteración:

- Id. de cliente
- Nombre de cliente
- Dirección del cliente

El id. del cliente tendrá el formato *ATCUS\<number\>*, donde \<number\> es un valor entre **000000001** y **999999999**.

El siguiente ejemplo utiliza un parámetro, **start**, para definir el primer número que se usa. Utiliza un segundo parámetro, **nr**, para definir el número de clientes que deben crearse. Para cada iteración, los parámetros en el archivo de parámetros de Excel se cambian mediante una característica UpdateCustomer. A continuación, la línea de comandos de RSAT se llama en una característica RunTestCase.

Abra el Entorno de scripting integrado (ISE) de Microsoft Windows PowerShell en modo de administración y pegue el siguiente código en la ventaja que se denomina **Untitled1.ps1**.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Ejecutar una secuencia de comandos que depende de los datos de Microsoft Dynamics 365

El siguiente ejemplo utiliza una llamada del protocolo abierto de datos (OData) para encontrar el estado del pedido de un pedido de compra. Si el estado no se **factura**, puede, por ejemplo, llamar a un caso de prueba de RSAT que registra la factura.

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
