---
title: Usar el tutorial de Regression Suite Automation Tool
description: En este tema se muestra cómo usar la Regression Suite Automation Tool (RSAT). Describe varias características y proporciona ejemplos que emplean secuencias de comandos avanzados.
author: robinarh
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 798717b276e68949a9425350720bf683a37d6fb5
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692999"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Tutorial de Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato pdf. 

Este tutorial le muestra algunas de las características avanzadas de la Regression Suite Automation Tool (RSAT), incluye una asignación de demostración y describe la estrategia y los puntos de aprendizaje clave. 

## <a name="notable-features-of-rsat-and-task-recorder"></a>Características notables de RSAT y Grabador de tareas

### <a name="validate-a-field-value"></a>Validar un valor del campo

RSAT le permite incluir pasos de validación dentro de su caso de prueba para validar los valores esperados. Para obtener información sobre esta característica, consulte el artículo [Validar valores esperados](../../dev-itpro/perf-test/rsat/rsat-validate-expected.md).

El siguiente ejemplo muestra cómo puede utilizar esta característica para validar si el inventario disponible es superior a 0 (cero).

1. En los datos de demostración en la empresa **USMF**, cree una grabación de tareas que tenga los siguientes pasos:

    1. Vaya a **Gestión de información de productos \> Productos \> Productos emitidos**.
    2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **1000** para el campo **Número de artículo**.
    3. Seleccione **Inventario disponible**.
    4. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **1** para el campo **Sitio**.
    5. En la lista, marque la fila seleccionada.
    6. Valide que el valor del campo **Total disponible** es **411,0000000000000000**.

2. Guarde la grabación de la tarea y adjúntela a su caso de prueba en Azure Devops.
3. Agregue el caso de prueba al plan de pruebas, y cargue el caso de prueba en RSAT.
4. Abra el archivo de parámetros de Excel. En la pestaña **InventOnhandItem**, verá una sección **Validar InventOnhandItem** que incluye un campo **Operador**.

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. Para validar que el inventario disponible será siempre superior a 0, cambie el valor del campo **Valor** de **411** a **0** y el valor del campo **Operador** de un signo igual (**=**) a un signo mayor que (**\>**).

    ![Valores cambiados de los campos Valor y y Operador](./media/use_rsa_tool_09.png)

6. Guarde y cierre el archivo de parámetros de Excel.
7. Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel en Azure DevOps.

Ahora, si es el valor del campo **Total disponible** para el artículo especificado en el inventario es superior a 0 (cero), las pruebas se aprobarán, independientemente del valor real del inventario disponible.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Variables guardadas y encadenamiento de casos de prueba

