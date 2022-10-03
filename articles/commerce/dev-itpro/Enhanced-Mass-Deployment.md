---
title: Implementación masiva de componentes de autoservicio de Commerce sellados
description: Este artículo explica cómo usar el marco para instaladores de componentes de autoservicio para instalar y dar servicio a las implementaciones de manera silenciosa.
author: jashanno
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2021-04-30
ms.openlocfilehash: 426473c14cdf9e171810aafd97dbb1afd5988b2f
ms.sourcegitcommit: 24673493d14f2045a08fe7240689bee34e099cb5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2022
ms.locfileid: "9589099"
---
# <a name="mass-deployment-of-sealed-commerce-self-service-components"></a>Implementación masiva de componentes de autoservicio de Commerce sellados

[!include [banner](../includes/banner.md)]

Este artículo se aplica al marco sellado, los instaladores de componentes que se publican todos los meses, a partir de la versión 10.0.18, y que están disponibles en la biblioteca de activos compartidos en Microsoft Dynamics Lifecycle Services (LCS). Tenga en cuenta que las primeras versiones de estos nuevos instaladores se designan como **(Versión preliminar)**. Sin embargo, la única finalidad de esta designación es diferenciar los nuevos instaladores mientras Microsoft determina si existen requisitos funcionales adicionales para usarlos. No significa que los instaladores no sean válidos para producción. Basándose en el lanzamiento de estos nuevos instaladores, Microsoft planea dejar en desuso los instaladores antiguos (heredados) alrededor de octubre de 2023. 

En este artículo se explica cómo usar los nuevos instaladores para realizar una instalación silenciosa y realizar actualizaciones de servicio a través de argumentos de la línea de comandos. Estos argumentos le permiten realizar implementaciones masivas de varias maneras diferentes.

> [!NOTE]
> Los nuevos instaladores sellados de autoservicio no estarán disponibles en la sede central y solo se pueden descargar a través de LCS.

## <a name="delimiters-for-mass-deployment"></a>Delimitadores para implementación masiva

La siguiente tabla muestra los delimitadores que se pueden utilizar en la ejecución de la línea de comandos.


