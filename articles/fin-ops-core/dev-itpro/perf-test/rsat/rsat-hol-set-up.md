---
title: Configurar e instalar tutorial Regression Suite Automation Tool
description: Este tema es un tutorial que muestra cómo configurar e instalar Regression Suite Automation Tool (RSAT).
author: robinarh
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 9cab5d9c9daf80fe5d2a510d189e71993265aa278342d5a99666615303158f61
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742285"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Configurar e instalar tutorial Regression Suite Automation Tool

Este tema es un tutorial que le ayuda a configurar e iniciar la RSAT y las herramientas asociadas al uso de la RSAT.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Utilice las herramientas del navegador de Internet para descargar y guardar esta página en formato PDF.

## <a name="key-concepts"></a>Conceptos clave

- Comprender la instalación y la configuración de requisitos previos necesarios para las distintas aplicaciones que admite la Regression Suite Automation Tool (RSAT).
- Comprender cómo la característica del Grabador de tareas, junto con Microsoft Dynamics Lifecycle Services (LCS) y Microsoft Azure DevOps, le permite crear, configurar, ejecutar, investigar e informar sobre casos de prueba.
- Permitir a usuarios funcionales grabar tareas empresariales mediante el uso del Grabador de tareas y convertir las grabaciones de tareas en un conjunto de pruebas automatizadas, sin tener que escribir código fuente.

## <a name="before-you-begin"></a>Antes de comenzar

### <a name="prerequisites"></a>Requisitos previos

- Para este tutorial se requiere un entorno ejecute la versión 10.0 de Microsoft Dynamics 365 for Finance and Operations (abril de 2019) o versiones posteriores. Para los clientes que utilizan Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, también se admite la Platform update 20 (PU20) o superior.
- El usuario debe tener derechos de administración para el entorno.
- Debe tener acceso al LCS de suscriptor de cliente y a Azure DevOps (anteriormente conocido como Microsoft Visual Studio Team Services \[VSTS\]).
- El usuario que crea y administra conjuntos de pruebas debe tener una licencia de Azure DevOps Test Plans o Test Manager. Las licencias siguientes también le brindarán acceso a Test Plans:
    - Licencia de Visual Studio Enterprise
    - Licencia de Visual Studio Test Professional
    - Licencia de suscriptor de plataformas de MSDN
- RSAT debe tener acceso al entorno de prueba a través de un explorador web.
- Para generar y editar parámetros de prueba, debe tener instalado Microsoft Excel.

## <a name="configure-azure-devops"></a>Configurar Azure DevOps

### <a name="user-eligibility"></a>Idoneidad del usuario

