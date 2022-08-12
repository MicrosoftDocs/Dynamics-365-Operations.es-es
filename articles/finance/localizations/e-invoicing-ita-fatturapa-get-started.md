---
title: Configurar la integración directa de FatturaPA italiana con SDI
description: Este artículo proporciona información que lo ayudará a comenzar con la facturación electrónica para Italia y configurar la integración directa de FatturaPA italiana con el sistema Exchange (SDI).
author: abaryshnikov
ms.date: 07/27/2022
ms.topic: article
audience: Application User, Developer
ms.reviewer: kfend
ms.search.region: Global
ms.author: abaryshnikov
ms.search.validFrom: 2021-10-18
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 363b7b5e3d5abbb990fea8f8ad4d0c1bebf80102
ms.sourcegitcommit: 6d9fcb52d723ac5022a3002e0ced8e7b56e9bc2a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "9203181"
---
# <a name="set-up-direct-integration-of-italian-fatturapa-with-sdi"></a>Configurar la integración directa de FatturaPA italiana con SDI

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Es posible que la facturación electrónica para Italia no admita actualmente todas las funciones que están disponibles para las facturas electrónicas en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.

Este artículo proporciona información que le ayudará a comenzar con la facturación electrónica para Italia en Finance y Supply Chain Management. Le guía a través de los pasos de configuración que dependen del país o la región en Regulatory Configuration Services (RCS). Estos pasos complementan los pasos que se describen en [Empiece a utilizar la facturación electrónica](e-invoicing-get-started.md).

## <a name="prerequisites"></a>Requisitos previos

Antes de que pueda completar los pasos en este artículo, debe completar los siguientes requisitos previos:

