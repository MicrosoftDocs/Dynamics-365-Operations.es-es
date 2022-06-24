---
title: Directrices de implementación para cajas registradoras de Noruega (heredadas)
description: Este artículo es una guía de implementación que muestra cómo habilitar la localización de Microsoft Dynamics 365 Commerce para Noruega.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-2-28
ms.openlocfilehash: 7a6450215f152779428d3b0fd83bf09761e2ad98
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894471"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Directrices de implementación para cajas registradoras de Noruega (heredadas)

[!include [banner](../includes/banner.md)]

Este artículo es una guía de implementación que muestra cómo habilitar la localización de Microsoft Dynamics 365 Commerce para Noruega. La localización consta de varias extensiones de los componentes de Commerce. Por ejemplo, las extensiones le permiten imprimir campos personalizados en recibos, registrar eventos de auditoría adicionales, transacciones de ventas y transacciones de pago en el punto de venta (POS), firmar digitalmente transacciones de ventas e imprimir informes X y Z en formatos locales. Para obtener más información sobre la localización para Noruega, consulte [Funcionalidad de caja registradora para Noruega](./emea-nor-cash-registers.md).

Esta muestra es parte del kit de desarrollo de software (SDK) para minoristas. Para obtener información sobre el SDK, consulte [Kit de desarrollo de software (SDK) al por menor](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Esta muestra consta de extensiones para Commerce Runtime (CRT), Retail Server y POS. Para ejecutar este ejemplo, debe modificar y compilar el CRT, Retail Server y proyectos POS. Le recomendamos que utilice un SDK para minoristas sin modificar para realizar los cambios que se describen en este artículo. También le recomendamos que utilice un sistema de control de fuente, como Microsoft Visual Studio Online (VSO), donde aún no se han cambiado archivos.

> [!NOTE]
> En Commerce 10.0.8 y versiones posteriores, Retail Server se conoce como Commerce Scale Unit. Dado que este artículo se aplica a varias versiones anteriores de la aplicación, *Retail Server* se utiliza en todo el artículo.
>
> Algunos pasos de los procedimientos de este artículo difieren, según la versión de Commerce que esté utilizando. Para obtener más información, vea [Novedades o cambios en Dynamics 365 Retail](../get-started/whats-new.md).

### <a name="using-certificate-profiles-in-commerce-channels"></a>Uso de perfiles de certificado en canales comerciales

En las versiones de Commerce 10.0.15 y posteriores, puede utilizar la característica [Perfiles de certificado definidos por el usuario para tiendas minoristas](./certificate-profiles-for-retail-stores.md) que admite la conmutación por error a fuera de línea cuando las oficinas centrales de Key Vault o Commerce no están disponibles. La característica extiende la característica [Gestionar secretos para canales minoristas](../dev-itpro/manage-secrets.md).

Siga estos pasos para aplicar esta funcionalidad en la extensión CRT.

1. Crear un nuevo proyecto de extensión CRT (tipo de proyecto de biblioteca de clases C#). Utilice las plantillas de muestra del kit de desarrollo de software (SDK) de Retail (RetailSDK\SampleExtensions\CommerceRuntime).

2. Agregue un controlador personalizado para CertificateSignatureServiceRequest en el proyecto SequentialSignatureRegister.

3. Para leer una llamada secreta, `GetUserDefinedSecretCertificateServiceRequest` usando un constructor con el parámetro profileId. Eso hará que la funcionalidad comience a trabajar con la configuración de los perfiles de certificado. Según la configuración, el certificado se recuperará de Azure Key Vault o del almacenamiento de la máquina local.

    ```csharp
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);

    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
    ```

4. Cuando se recupere el certificado, proceda con la firma de datos.

5. Construya el proyecto de ampliación CRT.

6. Copie la biblioteca de clases de salida y péguela en ...\RetailServer\webroot\bin\Ext para la prueba manual.

7. En el archivo CommerceRuntime.Ext.config, actualice la sección de composición de la extensión con la información de la biblioteca personalizada.

## <a name="development-environment"></a>Entorno de desarrollo

Complete estos procedimientos para configurar un entorno de desarrollo para que pueda probar y ampliar la muestra.

### <a name="the-crt-extension-components"></a>Los componentes de la extensión CRT

Los componentes de extensión de CRT se incluyen en los ejemplos de CRT. Para completar los siguientes procedimientos, abra la solución CRT, **CommerceRuntimeSamples.sln**, bajo **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="receiptsnorway-component"></a>Componente ReceiptsNorway

1. Encuentre el proyecto **Runtime.Extensions.ReceiptsNorway** y compílelo.
2. En la carpeta **Extensions.ReceiptsNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.ReceiptsNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio Microsoft Internet Information Services (IIS) Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salespaymenttransext-component"></a>Componente SalesPaymentTransExt

1. Encuentre el proyecto **Runtime.Extensions.SalesPaymentTransExt** y compílelo.
2. En la carpeta **Extensions.SalesPaymentTransExt\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesPaymentTransExt.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="xzreportsnorway-component"></a>Componente XZReportsNorway

1. Encuentre el proyecto **Runtime.Extensions.XZReportsNorway** y compílelo.
2. En la carpeta **Extensions.XZReportsNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.XZReportsNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

# <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>Componente de muestra RegisterAuditEvent

1. Encuentre el proyecto **Runtime.Extensions.RegisterAuditEventSample** y compílelo.
2. En la carpeta **Extensions.RegisterAuditEventSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignature-sample-component"></a>Componente de muestra SalesTransactionSignature

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureSample** y compílelo.
2. Modifique el archivo **App.config** especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas.
3. Compile el proyecto.
4. En la carpeta **Extensions.SalesTransactionSignatureSample\\bin\\Debug**, busque los siguientes archivos:

    - El archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - El archivo de configuración **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copie los archivos a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

6. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

7. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

# <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>Componente de muestra RegisterAuditEvent

1. Encuentre el proyecto **Runtime.Extensions.RegisterAuditEventSample** y compílelo.
2. En la carpeta **Extensions.RegisterAuditEventSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignature-sample-component"></a>Componente de muestra SalesTransactionSignature

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureSample** y compílelo.
2. Modifique el archivo **App.config** especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas.
3. Compile el proyecto.
4. En la carpeta **Extensions.SalesTransactionSignatureSample\\bin\\Debug**, busque los siguientes archivos:

    - El archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - El archivo de configuración **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copie los archivos a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

6. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

7. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignaturesamplemessages-component"></a>Componente SalesTransactionSignatureSample.Messages

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureSample.Messages**.
2. En la carpeta **Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

# <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>Componente de muestra RegisterAuditEvent

1. Encuentre el proyecto **Runtime.Extensions.RegisterAuditEventSample** y compílelo.
2. En la carpeta **Extensions.RegisterAuditEventSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignature-sample-component"></a>Componente de muestra SalesTransactionSignature

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureSample** y compílelo.
2. Modifique el archivo **App.config** especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas.
3. Compile el proyecto.
4. En la carpeta **Extensions.SalesTransactionSignatureSample\\bin\\Debug**, busque los siguientes archivos:

    - El archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - El archivo de configuración **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copie los archivos a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

6. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

7. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. En la carpeta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

# <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>Componente de muestra RegisterAuditEvent

1. Encuentre el proyecto **Runtime.Extensions.RegisterAuditEventSample** y compílelo.
2. En la carpeta **Extensions.RegisterAuditEventSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister**.
2. Modifique el archivo **App.config** especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas.
3. Compile el proyecto.
4. En la carpeta **Extensions.SequentialSignatureRegister\\bin\\Debug**, busque los siguientes archivos:

    - El archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - El archivo de configuración **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copie los archivos a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

6. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

7. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignaturenorway-component"></a>Componente SalesTransactionSignatureNorway

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. En la carpeta **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. En la carpeta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Encuentre el proyecto **Runtime.Extensions.SalesPaymentTransExtNorway** y compílelo.
2. En la carpeta **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

# <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>Componente RegisterAuditEventNorway

1. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

2. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister**.
2. Modifique el archivo **App.config** especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas.
3. Compile el proyecto.
4. En la carpeta **Extensions.SequentialSignatureRegister\\bin\\Debug**, busque los siguientes archivos:

    - El archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - El archivo de configuración **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copie los archivos a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

6. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

7. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignaturenorway-component"></a>Componente SalesTransactionSignatureNorway

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. En la carpeta **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. En la carpeta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Encuentre el proyecto **Runtime.Extensions.SalesPaymentTransExtNorway** y compílelo.
2. En la carpeta **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

# <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>Componente RegisterAuditEventNorway

1. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

2. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister**.
2. Modifique el archivo **App.config** especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas.
3. Compile el proyecto.
4. En la carpeta **Extensions.SequentialSignatureRegister\\bin\\Debug**, busque los siguientes archivos:

    - El archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - El archivo de configuración **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copie los archivos a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

6. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

7. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="salestransactionsignaturenorway-component"></a>Componente SalesTransactionSignatureNorway

1. Encuentre el proyecto **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. En la carpeta **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encuentre el proyecto **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. En la carpeta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Encuentre el proyecto **Runtime.Extensions.SalesPaymentTransExtNorway** y compílelo.
2. En la carpeta **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copie el archivo de ensamblado a la carpeta de extensiones de CRT:

    - **Retail Server:** Copie el ensamblaje en la carpeta **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** Copie el ensamblaje en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.

4. Busque el archivo de configuración de la extensión para CRT:

    - **Retail Server:** El archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin\\ext** en la ubicación del sitio de IIS Retail Server.
    - **CRT local en Modern POS:** El archivo se llama **CommerceRuntime.MPOSOffline.Ext.config** y está en la ubicación del agente del cliente de CRT local.

5. Registre el cambio de CRT en el archivo de configuración de extensión.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **No** edite los archivos commerceruntime.config y CommerceRuntime.MPOSOffline.config. Estos archivos no están pensados para ninguna personalización.

---

### <a name="the-retail-server-extension-components"></a>Los componentes de la extensión Retail Server

#### <a name="salestransactionsignature-retail-server-sample-component"></a>Componente de muestra de Retail Server SalesTransactionSignature

1. En la carpeta **RetailSDK\\SampleExtensions\\RetailServer\\RetailServer.Extensions.SalesTransactionSignatureSample**, busque el proyecto **RetailServer.Extensions.SalesTransactionSignatureSample** y compílelo.
2. En la carpeta **RetailServer\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.RetailServer.SalesTransactionSignatureSample.dll**.
3. Copie el archivo de ensamblaje en la carpeta de extensiones de Retail Server.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    La carpeta es **\\bin** en la ubicación del sitio de IIS Retail Server.

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    La carpeta es **\\bin** en la ubicación del sitio de IIS Retail Server.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    La carpeta es **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    La carpeta es **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    La carpeta es **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    La carpeta es **\\bin\\ext** en la ubicación del sitio de IIS Retail Server.

    ---

4. Busque el archivo de configuración de Retail Server. El archivo se llama **web.config** y está en la carpeta raíz en la ubicación del sitio de IIS Retail Server.
5. Registre las extensiones de Retail Server en la sección **extensionComposition** del archivo de configuración.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Registre las dependencias de las extensiones de Retail Server.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4/)

    1. En la carpeta **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**, busque los siguientes archivos:

        - El archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
        - El archivo de configuración **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

    2. Copie los archivos en la carpeta **\\bin** en la ubicación del sitio de IIS Retail Server.
    3. Registre el cambio CRT en el archivo de configuración de extensión para CRT. Este archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin** en la ubicación del sitio de IIS Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later/)

    1. En la carpeta **CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
    2. Copie el archivo en la carpeta **\\bin** en la ubicación del sitio de IIS Retail Server.
    3. Registre el cambio CRT en el archivo de configuración de extensión para CRT. Este archivo se llama **commerceruntime.ext.config** y está en la carpeta **bin** en la ubicación del sitio de IIS Retail Server.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > No se necesitan acciones.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    > [!NOTE]
    > No se necesitan acciones.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    > [!NOTE]
    > No se necesitan acciones.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    > [!NOTE]
    > No se necesitan acciones.

    ---