| Delimitador                 | Description |
|---------------------------|-------------|
| -AadTokenIssuerPrefix | El prefijo para el emisor de tokens de Microsoft Azure Active Directory (Azure AD). |
| -AsyncClientAadClientId | El id. de cliente de Azure AD que Async Client debe usar durante las comunicaciones con la sede central. |
| -AsyncClientAppInsightsInstrumentationKey | La clave de instrumentación de AppInsights de Async Client. |
| -AsyncClientCertFullPath | La ruta de acceso URN con formato completo que usa la huella digital como la métrica de búsqueda de la ubicación del certificado de identidad de Async Client que debe usarse para autenticar con Azure AD para las comunicaciones con la sede central. Por ejemplo, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` es una URN con formato correcto. El valor **\<MyThumbprint\>** se reemplazará por la huella digital del certificado que se debe usar. No utilice este parámetro junto con el parámetro **-AsyncClientCertThumbprint**. |
| -AsyncClientCertThumbprint | La huella digital del certificado de identidad de Async Client que debe usarse para autenticar con Azure AD para las comunicaciones con la sede central. Esta huella digital se utilizará para buscar la ubicación de **LocalMachine/Mi tienda** y el nombre para encontrar el certificado correcto para usar. No utilice este parámetro junto con el parámetro **-AsyncClientCertFullPath**. |
| -ClientAppInsightsInstrumentationKey | La clave de instrumentación AppInsights de cliente. |
| -CloudPosAppInsightsInstrumentationKey | La clave de instrumentación de AppInsights de PDV en la nube. |
| -Config | El archivo de configuración que debe utilizarse durante la instalación. Un ejemplo de un nombre de archivo es **Contoso.CommerceScaleUnit.xml**. |
| -CposAadClientId | El id. de cliente de Azure AD que PDV en la nube debe usar durante la activación del dispositivo. Este parámetro no es necesario para las implementaciones locales. |
| -Device | El id. de dispositivo, como se muestra en la página **Dispositivos** en la sede central. |
| -EnvironmentId | El id. de entorno. |
| -HardwareStationAppInsightsInstrumentationKey | La clave de instrumentación de AppInsights de Hardware Station. |
| Instalar | Un parámetro que especifica si se debe instalar el componente proporcionado por este instalador. Este parámetro es necesario para realizar una instalación y no tiene un guion inicial. |
| -InstallOffline | Para Modern POS, este parámetro especifica que la base de datos sin conexión también debe instalarse y configurarse. Utilice también el parámetro **-SQLServerName**. De lo contrario, el instalador intentará encontrar una instancia predeterminada que cumpla con los requisitos previos. Al usar la autenticación Azure Active Directory (Azure AD), el PDV fuera de línea no funcionará, ya que siempre se requiere conectividad en línea. |
| -Port | El puerto con el que debe estar asociado y utilizarse por el directorio virtual de Retail Server. Si no se establece ningún puerto, se usará el puerto predeterminado 443. |
| -Register | El id. de caja registradora, como se muestra en la página **Cajas registradoras** en la sede central. |
| -RetailServerAadClientId | El id. de cliente de Azure AD que Retail Server debe usar durante las comunicaciones con la sede central. |
| -RetailServerAadResourceId | El id. de recurso de aplicación de Azure AD de Retail Server que debe usarse durante la activación del dispositivo. Este parámetro no es necesario para las implementaciones locales. |
| -RetailServerCertFullPath | La ruta de acceso URN con formato completo que usa la huella digital como la métrica de búsqueda del certificado de identidad de Retail Server que debe usarse para autenticar con Azure AD para las comunicaciones con la sede central. Por ejemplo, `store://My/LocalMachine?FindByThumbprint=<MyThumbprint>` es un URN con formato correcto donde el valor **\<MyThumbprint\>** se reemplazará por la huella digital del certificado que se debe usar. No utilice este parámetro junto con el parámetro **-RetailServerCertThumbprint**. |
| -RetailServerCertThumbprint | La huella digital del certificado de identidad de Retail Server que debe usarse para autenticar con Azure AD para las comunicaciones con la sede central. Esta huella digital se utilizará para buscar la ubicación de **LocalMachine/Mi tienda** y el nombre para encontrar el certificado correcto para usar. No utilice este parámetro junto con el parámetro **-RetailServerCertFullPath**. |
| -RetailServerURL | La URL de Retail Server que el instalador debe usar. (Esta URL también se conoce como la Commerce Scale Unit \[CSU\] URL). Para Modern POS, este valor se utilizará durante la activación del dispositivo. |
| -SkipAadCredentialsCheck| Un conmutador que indica si se deben omitir las comprobaciones de requisitos previos de credencial de Azure AD. El valor predeterminado es **falso**. |
| -SkipCertCheck | Un conmutador que indica si se deben omitir las comprobaciones de requisitos previos de certificado. El valor predeterminado es **falso**. |
| -SkipIisCheck | Un conmutador que indica si se deben omitir las comprobaciones de requisitos previos de Internet Information Services (IIS). El valor predeterminado es **falso**. |
| -SkipNetFrameworkCheck | Un conmutador que indica si se deben omitir las comprobaciones de requisitos previos de .NET Framework. El valor predeterminado es **falso**. |
| -SkipScaleUnitHealthcheck | Un conmutador que indica si se debe omitir la comprobación de estado de los componentes instalados. El valor predeterminado es **falso**. |
| -SkipSChannelCheck | Un conmutador que indica si se deben omitir las comprobaciones de requisitos previos de canal seguro. El valor predeterminado es **falso**. |
| -SkipSqlFullTextCheck | Un conmutador que indica si se debe omitir la validación del requisito previo de SQL Server que requiere la búsqueda de texto completo. El valor predeterminado es **falso**. |
| -SkipSqlServerCheck | Un conmutador que indica si se deben omitir las comprobaciones de requisitos previos de SQL Server. El valor predeterminado es **falso**. |
| -SqlServerName | El nombre de SQL Server. Si no se especifica el nombre, el instalador intentará encontrar la instancia predeterminada. |
| -SslcertFullPath | La ruta URN con formato completo que usa la huella digital como la métrica de búsqueda de la ubicación del certificado que se debe usar para cifrar el tráfico HTTP a la unidad de escalado. Por ejemplo, `store:\/\/My\/LocalMachine\?FindByThumbprint\=\<MyThumbprint\>` es un URN con formato correcto donde el valor **\<MyThumbprint\>** se reemplazará por la huella digital del certificado que se debe usar. No utilice este parámetro junto con el parámetro **SslCertThumbprint**. |
| -SslCertThumbprint | La huella digital del certificado que debe usarse para cifrar el tráfico HTTP a la unidad de escalado. Esta huella digital se utilizará para buscar la ubicación de **LocalMachine/Mi tienda** y el nombre para encontrar el certificado correcto para usar. No utilice este parámetro junto con el parámetro **-SslCertFullPath**. |
| -StoreSystemAosUrl | La URL de la sede central (AOS). |
| -StoreSystemChannelDatabaseId | El id. de base de datos de canal (nombre). |
| -TenantId | El id. de inquilino de Azure AD. |
| -TransactionServiceAzureAuthority | La autoridad de Azure AD de Transaction Service. |
| -TransactionServiceAzureResource | El recurso de Azure AD de Transaction Service. |
| -TrustSqlServerCertificate | Un conmutador que indica si se debe confiar en el certificado del servidor mientras se establece una conexión con SQL Server. Para ayudar a evitar riesgos de seguridad, las implementaciones de producción nunca deben proporcionar un valor de **verdadero** aquí. El valor predeterminado es **falso**. |
| -Verbosity | El nivel de registro que se solicita durante la instalación. Por lo general, no se debe usar este valor. |
| -WindowsPhoneAppInsightsInstrumentationKey | La clave de instrumentación de AppInsights de Hardware Station. |