- Complete los pasos de [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started.md).
- Importe la función de facturación electrónica **FatturaPA italiana (IT)** en RCS desde el repositorio global. Para obtener más información, consulte la sección [Importar una función de facturación electrónica del proveedor de configuración de Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider) del artículo "Introducción a la facturación electrónica" mencionado anteriormente.
- Agregue enlaces de los certificados necesarios al entorno de servicio. Los certificados necesarios incluyen el certificado de firma digital, el certificado de autoridad certificadora (CA) y el certificado de clientes. Para obtener más información, vea la sección [Cree un secreto de certificado digital](e-invoicing-get-started-service-administration.md#create-a-digital-certificate-secret) del artículo "Comenzar con la administración del servicio de facturación electrónica".

## <a name="country-specific-configuration-for-the-italian-fatturapa-it-electronic-invoicing-feature"></a>Configuración específica del país para la función de facturación electrónica italiana FatturaPA (IT)

Complete los procedimientos siguientes antes de implementar la configuración de la aplicación en su aplicación conectada de Finance o Supply Chain Management.

Esta sección complementa la sección [Configuración específica del país para la instalación de la aplicación](e-invoicing-get-started.md#country-specific-configuration-of-application-setup) en el artículo "Comenzar con la facturación electrónica".

### <a name="create-a-new-feature"></a>Crear una nueva característica

1. Inicie sesión en RCS.
2. En el espacio de trabajo **Informes electrónicos**, en **Proveedores de configuración**, marque el proveedor de configuración de su empresa como activo.
3. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
4. Sobre la página **Funciones de facturación electrónica**, seleccione **Agregar** \> **Basado en una característica existente**.
5. Bajo **Proveedor de configuración de Microsoft**, seleccione **FatturaPA italiana (IT)** como función base, ingrese un nombre y luego seleccione **Crear característica**.

### <a name="set-up-application-specific-parameters"></a>Configurar parámetros específicos de la aplicación

1. Sobre la página **Funciones de facturación electrónica**, seleccione la función para editar.
2. En la pestaña **Versiones**, verifique que esté seleccionada la versión **Borrador**.
3. En la pestaña **Configuraciones**, seleccione una configuraión y luego **Parámetros específicos de la aplicación**.
4. En la sección **Búsquedas**, asegúrese de que la búsqueda **Lista de subcategorías de inversión del sujeto pasivo Natura** está seleccionada.
5. En la sección **Condiciones**, seleccione **Agregar**.
6. Agregue condiciones específicas para cada subcategoría definida en el sistema y luego guarde los cambios.

    > [!NOTE]
    > En la columna **Nombre**, puede seleccionar el valor **\*Blanco\*** o **\*No en blanco\*** del marcador de posición en lugar de un valor específico.

### <a name="configure-a-processing-pipeline-for-export"></a>Configurar una canalización de procesamiento para la exportación

1. Sobre la página **Funciones de facturación electrónica**, seleccione la función para editar.
2. En la pestaña **Configuraciones**, seleccione **Facturas de ventas** y luego seleccione **Editar**.
3. En la sección **Canalización de procesamiento**, revise las acciones y configure todos los campos obligatorios:

    - Para la acción **Firmar documento**, en el campo **Nombre del certificado**, especifique el Certificado de firma digital.
    - Para la acción **Entregar**, establezca los campos **Dirección URL** y **Certificados**. El valor del campo **Certificados** es una cadena de certificados, el primero de los cuales es el certificado de CA raíz (caentrate.cer) y el segundo es el certificado de Clientes.

4. En la sección **Reglas de aplicabilidad**, revise las cláusulas y revise o establezca los campos obligatorios:
    - Revise la cláusula **LegalEntityID** y actualice con el valor correcto de su entidad legal.

5. Seleccione **Validar** para asegurarse de que se hayan configurado todos los campos obligatorios.
6. Guarde los cambios y cierre la página.
7. En la pestaña **Configuraciones**, seleccione **Facturas de proyectos** y luego seleccione **Editar**.
8. Repita los pasos del 3 al 6 para las facturas del proyecto.

### <a name="configure-the-processing-pipeline-for-import"></a>Configurar la canalización de procesamiento para la importación

1. Sobre la página **Funciones de facturación electrónica**, seleccione la función para editar.
2. En la pestaña **Configuraciones**, seleccione **Importar facturas** y luego seleccione **Editar**.
3. En la sección **Canal de datos** de la pestaña **Parámetros**, en el campo **Canal de datos**, ingrese un valor de cadena.
4. Sobre la pestaña **Reglas de aplicabilidad**, establezca los campos para la configuración. Puede usar la cláusula predeterminada de **Canal** cláusula pasando el valor que establezca para el campo **Canal de datos** en el paso anterior al campo **Valor**.

    ![Configurar reglas de aplicabilidad.](media/e-invoicing-ita-fatturapa-get-started-apprules-setup.png)

5. Seleccione **Validar** para asegurarse de que se hayan configurado todos los campos obligatorios.

### <a name="deploy-the-feature"></a>Implementar la característica

1. Complete, publique e implemente la característica en el entorno del servicio. Para obtener más información, consulte la sección [Implementar la función de facturación electrónica en el entorno de servicio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment) del artículo "Introducción a la facturación electrónica".
2. Implemente la función en la la aplicación conectada. Para obtener más información, consulte la sección [Implementar la función de facturación electrónica en la aplicación conectada](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-connected-application) del artículo "Introducción a la facturación electrónica".

### <a name="set-up-finance"></a>Configurar Finance

1. Inicie sesión en su entorno de Finance.
2. En el espacio de trabajo **Informes electrónicos**, en la sección **Proveedores de configuración**, seleccione el icono **Microsoft**.
3. Seleccione **Repositorios** \> **Global** \> **Abrir**.
4. Seleccione e importe las configuraciones de **Modelo de contexto de factura de cliente** e **Importación de facturas de proveedores (IT)**.
5. Vaya a **Administración de la organización** \> **Configuración** \> **Parámetros de documentos electrónicos**.
6. Sobre la pestaña **Características**, busque y seleccione la función **Factura electrónica italiana** y, a continuación, seleccione la casilla **Permitir**.
7. Sobre la pestaña **Documento electronico**, asegúrese de que los campos para **Diario de facturas del cliente** y **Factura del proyecto** se establecen de acuerdo con la información en [Configurar la instalación de la aplicación](e-invoicing-get-started.md#configure-the-application-setup).

### <a name="set-up-vendor-invoice-import"></a>Configurar importación de factura de proveedor 

1. En Finance, en el espacio de trabajo **Informes electrónicos**, en **Proveedores de configuración**, marque el proveedor de configuración de su empresa como activo.
2. Seleccione **Configuraciones de informes**.
3. Seleccione **Modelo de contexto de factura de cliente** y luego seleccione **Crear configuración**.
4. Seleccione **Derivar del nombre: contexto de factura de cliente, Microsoft** para crear una configuración derivada.
5. En la versión **Borrador**, seleccione **Diseñador**.
6. En el árbol **Modelo de datos**, seleccione **Asignar modelo a origen de datos**.
7. En el árbol **Definiciones**, seleccione **DataChannel** y luego seleccione **Diseñador**.
8. En el árbol **Fuentes de datos**, expanda el contenedor **\$Context\_Channel**.
9. En el campo **Valor**, seleccione **Editar**. 
10. Especifique el nombre del canal de datos. El nombre debe tener un máximo de 10 caracteres. Debe coincidir con el valor del parámetro **Canal de datos** del canal de datos para la función de facturación electrónica en RCS.
11. Guarde sus cambios y luego vaya a **Configuraciones de informes** \> **Versión de configuración completa**.
12. En la pestaña **Canales externos**, en la sección **Canales**, seleccione **Agregar**.
13. En el campo **Canal**, ingrese el valor **\$Canal de contexto**.
14. Escriba valores en los campos **Descripción** y **Empresa**.
15. En el campo **Contexto del documento**, seleccione la nueva configuración que derivó del **Modelo de contexto de factura de cliente**. La descripción del mapeo debe ser **Contexto del canal de datos**.
16. En la pestaña **Orígenes de importación**, seleccione **Agregar** y, a continuación, establezca los siguientes valores:

    - **Nombre:** OutputFile
    - **Nombre de la entidad de datos:** Encabezado de la factura del proveedor (**Entidad de datos:** VendorInvoiceHeaderEntity)
    - **Mapeo de modelos:** Importación de facturas de proveedores (IT)

> [!NOTE]
> Si tiene facturas de proveedores de importación de diferentes fuentes, puede crear varios canales externos y varias configuraciones derivadas que tienen diferentes valores de **\$Canal de contexto**. Por ejemplo, es posible que desee importar facturas de proveedores para distintas entidades legales.

## <a name="proxy-server-setup"></a>Configuración del servidor proxy

Esta sección proporciona información que le ayudará a instalar y configurar el servicio de proxy para la comunicación entre el sistema Exchange (SDI) y el servicio de facturación electrónica.

### <a name="create-an-app-registration"></a>Crear un registro de aplicación

1. Utilice el siguiente script de Windows PowerShell para crear un certificado autofirmado para la autenticación de servicio a servicio (S2S).

    ```powershell
    $certOutputLocation = "C:\certs\proxytest"
    $certName = "sdiProxyClientS2SCert"
    $certPassword = "123"

    $certCerFile = Join-Path $certOutputLocation "$certName.cer"
    $certPfxFile = Join-Path $certOutputLocation "$certName.pfx"

    $securePassword = ConvertTo-SecureString $certPassword -AsPlainText -Force

    $cert = New-SelfSignedCertificate -KeyLength 2048 -KeyExportPolicy Exportable -FriendlyName "CN=$certName" -CertStoreLocation Cert:\CurrentUser\My -Subject $certName -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider"

    Export-Certificate -Cert $cert -FilePath $certCerFile -type CERT | Out-Null
    Export-PfxCertificate -Cert $cert -FilePath $certPfxFile -Password $securePassword | Out-Null
    ```

2. Guarde el archivo de certificado .pfx en el almacén de claves y luego elimine la copia local.
3. Inicie sesión en el [portal de Azure](https://portal.azure.com) como administrador.
4. Cree un registro de aplicación para el servicio SDI Proxy.

    1. Vaya a **Registros de aplicaciones**, cree un registro y luego establezca los siguientes valores para él:

        - **Nombre:** Cliente proxy SDI
        - **Tipos de cuenta admitidos:** Cuentas en este directorio organizativo únicamente (inquilino único)

    2. Seleccione **Registrarse** y luego seleccione el registro de la aplicación que acaba de crear.
    3. Vaya a **Permisos de la API** y seleccione **Otorgar consentimiento de administrador**.
    4. Vaya a **Certificados y secretos**, seleccione **Cargar certificado** y cargue el archivo de certificado .cer para la autenticación S2S.
    5. Vaya a **Aplicaciones empresariales** y seleccione la aplicación que creó.
    6. Guarde los valores **ID de aplicación** (ID de cliente) e **ID de objeto** para la aplicación.
    7. El equipo del Servicio de facturación debe otorgar acceso al servicio a la aplicación. Envíe los valores de los siguientes parámetros a <D365EInvoiceSupport@microsoft.com>:

        - Id. de suscriptor AAD
        - Id. de entorno LCS
        - Id. de aplicación
        - Id. de objeto

5. En RCS, agregue la aplicación a la lista de aplicaciones del entorno de servicio.

    1. Vaya a **Funciones de globalización** \> **Ambientes** \> **Facturacion electronica** \> **Entornos de servicio** y seleccione su entorno.
    2. En la sección **Aplicaciones**, agregue una fila a la cuadrícula e ingrese el nombre y el ID de objeto de la aplicación.

        ![Agregar la aplicación al entorno de servicio.](media/e-invoicing-ita-fatturapa-get-started-add-app-to-env.png)

    3. Seleccione **Guardar** y, a continuación, seleccione **Publicar**.

### <a name="create-an-azure-virtual-machine"></a>Crear una máquina virtual de Azure

1. En el [portal de Azure](https://portal.azure.com), vaya a **Máquinas virtuales** y luego seleccione **Crear nueva**.
2. En la pestaña **Lo esencial**, seleccione su suscripción y grupo de recursos. Los valores deben ser la suscripción y el grupo de recursos donde se encuentran su almacén de claves y Blob Storage.
3. Seleccione la región. Este valor debe ser la región donde se implementa su entorno de finanzas.
4. Agregue el nombre de usuario y la contraseña del administrador y guárdelos en el almacén de claves.
5. En el campo **Seleccionar puertos entrantes**, seleccione **HTTPS (443)** y **RPD (3389)**.

    > [!NOTE]
    > Le recomendamos que desactive el puerto **RDP (3389)** puerto cuando el sistema pasa a producción. Puede volver a habilitarlo si debe conectarse a la máquina virtual (VM) para solucionar problemas.

    ![Establecer los campos en la pestaña Conceptos básicos para crear una máquina virtual de Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-1.png)

6. En la pestaña **Discos**, en la ficha desplegable **Avanzado**, seleccione la casilla **Usar discos administrados**. Deje la casilla **Disco de SO efímero** desactivada.

    ![Establezcar los campos en la pestaña Discos para crear una máquina virtual de Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-2.png)

7. Sobre la pestaña **Redes**, debajo del campo **IP pública**, seleccione **Crear nuevo**.

    ![Establezca los campos en la pestaña Redes para crear una máquina virtual de Azure.](media/e-invoicing-ita-fatturapa-get-started-create-vm-3.png)

8. En el cuadro de diálogo **Crear dirección IP pública**, en el grupo de campos **SKU**, seleccione la opción **Estándar**. En el grupo de campos **Asignación**, seleccione la opción **Estático**.

    ![Creando una dirección IP pública.](media/e-invoicing-ita-fatturapa-get-started-create-vm-4.png)

9. En la pestaña **Gestión**, desactive la casilla **Apagado automatico** para deshabilitar el apagado automático.
10. Establezca el campo **Actualizaciones del sistema operativo invitado** en **Manual** y, a continuación, establezca otras políticas.
11. Revise y cree la VM.
12. En la nueva VM, vaya a **Identidad** \> **Sistema asignado** y establezca la opción **Estado** en **Activado**.
13. Otorgue acceso a la máquina virtual al almacén de claves.

    1. En el almacén de claves, vaya a **Control de acceso (IAM)** \> **Asignaciones de roles**.
    2. Seleccione **Agregar asignaciń de roles** y luego configure los siguientes campos:

        1. En el campo **Papel**, especifique **Usuario de Key Vault Secrets**.
        2. En el campo **Asignar acceso a**, especifique **Máquina virtual**.
        3. En el campo **Suscripción**, especifique su suscripción.
        4. En el campo **Seleccionar**, especifique su VM.

    3. Vaya a **Directivas de acceso**.
    4. Seleccione **Agregar directiva de acceso** y luego configure los siguientes campos:

        1. En el campo **Entidad de seguridad seleccionada**, seleccione su VM.
        2. En la sección **Certificado**, seleccione los permisos **Lista** y **Obtener**.

14. En el [Portal de Azure](https://portal.azure.com), vaya a **Direcciones IP públicas** y seleccione la dirección IP que se creó en la máquina virtual.
15. Vaya a **Configuración** y configure el nombre del Sistema de nombres de dominio (DNS).

### <a name="prepare-the-proxy-service-environment"></a>Preparar el entorno del servicio proxy

Siga estos pasos en la máquina donde está alojado el servicio de proxy.

1. Conéctese a la máquina virtual mediante Conexión a escritorio remoto.
2. Abra el complemento Certificado de máquina local. Para más información, vea [Cómo: ver certificados con el complemento MMC](/dotnet/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in).
3. Importe el certificado de producción **caentrate.cer** y **CAEntratetest.cer** para realizar pruebas en la [Tienda de autoridades de certificación raíz de confianza](/dotnet/framework/wcf/feature-details/working-with-certificates#certificate-stores). (**CAEntratetest.cer** es el certificado de CA raíz proporcionado por la autoridad).
4. En el Panel de control, abra **Activar o desactivar las características de windows** o vaya a **Administrador del servidor** \> **Agregar roles y funciones** para el sistema operativo (SO) del servidor y active las funciones de Internet Information Services (IIS):

    - Herramientas de gestión web
        - Consola de administración de IIS
    - Servicios de World Wide Web
        - Funciones de desarrollo de aplicaciones
            - Extensibilidad de .NET 4.7 (o 4.8)
            - ASP
            - ASP.NET 4.7 (o 4.8)
            - CGI
            - Extensiones ISAPI
            - Filtros ISAPI
        - Funciones HTTP comunes
            - Documento predeterminado
            - Navegación de directorio
            - Errores HTTP
            - Contenido estático
        - Estado y diagnóstico
            - Registro HTTP
            - Seguimiento
        - Funciones de rendimiento
            - Compresión de contenido estático
        - Seguridad
            - Solicitar filtrado

    ![Acivar las características de IIS.](media/e-invoicing-ita-fatturapa-get-started-turnon-features.png)

### <a name="set-up-the-sdi-proxy-service-in-iis"></a>Configurar el servicio de proxy SDI en IIS

1. En Microsoft Dynamics Lifecycle Services (LCS), vaya a la biblioteca de activos compartidos y seleccione el tipo de activo **Paquete de datos**.
2. Busque **Servicio de Facturación Electrónica Sdi Proxy** y descárguelo a la VM.
3. Configure el servicio.

    1. Descomprima la carpeta de archivo **Servicio de Facturación Electrónica Sdi Proxy** que descargó.
    2. En la carpeta **src\\FattureService**, abra el archivo **appsettings.json** y establezca los siguientes parámetros:

        - **KeyVaultUri** - Especifique la dirección de la bóveda de claves que almacena el certificado de cliente para el servicio de facturación.
        - **TenantId** - Especifique el identificador único global (GUID) del inquilino del cliente.
        - **EnvironmentId** - Especifique el ID del entorno LCS.
        - **ClientId** – Especifique el ID de la aplicación del registro de la aplicación de servicios intermedios en el inquilino del cliente.
        - **ClientCertificateName** – especifique el nombre del certificado S2S en el almacén de claves.
        - **SecurityServiceClientOptions.Endpoint** - Especifique la URL del servicio de seguridad.
        - **SecurityServiceClientOptions.Resource** - Especifique el alcance para el que obtener el token.
        - **InvoicingServiceClientOptions.Endpoint** - Especifique el punto final del servicio de facturación. Este valor debe ser el mismo punto final que se usa para RCS y Finance.
        - **InvoicingServiceClientOptions.ServiceEnvironmentId** - Especifique el nombre del entorno de servicio. Este valor debe ser el nombre de su entorno de finanzas.
        - **NotificationsFolder** - Especifique la carpeta en la que guardar los archivos de notificación entrantes.

    3. En el archivo **web.config**, busque la siguiente línea y agregue la huella digital del certificado del servidor proxy.

        `<serviceCertificate findValue="[certificate thumbprint]" storeLocation="LocalMachine" storeName="My" x509FindType="FindByThumbprint">`

        > [!TIP]
        > Cuando el sistema entra en producción, puede cambiar algunos valores en el archivo web.config para ayudar a reducir la cantidad de información de registro que se recopila y ayudar a ahorrar espacio en el disco. En el nodo **\<system.diagnostics\>\<source\>**, cambie el valor de **switchValue** a **Error crítico**. Para obtener más información, vea [Visor de seguimiento de servicios de MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).

4. Abra el Administrador de IIS. En el árbol de la izquierda, permanezca en el nodo raíz. A la derecha, seleccione **Certificados de servidor**.

    ![Selección de certificados de servicio en el Administrador de IIS.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-1.png)

5. Abra el menú y seleccione **Importar**.
6. En el cuadro de diálogo **Importar certificado**, en el campo **Archivo de certificado (.pfx)**, especifique la ruta del archivo .pfx para el certificado del servidor proxy.

    ![Especificar el archivo de certificado del servicio de proxy.](media/e-invoicing-ita-fatturapa-get-started-proxy-cert-2.png)

7. Mantenga seleccionado (o haga clic con el botón derecho) **Sitios** y luego seleccione **Agregar sitio web**.
8. En el cuadro de diálogo **Agregar sitio web**, en el campo **Nombre de sitio** introduzca un nombre para el sitio.
9. En el campo **Camino físico**, apunte a la carpeta **src\\FattureService**.
10. En el campo **Tipo de enlace**, seleccione **https**.
11. En el campo **Nombre de host**, especifique el nombre de host.
12. Deje los campos **dirección IP** y **Puerto** establecidos en los valores predeterminados.
13. Asegúrese de que la casilla **Requerir indicación de nombre de servidor** está desactivada, porque SDI no es compatible con esa tecnología.
14. En el campo **Certificado SSL**, seleccione el certificado del servidor proxy que importó.
15. En el campo **Grupo de aplicaciones**, especifique un grupo para el sitio y anote su nombre (por ejemplo, **SdiAppPool**).

    ![Agregar un sitio web.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-1.png)

16. Una vez que haya terminado de crear el sitio web, abra el menú de **Configuración de SSL**.

    ![Abriendo el menú de Configuración SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-2.png)

17. Seleccione la casilla **Requerir SSL** y luego, en el grupo de campos **Certificados de cliente**, seleccione la opción **Exigir**.

    ![Configurar las opciones de SSL.](media/e-invoicing-ita-fatturapa-get-started-proxy-iis-setup-3.png)

18. Abra **Navegación de directorio** y seleccione **Permitir**.
19. En cualquier navegador web, vaya a **serverDNS/TrasmissioneFatture.svc**. Debe aparecer una página estándar sobre el servicio.

    ![Comprobando el servicio en un navegador.](media/e-invoicing-ita-fatturapa-get-started-proxy-open-browser.png)

20. Cree las siguientes carpetas para almacenar registros y archivos:

    - **C:\\Logs\\** – Almacene los archivos de registro aquí. Estos archivos pueden ser vistos por el [Visor de seguimiento de servicios de MS](/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe).
    - **C:\\Files\\** – Guarde todos los archivos de respuesta aquí.

21. En el Explorador de archivos, conceda **SERVICIO DE RED** e **IIS AppPool\\SdiAppPool** (o **IIS AppPool\\DefaultAppPool** si está utilizando el grupo predeterminado) acceso a las carpetas **Registros** y **Archivos**.

    1. Mantenga seleccionada (o haga clic con el botón derecho) una de las carpetas y luego seleccione **Propiedades**.
    2. En el cuadro de diálogo **Propiedades**, en la pestaña **Seguridad**, seleccione **Editar**.
    3. Agregue los usuarios si no aparecen en la lista.
    4. Repita los pasos 1 a 3 para la otra carpeta.

    ![Agregar permisos al usuario del servicio.](media/e-invoicing-ita-fatturapa-get-started-proxy-add-user.png)

## <a name="privacy-notice"></a>Aviso de privacidad 

Habilitar la función **Factura electrónica italiana** puede requerir que se envíen datos limitados. Estos datos incluyen el número de identificación fiscal de la organización. Un administrador puede habilitar y deshabilitar la función de factura electrónica italiana. Para desactivar la función, siga estos pasos.

1. Vaya a **Administración de la organización** \> **Configuración** \> **Parámetros de documentos electrónicos**.
2. En la pestaña **Características**, seleccione las filas que contienen la función **Factura electrónica italiana** y, a continuación, seleccione **Deshabilitar ahora**.

Los datos que se importan de estos sistemas externos a este servicio en línea de Dynamics 365 están sujetos a nuestra [declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=512132). Para más información, vea la sección "Aviso de privacidad" en la documentación de características específicas de cada país o región.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general sobre facturación electrónica](e-invoicing-service-overview.md)
- [Comenzar con la administración de servicios de facturación electrónica](e-invoicing-get-started-service-administration.md)
- [Comenzar con la facturación electrónica](e-invoicing-get-started.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