### <a name="the-modern-pos-extension-components"></a>Los componentes de la extensión Modern POS

#### <a name="implement-the-proxy-code-for-offline-mode"></a>Implementar el código proxy para el modo fuera de línea

Esta parte es equivalente al controlador Retail Server, pero extiende el CRT local que se utiliza cuando el cliente no está conectado.

1. En el archivo **customization.settings**, cambie la sección **@(RetailServerLibraryPathForProxyGeneration)** para que utilice el nuevo ensamblado Retail Server para la generación de proxy.
2. Implemente los siguientes métodos de interfaz en la clase **StoreOperationsManager**. Para la primera iteración, agregue el siguiente código:

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    ---

3. Para volver a generar el código proxy, compile la carpeta **Proxies** desde la línea de comando usando el comando **msbuild /t:Rebuild**.
4. Resuelva las dependencias del proyecto **Proxies.RetailProxy**:

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    Abra **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, agregue el proyecto **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\CommerceRuntime.Extensions.SalesTransactionSignatureSample** a la solución y agregue una referencia de proyecto al proyecto **RetailProxy** para hacer referencia a **SalesTransactionSignatureSample**.

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    Abra **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, agregue el proyecto **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages** a la solución y agregue una referencia de proyecto al proyecto **RetailProxy** para hacer referencia a **SalesTransactionSignatureSample.Messages**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    ---

