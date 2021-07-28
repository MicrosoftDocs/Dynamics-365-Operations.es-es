---
title: Instale y conecte la aplicación móvil Warehouse Management
description: Este tema explica cómo instalar la aplicación móvil Warehouse Management en cada uno de sus dispositivos móviles y configurarla para conectarse a su entorno Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5aa67673fe05394f498d0844b8e58ba6f0ec1d85
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346091"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Instale y conecte la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Este tema describe cómo configurar la nueva aplicación de almacén para gestión de almacenes. Si busca información sobre cómo configurar la aplicación de almacén anterior (ahora en desuso), consulte [Instalar y conectar la aplicación del almacén](../../supply-chain/warehousing/install-configure-warehousing-app.md).

Este tema explica cómo descargar e instalar la aplicación móvil Warehouse Management en cada uno de sus dispositivos móviles y configurarla para conectarse a su entorno Supply Chain Management. Puede configurar cada dispositivo manualmente o puede importar la configuración de conexión a través de un archivo o escaneando un código QR.

## <a name="system-requirements"></a>Requisitos del sistema

La aplicación móvil Warehouse Management está disponible para los sistemas operativos Google Android y Windows. Para utilizar la aplicación, debe tener instalado uno de los sistemas operativos siguientes instalado en sus dispositivos móviles:

- Windows 10 (Plataforma universal de Windows \[UWP\]) October 2018 update 1809 (build 10.0.17763) o posterior
- Android 4.4 o posterior

## <a name="turn-on-the-feature"></a>Activar la característica

Antes de poder usar la aplicación, debe estar activada en su sistema una característica relacionada. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Configuración de usuario, iconos y títulos de pasos para la nueva aplicación de almacén*

## <a name="get-the-warehouse-management-mobile-app"></a>Obtenga la aplicación móvil Warehouse Management

Para implementaciones más pequeñas, normalmente deseará instalar la aplicación desde la tienda correspondiente en cada dispositivo y luego configurar manualmente la conexión a los entornos que está utilizando.