Asegúrese de que el usuario se crea en Azure DevOps y tiene un nivel de suscripción que brinda acceso a Azure Test Plans. Se requiere una licencia de Azure DevOps Test Plans solo si el usuario creará y administrará casos de prueba (es decir, no todos los usuarios de RSAT requieren esta licencia). Para obtener información sobre los requisitos de la licencia, consulte [Requisitos de la licencia](/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Crear un proyecto nuevo de Azure DevOps

RSAT utiliza Azure Devops para la administración de casos de prueba y de conjuntos de pruebas, la generación de informes y la investigación de los resultados de ejecución de las prueba.

> [!NOTE]
> Puede utilizar un proyecto existente de Azure DevOps. Sin embargo, si su proyecto existente de Azure DevOps se configura de modo que tenga una plantilla personalizada, recibirá un error "Error de sincronización de VSTS" cuando sincroniza casos de prueba del Modelador de procesos empresariales (BPM) a Azure DevOps (consulte la sección [Probar la sincronización de BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)). Si las siguientes prácticas recomendadas se han seguido para la plantilla personalizada, podrá sincronizar los casos de prueba con Azure DevOps. (Estas prácticas recomendadas aparecen en el mensaje de error.)

- No eliminar tipos de elementos de trabajo o campos listos para usar.
- No eliminar estados de un tipo de elemento de trabajo.
- No agregar campos obligatorios a un tipo de elemento de trabajo.

![Mensaje de error con una lista de prácticas recomendadas.](./media/setup_rsa_tool_02.png)

De lo contrario, para este tutorial, le recomendamos que cree un nuevo proyecto de Azure DevOps. Para obtener más información, consulte [Problemas al sincronizar a BPM usando una plantilla de proceso de Azure DevOps (VSTS)](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Abra la URL de Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).
2. Seleccione **Crear proyecto** en la esquina superior derecha de la página Azure DevOps.

    ![Botón Crear proyecto.](./media/setup_rsa_tool_03.png)

3. Rellene los siguientes campos y, a continuación, seleccione **Crear**:

    - **Nombre del proyecto**
    - **Control de la versión**: Seleccione **Control de versiones de Team Foundation**. Tenga en cuenta que la opción predeterminada, **Git**, no es compatible.
    - **Trabajo de elemento de proceso**

    ![Cuadro de diálogo Crear nuevo proyecto.](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Crear un token de acceso personal

En este tutorial, utilizará al Modelador de procesos empresariales (BPM) de LCS para crear una biblioteca del caso de prueba y sincronizar sus casos de prueba con Azure DevOps. Necesitará un token de acceso personal para sincronizar BPM con Azure DevOps.

1. Seleccione el icono del perfil en la esquina superior derecha de la página para el proyecto de Azure DevOps y luego seleccione **Seguridad**.

    ![Comando Seguridad.](./media/setup_rsa_tool_05.png)

2. En el panel izquierdo, en **Seguridad**, seleccione **Tokens de acceso personal**. A continuación, seleccione **Nuevo token**.

    ![Botón Nuevo token en la pestaña Tokens de acceso personal en Configuración de usuario.](./media/setup_rsa_tool_06.png)

3. Rellene los siguientes campos y, a continuación, seleccione **Crear**:

    - **Nombre**
    - **Vencimiento (UTC)**: seleccione **Personalizar definido** y use el selector de fecha para seleccionar la última fecha disponible.
    - **Ámbitos**: seleccione la opción **Acceso completo**.

    ![Cuadro de diálogo Crear un nuevo token de acceso personal.](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Anote el token de acceso personal que se crea. Lo necesitará más adelante cuando realice la configuración de RSAT.

    ![Token de acceso personal.](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>Configurar el proyecto LCS

Necesita un proyecto de Lifecycle Services (LCS) para su biblioteca de pruebas maestra. El Modelador de procesos empresariales (BPM) de LCS se utiliza como la biblioteca maestra para sus casos de prueba. BPM se emplea para adminsitrar y distribuir bibliotecas de prueba en proyectos de LCS. Por ejemplo, un partner de Microsoft o un proveedor de software independiente (ISV) que crea bibliotecas de prueba publicarán casos de prueba en forma de biblioteca de BPM. En BPM, los casos de prueba se organizan por proceso empresarial. BPM no define el orden o la frecuencia de ejecución de la aprobación de su prueba. Estos detalles se administran en Azure DevOps, como se describe más tarde en este tema.  

Para su proyecto de LCS, puede usar una implementación de cliente existente o un proyecto de partner.

### <a name="update-the-lcs-language"></a>Actualizar el lenguaje LCS

> [!NOTE]
> Para que la interfaz de usuario (IU) muestre correctamente los procesos empresariales, el idioma preferido de LCS debe establecerse en **Inglés (Estados Unidos)**.

1. Vaya al proyecto de implementación de LCS
2. Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha de la página y, a continuación, seleccione **Preferencia de idioma**.

    ![Actualizar preferencia de idioma.](./media/setup_rsa_tool_09.png)

3. En el campo **Idioma preferido**, seleccione **Inglés (Estados Unidos)** y, a continuación, seleccione **Guardar**.

    ![Pestaña Preferencia de idioma en Configuración de usuario.](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Configurar LCS para conectarse al proyecto de Azure DevOps

Si creó un nuevo proyecto de Azure DevOps anteriormente, configure el proyecto de LCS para conectarse a este. De lo contrario, si su proyecto de LCS ya está conectado a su proyecto de Azure DevOps , puede continuar con la siguiente sección.

1. Vaya al proyecto de implementación de LCS
2. Seleccione el botón **Menú** y, a continuación, seleccione **Configuración del proyecto**.

    ![Comando Configuración del proyecto.](./media/setup_rsa_tool_11.png)

3. En el panel izquierdo, seleccione **Visual Studio Team Services** y, seguidamente, seleccione **Configurar Visual Studio Team Services**.

    ![Pestaña de Visual Studio Team Services en Configuración del proyecto.](./media/setup_rsa_tool_12.png)

4. En el campo **URL del sitio Azure DevOps**, introduzca la URL del sitio de Azure DevOps. En el campo **Token de acceso personal**, introduzca el token de acceso personal que creó anteriormente.

    > [!NOTE]
    > Aunque VSTS ahora se conoce como Azure DevOps, para conectar LCS a su proyecto de Azure DevOps, utilice la dirección URL antigua. Por ejemplo, la dirección URL de Azure DevOps que se usa en este tutorial es `https://dev.azure.com/D365FOFastTrack/`. Sin embargo, en la siguiente ilustración, se especifica como `https://D365FOFastTrack.visualstudio.com/`.

    ![Paso 1 en la configuración de Visual Studio Team Services.](./media/setup_rsa_tool_13.png)

5. Seleccione **Continuar**.
6. En el campo **Poryecto de Visual Studio Team Services**, seleccione el proyecto VSTS en el sitio seleccionado para vincularlo con el proyecto de LCS. El campo **Plantilla de proceso** se establece de forma predeterminada en **Ágil**. Para una plantilla personalizada, revise la guía práctica recomendada en la sección [Crear un nuevo proyecto de Azure DevOps](#create-a-new-azure-devops-project). A continuación, seleccione **Continuar**.

    ![Paso 2 en la configuración de Visual Studio Team Services.](./media/setup_rsa_tool_14.png)

7. Revise su configuración y, a continuación, seleccione **Guardar**.

    ![Paso 3 en la configuración de Visual Studio Team Services.](./media/setup_rsa_tool_15.png)

8. Seleccione **Autorizar** para autorizar LCS y acceder al sitio de Azure DevOps configurado en su nombre y para activar las características que se integran con VSTS.

    ![Botón Autorizar.](./media/setup_rsa_tool_16.png)

9. Aparece un cuadro de mensaje que indica: "Se le redirigirá a un sitio externo para autorizar a LCS a conectar con Visual Studio Team Services en su nombre. ¿Desea continuar?" Seleccione **Sí**.

    ![Cuadro de mensaje.](./media/setup_rsa_tool_17.png)

10. Seleccione **Aceptar**.

    ![Autorizar acceso.](./media/setup_rsa_tool_18.png)

11. Si es un usuario autorizado, la IU debe devolverse a la página de configuración del proyecto de LCS.

    ![Usuario autorizado.](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Crear una nueva biblioteca de BPM

1. Vaya al proyecto de implementación de LCS
2. Seleccione el botón **Menú** y, a continuación, seleccione **Modelador de procesos empresariales**.

    ![Comando Modelador de procesos empresariales.](./media/setup_rsa_tool_20.png)

3. Seleccione **Nueva biblioteca**.

    ![Botón Nueva biblioteca.](./media/setup_rsa_tool_21.png)

4. En el campo **Nombre de biblioteca**, introduzca un nombre y seleccione **Crear**. Para este tutorial, asigne un nombre a la biblioteca de BPM **RSAT**.

    ![Cuadro de diálogo Crear nueva biblioteca.](./media/setup_rsa_tool_22.png)

5. Abra la nueva biblioteca de BPM **RSAT**.
6. Seleccione el proceso **Proceso empresarial principal de ejemplo** y, a continuación, a la derecha, seleccione **Modo de edición**.

    ![Botón Modo de edición.](./media/setup_rsa_tool_23.png)

7. Cambie el valor del campo **Nombre** y del campo **Descripción** para **Crear un producto**. A continuación, seleccione **Guardar**.

    ![Campos Nombre y Descripción.](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Ambiente

### <a name="version-requirement"></a>Requisito de versión

Se requiere un entorno de prueba o de espacio aislado que ejecute la versión 10. Para los clientes que utilizan la versión 7.3, también se admite la Platform update 20 o superior.

> [!NOTE]
> RSAT debe tener acceso al entorno de prueba a través de un explorador web.

### <a name="user-criteria"></a>Criterios del usuario

El usuario debe tener derechos de administración para este entorno.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Configuración de ayuda para conectar con LCS

Este paso es necesario para conectar con LCS y poder guardar grabaciones de tareas en la biblioteca de BPM adecuada en LCS a través del cliente.

1. Abra el cliente.
2. Vaya a **Administración del sistema \> Configuración \> Parámetros del sistema**.
3. En la pestaña **Ayuda**, en el campo **Configuración de ayuda de Lifecycle Services**, seleccione el proyecto de LCS pertinente (**RSAT** para este tutorial).

    ![Campo Configuración de ayuda de Lifecycle Services en la pestaña Ayuda.](./media/setup_rsa_tool_25.png)

    Las bibliotecas de BPM se rellenan en el proyecto de LCS apropiado.

4. Seleccione **Guardar**.
5. Es posible que tenga que actualizar el explorador para ver el contenido de la ayuda actualizado.

    ![Notificación sobre la actualización del explorador.](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Grabaciones de tareas

> [!NOTE]
> Asegúrese de que todas sus grabaciones de tareas comienzan en el panel principal. Las grabaciones individuales deben ser breves y centrarse en una tarea empresarial, como la creación de un pedido de ventas.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Crear una grabación de tareas y guardarla en la biblioteca de BPM

Cree una grabación de tareas correspondiente que pueda adjuntar al proceso empresarial simple que se creó en la nueva biblioteca de BPM.

1. Abra el cliente.
2. En el panel principal, seleccione el botón **Configuración** (el símbolo de engranaje) y, a continuación, seleccione **Grabador de tareas**.

    ![Seleccione Grabador de tareas en el menú Configuración.](./media/setup_rsa_tool_27.png)

3. Seleccione **Crear grabación**.

    ![Botón Crear grabación.](./media/setup_rsa_tool_28.png)

4. Rellene los campos **Nombre de la grabación** y **Descripción de la grabación** y, a continuación, seleccione **Inicio**.

    ![Campos Nombre de la grabación y Descripción de la grabación.](./media/setup_rsa_tool_29.png)

5. Grabe los pasos para crear un producto. Cuando haya terminado, seleccione **Detener** para detener la grabación.

    ![Pasos para crear un producto.](./media/setup_rsa_tool_30.png)

6. Seleccione **Guardar en Lifecycle Services**.

    ![Guarde la grabación de tareas en Lifecycle Services.](./media/setup_rsa_tool_31.png)

    La información de la biblioteca se carga desde LCS.

    ![Cargando información de la biblioteca.](./media/setup_rsa_tool_32.png)

7. Seleccione la biblioteca de BPM a la que asociar la grabación de tareas. Para este tutorial, seleccione la biblioteca de BPM **RSAT** que se creó anteriormente y el proceso empresarial **Crear un producto** en esta. A continuación seleccione **Aceptar**.

    ![Asociar la grabación de tareas con una biblioteca de BPM y un proceso empresarial.](./media/setup_rsa_tool_33.png)

    Aparece un mesaje "El almacenamiento en Lifecycle Services se realizó correctamente".

    ![Mensaje que indica que se guardó correctamente en LCS.](./media/setup_rsa_tool_34.png)

8. Si desea guardar la grabación de tareas localmente y, seguidamente, cargarla en BPM a través de LCS, siga estos pasos:

    1. Una vez que se complete la grabación, seleccione **Guardar en este equipo**.

        ![Descargar el paquete de grabación de tareas.](./media/setup_rsa_tool_35.png)

    2. En la barra de notificación del explorador, seleccione **Guardar** o **Guardar como** para guardar el archivo en su equipo local.

        ![Barra de notificación.](./media/setup_rsa_tool_36.png)

    3. Vaya a la biblioteca de BPM **RSAT** y seleccione el proceso empresarial para guardar la grabación de tareas.
    4. En la pestaña **Información general**, seleccione **Cargar**.

        ![Botón Cargar.](./media/setup_rsa_tool_37.png)

    5. Seleccione **Examinar**, y seleccione el archivo .axtr que guardó anteriormente. A continuación, seleccione **Cargar**.

        ![Selección del archivo .axtr que se va a cargar.](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>Probar la sincronización de BPM a Azure DevOps

Ahora que una grabación de tareas está vinculada al proceso empresarial, debe validar que el proceso empresarial y la grabación de tareas asociada se pueden sincronizar con Azure DevOps como una característica y un caso de prueba (respectivamente) mediante la característica de sincronización de VSTS en LCS.

> [!NOTE]
> El tipo de elemento de trabajo correspondiente que se crea en Azure DevOps variará, según la plantilla de proceso que seleccionó cuando configuró el proyecto de LCS con Azure DevOps, tal como se describe en la sección [Crear un nuevo proyecto de Azure DevOps](#create-a-new-azure-devops-project).

1. Vaya a la biblioteca de BPM y abra la biblioteca **RSAT** que creó anteriormente.
2. Seleccione el botón de los puntos suspensivos (**...**) y seleccione **Sincronización de VSTS**.

    ![Comando Sincronización de VSTS en el menú de puntos suspensivos.](./media/setup_rsa_tool_39.png)

    Una vez que se complete la sincronización de VSTS, aparece una pestaña **Requisitos** en el lado izquierdo e incluye el elemento de trabajo de Azure DevOps correspondiente.

    > [!NOTE]
    > El elemento de trabajo que se crea en Azure DevOps tendrá el nombre de la biblioteca de BPM como prefijo del título.

    ![Pestaña Requisitos.](./media/setup_rsa_tool_40.png)

3. Actualice la página.
4. Seleccione el botón de los puntos suspensivos (**...**). Verá una opción adicional **Sincronizar casos de prueba**. Seleccione esta opción.

    ![Comando Sincronizar casos de prueba en el menú de puntos suspensivos.](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Si la opción **Sincronizar casos de prueba** no está disponible después de actualizar la página, vaya a la página principal para BPM y seleccione **Sincronizar casos de prueba** para toda la biblioteca. De esta manera, fuerza de forma eficaz una sincronización para toda la biblioteca.
    >
    > ![Selección de Sincronizar casos de prueba para toda la biblioteca.](./media/setup_rsa_tool_42.png)

    Una vez que se completen los casos de prueba, se crea un nuevo caso de prueba en la pestaña **Requisitos**.

    ![Nuevo caso de prueba en la pestaña Requisitos.](./media/setup_rsa_tool_43.png)

5. Vaya a su proyecto de Azure DevOps y seleccione **Tableros \> Artículos de trabajo**.

    ![Comando Artículos de trabajo en Tableros.](./media/setup_rsa_tool_44.png)

6. Valide que existen el artículo de trabajo y el caso de prueba que creó a través de la sincronización de BPM.

    ![Artículo de trabajo y caso de prueba.](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Instalar y configurar RSAT

RSAT se puede instalar en cualquier equipo que ejecute Windows 10 y que pueda conectarse al entorno a través de un explorador Web (Internet Explorer o Google Chrome).

> [!NOTE]
> Antes de instalar una nueva versión de la herramienta, le recomendamos que desinstale la versión anterior.

### <a name="install-an-authentication-certificate"></a>Instalar un certificado de autenticación

Para habilitar una autenticación, debe generar e instalar un certificado en el mismo equipo en el que se está ejecutando RSAT.

#### <a name="generate-a-certificate"></a>Generar un certificado

1. Para generar un archivo de certificado, abra una ventana de Microsoft Windows PowerShell como administrador, y ejecute el siguiente comando.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. Abra el gestor de certificados introduciendo **certlm.msc** en el cuadro de diálogo **Ejecutar** y confirme que el certificado **Certificado de prueba automatizada D365** se crea en **Personal \> Certificados**.

    > [!NOTE]
    > Asegúrese de introducir **certlm.msc**, no **certmgr.msc**, ya que los certificados se almacenan en el equipo local.

    ![Certificado de prueba automatizada D365.](./media/setup_rsa_tool_46.png)

3. Haga clic con el botón secundario en el certificado y seleccione **Copiar**.
4. Vaya a **Entidades de certificación raíz de confianza \> Certificados**.

    ![Carpeta Certificados en el carpeta Entidades de certificación raíz de confianza.](./media/setup_rsa_tool_47.png)

5. En el menú **Acción**, seleccione **Pegar** para copiar el certificado en la ubicación **Entidades de certificación raíz de confianza** .

    ![Comando Pegar en el menú Acción.](./media/setup_rsa_tool_48.png)

6. Para obtener la huella digital del certificado instalado, pero sin espacios ni caracteres especiales, abra una ventana de Windows PowerShell como administrador y ejecute los siguientes comandos.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Guarde la huella digital, ya que la necesitará más adelante cuando actualice los archivos .wif para Application Object Server (AOS) y ajuste la configuración de RSAT.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Configurar el equipo de AOS para que confíe en la conexión

> [!NOTE]
> Si el entorno es un entorno de nivel 2+, la huella digital del certificado debe actualizarse en el archivo wif.config para **todos** los equipos de AOS del entorno.

1. Establezca una conexión de Remote Desktop Protocol (RDP) par el equipo de AOS. Los datos de inicio de sesión están disponibles en la página de detalles del entorno en LCS.
2. Abra Microsoft Internet Information Services (IIS) y encuentre **AOSService** en la lista de sitios.

    ![AOSService en la lista de sitios.](./media/setup_rsa_tool_49.png)

3. Haga clic con el botón secundario en **Explorar** para abrir la carpeta **\<Drive\>: \\AosService\\WebRoot**. Encuentre el archivo **wif.config**.

    ![Archivo wif.config en la carpeta WebRoot.](./media/setup_rsa_tool_50.png)

4. Actualice el archivo **wif.config** agregando una nueva entrada de la autoridad para el nombre del certificado y de la autoridad, como se muestra en el siguiente ejemplo.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Si varios usuarios utilizan la misma aplicación cada usuario debe generar huellas digitales independientes, y cada una de estas huellas digitales debe agregarse en la sección **\<keys\>**.

5. Si hay más de un equipo de AOS, repita los pasos 3 a 4 para cada equipo adicional.

    > [!NOTE]
    > A diferencia de los entornos de nivel 2 anteriores, los nuevos entornos de nivel 2 se implementan con dos instancias de AOS.

6. Ejecute **iisreset** en todos los equipos de AOS.

    > [!NOTE]
    > Si no tiene derechos de administración para ejecutar **iisreset** en un equipo de nivel 1, en la página Detalles del entorno en LCS, seleccione Mantener > Reiniciar servicios.

#### <a name="tier-2-environment"></a>Entorno de nivel 2+

Si se utiliza un entorno de nivel 2+ (espacio aislado Prueba de aceptación estándar o superior), verifique o establezca la siguiente configuración de registro en el equipo en el que está instalado la RSAT. Este paso es necesario porque le ayuda a evitar la autenticación o errores de conexión de RSAT.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>Instalar RSAT

1. Vaya a <https://www.microsoft.com/download/details.aspx?id=57357> y seleccione **Descargar**.
2. Seleccione todos los archivos y, a continuación, seleccione **Siguiente**.

    ![Selección de todos los archivos.](./media/setup_rsa_tool_51.png)

3. Haga doble clic en el paquete .msi para ejecutar el instalador. Posteriormente, cuando se complete la instalación, seleccione **Finalizar**.

    ![Archivo Instalador de RSAT.](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Instalar Selenium y controladores del explorador

En versiones anteriores de RSAT, tuvo que instalar Selenium y los controladores del explorador. Ya no tendrá que instalar estos controladores porque se instalan automáticamente.

1. La primera vez que abra la RSAT, se le pedirá que descargue e instale automáticamente Selenium. Para obtener más información, consulte la sección [Configurar RSAT](#configure-rsat).
2. Antes de poder ejecutar un caso de prueba, se le pedirá que descargue e instale automáticamente el controlador del explorador que corresponda al explorador predeterminado que está seleccionado en la configuración de RSAT. Para obtener más información, consulte la sección [Cargar y ejecutar casos de prueba](#load-and-run-test-cases).

## <a name="get-started-with-rsat"></a>Introducción a RSAT

### <a name="create-a-test-plan-and-test-suites"></a>Crear un plan de prueba y conjuntos de pruebas

1. Vaya al proyecto de Azure DevOps y seleccione **Planes de prueba**.

    ![Comando Planes de prueba.](./media/setup_rsa_tool_53.png)

2. Seleccione **Nuevo plan de prueba**.

    ![Botón Nuevo plan de prueba.](./media/setup_rsa_tool_54.png)

3. Rellene el campo **Nombre** y seleccione **Crear**. Para este tutorial, asigne un nombre al plan de prueba **Plan de prueba de RSAT**.

    ![Cuadro de diálogo Nuevo plan de prueba.](./media/setup_rsa_tool_55.png)

4. Seleccione el signo más (**+**) y, a continuación, seleccione **Conjunto estático** para crear un conjunto estático en el nuevo plan de prueba. Asigne un nombre al nuevo conjunto de pruebas **T01 – Fabricar para existencias**.

    > [!NOTE]
    > También puede crear un conjunto basado en consultas, si desea que los nuevos casos de prueba de BPM se incluyan automáticamente en el conjunto de pruebas de RSAT.

    ![Creación de un conjunto estático.](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Adjuntar casos de prueba a conjuntos de pruebas

1. Seleccione **Agregar existente** en el lado derecho para agregar casos de prueba existentes al conjunto de pruebas.

    ![Botón Agregar existente.](./media/setup_rsa_tool_57.png)

2. En la página **Agregar casos de prueba a conjunto**, seleccione **Ejecutar consulta** y, seguidamente, seleccione el caso de prueba para agregar al conjunto de pruebas. Para este tutorial, seleccione el caso de prueba **Crear un nuevo producto** . A continuación, seleccione **Agregar casos de prueba** en la esquina inferior derecha de la página (este botón no se muestra en la siguiente ilustración).

    ![Botón Ejecutar consulta.](./media/setup_rsa_tool_58.png)

    El caso de prueba se agrega al conjunto de pruebas **T01-Fabricar para existencias**.

    ![Caso de prueba agregado al conjunto de pruebas.](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>Configurar RSAT

1. Abra RSAT.

    ![Icono de RSAT.](./media/setup_rsa_tool_60.png)

2. Recibe un mensaje de advertencia que dice: "La Regression Suite Automation Tool requiere Selenium, ¿desea descargarlo e instalarlo automáticamente ahora?" Seleccione **Sí**.

    ![Mensaje de advertencia que Regression Suite Automation Tool requiere Selenium.](./media/setup_rsa_tool_61.png)

3. Seleccione el botón **Configuración** (el símbolo de engranaje) en la esquina superior derecha y, a continuación, en el cuadro de diálogo que aparece, rellene los siguientes campos:

    - **URL de Azure DevOps**: introduzca la dirección URL de su proyecto de Azure DevOps, como `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Token de acceso**: introduzca el token de acceso que permite a la herramienta conectarse a Azure DevOps. Utilice el token de acceso personal que creó anteriormente en este tutorial. Para obtener más información, consulte [Autenticar acceso con tokens de acceso personales](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Nombre del proyecto**: seleccione el nombre de su proyecto de Azure DevOps .
    - **Plan de prueba**: seleccione el plan de prueba de Azure DevOps que contiene sus casos de prueba. Para obtener más información, consulte [Crear planes de prueba y conjuntos de pruebas](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). Tras seleccionar un plan de prueba, seleccione **Conexión de prueba** para probar su conexión a Azure DevOps.
    - **Nombre de host**: introduzca el nombre de host del entorno de prueba, como **\<myaos\>.cloudax.dynamics.com**. No incluya el prefijo **https://** o **http://**.
    - **Nombre de host de SOAP**: introduzca el nombre de host de SOAP del entorno de prueba. Normalmente, el nombre de host de SOAP es el mismo que el nombre de host, pero tiene un sufijo **soap**. A continuación se muestra un ejemplo: **\<myaos\>soap.cloudax.dynamics.com**. No incluya el prefijo **https://** o **http://**.

        > [!NOTE]
        > Para encontrar el nombre de host y el nombre de host de SOAP, abra el Administrador de IIS, haga clic con el botón derecho en **Sitios \> AOSService** y, a continuación, seleccione **Editar enlaces**. Los valores de la columna **Nombre de host** le brindan el nombre de host y el nombre de host de SOAP (el nombre de host de SOAP tiene el sufijo **soap** en la dirección URL).

        ![Nombre de host y nombre de host de SOAP en la columna Nombre de host.](./media/setup_rsa_tool_63.png)

    - **Nombre de usuario administrador**: introduzca la dirección de correo electrónico de un usuario administrador en el entorno de prueba.
    - **Huella digital**: introduzca la huella digital del certificado de autenticación, tal como se describe anteriormente en este tutorial.
    - **Directorio de trabajo**: especifique la ubicación de la carpeta para almacenar los archivos de automatización de pruebas, como archivos de datos de pruebas de Excel. Por ejemplo, introduzca o seleccione **C:\\Temp\\RegressionTool**.

        > [!NOTE]
        > Si el nombre de la carpeta tiene espacios, la ejecución no se realizará correctamente porque la carpeta no se puede encontrar. Este problema es un problema conocido y se debe corregir en la última versión de la herramienta.

    - **Explorador predeterminado**: seleccione **Internet Explorer** o **Google Chomre**. Asegúrese de que se han instalado los controladores del explorador adecuados.
    - **Tiempo de espera de ejecución de la prueba**: especifique el período de tiempo de espera, en minutos, para ejecuciones de prueba. Cuando transcurra el período de tiempo de espera, todas las ventanas activas se cierran y fallan los casos de prueba pendientes.
    - **Tiempo de espera de la acción de prueba**: este campo controla el período de tiempo de espera, en minutos, para solicitudes de servidor del entorno de Finance and Operations. Normalmente, el valor predeterminado (2 minutos) debe ser suficiente. Sin embargo, para entornos más lentos, es posible que desee aumentar el valor si se producen errores relacionados con los tiempos de espera.
    - **Nombre de la empresa**: introduzca el nombre de la empresa que se utilizará como la empresa predeterminada cuando se crea un archivo de parámetros de Excel. Puede cambiar la empresa más adelante editando el archivo de parámetros de Excel.

    ![Cuadro de diálogo Configuración.](./media/setup_rsa_tool_62.png)

4. Seleccione **Aplicar** para aplicar y guardar su configuración.

    Para guardar su configuración actual en un archivo de configuración en su equipo, seleccione **Guardar como**. Para restaurar su configuración desde un archivo de configuración en su equipo, seleccione **Abrir**.

5. Haga clic en **Cerrar** para cerrar el cuadro de diálogo.

### <a name="load-and-run-test-cases"></a>Cargar y ejecutar casos de prueba

1. Seleccione **Cargar** para cargar el plan de prueba **Plan de prueba de RSAT** desde el proyecto de Azure DevOps.

    ![Botón Cargar.](./media/setup_rsa_tool_64.png)

2. Seleccione el caso de prueba **Crear un nuevo producto** desde el conjunto de pruebas y, a continuación, seleccione **Nuevo \> Generar archivos Ejecución de prueba y Parámetro**.

    ![Comando Generar archivos Ejecución de prueba y Parámetro en el menú Nuevo.](./media/setup_rsa_tool_65.png)

    El archivo de parámetros de Excel se crea en la carpeta local que especificó en la configuración de RSAT (por ejemplo, **C:\\Temp\\RegressionTool**).

    ![Archivo de parámetros de Excel creado.](./media/setup_rsa_tool_66.png)

3. Si desea guardar los archivos de parámetros, seleccione **Cargar**. Los archivos de automatización de pruebas de todos los casos de prueba seleccionados se cargan en Azure DevOps para un uso posterior. (Estos archivos incluyen archivos de parámetros de prueba de Excel.)

    De esta manera, puede seleccionar **Cargar** para cargar archivos de parámetros (y archivos de automatización) del caso de prueba directamente desde Azure DevOps. No es necesario volver a generar los archivos de parámetros. Este enfoque será importante más adelante, cuando quiera mantener las modificaciones en el archivo de parámetros y no quiera que se sobrescriban.

4. Para verificar que los archivos de automatización y los archivos de parámetros se guardan en Azure DevOps, vaya al proyecto de Azure DevOps, seleccione **Tableros \> Artículos de trabajo** y seleccione el caso de prueba **Crear un nuevo producto**. En la pestaña **Archivos adjuntos**, debe ver cuatro archivos:

    - **.cs** – Archivo de automatización C\#
    - **.dll** – Archivo de automatización compilado como un ensamblado
    - **.xlsx** – Archivo de parámetros de Excel
    - **.xml** – Archivo de las grabaciones

    ![Archivos en la pestaña Archivos adjuntos.](./media/setup_rsa_tool_67.png)

5. Seleccione el caso de prueba que desea ejecutar y, a continuación, seleccione **Ejecutar**.

    > [!NOTE]
    > Antes de ejecutar los casos de prueba, si utiliza Internet Explorer como el explorador, asegúrese de que la resolución de su escritorio está establecida en **100%** en **Configuración de la pantalla de Windows \> Escala y diseño**. Si no puede cambiar esta configuración en una máquina virtual (VM), cámbiela en el cliente (portátil) desde el que está intentando acceder a la VM. La configuración de la resolución será heredada por la configuración de la pantalla de la VM.

    ![Resolución del escritorio establecida en 100%.](./media/setup_rsa_tool_68.png)

6. Si los controladores del explorador no están instalados en el sistema, recibirá un mensaje de advertencia que dice: "Esta operación requiere el controlador del \<browser name\>. ¿Desea descargarlo e instalarlo automáticamente ahora?" Seleccione **Sí**.

    ![Mensaje de advertencia para Internet Explorer.](./media/setup_rsa_tool_69.png)

    ![Mensaje de advertencia para Chrome.](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Si utiliza Chrome como el explorador y recibe un mensaje de error que indica que la sesión no se creó porque la versión de Chrome no es correcta, descargue el último controlador de Chrome desde <http://chromedriver.chromium.org/downloads> a la carpeta **C:\\Archivos de programa (x86)\\Regression Suite Automation Tool\\Común\\Externo\\Selenium**.

    ![Mensaje de error para Chrome.](./media/setup_rsa_tool_71.png)

    Se ejecuta el caso de prueba y se actualiza el campo **Resultado**.

    ![Campo de resultado actualizado.](./media/setup_rsa_tool_72.png)

    Si ha seguido este tutorial tal y como está escrito, el caso de prueba **Crear un nuevo producto** no se realizará correctamente porque la grabación de tareas para la creación de un producto guardó el nombre del producto como un valor codificado. Si vuelve a ejecutar el mismo caso de prueba, debe recibir un mensaje de error, ya que el producto ya existe.

    ![Campo Resultado establecido en Fallido.](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Ver los resultados de la prueba

1. Haga doble clic en el caso de prueba fallido.

    Recibe un mensaje de error.

    ![Mensaje de error.](./media/setup_rsa_tool_73.png)

2. Seleccione **Detalles** para ver el mensaje de error completo.

    ![Mensaje de error completo.](./media/setup_rsa_tool_74.png)

3. Para ver una versión detallada del mensaje de error en Azure DevOps, seleccione **Abrir en Azure DevOps**. En Azure DevOps, puede ver el estado del caso de prueba y el mensaje de error detallado.

    ![Mensaje de error detallado en Azure DevOps.](./media/setup_rsa_tool_75.png)

4. Para ver los resultados de la prueba directamente en el proyecto de Azure DevOps , vaya a **Planes de prueba \> Planes de prueba \> Ejecuciones**. Haga doble clic en la ejecución de la prueba sobre la que desea ver más detalles.

    ![Lista de ejecuciones de pruebas en Azure DevOps.](./media/setup_rsa_tool_76.png)

5. La pestaña **Resumen de la ejecución** indica que el caso de prueba ha fallado, aunque no proporciona el mensaje de error real. Para ver el mensaje de error detallado, seleccione la pestaña **Resultados de la prueba**.

    ![Pestaña Resumen de la ejecución.](./media/setup_rsa_tool_77.png)

    La pestaña **Resultados de la prueba** proporciona información sobre el caso de la prueba, junto con el resultado y el mensaje de error.

    ![Pestaña Resultados de prueba.](./media/setup_rsa_tool_78.png)

6. Haga doble clic en el registro relevante para ver el mensaje de error detallado.

    ![Mensaje de error detallado.](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Todos los mensajes de error están disponibles localmente en **C:\\Usuarios\\\$YourUserName\\AppData\\Roaming\\RegressionTool\\errormsg-.txt**.

7. También puede exportar los resultados de la prueba del nivel del plan de prueba seleccionando **Exportar**.

    ![Exportación de un plan de prueba.](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Modificar el archivo de parámetros de Excel

1. Abra RSAT.
2. Seleccione el caso de prueba y, a continuación. seleccione **Editar** para abrir el archivo de parámetros de Excel.

    En la hoja **EcoResProductCreate**, compruebe que el valor del campo **Código de producto** está codificado. Debe actualizar este campo a un nuevo código de producto antes de volver a ejecutar el caso de prueba.

3. Para generar un código de producto único para cada ejecución sin tener que volver a abrir el archivo de parámetros de Excel y actualizar manualmente el código de producto cada vez, utilice la siguiente fórmula de Excel.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Además de la pestaña **General**, el archivo de parámetros de Excel contiene una pestaña de datos para cada página del formulario que visita el caso de prueba.

    ![Campo Código de producto.](./media/setup_rsa_tool_81.png)

4. Seleccione **Guardar** y, a continuación, cierre el libro de Excel.
5. Seleccione **Cargar** para guardar el archivo de parámetros de Excel en Azure DevOps.

    ![Mensaje de carga correcta.](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Para ejecutar casos de prueba en un determinado contexto del usuario, introduzca el id. de correo electrónico del usuario en el campo **Usuario de la prueba** en la pestaña **General** del archivo de parámetros de Excel. En la última versión de RSAT, se ha actualizado el diseño de los campos en el archivo de parámetros de Excel, pero el concepto permanece igual.
    >
    > ![Campo Usuario de la prueba.](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Validar los resultados

- Seleccione **Ejecutar** para volver a ejecutar el caso de prueba y verifique que se ha aprobado el caso de prueba. Puede ver los resultados de la prueba tal y como se descibe en la sección [Ver los resultados de la prueba](#view-the-test-results).

    ![Campo Resultado establecido en Aprobado.](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Encadenamiento de casos de prueba

Una característica clave de RSAT es el encadenamiento de casos de prueba (es decir, la capacidad de una prueba para transferir valores a otras pruebas). Los casos de prueba se ejecutan según el pedido definido en el plan de prueba de Azure DevOps . (Este pedido también se puede actualizar en la propia herramienta de prueba.) Por lo tanto, si desea transferir variables desde un caso de prueba a otro, es muy importante que las pruebas estén en el orden correcto.

En esta sección, creará una variable guardada en el primer caso de prueba, creará un segundo caso de prueba y transferirá la variable guardada del primer caso de prueba al segundo caso de prueba. A continuación, ejecutará los casos de prueba como un caso de prueba encadenado en RSAT.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Modificar una grabación de tareas existente para crear una variable guardada

1. Abra el cliente.
2. Seleccione el botón **Configuración** (el símbolo de engranaje) y, a continuación, seleccione **Grabador de tareas**.
3. Seleccione **Editar grabación**.

    ![Botón Editar grabación.](./media/setup_rsa_tool_85.png)

4. Seleccione **Abrir desde Lifecycle Services**.

    ![Botón Abrir desde Lifecycle Services.](./media/setup_rsa_tool_86.png)

5. Seleccione **Seleccionar la biblioteca de Lifecycle Services**.

    ![Botón Seleccionar la biblioteca de Lifecycle Services.](./media/setup_rsa_tool_87.png)

    Las bibliotecas de BPM se cargan desde LCS.

    ![Cargando bibliotecas de BPM.](./media/setup_rsa_tool_88.png)

6. Una vez que las bibliotecas de BPM se carguen desde LCS, seleccione la biblioteca de BPM **RSAT** y el proceso empresarial **Crear un nuevo producto** con el que se asoció la grabación de tareas. A continuación seleccione **Aceptar**.

    ![Selección de una biblioteca de BPM y un proceso de negocio.](./media/setup_rsa_tool_89.png)

7. El nombre de la grabación de tareas adecuada se introduce en el campo **Nombre de la grabación**. Seleccione **Inicio**.

    ![Nombre de la grabación de tareas en el campo Nombre de la grabación.](./media/setup_rsa_tool_90.png)

8. Vaya a **Gestión de información de productos \> Productos** y seleccione **Nuevo** para abrir la página en la que se grabó la grabación de tareas original **Crear un producto**.
9. Seleccione **Insertar paso**.

    > [!NOTE]
    > El nuevo paso se inserta **después** del paso que seleccionó en el panel.

    ![Botón Insertar paso.](./media/setup_rsa_tool_91.png)

10. Haga clic con el botón secundario en el campo **Código de producto** y, a continuación, seleccione **Grabador de tareas \> Copiar**.

    ![Comando Copiar.](./media/setup_rsa_tool_92.png)

11. Se agrega un nuevo paso al panel. Anote el valor en el campo **Código de producto**, puesto que lo necesitará más adelante.

    ![Nuevo paso agregado.](./media/setup_rsa_tool_93.png)

12. Seleccione **Edición finalizada**.
13. Seleccione **Guardar en Lifecycle Services** y asocie la nueva grabación de tareas con la misma biblioteca de BPM y el proceso empresarial con el que se asoció la grabación de tareas. Para obtener más información, consulte la sección [Crear una grabación de tareas y guardarla en la biblioteca de BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Vaya a la biblioteca de BPM y seleccione **Sincronizar casos de prueba** para sobrescribir la grabación de tareas vinculada al caso de prueba en Azure DevOps, tal y como se describe en la sección [Probar la sincronización de BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).
15. Abra RSAT y seleccione **Cargar** para recargar todos los casos de prueba del conjunto de pruebas. Debe volver a generar los archivos de automatización y de parámetros para el caso de prueba adecuado seleccionando el caso de prueba y luego seleccionandolo **Nuevo \> Generar archivos Ejecución de prueba y Parámetro**, tal y como se describe en la sección [Cargar y ejecutar casos de prueba](#load-and-run-test-cases).

    > [!NOTE]
    > Si el archivo de parámetros de Excel se deja abierto, la regeneración fallará. Por lo tanto, asegúrese de que el archivo de de parámetros de Excel para el caso de prueba está cerrado antes de generar el nuevo archivo de parámetros de Excel.

16. Seleccione **Editar** para abrir el nuevo archivo de parámetros de Excel. Verá una nueva entrada **Variable guardada** en la línea 9. Esta variable, **{{EcoResProductCreate\_Identificación\_ProductNumber\_Copia}}** se guarda en el archivo XML de la grabación de tareas y se puede utilizar en pruebas posteriores.

    ![Entrada de variable guardada.](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Crear un nuevo caso de prueba

1. Vaya a la biblioteca de BPM **RSAT**.
2. Seleccione el proceso **Proceso empresarial de soporte de ejemplo** y, a continuación, a la derecha, seleccione **Modo de edición**.
3. Cambie el valor del campo **Nombre** y del campo **Descripción** para **Lanzar un producto**. A continuación, seleccione **Guardar**.

    ![Nombre y descripción cambiados para Lanzar un producto.](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Crear una nueva grabación de tareas que tenga una función Validar

- Cree una grabación de tareas para lanzar el producto que se creó anteriormente en la entidad jurídica de USRT. Para obtener más información, consulte la sección [Crear una grabación de tareas y guardarla en la biblioteca de BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > Para los casos de prueba encadenados, le recomendamos que busque o filtre la grabación que necesita *escribiendo manualmente el valor del campo*. De esa manera, la herramienta puede determinar el registro que debe realizar la acción en el caso de prueba posterior.

    ![Nueva grabación de tareas que tenga una función Validar.](./media/setup_rsa_tool_96.png)

    Como se muestra en la ilustración anterior, después de encontrar el producto usando el filtro rápido, pero antes de seleccionar **Lanzar productos**, valide el valor del campo **Código de producto** para asegurarse de que el id. del producto es el id. del producto que se creó anteriormente. Para validar el valor, haga clic con el botón secundario en el campo **Código de producto** y, a continuación, seleccione **Grabador de tareas \> Validar \> Valor actual**.

    ![Validación del valor actual.](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Guardar la grabación de tareas en BPM

1. Una vez que se complete la grabación de tareas, seleccione **Guardar en Lifecycle Services**.

    ![Guarde la grabación de tareas completada en Lifecycle Services.](./media/setup_rsa_tool_98.png)

2. La información de la biblioteca se carga desde LCS.

    ![Cargando información de la biblioteca de LCS.](./media/setup_rsa_tool_99.png)

3. Seleccione la biblioteca de BPM a la que asociar la grabación de tareas. Para este tutorial, seleccione la biblioteca de BPM **RSAT** que se creó anteriormente y el proceso empresarial **Lanzar un producto** en esta. A continuación seleccione **Aceptar**.

#### <a name="sync-bpm-to-azure-devops"></a>Sincronizar BPM con Azure DevOps

1. Vaya a la biblioteca de BPM y abra la biblioteca **RSAT**.
2. Seleccione **Sincronización de VSTS** y luego **Sincronizar casos de prueba**. Para obtener más información, consulte la sección [Probar la sincronización de BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).

    Una vez que se complete la sincronización, el nuevo artículo de trabajo y el caso de prueba correspondiente para el proceso empresarial **Lanzar un producto** aparecerán en Azure DevOps en **Tableros \> Artículos de trabajo**.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Agregar nuevo caso de prueba al conjunto de prueba existente

1. Vaya a **Planes de prueba \> Planes de prueba** y seleccione el plan **Plan de prueba de RSAT**.
2. Seleccionar **Agregar existente**.
3. En la página **Agregar casos de prueba al conjunto**, seleccione **Ejecutar consulta**.
4. Seleccione el nuevo caso de prueba que se creó para **Lanzar un producto** y, a continuación, seleccione **Agregar casos de prueba** en la esquina inferior derecha de la página (este botón no se muestra en la siguiente ilustración).

    ![Página Agregar casos de prueba a conjunto.](./media/setup_rsa_tool_100.png)

    El conjunto d epruebas ahora tiene dos casos de prueba.

    ![Dos casos de prueba en el conjunto de pruebas.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Cargar casos de prueba en RSAT

1. Abra RSAT y seleccione **Cargar**.
2. Se cargan los casos de prueba y recibe una advertencia que dice: "Esta acción sobrescribirá los archivos de datos de pruebas de Excel, se perderán los cambios locales. ¿Desea continuar?" Seleccione **Sí** para actualizar los archivos de parámetros de Excel en el sistema local, pero no los archivos de parámetros de Excel que se cargaron en Azure DevOps.

    ![Esta acción sobrescribirá los archivos de datos de prueba de Excel.](./media/setup_rsa_tool_102.png)

    Se cargan los dos casos de prueba, junto con el archivo de parámetros de Excel para el primer caso de prueba. Puesto que seleccionó **Cargar** en la última ejecución, los archivos de parámetros se extraen de Azure DevOps.

    ![Casos de prueba caragdos.](./media/setup_rsa_tool_103.png)

3. Seleccione solo el segundo caso de prueba y, a continuación, seleccione **Nuevo \> Generar archivos de ejecución de prueba y parámetro**.

#### <a name="edit-the-excel-parameter-file"></a>Editar el archivo de parámetros de Excel

1. Seleccione solo el segundo caso de prueba y, a continuación. seleccione **Editar** para abrir el archivo de parámetros de Excel correspondiente.
2. Copie la variable guardada **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (consulte la sección [Modificar una grabación de tareas existente para crear una variable guardada](#modify-an-existing-task-recording-to-create-a-saved-variable)) deel primer caso de prueba en todos los campos en los que se utiliza el código de producto. En este caso, copie la variable en los campos **Código de producto** y **Validar código de producto** en la hoja **EcoResProductListPage**.

    ![Campos Código de producto y Validar código de producto.](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > Las variables se pueden transferir entre las pruebas solo durante la misma prueba. Los nombres de las variables deben coincidir exactamente.

3. Seleccione **Guardar** y, a continuación, cierre el libro de Excel.
4. Seleccione **Cargar** para guardar los cambios realizados en el archivo de parámetros de Excel.

#### <a name="run-the-chained-test-cases"></a>Ejecutar los casos de prueba encadenados

1. Seleccione ambos casos de prueba y, a continuación, seleccione **Ejecutar**.
2. Verifique que se hayan aprobado ambos casos de prueba.

    ![Campo Resultado establecido en aprobado para ambos casos de prueba.](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]