5. Ajuste los métodos de interfaz en la clase **StoreOperationsManager**:

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    > [!NOTE]
    > Este paso no se aplica a esta versión.

    ---

6. Actualice el archivo **dllhost.exe.config** para que el intermediario del cliente cargue el nuevo ensamblado RetailProxy.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Componente de extensión de proxy minorista (Retail 7.3.1 y posterior)

Complete el siguiente procedimiento solo si está utilizando Retail 7.3.1 y posterior.

1. En la carpeta **RetailSDK\\SampleExtensions\\RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample**, busque el proyecto **RetailServer.Extensions.SalesTransactionSignatureSample** y compílelo.
2. En la carpeta **RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample\\bin\\Debug**, busque el archivo de ensamblaje **Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample**.
3. Copie los archivos de ensamblado en la carpeta **\\ext** en la ubicación del agente de cliente de CRT.
4. Registre el cambio en el proxy de Retail en el archivo de configuración de extensión. El archivo se llama **RetailProxy.MPOSOffline.ext.config** y está bajo la ubicación del corredor del cliente de CRT local.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Componentes de la extensión Modern POS

1. Abra la solución en **RetailSdk\\POS\\ModernPOS.sln** y asegúrese de que se pueda compilar sin errores. Además, asegúrese de poder ejecutar Modern POS de Microsoft Visual Studio usando el comando **Ejecutar**.

    > [!NOTE]
    > Los puntos de venta modernos no deben personalizarse. Debe habilitar el Control de cuentas de usuario (UAC) y debe desinstalar las instancias instaladas previamente de Modern POS según sea necesario.

