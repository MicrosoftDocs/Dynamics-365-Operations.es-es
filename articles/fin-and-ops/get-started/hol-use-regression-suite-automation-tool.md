---
title: Utilizar tutorial Regression Suite Automation Tool
description: En este tema se muestra cómo usar la Regression Suite Automation Tool (RSAT). Describe varias características y proporciona ejemplos que emplean secuencias de comandos avanzados.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 8f3cd6a27ba0e09e48c0562aff46791228bb46b5
ms.sourcegitcommit: f6581bab16225a027f4fbfad25fdef45bd286489
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "1703861"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Utilizar el tutorial Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato pdf. 

Este tutorial le muestra algunas de las características avanzadas de la Regression Suite Automation Tool (RSAT), incluye una asignación de demostración y describe la estrategia y los puntos de aprendizaje clave.

## <a name="features-of-rsattask-recorder"></a>Características de RSAT/Grabador de tareas

### <a name="validate-a-field-value"></a>Validar un valor del campo

Para obtener más información sobre esta característica, consulte [Crear una nueva grabación de tareas que tenga una función Validar](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Variable guardada

Para obtener más información sobre esta característica, consulte [Modificar una grabación de tareas existente para crear una variable guardada](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Caso de prueba derivado

1. Abra la Regression Suite Automation Tool (RSAT) y seleccione los casos de prueba que creó en [Configurar e instalar Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).
2. Seleccione **Nuevo \> Crear caso de prueba derivado**.

    ![Comando Crear caso de prueba derivado en el menú Nuevo](./media/use_rsa_tool_01.png)

3. Recibe un mensaje que indica que se creará un caso de prueba derivado para cada caso de prueba seleccionado en el conjunto de pruebas actual, y que cada caso de prueba derivado tendrá su propia copia del archivo de parámetros de Excel. Seleccione **Aceptar**.

    > [!NOTE]
    > Cuando ejecute un caso de prueba derivado, se utiliza el grabador de tareas de su caso de prueba principal y su propia copia del archivo de parámetros de Excel. De esta manera, puede ejecutar la misma prueba con distintos parámetros, sin tener que mantener más de un grabador de tareas. Un caso de prueba derivado no tiene que formar parte del mismo conjunto de pruebas que su caso de prueba principal.

    ![Cuadro de mensaje](./media/use_rsa_tool_02.png)

    Se crean dos casos de prueba derivados adicionales, y la casilla **¿Derivado?** se selecciona para ellos.

    ![Casos de prueba derivados creados](./media/use_rsa_tool_03.png)

    Se crea automáticamente un caso de prueba derivado en Azure DevOps. Es un artículo secundario del caso de prueba **Crear un nuevo producto** y se etiqueta con una palabra clave especial: **RSAT:DerivedTestSteps**. Estos casos de prueba también se agregan automáticamente al plan de prueba en Azure DevOps.

    ![Palabra clave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Si, por algún motivo, los casos de prueba derivados que se crean no lo hacen en el orden correcto, vaya a Azure DevOps y reordene los casos de prueba en el conjunto de pruebas, de modo que la RSAT pueda ejecutarlos en el orden correcto.

4. Seleccione los casos de prueba derivados y, a continuación. seleccione **Editar** para abrir los archivos de parámetros de Excel correspondientes.
5. Edite estos archivos de parámetros de Excel del mismo modo que editó los archivos principales. Es decir, asegúrese de que el id. de producto esté establecido para que se genere automáticamente. Asegúrese también de que la variable guardada se copie a los campos correspondientes.
6. En la pestaña **General** de ambos archivos de parámetros de Excel, actualice el valor del campo **Empresa** a **USSI**, de modo que los casos de prueba derivados se ejecuten con una entidad jurídica distinta a la del caso de prueba principal. Para ejecutar los casos de prueba con un usuario específico (o el rol asociado a un usuario específico), puede actualizar el valor del campo **Usuario de la prueba**.
7. Seleccione **Ejecutar** y valide que el producto se crea tanto en la entidad jurídica de USMF y como en la entidad jurídica de USSI.

### <a name="validate-notifications"></a>Validar notificaciones

Esta característica se puede utilizar para validar si se produjo una acción. Por ejemplo, cuando se crea, estima y inicia una orden de producción, Microsoft Dynamics 365 for Finance and Operations muestra un mensaje "Producción – Inicio" para notificarle que se ha iniciado el pedido de producción.

![Notificación Producción – Inicio](./media/use_rsa_tool_05.png)

Puede validar este mensaje a través RSAT introduciendo el texto del mensaje en la pestaña **MessageValidation** del archivo de parámetros de Excel para la grabación adecuada.

![Pestaña Validación de mensaje](./media/use_rsa_tool_06.png)

Una vez que se ejecute el caso de prueba, el mensaje del archivo de parámetros de Excel se compara con el mensaje que se muestra en Finance and Operations. Si los mensajes no coinciden, el caso de prueba fallará.

> [!NOTE]
> Puede introducir más de un mensaje en la pestaña **MessageValidation** en el archivo de parámetros de Excel. Los mensajes también pueden ser de error o de advertencia en lugar de mensajes informativos.

### <a name="validate-values-by-using-operators"></a>Validar valores mediante el uso de operadores

En versiones anteriores de RSAT, podía validar valores solo si un valor de control era igual a un valor esperado. La nueva característica le permite validar que una variable no es igual a, menor que o mayor que un valor especificado.

- Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    En el archivo de parámetros de Excel, aparece un nuevo campo **Operador**.

    > [!NOTE]
    > Si ha estado utilizando una versión anterior de RSAT, debe generar los nuevos archivos de parámetros de Excel.

    ![Campo Operador](./media/use_rsa_tool_07.png)

El siguiente ejemplo muestra cómo puede utilizar esta característica para validar si el inventario disponible es superior a 0 (cero).

1. En los datos de demostración en la empresa **USMF**, cree una grabación de tareas que tenga los siguientes pasos:

    1. Vaya a **Gestión de información de productos \> Productos \> Productos emitidos**.
    2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **1000** para el campo **Número de artículo**.
    3. Seleccione **Inventario disponible**.
    4. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro de un valor de **1** para el campo **Sitio**.
    5. En la lista, marque la fila seleccionada.
    6. Valide que el valor del campo **Total disponible** es **411,0000000000000000**.

2. Guarde la grabación de tareas en la biblioteca de BPM en LCS y sincronícela en Azure DevOps.
3. Agregue el caso de prueba al plan de pruebas, y cargue el caso de prueba en RSAT.
4. Abra el archivo de parámetros de Excel. En la pestaña **InventOnhandItem**, verá una sección **Validar InventOnhandItem** que incluye un campo **Operador**.

    ![Campo Operador](./media/use_rsa_tool_08.png)

5. Para validar que el inventario disponible será siempre superior a 0, cambie el valor del campo **Valor** de **411** a **0** y el valor del campo **Operador** de un signo igual (**=**) a un signo mayor que (**\>**).

    ![Valores cambiados de los campos Valor y y Operador](./media/use_rsa_tool_09.png)

6. Guarde y cierre el archivo de parámetros de Excel.
7. Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel en Azure DevOps.

Ahora, si es el valor del campo **Total disponible** para el artículo especificado en el inventario es superior a 0 (cero), las pruebas se aprobarán, independientemente del valor real del inventario disponible.

### <a name="generator-logs"></a>Registros del generador

Esta característica crea una carpeta que contiene los registros de los casos de prueba que se han ejecutado.

- Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor en el siguiente elemento de **falso** a **verdadero**.

    ```
    <add key="LogGeneration" value="false" />
    ```

Una vez que se ejecuten los casos de prueba, puede encontrar los archivos de registro en **C:\\Usuarios\\\<Nombre de usuario\>\\AppData\\Roaming\\RegressionTool\\generatorLogs**.

![Carpeta GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> Si había casos de prueba existentes antes de cambiar el valor del archivo .config, los registros no se generarán para aquellos casos de prueba hasta que genere nuevos archivos de ejecución de pruebas.
> 
> ![Comando Generar solo archivos Ejecución de texto en el menú Nuevo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Captura de pantalla

Esta característica realiza capturas de pantalla de los pasos que se realizaron durante la grabación de tareas.

- Para utilizar esta característica, abra el archivo **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** en la carpeta de instalación de RSAT (por ejemplo, **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool**) y cambie el valor del siguiente elemento de **falso** a **verdadero**.

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

En **C:\\Usuarios\\\<Nombre de usuario\>\\AppData\\Roaming\\regressionTool\\reproducción**, se cra una carpeta independiente para cada caso de prueba que se ejecuta.

![Carpeta Captura de pantalla para un caso de prueba](./media/use_rsa_tool_12.png)

En cada una de estas carpetas, puede encontrar capturas de pantalla de los pasos que se realizaron mientras se ejecutaban los casos de prueba.

![Archivos Captura de pantalla](./media/use_rsa_tool_13.png)

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

En la ilustración siguiente se muestran los procesos empresariales para este escenario en RSAT.

![Procesos empresariales para el escenario de demostración](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Estrategia – Aprendizaje clave

### <a name="data"></a>Datos

- Asegúrese de que tiene volúmenes de datos representativos (una copia de los datos de configuración de producción/dorados más los datos migrados).
- Cuando genere nuevos datos mediante el grabador de tareas, cree nombres de pruebas que no entren en conflicto con nombres existentes (por ejemplo, utilice un prefijo como **RSATxxx**).
- Utilice la Restauración en un momento determinado de Azure para volver a ejecutar pruebas en entornos que no son del nivel 1.
- Aunque puede utilizar las funciones de Excel **ALEATORIO** y **AHORA** para generar una combinación única, el esfuerzo es considerablemente elevado. He aquí un ejemplo.

    ```
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Grabador de tareas

- Defina los escenarios antes de comenzar la grabación. Un proyecto bien gestionado tiene escenarios de prueba predefinidos. Para crear un caso de prueba, considere cómo de previsible es el resultado de esos escenarios de prueba.
- Divida las grabaciones si son realizadas por distintos roles, o si hay un tiempo de espera o un evento externo para el paso siguiente.
- Evite seleccionar valores en las listas. En su lugar, utilice formatos de texto, como **FIFO**, **AudioRM** y **SiteWH**. Cuando seleccione de una lista, se graba la posición del valor de la lista, no el valor en sí. Si los artículos se agregan a esa lista, el puesto de valor puede cambiar. Por lo tanto, su grabación utilizará un parámetro diferente, y el resto del escenario podría verse afectado.
- Piense en el comportamiento de varios usuarios. Por ejemplo, supongamos que su pedido de ventas recién creado no se seleccionará siempre automáticamente. En su lugar, utilice siempre el filtro para encontrar el orden correcto.
- Utilice la función Copiar en el Grabador de tareas para guardar el nombre de un producto recién creado para que pueda usarse en casos de prueba encadenados.
- Use la función Validar en el Grabador de tareas para establecer los puntos de control que verifiquen que los pasos se han ejecutado correctamente.

### <a name="rsat"></a>RSAT

- Para ejecutar la prueba en otra empresa, puede cambiar la empresa en la pestaña **General** del archivo de parámetros de Excel. Asegúrese de que la configuración y los datos estén disponibles en la empresa recién seleccionada.
- Puede cambiar el usuario de la prueba en la pestaña **General** del archivo de parámetros de Excel. Especifique el id. de correo electrónico del usuario que ejecutará el caso de prueba. De esta manera, el caso de prueba se puede ejecutar mediante los permisos de seguridad del usuario especificado.
- Para esperar antes de que se inicie la prueba, puede definir una pausa en la pestaña **General** del archivo de parámetros de Excel. Esta pausa se puede utilizar en un trabajo por lotes (por ejemplo, si un flujo de trabajo debe ejecutarse antes de que se realice el paso siguiente).

## <a name="advanced-scripting"></a>Secuencia de comandos avanzada

### <a name="command-line"></a>Línea de comandos

RSAT se puede llamar desde una ventana **Símbolo del sistema**.

> [!NOTE]
> Verifique que la variable de entorno **TestRoot** está establecida en la ruta de instalación de RSAT. (En Microsoft Windows, abra **Panel de control**, seleccione **Sistema y seguridad \> Sistema \> Configuración del sistema avanzado** y, a continuación, seleccione **Variables de entorno**).

1. Abra una ventana **Símbolo del sistema** como administrador.
2. Ejecute la herramienta desde el directorio de instalación.

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Enumere todos los comandos.

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a>Ejemplos de Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Ejecutar un caso de prueba en un bucle

Tiene una secuencia de comandos de prueba que crea un nuevo cliente. Mediante la secuencia de comandos, este caso de prueba se puede ejecutar en un bucle aleatorizando los siguientes datos antes de que se ejecute cada iteración:

- Id. de cliente
- Nombre de cliente
- Dirección del cliente

El id. del cliente tendrá el formato *ATCUS\<number\>*, donde \<number\> es un valor entre **000000001** y **999999999**.

El siguiente ejemplo utiliza un parámetro, **start**, para definir el primer número que se usa. Utiliza un segundo parámetro, **nr**, para definir el número de clientes que deben crearse. Para cada iteración, los parámetros en el archivo de parámetros de Excel se cambian mediante una función UpdateCustomer. A continuación, la línea de comandos de RSAT se llama en una función RunTestCase.

Abra el Entorno de scripting integrado (ISE) de Microsoft Windows PowerShell en modo de administración y pegue el siguiente código en la ventaja que se denomina **Untitled1.ps1**.

```
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
$excelFilename = "full path to excel file parameter file"
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

```
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
