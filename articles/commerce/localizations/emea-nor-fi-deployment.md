---
title: Directrices de implementación de cajas registradoras para Noruega
description: Este artículo proporciona orientación sobre cómo habilitar la función de caja registradora para la localización de Microsoft Dynamics 365 Commerce para Noruega.
author: EvgenyPopovMBS
ms.date: 10/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 0e66ef93e65fecaca23f0434c386507a0672d251
ms.sourcegitcommit: 2bc6680dc6b12d20532d383a0edb84d180885b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "9631325"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Directrices de implementación de cajas registradoras para Noruega

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Debe implementar los pasos que se describen en este artículo solo si está utilizando Microsoft Dynamics 365 Commerce versión 10.0.29 o posterior. En Commerce version 10.0.28 o anterior, debe utilizar la versión anterior del kit de desarrollo de software (SDK) de Retail en una máquina virtual (VM) de desarrollador en Microsoft Dynamics Lifecycle Services (LCS). Para más información, vea [Directrices de implementación para cajas registradoras en Noruega (heredado)](./emea-nor-loc-deployment-guidelines.md). Si está utilizando la versión 10.0.28 o anterior de Commerce y está migrando a la versión 10.0.29 o posterior de Commerce, debe seguir los pasos en [Migrar desde la funcionalidad de comercio heredada para Noruega](./emea-nor-fi-migration.md).

Este artículo proporciona orientación sobre cómo habilitar la función de caja registradora para la localización de Commerce para Noruega. La localización consta de varias extensiones de componentes que le permiten realizar acciones como imprimir campos personalizados en recibos, registrar eventos de auditoría adicionales, transacciones de ventas y transacciones de pago en el punto de venta (PDV), firmar digitalmente transacciones de ventas e imprimir informes en formatos locales. Para obtener más información sobre la localización para Noruega, consulte [Funcionalidad de caja registradora para Noruega](./emea-nor-cash-registers.md). Para obtener más información sobre cómo configurar Commerce para Noruega, consulte [Configurar Commerce para Noruega](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

## <a name="set-up-fiscal-registration-for-norway"></a>Configuración del registro fiscal para Noruega

La muestra de integración fiscal para Noruega se basa en la [funcionalidad de integración fiscal](fiscal-integration-for-retail-channel.md) y es parte del SDK de Commerce. La extensión de PDV de muestra se encuentra en la carpeta **src\\FiscalIntegration\\SequentialSignatureNorway** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). La [muestra ](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) consta de un proveedor de documentos fiscales y un conector fiscal, que son extensiones de Commerce Runtime (CRT). Para obtener más información sobre cómo usar el SDK de Commerce, consulte [Descargue muestras de Commerce SDK y paquetes de referencia de GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md) y [Configure una canalización de compilación para el SDK de empaquetado independiente](../dev-itpro/build-pipeline.md).