## <a name="general-overview"></a>Visión general

El nuevo marco para instaladores de autoservicio tiene varias características y mejoras. Actualmente, el nuevo marco genera instaladores solo para Modern POS, estación de hardware y CSU (autohospedado). Es importante comprender el uso básico de la línea de comandos de los instaladores sellados, que debería ser similar al que se usa en el siguiente ejemplo. 
 
```Console
<Component Installer Name>.exe install -<Parameter Name> "<Parameter Information>"
```

El instalador requiere el parámetro **install** (o **uninstall** para eliminar la instalación) y cualquier parámetro específico de esa instalación. **Nombre del parámetro** debe incluir cualquier parámetro que sea necesario, como el registro, la URL de CSU o la información del certificado. **Información de parámetros** debe incluir cualquier información adicional sobre los parámetros.

El marco sellado se ha creado para permitir las siguientes alteraciones:
- **Sellado**: el nuevo marco de instalador separa por completo los instaladores de componentes básicos distribuidos por Microsoft de las personalizaciones basadas en la extensibilidad. Las personalizaciones se instalarán después, pero luego se liberarán de las actualizaciones (de modo que las actualizaciones solo se permitirán para el componente base de Microsoft, solo para las personalizaciones o para ambos).
- **Sin GUI**: ya no hay una interfaz de usuario (UI). En su lugar, hay un ejecutable totalmente basado en línea de comandos para cada instalador de componentes. Este cambio es uno de varios cambios o características clave que se usan para enfocar el nuevo marco del instalador para su uso con la implementación masiva.
- **Mayor profundidad**: los registros mejorados del instalador permiten una mejor validación de la finalización o error de la instalación, los pasos que se realizaron, y las advertencias o errores que se generaron.
- **Limpiar**: en el nuevo marco, los instaladores de componentes trabajan más para mantener la limpieza de los directorios de instalación, borrando todo el contenido de la carpeta del componente antes de instalar los componentes más recientes. Esta limpieza garantiza que no haya archivos sobrantes que puedan causar problemas y evitar una instalación correcta.

Tres componentes no se han migrado al nuevo marco: simulador de periféricos virtual, Async Server Connector Service (usado para el soporte de Dynamics AX 2012 R3) y el reemplazo del servicio en tiempo real (usado para el soporte de Dynamics AX 2012 R3).

> [!NOTE]
> Los instaladores se almacenan localmente y se conservan.  Es importante, con el tiempo, administrar o eliminar los instaladores retenidos para no desperdiciar el espacio en disco. Se recomienda mantener el instalador actual para los componentes básicos y cualquier instalador de extensión para las últimas versiones con la finalidad de recuperación de situaciones extremas.

## <a name="migration"></a>Migración

La migración de los antiguos instaladores de componentes del marco de autoservicio a los nuevos instaladores de componentes de marco requiere la desinstalación de los antiguos componentes.

- **Modern POS**: el nuevo marco de instalador hizo que la aplicación recibiera un nuevo id. de firma de aplicación. Por lo tanto, se requiere la desinstalación completa de los componentes antiguos antes de instalar el nuevo componente de marco de Modern POS. Debido al requisito de desinstalación completa, se requerirá de nuevo la activación del dispositivo. (La reactivación de este dispositivo es un requisito único, siempre que la desinstalación no se vuelva a producir).
- **Hardware station**: como sitio web de IIS, el nuevo marco de instalador requiere que se revise la estructura de carpetas base. Por lo tanto, se requiere la desinstalación completa de los componentes antiguos antes de instalar el nuevo componente hardware station de marco de Modern POS.
- **Commerce Scale Unit (CSU, autohospedado)**: como una serie de sitios web de IIS, el nuevo marco de instalador requiere que se modifique la estructura de carpetas base.  Por lo tanto, se requiere la desinstalación completa de los componentes antiguos antes de instalar el nuevo componente de marco de CSU (autohospedado).