2. Incluya las siguientes carpetas de código fuente existentes en el proyecto **Pos. Extensiones**.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Habilite las extensiones para que se compilen en **tsconfig.json** eliminando las siguientes carpetas de la lista de exclusión.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Habilite las extensiones para que se carguen en **extensions.json** agregando las siguientes líneas en el lugar apropiado.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Para obtener más información y ejemplos que muestran cómo incluir carpetas de código fuente y habilitar la carga de extensiones, consulte las instrucciones en el archivo readme.md en el proyecto **Pos.Extensions**.

5. Compile la solución.
6. Ejecute Modern POS en el depurador y pruebe la funcionalidad.

### <a name="cloud-pos-extension-components"></a>Componentes de la extensión Cloud POS

1. Abra la solución en **RetailSdk\\POS\\CloudPOS.sln** y asegúrese de que se pueda compilar sin errores.
2. Incluya las siguientes carpetas de código fuente existentes en el proyecto **Pos. Extensiones**.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Habilite las extensiones para que se compilen en **tsconfig.json** eliminando las siguientes carpetas de la lista de exclusión.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Habilite las extensiones para que se carguen en **extensions.json** agregando las siguientes líneas en el lugar apropiado.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Para obtener más información y ejemplos que muestran cómo incluir carpetas de código fuente y habilitar la carga de extensiones, consulte las instrucciones en el archivo readme.md en el proyecto **Pos.Extensions**.

5. Compile la solución.
6. Ejecute la solución utilizando el comando **Ejecutar** y siguiendo los pasos del manual Retail SDK.
7. Pruebe la funcionalidad.

### <a name="set-up-required-parameters-in-headquarters"></a>Configure los parámetros obligatorios en la sede