Complete los pasos de configuración del registro fiscal que se describen en [Configurar la integración fiscal para los canales comerciales](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Configuración de un proceso de registro fiscal](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Asegúrese de tomar nota de la configuración del proceso de registro fiscal que sea [específico de Noruega](#configure-the-fiscal-registration-process).
1. [Establecimiento de la configuración de tratamiento de errores](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Habilitar la ejecución manual del registro fiscal aplazado](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-deferred-fiscal-registration).
1. [Configurar los componentes de canal](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Configurar el proceso de registro fiscal

Siga estos pasos para habilitar el proceso de registro fiscal para Noruega en Commerce Headquarters.

1. Descargue los archivos de configuración para el proveedor de documentos fiscales y el conector fiscal de Commerce SDK:

    1. Abra el respositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Abra la última rama de versión disponible.
    1. Abra **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime**.
    1. Descargue el archivo de configuración del proveedor de documentos fiscales en **DocumentProvider.SequentialSignNorway \> Configuración \> DocumentProviderSequentialSignatureNorwaySample.xml**.
    1. Descargue el archivo de configuración del conector fiscal en **Connector.SequentialSignNorway \> Configuración \> ConnectorSequentialSignatureNorwaySample.xml**.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros compartidos**. En la pestaña **General**, configure la opción **Habilitar integración fiscal** en **Sí**.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Conectores fiscales** y cargue el archivo de configuración del conector fiscal que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Proveedores de documentos fiscales** y cargue el archivo de configuración del proveedor de documentos fiscales que descargó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles funcionales del conector**. Cree un nuevo perfil funcional del conector y seleccione el proveedor de documentos y conector que cargó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos del conector**. Cree un nuevo perfil técnico de conector y seleccione el conector que cargó anteriormente. Establezca el tipo de conector en **Interno**.
1. Vaya a **Retail y Commerce \> Configuración del canal \> Integración fiscal \> Grupos de conectores fiscales** y cree un nuevo grupo fiscal de conectores para el perfil funcional del conector que creó antes.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Procesos de registro fiscal**. Cree un nuevo proceso de registro fiscal y un paso de proceso de registro fiscal, y seleccione el grupo de conectores fiscales que creó anteriormente.
1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad**. Seleccione un perfil de funcionalidad que esté vinculado a la tienda donde se debe activar el proceso de registro. Sobre la ficha desplegable **Proceso de registro fiscal**, seleccione el proceso de registro fiscal que creó anteriormente. Sobre la ficha desplegable **Servicios fiscales**, seleccione el perfil técnico del conector que creó anteriormente. 
1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**. Abra la programación de distribución y seleccione los trabajos **1070** y **1090** para transferir datos a la base de datos del canal.

### <a name="configure-the-digital-signature-parameters"></a>Configurar los parámetros de la firma digital

Debe configurar los certificados que se utilizarán para la firma digital de transacciones de ventas en una tienda. Se usa un certificado digital que se almacena en Azure Key Vault para realizar la firma. Para el modo fuera de línea de Modern POS, la firma también se puede realizar mediante un certificado digital que se almacena en el almacenamiento local de la máquina en la que está instalado Modern POS.

Antes de poder utilizar un certificado digital almacenado en el almacenamiento de Key Vault, se deben completar los siguientes pasos.

1. Se debe crear el almacenamiento de Key Vault. Le recomendamos que implemente el almacenamiento en la misma región geográfica que Commerce Scale Unit.
1. El certificado debe cargarse en el almacenamiento de Key Vault como un secreto de cadena base64.
1. La aplicación Application Object Server (AOS) debe estar autorizada para leer secretos del almacenamiento de Key Vault.

Para obtener más información sobre cómo trabajar con Key Vault, consulte [Empezar a utilizar Azure Key Vault](/azure/key-vault/key-vault-get-started).

A continuación, en la página **Parámetros de Key Vault**, debe especificar los parámetros para acceder al almacenamiento de Key Vault:

- **Nombre** y **Descripción** - El nombre y la descripción del almacenamiento de Key Vault.
- **URL de Key Vault** - La URL del almacenamiento de Key Vault.
- **Cliente de almacén de claves** - Introduzca el ID de cliente interactivo de la aplicación Azure Active Directory (Azure AD) que está asociada con el almacenamiento de Key Vault para autenticación. Este cliente debe tener acceso para leer secretos del almacenamiento.
- **Clave secreta de Key Vault** - Una clave secreta que está asociada con la aplicación Azure AD que se utiliza para la autenticación en el almacenamiento de Key Vault.
- **Nombre**, **Descripción** y **Referencia secreta** - El nombre, descripción y referencia secreta del certificado.

A continuación, debe configurar un conector para sus certificados que se almacenan en Key Vault o en el almacenamiento de certificados local. Este conector se utiliza para firmar en el lado del canal.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Integración fiscal \> Perfiles técnicos del conector**.
1. En la ficha desplegable **Ajustes**, especifique los siguientes parámetros para firmas digitales:

    - **Nombre secreto** - Seleccione el nombre secreto que configuró anteriormente en la página **Parámetros de Key Vault**.
    - **Huella digital del certificado local** - Proporcione una huella digital para un certificado que se almacena localmente.
    - **Algoritmo hash** - Especifique uno de los algoritmos hash criptográficos compatibles con Microsoft .NET, como **SHA1**.
    - **Nombre de la tienda de certificados** - Este campo es opcional. Úselo para especificar un nombre de tienda predeterminado que debe usarse para buscar certificados locales.
    - **Ubicación de la tienda de certificados** - Este campo es opcional. Úselo para especificar una ubicación de tienda predeterminado que debe usarse para buscar certificados locales.
    - **Pruebe primero el certificado local** - Seleccione esta opción para usar el certificado de la tienda local de forma predeterminada para firmar datos, en lugar del certificado de Key Vault.
    - **Activar la comprobación de estado** – Para obtener más información sobre la función de comprobación de estado, consulte [Comprobar estado del registro fiscal](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Solo el algoritmo hash criptográfico **SHA1** es actualmente aceptable para Noruega.
> - El nombre y la ubicación de la tienda predeterminados se agregan para simplificar el proceso de búsqueda de certificados locales en CRT. X509StoreProvider tiene una lista de carpetas donde se almacenan los certificados. Si no se especifican el nombre y la ubicación de la tienda predeterminados, X509StoreProvider intenta encontrar un certificado en todas las carpetas de su lista.

### <a name="configure-channel-components"></a>Configurar los componentes de canal

#### <a name="development-environment"></a>Entorno de desarrollo

Siga estos pasos para configurar un entorno de desarrollo para que pueda probar y ampliar la muestra.

1. Clonar o descargar el repositorio de [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Seleccione una versión de rama de lanzamiento correcta de acuerdo con su SDK/versión de la aplicación. Para más información, vea [Descargar muestras y paquetes de referencia del SDK de Commerce desde GitHub y NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra la solución **SequentialSignatureNorway.sln** en **Dynamics365Commerce.Solutions\\FiscalIntegration\\SequentialSignatureNorway** y compílela.
1. Instale las extensiones de CRT:

    1. Busque el instalador de extensiones de CRT:

        - **Commerce Scale Unit:** En la carpeta **SequentialSignatureNorway\\ScaleUnit\\ScaleUnit.SequentialSignNorway.Installer\\bin\\Debug\\net461**, busque el instalador **ScaleUnit.SequentialSignNorway.Installer**.
        - **CRT local en Modern POS:** En la carpeta **SequentialSignatureNorway\\ModernPOS\\ModernPos.SequentialSignNorway.Installer\\bin\\Debug\\net461**, busque el instalador **ModernPos.SequentialSignNorway.Installer**.

    1. Inicie el instalador de extensiones de CRT desde la línea de comandos:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **CRT local en Modern POS:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Entorno de producción

Siga los pasos en [Configurar una canalización de compilación para una muestra de integración fiscal](fiscal-integration-sample-build-pipeline.md) para generar y lanzar la unidad de escala en la nube y los paquetes implementables de autoservicio para la muestra de integración fiscal. El archivo YAML de plantilla **SequentialSignatureNorway build-pipeline.yaml** se puede encontrar en la carpeta **Pipeline\\YAML_Files** del repositorio [Soluciones de Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Habilite la firma digital en modo fuera de línea para Modern POS

Para habilitar la firma digital en modo fuera de línea para Modern POS, debe seguir estos pasos después de activar Modern POS en un nuevo dispositivo.

1. Inicie sesión en POS.
1. Sobre la página **Estado de conexión a la base de datos**, asegúrese de que la base de datos fuera de línea esté completamente sincronizada. Cuando el valor del campo **Descargas pendientes** sea **0** (cero), la base de datos está completamente sincronizada.
1. Salga de POS.
1. Espere un momento a que la base de datos fuera de línea esté completamente sincronizada.
1. Inicie sesión en POS.
1. Sobre la página **Estado de conexión a la base de datos**, asegúrese de que la base de datos fuera de línea esté completamente sincronizada. Cuando el valor del campo **Transacciones pendientes en la base de datos sin conexión** sea **0** (cero), la base de datos está completamente sincronizada.
1. Vuelva a abrir Modern POS.