## <a name="modern-pos"></a>Modern POS

### <a name="before-you-begin"></a>Antes de comenzar

Es fundamental que elimine el antiguo componente Modern POS de autoservicio. Para obtener más información, consulte los pasos de migración descritos anteriormente en este artículo.

> [!NOTE]
> En un sistema de un solo ordenador, como una topología de desarrollador o un entorno de demostración, o cuando Commerce Scale Unit y el PDV Moderno están instalados en el mismo ordenador, es posible que Store Commerce no pueda completar la activación del dispositivo. Este problema se produce porque Store Commerce no puede realizar llamadas de red al mismo equipo (es decir, llamadas a sí mismo). Si bien esto nunca debería ser un escenario en una configuración de producción, el problema se puede mitigar habilitando una excepción de bucle invertido de AppContainer para que las comunicaciones puedan ocurrir en el mismo ordenador. Varias aplicaciones están disponibles públicamente para ayudar a habilitar este bucle invertido. Para obtener más información sobre el bucle invertido, consulte [Cómo habilitar el bucle invertido y solucionar los problemas de aislamiento de la red](/previous-versions/windows/apps/hh780593(v=win.10)). Es importante comprender que un bucle invertido puede ser un riesgo para la seguridad, por lo que no se recomienda utilizar un bucle invertido a menos que sea absolutamente necesario.

### <a name="examples-of-silent-deployment"></a>Ejemplos de implementación silenciosa

Esta sección muestra ejemplos de comandos que se utilizan para instalar Modern POS.

#### <a name="silently-install-modern-pos"></a>Realizar instalación silenciosa de Modern POS

El siguiente comando instala (o actualiza) Modern POS de forma silenciosa. Tiene la estructura de comando estándar que se usa para el servicio silencioso de los componentes que están instalados actualmente. La estructura utiliza los valores básicos de **&lt;NombreInstalador&gt;.exe**.

El siguiente comando básico muestra las opciones disponibles si se solicita una instalación. Se recomienda encarecidamente utilizar este comando cuando se prueba o se utiliza el instalador por primera vez.

```Console
CommerceModernPOS.exe -help install
```

> [!NOTE]
> No se requiere un archivo de configuración para Modern POS. El instalador ahora tiene parámetros (mostrados anteriormente en este artículo) para los distintos valores que se utilizan durante la activación del dispositivo.

El siguiente comando especifica todos los parámetros que deben usarse durante la activación del dispositivo después de instalar la aplicación Modern POS. Este ejemplo utiliza el registro **Houston-3**, que es un valor de uso común en los datos de demostración de Dynamics 365 Commerce.

```Console
CommerceModernPOS.exe install -Register "Houston-3" -Device "Houston-3" -RetailServerURL "https://MyDynamics365CommerceURL.dynamics.com/Commerce"
```

El siguiente comando especifica los parámetros que deben usarse para instalar y configurar la base de datos sin conexión. SQL Server se especifica junto con el archivo de configuración que debe utilizarse.

```Console
CommerceModernPOS.exe install -InstallOffline -SQLServerName "SQLExpress" -Config "ModernPOS.Houston-3.xml"
```

Puede mezclar y combinar estos conceptos para lograr los resultados de instalación que desea.

## <a name="hardware-station"></a>Estación de hardware

### <a name="before-you-begin"></a>Antes de comenzar

Es fundamental que elimine el antiguo componente de estación de hardware de autoservicio. Para obtener más información, consulte los pasos de migración descritos anteriormente en este artículo. Ya no existe una herramienta de información de cuenta de comerciante. En cambio, la información de la cuenta de comerciante se instala cuando un terminal del PDV se empareja con la estación de hardware. Cuando se pruebe este instalador por primera vez, es muy recomendable que ejecute el siguiente comando:

```Console
CommerceHardwareStation.exe -help install
```

### <a name="examples-of-silent-deployment"></a>Ejemplos de implementación silenciosa

Esta sección muestra ejemplos de comandos que se usan para instalar la estación de hardware.

#### <a name="silently-install-hardware-station"></a>Realizar la instalación silenciosa de la estación de hardware

El siguiente comando instala (o actualiza) la estación de hardware de forma silenciosa. Tiene la estructura de comando estándar que se usa para los componentes de servicio que están instalados actualmente. La estructura utiliza los valores básicos de **&lt;NombreInstalador&gt;.exe**.

El siguiente comando básico ejecuta el instalador del archivo ejecutable.