Para obtener más información, consulte [Funcionalidad de registro de efectivo para Noruega](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Entorno de producción

Siga estos pasos para crear paquetes desplegables que contengan componentes de Commerce y aplicar esos paquetes en un entorno de producción.

1. Complete los pasos en la sección [Componentes de la extensión Cloud POS](#cloud-pos-extension-components) o [Componentes de extensión Modern POS](#modern-pos-extension-components) anteriormente en este artículo.
2. Realice los siguientes cambios en los archivos de configuración del paquete en la carpeta **RetailSdk\\Assets**:

    1. En los archivos de configuración **commerceruntime.ext.config** y **CommerceRuntime.MPOSOffline.Ext.config**, agregue las siguientes líneas a la sección **composition**:

        # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. Habilite la personalización del proxy comercial:

        # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

        En el archivo de configuración **dllhost.exe.config**, agregue las siguientes líneas a la subsección **appSettings** de la sección **configuration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

        En el archivo de configuración **dllhost.exe.config**, agregue las siguientes líneas a la subsección **appSettings** de la sección **configuration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        En el archivo de configuración **RetailProxy.MPOSOffline.ext.config**, agregue las siguientes líneas a la sección **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

        En el archivo de configuración **RetailProxy.MPOSOffline.ext.config**, agregue las siguientes líneas a la sección **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

        En el archivo de configuración **RetailProxy.MPOSOffline.ext.config**, agregue las siguientes líneas a la sección **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

        En el archivo de configuración **RetailProxy.MPOSOffline.ext.config**, agregue las siguientes líneas a la sección **composition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Realice los siguientes cambios en el archivo de configuración de personalización del paquete **Ajustes de personalización**:

    1. Habilite la personalización del proxy de Retail.

        # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

        Agregue las siguientes líneas a la sección **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

        Agregue las siguientes líneas a la sección **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Agregue las siguientes líneas a la sección **ItemGroup** para incluir la extensión de proxy minorista en los paquetes desplegables:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

        Agregue las siguientes líneas a la sección **ItemGroup** para incluir la extensión de proxy minorista en los paquetes desplegables:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

        Agregue las siguientes líneas a la sección **ItemGroup** para incluir la extensión de proxy minorista en los paquetes desplegables:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

        Agregue las siguientes líneas a la sección **ItemGroup** para incluir la extensión de proxy minorista en los paquetes desplegables:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Agregue las siguientes líneas a la sección **ItemGroup** para incluir las extensiones CRT de Retail en los paquetes desplegables:

        # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Agregue las siguientes líneas a la sección **ItemGroup** para incluir la extensión de Retail Server en los paquetes desplegables:

        # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Modifique los siguientes archivos para incluir los archivos de recursos para Noruega en paquetes implementables:
    - Packages\_SharedPackagingProjectComponents\Sdk.ModernPos.Shared.csproj
    - Packages\RetailServer\Sdk.RetailServerSetup.proj
  
  - Para el archivo **Sdk.ModernPos.Shared.csproj** 
    - Agregue una línea a la sección **ItemGroup**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > En lugar de <File_name>, especifique un nombre para el archivo de recursos. Lo mismo es relevante para los otros ejemplos que se dan a continuación.
 
    - Agregue una línea a la sección **Target Name="CopyPackageFiles"**
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - Para el archivo **Sdk.RetailServerSetup.proj** 
    - Agregue una línea a la sección **ItemGroup**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Agregue una línea a la sección **Target Name="CopyPackageFiles"**
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. Modifique el archivo de configuración del certificado especificando la huella digital, la ubicación de la tienda y el nombre de la tienda para el certificado que se debe utilizar para firmar las transacciones de ventas. Luego copie el archivo de configuración a la carpeta **Referencias**.

    # <a name="application-update-4"></a>[Application Update 4](#tab/app-update-4)

    El archivo se llama **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** y se encuentra en **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="application-update-5-and-later"></a>[Actualización de aplicación 5 y posteriores](#tab/app-update-5-and-later)

    El archivo se llama **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** y se encuentra en **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    El archivo se llama **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** y se encuentra en **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 y versiones posteriores](#tab/retail-7-3-2)

    El archivo se llama **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** y se encuentra en **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 y versiones posteriores](#tab/retail-7-3-5)

    El archivo se llama **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** y se encuentra en **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 y versiones posteriores](#tab/retail-8-1-1)

    El archivo se llama **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** y se encuentra en **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    ---

6. Actualice el archivo de configuración de Retail Server. En el archivo **RetailSDK\\Packages\\RetailServer\\Code\\web.config**, agregue las siguientes líneas a la sección **extensionComposition**.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

7. Ejecute **msbuild** para todo Retail SDK para crear paquetes implementables.
8. Aplique los paquetes a través de Microsoft Dynamics Lifecycle Services (LCS) o manualmente. Para obtener más información, consulte [Crear paquetes implementables](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Habilite la firma digital en modo fuera de línea para Modern POS

Para habilitar la firma digital en modo fuera de línea para Modern POS, debe seguir estos pasos después de activar Modern POS en un nuevo dispositivo.

1. Inicie sesión en POS.
2. Sobre la página **Estado de conexión a la base de datos**, asegúrese de que la base de datos fuera de línea esté completamente sincronizada. Cuando el valor del campo **Descargas pendientes** sea **0** (cero), la base de datos está completamente sincronizada.
3. Salga de POS.
4. Espere un momento a que la base de datos fuera de línea esté completamente sincronizada.
5. Inicie sesión en POS.
6. Sobre la página **Estado de conexión a la base de datos**, asegúrese de que la base de datos fuera de línea esté completamente sincronizada. Cuando el valor del campo **Transacciones pendientes en la base de datos sin conexión** sea **0** (cero), la base de datos está completamente sincronizada.
7. Reinicie Modern POS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