Para implementaciones más grandes, puede automatizar la implementación y / o configuración de la aplicación, lo que puede ser más conveniente si administra muchos dispositivos. Por ejemplo, puede utilizar una solución de administración de dispositivos móviles y administración de aplicaciones móviles, como [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Para obtener información sobre cómo usar Intune para agregar aplicaciones, consulte [Agregar aplicaciones a Microsoft Intune](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Instale la aplicación desde una tienda de aplicaciones

La forma más sencilla de instalar la aplicación en un solo dispositivo es instalarla desde una tienda de aplicaciones, que siempre proporciona la última versión disponible en general. Microsoft Intune también puede buscar aplicaciones de las tiendas de aplicaciones. Utilice uno de los siguientes enlaces para instalar la aplicación desde una tienda de aplicaciones:

- **Windows (UWP):** [Gestión de almacenes en Microsoft Store](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Gestión de almacenes en Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Descargue la aplicación desde Microsoft App Center

Como alternativa a la instalación desde una tienda de aplicaciones, puede descargar la aplicación desde Microsoft App Center. El App Center proporciona paquetes instalables que puede descargar. Además de la versión actual, App Center también le permite descargar versiones anteriores y puede proporcionar versiones de vista previa con las próximas funciones que puede probar. Para descargar versiones actuales, anteriores o de vista previa de la aplicación móvil Warehouse Management desde Microsoft App Center, utilice uno de los siguientes enlaces:

- **Windows (UWP):** [Gestión de almacenes (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    Para obtener instrucciones sobre cómo instalar un paquete descargado en un dispositivo Windows y luego configurar los certificados necesarios, consulte [Instalar una compilación desde App Center](/appcenter/distribution/installation).

- **Android:** [Warehouse Management (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Si descarga una versión en vista previa, se requieren algunos pasos adicionales para instalarla. Para obtener más detalles, consulte [Probar aplicaciones Android](/appcenter/distribution/testers/testing-android).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Crear una aplicación de servicio web en Azure Active Directory

Para habilitar la aplicación móvil Warehouse Management para interactuar con un servidor específico de Supply Chain Management, debe registrar una aplicación de servicio web para el inquilino de Supply Chain Management en Azure Active Directory (Azure AD). El siguiente procedimiento muestra una manera de completar una tarea. Para obtener información detallada y alternativas, consulte los vínculos tras el procedimiento.

1. En un explorador web, vaya a [https://portal.azure.com](https://portal.azure.com/).
1. Especifique el nombre y la contraseña del usuario que tiene acceso a la suscripción de Azure.
1. En el portal de Azure, en el panel de navegación izquierdo, seleccione **Azure Active Directory**.

    ![Azure Active Directory.](media/app-connect-azure-aad.png "Azure Active Directory")

1. Asegúrese de estar trabajando con la instancia de Azure AD que utilice Supply Chain Management.
1. En la lista **Administrar**, seleccione **Registros de aplicación**.

    ![Registros de aplicación.](media/app-connect-azure-register.png "Registros de aplicación")

1. En la barra de herramientas, seleccione **Nuevo registro** para abrir el asistente **Registrar una solicitud**.
1. Escriba un nombre para la aplicación, seleccione la opción **Solo cuentas en el directorio de esta organización** y luego elija **Registrar**.

    ![Asistente de Registrar una aplicación.](media/app-connect-azure-register-wizard.png "Asistente de Registrar una aplicación")

1. Se abre su nuevo registro de aplicación. Anote el valor de **Id. de aplicación (cliente)**, puesto que lo necesitará más adelante. Este id. se referirá más adelante en este tema como *Id. de cliente*.

    ![Identificador de aplicación (cliente).](media/app-connect-azure-app-id.png "Id. de aplicación (cliente)")

1. En la lista **Administrar**, seleccione **Certificado y secretos**. Luego, seleccione uno de los siguientes botones, según cómo desee configurar la aplicación para la autenticación. (Para obtener más información, consulte la sección [Autenticar usando un certificado o secreto de cliente](#authenticate), más adelante en este tema).

    - **Cargar certificado**: cargue un certificado para usarlo como secreto. Recomendamos este enfoque, porque es más seguro y también se puede automatizar más completamente. Si está ejecutando la aplicación móvil Warehouse Management en dispositivos Windows, anote el valor de **Huella digital** que se muestra después de cargar el certificado. Necesitará este valor cuando configure el certificado en dispositivos Windows.
    - **Nuevo secreto de cliente**: cree una clave introduciendo una descripción de clave y una duración en la sección **Contraseñas** y luego seleccione **Añadir**. Haga una copia de la clave y guárdela de forma segura.

    ![Certificado y secretos.](media/app-connect-azure-authentication.png "Certificado y secretos")

Para obtener más información sobre cómo configurar aplicaciones de servicios web en Azure AD, vea los siguientes recursos:

- Para obtener instrucciones que muestran cómo usar Windows PowerShell para configurar aplicaciones de servicio web en Azure AD, consulte [Procedimiento: usar Azure PowerShell para crear una entidad de servicio con un certificado](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Para obtener detalles completos sobre cómo crear manualmente una aplicación de servicio web en Azure AD, vea los siguientes temas:

    - [Inicio rápido: registrar una aplicación en la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app)
    - [Procedimiento: usar el portal para crear una aplicación de Azure AD y entidad de servicio que puede acceder a los recursos](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Cree y configure una cuenta de usuario en Supply Chain Management.

Para permitir que Supply Chain Management use su aplicación Azure AD, siga estos pasos.

1. Cree un usuario correspondiente a las credenciales de usuario de la aplicación móvil Warehouse Management:

    1. En Supply Chain Management, vaya a **Administración del sistema \> Usuarios \> Usuarios**.
    1. Crear un usuario.
    1. Asigne el usuario del dispositivo móvil de almacenamiento.

    ![Asigne el usuario del dispositivo móvil de almacenamiento.](media/app-connect-app-users.png "Asignar el usuario del dispositivo móvil de almacenamiento")

1. Asocie su aplicación Azure AD con el usuario de la aplicación móvil Warehouse Management:

    1. Vaya a **Administración del sistema \> Configuración \> Aplicaciones de Azure Active Directory**.
    1. Crear una línea.
    1. Introduzca la ID de cliente que anotó en la sección anterior, asígnele un nombre y seleccione el usuario que acaba de crear. Se reomienda etiquetar todos los dispositivos. Luego, si un dispositivo se pierde, puede eliminar fácilmente su acceso a Supply Chain Management desde esta página.

    ![Aplicaciones de Azure Active Directory.](media/app-connect-aad-apps.png "Aplicaciones de Azure Active Directory")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Autenticar usando un certificado o secreto de cliente

La autenticación con Azure AD proporciona una forma segura de conectar un dispositivo móvil a Supply Chain Management. Puede autenticar usando un secreto de cliente o un certificado. Si va a importar la configuración de conexión, le recomendamos que use un certificado en lugar de un secreto de cliente. Debido a que el secreto del cliente siempre debe almacenarse de forma segura, no puede importarlo desde un archivo de configuración de conexión o un código QR, como se describe más adelante en este tema.

Los certificados se pueden usar como secretos para probar la identidad de la aplicación cuando se solicita un token. La parte pública del certificado se carga en el registro de la aplicación en Azure Portal, mientras que el certificado completo debe implementarse en cada dispositivo donde está instalada la aplicación móvil Warehouse Management. Su organización es responsable de administrar el certificado en términos de rotación, etc. Puede usar certificados autofirmados, pero siempre debe usar certificados no exportables.

Debe hacer que el certificado esté disponible localmente en cada dispositivo donde ejecute la aplicación móvil Warehouse Management. Para obtener información sobre cómo administrar certificados para dispositivos controlados por Intune si está usando Intune, consulte [Usar certificados para autenticación en Microsoft Intune](/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Configurar la aplicación importando la configuración de conexión

Para facilitar el mantenimiento y la implementación de la aplicación en muchos dispositivos móviles, puede importar la configuración de conexión en lugar de Introducirla manualmente en cada dispositivo. Esta sección explica cómo crear e importar la configuración.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Crear un archivo de configuración de conexión o un código QR

Puede importar la configuración de conexión desde un archivo o un código QR. Para ambos enfoques, primero debe crear un archivo de configuración que utilice el formato y la sintaxis de anotación de objetos de JavaScript (JSON). El archivo debe incluir una lista de conexiones que contenga las conexiones individuales que deben agregarse. La siguiente tabla resume los parámetros que debe especificar en el archivo de configuración de conexión.

| Parámetro | Descripción |
|---|---|
| ConnectionName | Especifique el nombre de la configuración de conexión. La longitud máxima es de 20 caracteres. Dado que este valor es el identificador único de una configuración de conexión, asegúrese de que sea único en la lista. Si ya existe una conexión con el mismo nombre en el dispositivo, la configuración del archivo importado la anulará. |
| ActiveDirectoryClientAppId | Especifica el id. de cliente que anotó mientras estaba configurando Azure AD en la sección [Crear una aplicación de servicio web en Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Especifique la URL raíz de Supply Chain Management. |
| ActiveDirectoryTenant | Especifica el inquilino de Azure AD que está utilizando con el servidor de Supply Chain Management. Este valor tiene la forma `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Este es un ejemplo: `https://login.windows.net/contosooperations.onmicrosoft.com`. |
| Compañía | Especifique la entidad jurídica en Supply Chain Management a la que desea que se conecte la aplicación. |
| ConnectionType | (Opcional) Especifique si la configuración de conexión debe usar un certificado o un secreto de cliente para conectarse a un entorno. Los valores válidos son *"certificate"* y *"clientsecret"*. El valor predeterminado es *"certificate"*.<p>**Nota:** los secretos de cliente no pueden importarse.</p> |
| IsEditable | (Opcional) Especifica si el usuario de la aplicación debería poder editar la configuración de conexión. Los valores válidos son *"verdadero"* y *"falso"*. El valor predeterminado es *"verdadero"*. |
| IsDefault | (Opcional) Especifica si la conexión es la conexión predeterminada. Una conexión que se establece como conexión predeterminada se preseleccionará automáticamente cuando se abra la aplicación. Sólo puede establecerse una conexión como conexión predeterminada. Los valores válidos son *"verdadero"* y *"falso"*. El valor predeterminado es *"falso"*. |
| CertificateThumbprint | (Opcional) Para dispositivos Windows, puede especificar la huella digital del certificado para la conexión. Para dispositivos Android, el usuario de la aplicación debe seleccionar el certificado la primera vez que se utiliza una conexión. |

El siguiente ejemplo muestra un archivo de configuración de conexión válido que contiene dos conexiones. Como puede ver, la lista de conexiones (denominada *"ConnectionList"* en el archivo) es un objeto que tiene una matriz que almacena cada conexión como un objeto. Cada objeto debe estar entre llaves ({}) y separado por comas, y la matriz debe estar entre corchetes (\[\]).

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Puede guardar la información como un archivo JSON o generar un código QR que tenga el mismo contenido. Si guarda la información como un archivo, le recomendamos que la guarde utilizando el nombre predeterminado, *connections.json*, especialmente si lo almacenará en la ubicación predeterminada en cada dispositivo móvil.

### <a name="save-the-connection-settings-file-on-each-device"></a>Guardar el archivo de configuración de conexión en cada dispositivo

Por lo general, utilizará una herramienta de administración de dispositivos o un script para distribuir los archivos de configuración de conexión a cada dispositivo que esté administrando. Si utiliza el nombre y la ubicación predeterminados cuando guarda el archivo de configuración de conexión en cada dispositivo, la aplicación móvil Warehouse Management los importará automáticamente, incluso durante la primera ejecución después de instalar la aplicación. Si usa un nombre o ubicación personalizados para el archivo, el usuario de la aplicación debe especificar los valores durante la primera ejecución. Sin embargo, la aplicación continuará usando después el nombre y la ubicación especificados.

Cada vez que se inicia la aplicación, vuelve a importar la configuración de conexión desde su ubicación anterior para determinar si ha habido algún cambio. La aplicación actualizará solo las conexiones que tengan los mismos nombres que las conexiones en el archivo de configuración de conexión. Las conexiones creadas por el usuario que usan otros nombres no se actualizarán.

No puede eliminar una conexión utilizando el archivo de configuración de conexión.

Como se ha mencionado, el nombre de archivo predeterminado es *connections.json*. La ubicación predeterminada del archivo depende de si está utilizando un dispositivo Windows o un dispositivo Android:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

Por lo general, las rutas se crean automáticamente después de la primera ejecución de la aplicación. Sin embargo, puede crearlos manualmente si debe transferir el archivo de configuración de conexión al dispositivo antes de la instalación.

> [!NOTE]
> Si se desinstala la aplicación, se eliminan la ruta predeterminada y sus contenidos.

### <a name="import-the-connection-settings"></a>Importar la configuración de conexión

Siga estos pasos para importar la configuración de conexión desde un archivo o un código QR.

1. Inicie la aplicación móvil Warehouse Management en su dispositivo móvil. La primera vez que inicie la aplicación, se mostrará un mensaje de bienvenida. Seleccione **Seleccionar una conexión**.

    ![Mensaje de bienvenida.](media/app-configure-welcome-screen.png "Mensaje de bienvenida")

1. Si está importando la configuración de conexión de un archivo, es posible que la aplicación ya haya encontrado el archivo si el nombre predeterminado y la ubicación predeterminada se usaron cuando se guardó. En este caso, continúe con el paso 4. De lo contrario, seleccione **Configurar conexión** y luego continúe con el paso 3.

    ![Configurar conexión.](media/app-configure-set-up-connection.png "Configurar conexión")

1. En el cuadro de diálogo **Configuración de la conexión**, seleccione **Agregar desde archivo** o **Agregar desde código QR**, dependiendo de cómo desee importar la configuración:

    - Si está importando la configuración de conexión desde un archivo, seleccione **Agregar desde archivo**, busque el archivo en su dispositivo local y selecciónelo. Si selecciona una ubicación personalizada, la aplicación la almacenará y la usará automáticamente la próxima vez.
    - Si está importando la configuración de conexión escaneando un código QR, seleccione **Añadir desde código QR**. La aplicación le solicita permiso para usar la cámara del dispositivo. Después de otorgar el permiso, se inicia la cámara para que pueda usarla para escanear. Dependiendo de la calidad de la cámara del dispositivo y la complejidad del código QR, es posible que le resulte difícil obtener un escaneo correcto. En ese caso, intente reducir la complejidad del código QR generando solo una conexión por código QR. (Actualmente, solo puede usar la cámara del dispositivo para escanear el código QR).

    ![Menú de configuración de conexión.](media/app-configure-connection-setup-flyout.png "Menú de configuración de conexión")

1. Cuando los ajustes de conexión se cargan correctamente, se muestra la conexión seleccionada.

    ![Configuración de conexión cargada.](media/app-configure-select-connection.png "Configuración de conexión cargada")

1. Si estás usando un dispositivo Android y utiliza un certificado para la autenticación, el dispositivo le solicita que seleccione el certificado.

    ![Seleccione la solicitud de certificado en un dispositivo Android.](media/app-configure-select-certificate.png "Seleccione la solicitud de certificado en un dispositivo Android")

1. La aplicación se conecta a su servidor de Supply Chain Management y muestra la página de inicio de sesión.

    ![Página de inicio de sesión.](media/app-configure-sign-in-page.png "Página de inicio de sesión")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Configurar manualmente la aplicación

Si no dispone de un archivo o de un código QR, puede configurar la aplicación manualmente en el dispositivo para que se conecte al servidor Supply Chain Management a través de la aplicación Azure AD.

1. Inicie la aplicación móvil Warehouse Management en su dispositivo móvil.
1. Si la aplicación se inicia en **Modo de demostración**, seleccione **Configuraciones de conexión**. Si aparece la página **Iniciar sesión** cuando se inicia la aplicación, seleccione **Cambiar conexión**.
1. Seleccione **Configurar conexión**.

    ![Configurar conexión.](media/app-configure-set-up-connection.png "Configurar conexión")

1. Seleccione **Introducir manualmente**.

    ![Menú de configuración de conexión.](media/app-configure-connection-setup-flyout.png "Menú de configuración de conexión")

    Aparece la página **Nueva conexión** y muestra la configuración necesaria para Introducir manualmente los detalles de la conexión.

    ![Campos de conexión manual.](media/app-configure-input-manually.png "Campos de conexión manual")

1. Especifique la siguiente información:

    - **Usar secreto del cliente**: establezca esta opción en _Sí_ para usar un secreto de cliente para autenticarse con Supply Chain Management. Establezca en _No_ para usar un certificado para la autenticación. (Para obtener más información, consulte la sección [Crear una aplicación de servicio web en Azure Active Directory](#create-service) que aparece más arriba en este tema.)
    - **Nombre de la conexión**: introduzca un nombre para la nueva conexión. Este nombre aparecerá en el campo **Seleccionar conexión** la próxima vez que abra la configuración de conexión. El nombre que introduzca debe ser único. (En otras palabras, debe diferir de todos los demás nombres de conexión que están almacenados en su dispositivo, si hay otros nombres de conexión almacenados allí.)
    - **Id. de cliente de Active Directory**: introduzca el id. de cliente que anotó mientras estaba configurando Azure AD en la sección [Crear una aplicación de servicio web en Azure Active Directory](#create-service).
    - **Secreto del cliente de Active Directory**: este campo solo está disponible cuando la opción **Usar secreto del cliente** está establecida en _Sí_. Introduzca el secreto de cliente que anotó mientras estaba configurando Azure AD en la sección [Crear una aplicación de servicio web en Azure Active Directory](#create-service).
    - **Huella digital del certificado de Active Directory**: este campo solo está disponible para dispositivos Windows y solo cuando la opción **Usar secreto del cliente** está establecida en _No_. Introduzca la huella digital del certificado que anotó mientras estaba configurando Azure AD en la sección [Crear una aplicación de servicio web en Azure Active Directory](#create-service).
    - **Recurso de Active Directory**: especifique la URL raíz de Supply Chain Management.

        > [!IMPORTANT]
        > No termine este valor con una barra inclinada (/).

    - **Inquilino de Active Directory**: introduca el inquilino de Azure AD que usa con el servidor de Supply Chain Management. Este valor tiene la forma `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Este es un ejemplo: `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!IMPORTANT]
        > No termine este valor con una barra inclinada (/).

    - **Empresa**: especifique la entidad jurídica (empresa) en Supply Chain Management a la que desea que se conecte la aplicación.

1. Seleccione el botón **Guardar** de la esquina superior derecha de la página.
1. Si estás usando un dispositivo Android y utiliza un certificado para la autenticación, el dispositivo le solicita que seleccione el certificado.
1. La aplicación se conecta a su servidor de Supply Chain Management y muestra la página de inicio de sesión.

## <a name="remove-access-for-a-device"></a>Quitar el acceso de un dispositivo

Si un dispositivo está perdido o defectuoso, debe quitar el acceso a Supply Chain Management de dicho dispositivo. Los siguientes pasos describen el proceso recomendado para la retirada de acceso.

1. Vaya a **Administración del sistema \> Configuración \> Aplicaciones de Azure Active Directory**.
1. Elimine la línea correspondiente al dispositivo al que desea eliminar el acceso. Anote el id. del cliente que se utiliza para el dispositivo, porque lo necesitará más adelante.

    Si ha registrado solo un id. de cliente, y varios dispositivos usan el mismo id. de cliente, debe enviar nuevas configuraciones de conexión a esos dispositivos. De lo contrario, perderán el acceso.

1. Inicie sesión en el portal Azure en [https://portal.azure.com](https://portal.azure.com/).
1. En el panel de navegación izquierdo, seleccione **Active Directory** y asegúrese de estar en el directorio correcto.
1. En la lista **Administrar**, seleccione **Registros de aplicación** y, a continuación, seleccione la aplicación que desea configurar. La página **Configuración** aparecerá y mostrará la información de configuración.
1. Asegúrese de que el id. de cliente de la aplicación coincida con el id. de cliente que anotó en el paso 2.
1. En la barra de herramientas, seleccione **Eliminar**.
1. En el mensaje de confirmación que aparece, haga clic en **Sí**.

## <a name="additional-resources"></a>Recursos adicionales

- [Configuración de usuario del dispositivo móvil](mobile-device-user-settings.md)
- [Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management](step-icons-titles.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]