```Console
HardwareStation.exe install -Port 443 -StoreSystemAOSURL "https://MyDynamics365CommerceURL.dynamics.com/" -StoreSystemChannelDatabaseID "Houston" -SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers"
```

> [!NOTE]
> No se requiere un archivo de configuración para la estación de hardware. El instalador ahora tiene parámetros (mostrados anteriormente en este artículo) para los distintos valores que se requieren.

El siguiente comando especifica todos los parámetros necesarios para omitir las comprobaciones de requisitos previos durante una instalación estándar. 

> [!NOTE]
> No se recomienda omitir comprobaciones sin realizar pruebas exhaustivas con antelación o en situaciones de desarrollo.

```Console
HardwareStation.exe install -SkipFirewallUpdate -SkipOPOSCheck -SkipVersionCheck -SkipURLCheck -Config "HardwareStation.Houston.xml"
```

Como es habitual, es común mezclar y combinar estos conceptos para lograr los resultados de instalación que desea.

## <a name="commerce-scale-unit-self-hosted"></a>Commerce Scale Unit (autoalojado)

Cuando se pruebe este instalador por primera vez, es muy recomendable que ejecute el siguiente comando:

```Console
CommerceStoreScaleUnitSetup.exe -help install
```

### <a name="before-you-begin"></a>Antes de comenzar

Es fundamental que elimine el antiguo componente CSU de autoservicio (autohospedado). Para obtener más información, consulte los pasos de migración descritos anteriormente en este artículo.

### <a name="examples-of-silent-deployment"></a>Ejemplos de implementación silenciosa

Esta sección muestra ejemplos de comandos que se utilizan para instalar CSU (autohospedado).

#### <a name="silently-install-csu-self-hosted"></a>Realizar instalación silenciosa de CSU (autohospedada)

El siguiente comando instala (o actualiza) CSU de forma silenciosa (autohospedada). Tiene la estructura de comando estándar que se usa para el servicio silencioso de los componentes que están instalados actualmente. La estructura utiliza los valores básicos de **&lt;NombreInstalador&gt;.exe**.

En comparación con otros instaladores de autoservicio, Commerce Scale Unit (CSU) es más complejo y requiere una gran cantidad de información adicional. El siguiente comando es el comando mínimo (con parámetros) necesario para ejecutar el instalador del archivo ejecutable cuando no hay un archivo de configuración presente.

```Console
CommerceScaleUnit.exe install -port 446 -SSLCertThumbprint "MySSLCertificateThumbprintOftenHasNumbers" -RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" -AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" -RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" -CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" -RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" -TrustSqlServerCertificate -Config "Contoso.StoreSystemSetup.xml"
```

> [!NOTE]
> Todavía se requiere un archivo de configuración para CSU (autohospedado).

El siguiente comando es un comando más completo que ejecuta el instalador del archivo ejecutable con algunos parámetros alternativos.

```Console
CommerceScaleUnit.exe install -Port 446 -SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" -AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" -RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" -CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" -RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" -TrustSqlServerCertificate -Verbosity 0 -Config "Contoso.StoreSystemSetup.xml"
```

El siguiente comando especifica los parámetros necesarios para omitir las comprobaciones de requisitos previos durante una instalación estándar. 

> [!NOTE]
> No se recomienda omitir comprobaciones sin realizar pruebas exhaustivas con antelación o en situaciones de desarrollo.


```Console
CommerceScaleUnit.exe installer -skipscaleunithealthcheck -skipcertcheck -skipaadcredentialscheck -skipschannelcheck -skipiischeck -skipnetcorebundlecheck -skipsqlservercheck -skipnetframeworkcheck -skipversioncheck -skipurlcheck -Config "Contoso.StoreSystemSetup.xml" -SSLCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -AsyncClientCertFullPath "store://My/LocalMachine?FindByThumbprint=MySSLCertificateThumbprintOftenHasNumbers" -RetailServerCertFullPath "store://My/LocalMachine?FindByThumbprint=MyCertificateThumbprintUsedByRetailServer" -AsyncClientAADClientID "MyAAD-Client-IDFor-AsyncClient" -RetailServerAADClientID "MyAAD-Client-IDFor-RetailServer" -CPOSAADClientID "MyAAD-Client-IDFor-CloudPOS" -RetailServerAADResourceID "https://retailstorescaleunit.retailserver.com" -TrustSqlServerCertificate
```

Puede mezclar y combinar estos conceptos para lograr los resultados de instalación que desea.

<!--## Mass deployment examples using InTune

This section will be added in a future update.

## Mass deployment examples using System Center Configuration Manager (SCCM)

This section will be added in a future update.-->

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