Una característica clave de RSAT es el encadenamiento de casos de prueba, es decir, la capacidad de una prueba para transferir variables a otras pruebas. Para más información, consulte el artículo [Copiar variables para encadenar casos de prueba](../../dev-itpro/perf-test/rsat/rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Caso de prueba derivado

RSAT le permite utilizar la misma grabación de tareas con múltiples casos de prueba, lo que permite que una tarea se ejecute con diferentes configuraciones de datos. Para más información consulte el articulo [Casos de prueba derivados](../../dev-itpro/perf-test/rsat/rsat-derived-test-cases.md).

### <a name="validate-notifications-and-messages"></a>Validar notificaciones y mensajes

Esta característica se puede utilizar para validar si se produjo una acción. Por ejemplo, cuando se crea, estima y inicia una orden de producción, la aplicación muestra un mensaje "Producción – Inicio" para notificarle que se ha iniciado el pedido de producción.

![Notificación Producción – Inicio](./media/use_rsa_tool_05.png)

Puede validar este mensaje a través RSAT introduciendo el texto del mensaje en la pestaña **MessageValidation** del archivo de parámetros de Excel para la grabación adecuada.

![Pestaña Validación de mensaje](./media/use_rsa_tool_06.png)

Una vez que se ejecute el caso de prueba, el mensaje del archivo de parámetros de Excel se compara con el mensaje que se muestra. Si los mensajes no coinciden, el caso de prueba fallará.

> [!NOTE]
> Puede introducir más de un mensaje en la pestaña **MessageValidation** en el archivo de parámetros de Excel. Los mensajes también pueden ser de error o de advertencia en lugar de mensajes informativos.

### <a name="snapshot"></a>Instantánea

Esta característica realiza capturas de pantalla de los pasos que se realizaron durante la grabación de tareas. Es útil para fines de auditoría o depuración.

- Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor del siguiente elemento de **falso** a **verdadero**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Cuando ejecute el caso de prueba, RSAT generará instantáneas (imágenes) de los pasos en la carpeta de reproducción de los casos de prueba en el directorio de trabajo. Si está utilizando una versión anterior de RSAT, las imágenes se guardan en **C:\\Usuarios\\\<Username\>\\AppData\\Roaming\\Herramienta de regresión\\reproducción** y se crea una carpeta separada para cada caso de prueba que se ejecuta.

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

![Flujo para el escenario de demostración](./media/use_rsa_tool_14.png)

La siguiente ilustración muestra la jerarquía de procesos empresariales para este escenario en Modelador de procesos empresariales LCS.

![Procesos empresariales para el escenario de demostración](./media/use_rsa_tool_15.png)

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
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>? 
Muestra ayuda sobre todos los comandos disponibles y sus parámetros.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="optional-parameters"></a>Parámetros opcionales

**``command``**


Dónde ``[command]`` es uno de los comandos especificados a continuación.


#### <a name="about"></a>acerca de
Muestra la versión actual.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls
Borra la pantalla.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**


#### <a name="download"></a>descargar
Descarga archivos adjuntos para el caso de prueba especificado en el directorio de salida. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``test_case_id``** Representa la identificación del caso de prueba.  
**``output_dir``** Representa el directorio de salida. El directorio debe existir.

##### <a name="examples"></a>Ejemplo

``download 123 c:\temp\rsat``   
``download 765 c:\rsat\last``


#### <a name="edit"></a>editar
Le permite abrir el archivo de parámetros en el programa Excel y editarlo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``excel_file``** Debe contener una ruta completa a un archivo Excel existente.

##### <a name="examples"></a>Ejemplo
``edit c:\RSAT\TestCase_123_Base.xlsx``  
``edit e:\temp\TestCase_456_Base.xlsx``


#### <a name="generate"></a>generar
Genera archivos de ejecución y parámetros de prueba para el caso de prueba especificado en el directorio de salida.
Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``test_case_id``** Representa la identificación del caso de prueba.  
**``output_dir``** Representa el directorio de salida. El directorio debe existir.

##### <a name="examples"></a>Ejemplo
``generate 123 c:\temp\rsat``  
``generate 765 c:\rsat\last``


#### <a name="generatederived"></a>generatederived
Genera un nuevo caso de prueba, derivado del caso de prueba proporcionado. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``parent_test_case_id``** Representa la identificación del caso de prueba primario.  
**``test_plan_id``** Representa la identificación del plan de prueba  
**``test_suite_id``** Representa la identificación del conjunto de prueba

##### <a name="examples"></a>Ejemplo
``generatederived 123 8901 678``


#### <a name="generatetestonly"></a>generatetestonly
Genera solo el archivo de ejecución de prueba para el caso de prueba especificado en el directorio de salida. Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[test_case_id] [output_dir]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``test_case_id``** Representa la identificación del caso de prueba.  
**``output_dir``** Representa el directorio de salida. El directorio debe existir.

##### <a name="examples"></a>Ejemplo
``generatetestonly 123 c:\temp\rsat``  
``generatetestonly 765 c:\rsat\last``


#### <a name="generatetestsuite"></a>generatetestsuite
Genera todos los casos de prueba para el conjunto especificado en el directorio de salida.
Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[test_suite_name] [output_dir]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``test_suite_name``** Representa el nombre del conjunto de prueba.  
**``output_dir``** Representa el directorio de salida. El directorio debe existir.

##### <a name="examples"></a>Ejemplo
``generatetestsuite Tests c:\temp\rsat``   
``generatetestsuite Purchase c:\rsat\last``


#### <a name="help"></a>ayuda
Idéntico a [?](#section) comando


#### <a name="list"></a>lista
Enumera todos los casos de prueba disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**


#### <a name="listtestplans"></a>listtestplans
Enumera todos los planes de prueba disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**


#### <a name="listtestsuite"></a>listtestsuite
Enumera casos de prueba para el conjunto de pruebas especificado. Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[suite_name]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``suite_name``** Nombre del conjunto deseado.

##### <a name="examples"></a>Ejemplo
``listtestsuite "sample suite name"``  
``listtestsuite NameOfTheSuite``


#### <a name="listtestsuitenames"></a>listtestsuitenames
Enumera todos los conjuntos de prueba disponibles.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**


#### <a name="playback"></a>reproducción
Reproduce un caso de prueba usando un archivo Excel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[excel_file]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``excel_file``** Una ruta completa al archivo Excel. El archivo debe existir. 

##### <a name="examples"></a>Ejemplo
``
playback c:\RSAT\TestCaseParameters\sample1.xlsx
playback e:\temp\test.xlsx
``


#### <a name="playbackbyid"></a>playbackbyid
Reproduce múltiples casos de prueba a la vez.
Puede usar el comando ``list`` para obtener todos los casos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``test_case_id1``** Identificación del caso de prueba existente.  
**``test_case_id2``** Identificación del caso de prueba existente.  
**``test_case_idN``** Identificación del caso de prueba existente.  

##### <a name="examples"></a>Ejemplo
``playbackbyid 878``  
``playbackbyid 2345 667 135``


#### <a name="playbackmany"></a>playbackmany
Reproduce muchos casos de prueba a la vez, utilizando archivos de Excel.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[excel_file1] [excel_file2] ... [excel_fileN]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``excel_file1``** Ruta completa al archivo Excel. El archivo debe existir.  
**``excel_file2``** Ruta completa al archivo Excel. El archivo debe existir.  
**``excel_fileN``** Ruta completa al archivo Excel. El archivo debe existir.  

##### <a name="examples"></a>Ejemplo
``playbackmany c:\RSAT\TestCaseParameters\param1.xlsx``  
``playbackmany e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx``


#### <a name="playbacksuite"></a>playbacksuite
Reproduce todos los casos de prueba del conjunto de pruebas especificado. Puede usar el comando ``listtestsuitenames`` para obtener todos los conjuntos de prueba disponibles. Use cualquier valor de la primera columna como parámetro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[suite_name]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``suite_name``** Nombre del conjunto deseado.

##### <a name="examples"></a>Ejemplo
``playbacksuite suiteName``  
``playbacksuite sample_suite``


#### <a name="quit"></a>quit
Cierra la aplicación.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**


#### <a name="upload"></a>upload
Carga todos los archivos que pertenecen al conjunto de pruebas o casos de prueba especificados.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``[suite_name] [testcase_id]``

#### <a name="required-parameters"></a>Parámetros necesarios
**``suite_name``** Carga todos los archivos que pertenecen al conjunto de pruebas especificado.
**``testcase_id``** Carga todos los archivos que pertenecen al conjunto (o conjuntos) de pruebas especificado(s).

##### <a name="examples"></a>Ejemplo
``upload sample_suite``  
``upload 123``  
``upload 123 456``


#### <a name="uploadrecording"></a>uploadrecording
Carga solo el archivo de grabación que pertenece a los casos de prueba especificados.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[testcase_id]``

##### <a name="required-parameters"></a>Parámetros necesarios
**``testcase_id``** Cargará el archivo de grabación que pertenece a los casos de prueba especificados.

##### <a name="examples"></a>Ejemplo
``uploadrecording 123``  
``uploadrecording 123 456``


#### <a name="usage"></a>usage
Muestra dos formas de invocar esta aplicación: una con un archivo de configuración predeterminado y otra con un archivo de configuración.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**


### <a name="windows-powershell-examples"></a>Ejemplos de Windows PowerShell

[!IMPORTANT] Los siguientes scripts de ejemplo se proporcionan TAL CUAL con fines ilustrativos y no cuentan con soporte de Microsoft.

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

```xpp
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
