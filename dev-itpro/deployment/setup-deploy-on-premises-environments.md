---
title: Configurar e implementar entornos locales
description: "Este tema proporciona información acerca de cómo planificar, configurar e implementar un entorno local."
author: kfend
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: d100f6dbcbdf8f4c12ab04670fb598a88d48d84b
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: es-es
ms.lasthandoff: 08/10/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>Configurar e implementar entornos locales

Este documento describe cómo planificar la implementación, configurar la infraestructura, implementar Microsoft Dynamics 365 For Finance and Operations, Enterprise Edition (local).

## <a name="finance-and-operations-components"></a>Componentes de Finance and Operations

La aplicación de Finance and Operations consta de tres componentes principales:

- AOS (Application Object Server, servidores de objetos de Microsoft)
- Business Intelligence (BI)
- Informes financieros/Management Reporter

Estos componentes dependen del siguiente software del sistema:

- Microsoft Windows Server 2016
- Microsoft SQL Server 2016 SP1, que tiene las siguientes características:

    - La búsqueda de índice de texto completo está habilitada.
    - SQL Server Reporting Services (SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > La aplicación no se ejecutará si la búsqueda de texto completo no está habilitada.

- SQL Server Management Studio
- Microsoft Azure Service Fabric independiente
- Windows PowerShell 5.0 o superior
- Active Directory Federation Services (ADFS) en Windows Server 2016

  El controlador de dominio debe ser Windows Server 2012 R2 o posteriormente con un nivel funcional de dominio de 2012 R2 o superior

  Para obtener más información acerca de los niveles funcionales, consulte: 
  - [Cuáles son niveles funcionales de Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Comprender los niveles funcionales de Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Lifecycle Services

Los bits de Finance and Operations se distribuyen a través de Microsoft Dynamics Lifecycle Services (LCS). Antes de que pueda implementar, debe comprar las claves de licencia a través del canal [Contratos Enterprise](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) y configurar un proyecto local en LCS. Las implementaciones solo se pueden iniciar a través de LCS. Para obtener más información acerca de cómo configurar proyectos locales en LCS, consulte [Crear un proyecto local en Lifecycle Services](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Autentificación

La aplicación local funciona con el ADFS. Para interactuar con LCS, también debe configurar Azure Active Directory (Azure AD).

## <a name="standalone-service-fabric"></a>Service Fabric independiente

Finance and Operations usa Service Fabric independiente. Para obtener más información, consulte la [documentación de Service Fabric](/azure/service-fabric/).

## <a name="infrastructure"></a>Infraestructura

Finance and Operations está diseñado para trabajar en una arquitectura hiperconvergente. La configuración de hardware incluye los siguientes componentes:

- Clúster del Service Fabric independiente que se basa en máquinas virtuales (MV) de Windows Server 2016
- SQL Server (se admiten Clustered SQL y Always-On)
- ADFS para autenticación
- Recurso compartido de archivo de versión 3 de Server Message Block (SMB)
- Opcional: Microsoft Office Server 2017

Para obtener más información, consulte los [requisitos del sistema](../get-started/system-requirements.md) y las directrices de tamaño.

### <a name="hardware-layout"></a>Diseño de hardware

Planifique su infraestructura y el clúster del Service Fabric basado en el tamaño recomendado en [Tamaño del hardware para entornos locales](../get-started/hardware-sizing-on-premises-environments.md). Para obtener más información sobre cómo planificar el clúster del Service Fabric, consulte [Planifique y prepare la implementación del clúster del Service Fabric independiente](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

En la tabla siguiente se muestra un ejemplo del diseño de hardware. Este ejemplo se usa en este tema para mostrar la configuración.

> [!NOTE]
> El nodo principal del clúster del Service Fabric debe tener al menos tres nodos. En este ejemplo, **OrchestratorType** se designa como el tipo de nodo principal.

| Propósito del equipo                                 | Nombre del equipo    | Dirección IP    |
|-------------------------------------------------|-----------------|---------------|
| Controlador de dominio                               | DAX7SQLAODC1    | 10.179.108.2  |
| ADFS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| Servidor de archivos                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| Clúster del SQL Always-On                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Cliente                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Clúster del Service Fabric/AOS 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Clúster del Service Fabric/AOS 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Clúster del Service Fabric/AOS 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Clúster del Service Fabric/Orchestrator 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Clúster del Service Fabric/Orchestrator 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Clúster del Service Fabric/Orchestrator 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Clúster del Service Fabric/nodo de Management Reporter | SQLAOSMR1       | 10.179.108.18 |
| Clúster del Service Fabric/nodo SSRS                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Configuración

### <a name="prerequisites"></a>Requisitos previos

Antes de comenzar la configuración, debe cumplir los siguientes requisitos previos. La configuración de estos requisitos previos se encuentra fuera del ámbito de este documento.

- Active Directory Domain Services (ADDS) está instalado y configurado en la red.
- ADFS está implementado.
- SQL Server, SSRS y Management Studio están instalados.

### <a name="overview"></a>Información general

Deben completarse los siguientes pasos para configurar la infraestructura para Finance and Operations.

1. Planificar su nombre de dominio y zonas DNS
2. Planificar y adquirir sus certificados
3. Planificar sus usuarios y cuentas de servicio
4. Crear zonas DNS y agregar los registros A
5. Unir las MV al dominio
6. Agregar el software necesario a las MV
7. Descargar las secuencias de comandos de configuración desde LCS
8. Describir su configuración
9. Instalar certificados
10. Configurar un clúster del Service Fabric independiente
11. Configurar la conectividad LCS para el inquilino
12. Configurar el almacenamiento de archivos
13. Configurar SQL Server
14. Configurar las bases de datos
15. Cifrar las credenciales
16. Configurar SSRS
17. Configurar el ADFS

### <a name="plan-your-domain-name-and-dns-zones"></a>Planificar su nombre de dominio y zonas DNS

Le recomendamos que use un nombre de dominio público registrado para la instalación de su producción de AOS. De esa manera, puede tener acceso fuera de la red, si se requiere acceso exterior.

Por ejemplo, si el dominio de su empresa es contoso.com, su zona para Finance and Operations (local) podría ser d365ffo.onprem.contoso.com y los nombres de host podrían ser los siguientes:

- ax.d365ffo.onprem.contoso.com para los equipos de AOS
- sf.d365ffo.onprem.contoso.com para el clúster del Service Fabric

### <a name="plan-and-acquire-your-certificates"></a>Planificar y adquirir sus certificados

Los certificados de la capa de sockets seguros (SSL) son obligatorios para garantizar un clúster del Service Fabric y todas las aplicaciones que se implementan. Para su producción y cargas de trabajo de espacio aislado, le recomendamos que adquiera certificados de una entidad emisora de certificados, como [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/) [Symantec](https://www.websecurity.symantec.com/ssl-certificate), [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate) o [GlobalSign](https://www.globalsign.com/en/ssl/). Si su dominio se configura con [servicios de certificados de Active Directory](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx) (ADCS), puede crear certificados a través de ADCS. Cada certificado debe contener una clave privada creada para el intercambio de claves, y se debe poder exportar en un archivo Intercambio de información personal (.pfx).

Los certificados autofirmados solo se pueden usar para fines de pruebas. Para mayor comodidad, las secuencias de comandos de configuración incluyen secuencias de comandos que generan y exportan certificados autofirmados. Como hemos mencionado, estos certificados se deben usar solo para fines de pruebas.

| Propósito                                      | Explicación | Requisitos adicionales |
|----------------------------------------------|-------------|-------------------------|
| Certificado SSL de SQL Server                   | Este certificado se utiliza para cifrar los datos que se tramiten a través de una red entre una instancia de SQL Server y una aplicación del cliente. | <p>El nombre de dominio deĺ certificado debe coincidir con el nombre de dominio completo (FQDN) de la instancia o escucha de SQL Server.</p><p>Por ejemplo, si la escucha de SQL se hospeda en el equipo DAX7SQLAOSQLA, el nombre DNS del certificado es DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Certificado del servidor de Service Fabric            | Este certificado se usa para ayudarle a garantizar la comunicación de nodo a nodo entre los nodos de Service Fabric. Este certificado también se usa como el certificado del servidor que se muestra al cliente que se conecta al clúster. | <p>El nombre de dominio del certificado debe coincidir con la zona DNS en la que se hospedan AOS y Service Fabric.</p><p>Por ejemplo, el nombre de dominio del certificado puede ser \*.onprem.contoso.com o \*.contoso.com.</p><p>Si usa un certificado comodín, el carácter comodín se aplica a un único nivel. Debe aplicarse un subdominio, nombre alternativo del sujeto (SAN), al certificado si es más de un nivel, como \*.contoso.com en el ejemplo anterior.</p> |
| Certificado del cliente de Service Fabric            | Los clientes usan este certificado para visualizar y gestionar el clúster del Service Fabric. | |
| Certificado de cifrado                     | Este certificado se usa para cifrar la información confidencial como la contraseña de SQL Server y las contraseñas de la cuenta del usuario. | <p>El uso de la clave del certificado debe incluir el cifrado de datos (10) y no debe incluir la autenticación del servidor o la autenticación del cliente.</p><p>Para obtener más información, consulte [Administrar secretos en aplicaciones de Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| Certificado SSL de AOS                          | <p>Este certificado se usa como el certificado del servidor que se muestra al cliente para el sitio web de AOS. También se usa para habilitar los certificados de Windows Communication Foundation (WCF)/Protocolo simple de acceso a objetos (SOAP).</p><p>El certificado del servidor de Service Fabric se puede usar aquí si es un certificado comodín.</p> | <p>El nombre de dominio del certificado debe coincidir con la zona DNS en la que se hospedan AOS y Service Fabric.</p><p>Por ejemplo, el nombre de dominio del certificado puede ser \*d365ffo.onprem.contoso.com, \*2.onprem.contoso.com o \*.contoso.com.</p><p>Si usa un certificado comodín, el comodín se aplica a un único nivel. Debe aplicarse un subdominio, SAN, al certificado si es más de un nivel, como \*.contoso.com en el ejemplo anterior.</p> |
| Certificado de autenticación de sesión           | AOS usa este certificado para ayudar a asegurar la información de la sesión de un usuario. | Este también es el certificado **File Share** que se usará en el momento de la implementación desde LCS. |
| Certificado de cifrado de datos y de firma de datos | AOS usa estos certificados para cifrar la información confidencial. | |
| Certificado de cliente de informes financieros       | Este certificado se usa para ayudarle a garantizar la comunicación entre los servicios de informes financieros y AOS. | |
| Certificado de informes                        | Este certificado se usa para ayudarle a garantizar la comunicación entre SSRS y AOS. | |
| Certificado de agemte local           | <p>Este certificado se usa para ayudarle a garantizar la comunicación entre un agente local que se hospede en entornos locales y LCS.</p><p>Este certificado permite al agente local actuar en nombre de su inquilino de Azure AD y comunicarse con LCS para orquestar y supervisar las implementaciones.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>Planificar sus usuarios y cuentas de servicio

Debe crear varias cuentas de usuario o servicio para trabajar en Finance and Operations (local). Debe crear una combinación de cuentas de servicio administradas de grupo (gMSAs), cuentas de dominio y cuentas de SQL. La siguiente tabla muestra las cuentas de usuario, su propósito y los nombres de ejemplo que se usarán en este tema.

| Cuenta de usuario                                            | Tipo           | Propósito | Nombre de usuario |
|---------------------------------------------------------|----------------|---------|-----------|
| Cuenta del servicio de aplicación de informes financieros         | gMSA           |         | Contoso\\svc-FRAS$ |
| Cuenta del servicio de proceso de informes financieros             | gMSA           |         | Contoso\\svc-FRPS$ |
| Cuenta del servicio de diseñador con un solo clic de informes financieros | gMSA           |         | Contoso\\svc-FRCO$ |
| Cuenta de servicio de AOS                                     | gMSA           | Este usuario se debe crear como garantía de futuro. Tenemos previsto habilitar AOS para trabajar con la gMSA en próximas versiones. Al crear este usuario en el momento de la configuración, ayudará a garantizar una transición perfecta a la gMSA. | Contoso\\svc-AXSF$ |
| Cuenta de servicio de AOS                                     | Cuenta de dominio | AOS utiliza a este usuario durante la liberación de GA. | Contoso\\AXServiceUser |
| Usuario Admin DB SQL de AOS                                   | Usuario de SQL       | Finance and Operations usa este usuario para autenticar con SQL\*. Este usuario también será reemplazado por el usuario de gMSA en futuras versiones. | AXDBAdmin |
| Cuenta de servicio de agente de implementación local                  | gMSA           | El agente local usa esta cuenta para orquestar la implementación local en distintos nodos. | Contoso\\Svc-LocalAgent$ |

\* El nombre de usuario de SQL y la contraseña para la autenticación de SQL están aseguradas, ya que se cifran y almacenan en un recurso compartido de archivo.

### <a name="create-dns-zones-and-add-a-records"></a>Crear zonas DNS y agregar los registros A

DNS se integra con AD DS y le permiten organizar, administrar y buscar recursos en una red. Cree una zona de búsqueda directa DNS y los registros A para el nombre de host de AOS y el clúster del Service Fabric. En esta configuración de ejemplo, el nombre de la zona DNS es d365ffo.onprem.contoso.com y los registros A/nombres de host son los siguientes:

- **ax**.d365ffo.onprem.contoso.com para los equipos de AOS
- **sf**.d365ffo.onprem.contoso.com para el clúster del Service Fabric

#### <a name="add-a-dns-zone"></a>Agregar una zona DNS

Realice el siguiente procedimiento para agregar una zona DNS.

1. Inicie sesión en el equipo del controlador de dominio, haga clic en **Inicio** e inicie DNS Manager escribiendo **dnsmgmt.msc**.
2. Haga clic con el botón secundario en el nombre del controlador de dominio y luego haga clic en **Zona nueva** \> **Siguiente**.
3. Seleccione **Zona principal**.
4. Deje seleccionada la casilla de verificación **Almacenar la zona en Active Directory (disponible solo si el servidor DNS es un controlador de dominio que se puede escribir)** y luego haga clic en **Siguiente**.
5. Seleccione **A todos los servidores DNS que se ejecuten en controladores de dominio en este dominio: Contoso.com** y luego haga clic en **Siguiente**.
6. Seleccione **Zona de búsqueda directa** y luego haga clic en **Siguiente**.
7. Especifique el nombre de la zona para su configuración y luego haga clic en **Siguiente**. Por ejemplo, introduzca **d365ffo.onprem.contoso.com**.
8. Seleccione **No permitir actualizaciones dinámicas** y luego haga clic en **Siguiente**.

#### <a name="set-up-an-a-record-for-aos"></a>Establecer un registro A para AOS

En la nueva zona DNS, cree un registro A denominado **ax.d365ffo.onprem.contoso.com** para **cada** nodo de clúster del Service Fabric del tipo **AOSNodeType** . No cree registros A para los otros tipos de nodo.

1. Haga clic con el botón derecho en la nueva zona y luego haga clic en **Nuevo host**.
2. Introduzca el nombre y la dirección IP del nodo del Service Fabric (por ejemplo, 10.179.108.12) y luego haga clic en **Agregar host**.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Establecer un registro A para Orchestrator

En la nueva zona DNS, cree un registro A denominado **sf.d365ffo.onprem.contoso.com** para **cada** nodo de clúster del Service Fabric del tipo **OrchestratorType** . No cree registros A para los otros tipos de nodo.

1. Haga clic con el botón derecho en la nueva zona y luego haga clic en **Nuevo host**.
2. Introduzca el nombre y la dirección IP del nodo del Service Fabric (por ejemplo, 10.179.108.15) y luego haga clic en **Agregar host**.

#### <a name="join-vms-to-the-domain"></a>Unir las MV al dominio

Una cada una de las MV al dominio siguiendo los pasos en [Cómo unir Windows Server 2016 a un dominio de Active Directory](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). De forma alternativa, utilice la secuencia de comandos de Windows PowerShell.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
Una vez que las MV se unan al dominio, agregue las cuentas de servicios AOS (Contoso\svc-AXSF$ , Contoso\svc-AXSF$) al grupo local de administradores. Puede comprobar el artículo [Agregar un miembro al grupo local](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx) para obtener información sobre cómo hacer esto.

#### <a name="disable-user-access-control"></a>Deshabilitar el control de acceso del usuario 

Ejecute la siguiente secuencia de comandos para deshabilitar el control de acceso del usuario en **cada** nodo del Service Fabric.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> Debe reiniciar el nodo una vez que la secuencia de comandos se complete correctamente.

#### <a name="add-prerequisite-software-to-vms"></a>Agregar el software necesario a las MV

La siguiente tabla muestra el software necesario que se debe aplicar a los equipos de cada tipo de nodo.

> [!NOTE]
> Tendrá que reiniciar el equipo después de instalar los componentes.

| Tipo de nodo | Componente | Comando |
|-----------|-----------|---------|
| AOS       | SNAC - Controlador ODBC | Consulte [Controlador ODBC 13.1 para Microsoft SQL Server - Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| AOS       | La versión 2.0-3.5 (CLR 2.0) de Microsoft .NET Framework | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AOS       | La versión 4.0-4.6 (CLR 4.0) de Microsoft .NET Framework | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AOS       | Servicios de Internet Information Server (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| AOS       | Microsoft SQL Server Management Studio 2016 | |
| AOS       | Paquetes Microsoft Visual C++ Redistributable para Microsoft Visual Studio 2013 | Consulte [Paquetes Microsoft Visual C++ Redistributable para Microsoft Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560) |
| AOS       | Motor de base de datos redistribuible de Microsoft Access 2010 | Consulte [Motor de base de datos redistribuible de Microsoft Access 2010](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| inteligencia empresarial        | La versión 2.0-3.5 (CLR 2.0) de .NET Framework | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| inteligencia empresarial        | La versión 4.0-4.6 (CLR 4.0) de .NET Framework | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| inteligencia empresarial        | Microsoft SQL Server 2016 SP1 | |
| inteligencia empresarial        | Management Studio 2016 | |
| inteligencia empresarial        | SQL Server Reporting Services 2016 en modo **Nativo** | |
| MR        | La versión 2.0-3.5 (CLR 2.0) de .NET Framework | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | La versión 4.0-4.6 (CLR 4.0) de .NET Framework | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Paquetes Visual C++ Redistributable para Visual Studio 2013 | Consulte [Paquetes Microsoft Visual C++ Redistributable para Microsoft Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560) |

#### <a name="download-setup-scripts-from-lcs"></a>Descargar las secuencias de comandos de configuración desde LCS

Hemos proporcionado varias secuencias de comandos para ayudar a mejorar la experiencia de configuración. Siga estos pasos para descargar las secuencias de comandos desde LCS.

1. Inicie sesión en LCS (<https://lcs.dynamics.com/v2>).
2. En el panel de información, haga clic en el icono **Biblioteca de activos compartidos**.
3. Haga clic en la pestaña **Modelo**.
4. En la cuadrícula, seleccione la fila **Dynamics 365 for Operations - Secuencias de comandos de implementaciones locales** .
5. Haga clic en **Versiones** y descargue la última versión de las secuencias de comandos.

### <a name="describe-your-configuration"></a>Describir su configuración

Esta sección proporciona información acerca de las secuencias de comandos que debe ejecutar. Las secuencias de comandos se describen en el orden en el que debe ejecutarlas. Para ejecutar las secuencias de comandos, rellene el archivo de plantillas en $(downloadPath)\\ConfigTemplate.xml. El archivo ConfigTemplate.xml describe los clústeres del Service Fabric, los certificados que se usan para configurarlos y las cuentas que deben conceder acceso a los certificados pertinentes. En el ejemplo provisto, los valores se rellenan para la infraestructura del ejemplo descrita en este tema. El archivo de plantillas se usará en la siguiente sección.

#### <a name="create-the-domain-account-for-a-service-user"></a>Cree la cuenta de dominio para un usuario del servicio

Ejecute el siguiente comando para crear la cuenta de usuario de dominio, contoso\\AXServiceUser.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>Crear gMSAs

1. Cambie el directorio a **$(DownloadPath)** y ejecute el siguiente comando de Windows PowerShell.

    > [!NOTE]
    > Esta secuencia de comandos no crea los usuarios. En su lugar, imprime los comandos que se deben ejecutar manualmente en el equipo del controlador de dominio.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Copie la salida del comando en una ventana de Windows PowerShell. Asegúrese de que se eliminan las interrupciones de línea y ejecute las líneas en el equipo de controlador de dominio de Active Directory mediante privilegios elevados (haga clic con el botón secundario y luego haga clic en **Ejecutar como administrador**).
3. Ejecute la siguiente secuencia de comandos en el equipo de controlador de dominio de Active Directory para validar que las cuentas se han creado correctamente. Asegúrese de que ejecuta la secuencia de comandos después de reemplazar el patrón que coincide con la convención de nomenclatura de las cuentas del servicio.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Ejecute la secuencia de comandos Export-AddGMSAsONVMScript.ps1 en el equipo cliente. Esta secuencia de comandos genera secuencias de comandos que se ejecutan en cada MV del Service Fabric de servicio y las agrega a una carpeta que se correspone con cada nombre de MV.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>Detener IIS

Use el Remote Desktop Protocol (RDP) para conectarse a cada MV del Service Fabric, y complete los pasos manuales en [Iniciar o detener el servidor Web (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). De forma alternativa, utilice la siguiente secuencia de comandos de Windows PowerShell mediante RDP para conectarse a cada MV del Service Fabric.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
_La función IIS debe instalarse pero deshabilitarse a medida que haya algunas dependencias para el dlls de IIS en el producto._

### <a name="install-certificates"></a>Instalar certificados

1. Si adquirió los certificados que se mostraban anteriormente en este tema desde un CA válido, rellene el nombre de archivo .pfx y la huella digital para los certificados en el archivo de .pfx para los certificados en el archivo ConfigTemplate.xml. Establezca el atributo **generateSelfSignedCert** en **Falso** y el atributo **exportable** en **Falso**. Copie los archivos .pfx a la carpeta de $(DownloadPath)\\InfrastructureScripts\\Certs.
2. Si utiliza los certificados autofirmados (solo para fines de pruebas), ejecute la siguiente secuencia de comandos. Para crear certificados autofirmados, en el archivo de ConfigTemplate.xml, asegúrese de que **generateSelfSignedCert** está establecido en **Verdadero** y que **exportable** está establecido en **Verdadero**. La secuencia de comandos actualizará el XML con la huella digital para certificados.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Exporte los nuevos certificados con la clave privada (el archivo .pfx). Use la siguiente secuencia de comandos para generar y ejecutar los comandos de exportación en Windows PowerShell. Los archivos .pfx se colocarán en la carpeta Certs.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Los certificados deben haberse instalado y estar presentes en el cert:\\CurrentUser\\My. Los certificados también deben poderse exportar.

    Si utiliza certificados autofirmados, omita a la siguiente sección. No tiene que completar este procedimiento.

4. Una vez que exporte o copie los archivos .pfx en la carpeta de $(DownloadPath)\\InfrastructureScript\\Certs, ejecute los siguientes comandos para generar secuencias de comandos que se colocarán en las carpetas que correspondan a las MV.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. Copie las secuencias de comandos en cada carpeta de las MV que correspondas al nombre de la carpeta.
6. En cada MV, ejecute las siguientes secuencias de comandos en el orden en que aparezcan.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Configurar un clúster del Service Fabric independiente

1. Ejecute el sigiuente comando para generar el archivo ClusterConfig.json.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    Para obtener más información, consulte [Paso 1B: Crear un clúster de varios equipos](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster), [Crear un clúster independiente en Windows mediante certificados X.509](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security) y [Crear un clúster independiente que se ejecute en Windows Server](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Descargue el [Paquete de instalación del Service Fabric independiente](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) en uno de sus nodos del Service Fabric. Una vez que se haya descargado el archivo zip, desbloquéelo haciendo clic con el botón secundario en el archivo zip y luego haciendo clic en **Propiedades**. En el cuadro de diálogo, seleccione la casilla de verificación **Desbloquear** en la parte inferior derecha.
3. Copie el archivo zip en uno de los nodos del clúster del Service Fabric y descomprímalo.
4. Ejecute los siguientes comandos para crear una regla de entrada en el firewall en los puertos 443 y 445 en todos los nodos.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Ejecute los siguientes comandos para crear una regla de entrada en el firewall en el puerto 80 solo para el nodo SSRS.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Copie el archivo ClusterConfig.json a su ubicación de instalación descomprimida de Service Fabric independiente.
7. Vaya hasta la ubicación de instalación descomprimida en Windows PowerShell mediante privilegios elevados, y ejecute el siguiente comando para probar ClusterConfig.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Si la prueba es correcta, ejecute el siguiente comando para implementar el clúster.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. Una vez creado el clúster, abra el explorador del Service Fabric en cualquier equipo cliente para validar la instalación:

    1. Instale el certificado de cliente del Service Fabric en CurrentUser\\My si no está aún instalado.
    2. Vaya **Configuración de IE** \> **Modo de compatibilidad** y desactive la casilla de verificación **Mostrar sitios de Intranet en modo de compatibilidad** .
    3. Vaya a `https://sf.d365ffo.onprem.contoso.com:19080`, donde sf.d365ffo.onprem.contoso.com es el nombre host del clúster del Service Fabric que se especifica en la zona. Si no se configura la resolución de nombres DNS, utilice la dirección IP del equipo.
    4. Seleccione el certificado del cliente. Aparece la página **Explorador del Service Fabric**.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Configurar la conectividad LCS para el inquilino

La implementación y el mantenimiento de Finance and Operations se orquestran a través de LCS mediante un agente local. Para establecer la conectividad desde LCS para el inquilino de Finance and Operations, debe configurar un certificado que permita al agente local actuar en nombre el inquilino de Azure AD (por ejemplo, Contoso.Onmicrosoft.com).

Use el certificado de agente local que adquirió de un CA o el certificado autofirmado que generó mediante las secuencias de comandos.

Solo las cuentas de usuario que tienen el rol del directorio de administrador global pueden agregar certificados para autorizar LCS. De forma predeterminada, la persona se registra en Microsoft Office 365 por su organización será el administrador global del directorio.

> [!NOTE]
> Debe configurar el certificado exactamente una vez por inquilino. Todos los entornos locales pueden usar el mismo certificado para conectarse con LCS.

1. Descargue e instale la última versión Azure PowerShell en un equipo cliente. Para obtener más información, consulte [Instalación y configuración de Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Inicie sesión en [el portal Azure del cliente](https://portal.azure.com) para comprobar que tiene el rol del directorio de administrador global.
3. Ejecute la siguiente secuencia de comandos desde $(DownloadPath)\\InfrastructureScripts.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Configurar el almacenamiento de archivos

Debe configurar dos recursos compartidos de archivos SMB 3.0 de alta disponibilidad. Para obtener más información sobre cómo habilitar SMB 3.0, consulte [Mejoras de seguridad SMB](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
La negociación del dialecto segura no puede detectar o evitar descargas de SMB 2.0 o 3.0 a SMB 1.0. Debido a esto, y para aprovechar todas las capacidades del cifrado SMB, le recomienda encarecidamente que deshabilite el servidor SMB 1.0

> [!NOTE]
> Para ayudar a garantizar que sus datos están protegidos mientras está en reposo en su entorno, el cifrado de disco BitLocker debe estar habilitado en cada equipo. Para obtener más información sobre cómo habilitar BitLocker, consulte [BitLocker: cómo implementar en Windows Server 2012 y superior](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- Un recurso compartido de archivos que almacena los documentos del usuario que se cargan a AOS (por ejemplo, \\\\DAX7SQLAOFILE1\\aos-storage).
- Un recurso compartido de archivos que almacena los archivos de creación y configuración más recientes para orquestrar la implementación (por ejemplo, \\\\DAX7SQLAOFILE1\\agent))

    > [!NOTE]
    > Mantenga esta ruta del recurso compartido de archivos lo más breve posible para evitar sobrepasar la longitud máxima de ruta en los archivos que se colocarán en el recurso compartido.

1. Ejecute el siguiente comando en el equipo del recurso compartido de archivos.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Configure el recurso compartido de archivos \\\\DAX7SQLAOFILE1\\aos-storage

2. En el administrador de servidores, seleccione **Servicios de archivo y almacenamiento** \> **Recursos compartidos**.
3. Haga clic en **Tareas** \> **Nuevo recurso compartido** para crear un nuevo recurso compartido con el nombre **aos-storage**.
4. Conceda los permisos **Modificar** a cada equipo en el clúster del Service Fabric, excepto **OrchestratorNodeType**.
5. Conceda los permisos **Modificar** al usuario de dominio de AOS (contoso\\AXServiceUser) y al usuario de gMSA (contoso\\svc-AXSF).

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Configure el recurso compartido de archivos \\\\DAX7SQLAOFILE1\\agent

6. Vuelva al administrador de servidores, seleccione **Servicios de archivo y almacenamiento** \> **Recursos compartidos**.
7. Haga clic en **Tareas** \> **Nuevo recurso compartido** para crear un nuevo recurso compartido con el nombre **agent**.
8. Conceda los permisos **Control total** al usuario de gMSA para el agente de implementación local (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Configurar SQL Server

1. Instale SQL Server 2016 SP1 con alta disponibilidad, ya sea como clústeres SQL que incluyen una red de aŕea de almacenamiento (SAN) o en una configuración Always-On.  Compruebe que **el motor de base de datos, Reporting Services, la búsqueda de texto completo** y **las herramientas de administración** ya están instalados.
> [!NOTE]
> Asegúrese de que SQL Always On está configurado de acuerdo con [Seleccionar página de sincronización de datos inicial (asistentes de grupo de disponibilidad Always On)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards) y siga [Para preparar las bases de datos secundarias manualmente](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Ejecutar el servicio de SQL como usuario de dominio.
3. Obtenga un certificado SSL de un CA para configurar Finance and Operations. Puede crear y usar un certificado autofirmado para fines de pruebas.

**Certificado autofirmado para instancia Clustered SQL**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Certificado autofirmado para instancia Always-On**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. Al usar el certificado, complete los pasos de [Cómo habilitar el cifrado SSL para una instancia de SQL Server mediante Microsoft Management Console](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) para configurar SSL en SQL Server.
5. Siga estos pasos para cada nodo del clúster. Asegúrese de que realiza los cambios en el nodo no activo y lo conmuta por error después de que se realicen los cambios.

    1. Importe el certificado en LocalMachine\\My.
    2. Conceda permisos del certificado a la cuenta de servicio que se utiliza para ejecutar el servicio de SQL. En Microsoft Management Console (MMC), haga clic con el botón secundario en el certificado (certlm.msc) y luego haga clic en **Tareas** \> **Administrar claves privadas**.
    3. Agregue la huella digital del certificado a HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\Certificate.
    4. En Microsoft SQL Server Configuration Managerr, establezca **ForceEncryption** en **Sí**.

6. Exporte la clave pública del certificado (el archivo .cer), y instálela en la raíz de confianza de cada nodo del Service Fabric.

### <a name="configure-the-orchestratordata-database"></a>Configure la base de datos OrchestratorData

1.  Cree una base de datos vacía y nómbrela **OrchestratorData**. El agente local usará esta base de datos para orquestar implementaciones.
2.  Conceda al agente local gMSA permisos (svc-LocalAgent$)  **db\_owner** en la base de datos:

    1. En el árbol, expanda el nombre del servidor, expanda **Seguridad** \> **Inicios de sesión** y luego haga clic con el botón secundario, y haga clic en **Nuevo inicio de sesión**.

        ![Nuevo comando de inicio de sesión](./media/OPSetup_01_NewLogin.png)


    2. Busque la cuenta de servicio **svc-LocalAgent$**. Haga clic en **Ubicaciones**, seleccione **Directorio entero** y luego haga clic en **Tipos de objeto** y seleccione **Cuenta de servicio**.

        ![Seleccione el cuadro de diálogo de usuario, cuenta de servicio o grupo](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. Establezca **Asignar ServerRole** en **Público**.
    4. Asigne el permiso de rol de la base de datos **db\_owner** a la base de datos OrchestratorData.

### <a name="configure-the-finance-and-operations-database"></a>Configure la base de datos de Finance and Operations.

1. Inicie sesión en LCS (<https://lcs.dynamics.com/v2>).
2. En el panel de información, haga clic en el icono **Biblioteca de activos compartidos**.
3. Haga clic en la pestaña **Modelo**. 
4. En la cuadrícula, haga clic en la fila **Dynamics 365 for Operations (local), Enterprise Edición - Datos de demostración** para descargar el código postal.
5. El código postal contiene los archivos .bak de datos vacíos y de demostración. Escoja el archivo .bak apropiado en función de sus necesidades. Por ejemplo, si necesita datos de demostración, restaure el archivo AxBootstrapDB_Demodata.bak. 
6. Restaure la base de datos de AxBootstrapDB_DemoData.bak
7. Cambie el nombre de la base de datos **AXDBRAIN**.
8. Ejecute las siguientes consultas en la base de datos restaurada.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Actualice los achivos de la base de datos:

    1. Haga clic con el botón derecho en la base de datos y luego haga clic en **Propiedades**.
    2. Haga clic en **Archivos** para cambiar las propiedades del archivo de la base de datos.
    3. En el campo **Tamaño inicial (MB)**, introduzca un valor superior a 5120.

        ![Cuadro de diálogo Propiedades de la base de datos](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. Para **AXDBBuild\_Data**, establezca el campo **Crecimiento automático/maximizar** a **200** megabytes (MB).
    5. Para **AXDBBuild\_Log**, establezca el campo **Crecimiento automático/maximizar** a **500** MB.

        ![Cambie el cuadro de diálogo Crecimiento automático](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Cree un nuevo usuario que tenga habilitada la autenticación de SQL (axdbadmin).
6. Use la información de la siguiente tabla para asignar los usuarios y los roles de la base de datos.

    | Usuario             | Tipo    | Rol de base de datos |
    |------------------|---------|---------------|
    | svc-AXSF$        | gMSA    | db\_owner     |
    | svc-LocalAgent$  | gMSA    | db\_owner     |
    | svc-FRPS$        | gMSA    | db\_owner     |
    | svc-FRAS$        | gMSA    | db\_owner     |
    | axdbadmin        | SqlUser | db\_owner     |

7. Brinde acceso al usuario svc-AXSF$ y al usuario SQL axdbadmin a los siguientes roles en la base de datos de tempdb:

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. En Management Studio, ejecute los siguientes comandos de Transact SQL (T-SQL):

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Ejecute el siguiente comando:
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>Configure la base de datos de informes financieros

1.  Cree una base de datos vacía y nómbrela **FinancialReporting**.
2.  Use la información de la siguiente tabla para asignar los usuarios y los roles de la base de datos.

    | Usuario             | Tipo | Rol de base de datos |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_owner     |
    | svc-FRPS$        | gMSA | db\_owner     |
    | svc-FRAS$        | gMSA | db\_owner     |

### <a name="encrypt-credentials"></a>Cifrar las credenciales

1. En cualquier equipo del cliente, instale el certificado de cifrado en el LocalMachine\\Mi almacén de certificados.
2. Conceda al usuario actual acceso de lectura a la clave privada de este certificado.
3. Cree el archivo Credentials.json como se muestra aquí.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** es la contraseña cifrada de usuario de dominio para el usuario de dominio de AOS (contoso\\axserviceuser).
    - **SqlUser** es el usuario cifrado de SQL (axdbadmin) que tiene acceso a la base de datos de Finance and Operations (AXDBRAIN) y **SqlPassword** es la contraseña cifrada de SQL.

4. Copie el archivo .json al recurso compartido de archivos SMB, \\\\AX7SQLAOFILE1\\agent\\Credentials\\Credentials.json.
5. Actualice el archivo Credentials.json con valores cifrados.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. En Credentials.json, sustituya **\<encryptedDomainUserPassword\>** por la contraseña cifrada del dominio.
    2. Sustituya **\<encryptedSqlUser\>** por el usuario de SQL cifrado de Finance and Operations.
    3. Sustituya **\<encryptedSqlPassword\>** por el usuario de SQL de Finance and Operations.
    
### <a name="set-up-ssrs"></a>Configurar SSRS

1.  Antes de empezar, asegúrese de que están instalados los requisitos previos que aparecen al principio de este tema.
2.  Siga los pasos para [Configurar SQL Server Reporting Services para una implementación local](../analytics/configure-ssrs-on-premises.md)

### <a name="configure-ad-fs"></a>Configurar el ADFS

Antes de que pueda completar este procedimiento, el ADFS debe implementarse en Windows Server 2016. Para obtener información sobre la implementación del ADFS, consulte [la Guía de implementación de Windows Server 2016 y la Guía de implementación de ADFS 2012 R2](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

Finance and Operations requiere una configuración adicional más allá de la configuración inmediata predeterminada de ADFS. Para los pasos siguientes, Windows PowerShell se ejecuta en un equipo que tenga instalado el servicio de rol de ADFS. La cuenta de usuario debe tener suficientes permisos para administrar ADFS. Por ejemplo, el usuario debe tener una cuenta de administrador de dominios.

1. Configurar el identificador de ADFS para que coincida con el emisor de token de ADFS.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Debe deshabilitar la Autenticación integrada de Windows (WIA) para conexiones de autenticación de la intranet a menos que haya configurado ADFS para entornos mixtos. Para obtener más información sobre cómo configurar WIA para que se pueda usar con ADFS, consulte [Configurar exploradores que usa la Autenticación integrada de Windows (WIA) con ADFS](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. Para iniciar sesión, la dirección de correo electrónico del usuario debe ser una entrada de autenticación aceptable.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

Para que el ADFS confíe en Finance and Operations para el intercambio de autenticación, deben registrarse varias entradas de la aplicación en ADFS bajo un grupo de aplicaciones de ADFS. Para acelerar el proceso de configuración y ayudar a reducir errores, puede usar la siguiente secuencia de comandos para el registro. Copie la secuencia de comandos Publish-ADFSApplicationGroup.ps1 y el directorio D365FO-OP en un equipo que tenga instalado el servicio de rol de ADFS. A continuación, ejecute la secuencia de comandos mediante una cuenta de usuario, como una cuenta de administrador, que tenga permisos suficientes para gestionar el ADFS. Para obtener más información sobre cómo usar la secuencia de comandos, consulte la documentación que se muestra en la secuencia de comandos. Anote los id. del cliente que se especificaron en la salida, ya que en un paso posterior se le pedirán para esta información en el LCS.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

La consola de gestión de ADFS debe parecerse a la siguiente ilustración. Para abrir el administrador de servidores, haga clic en **Herramientas** \> **Gestión de ADFS** y, en la parte inferior de la vista de árbol de la izquierda, haga clic en **Grupos de aplicaciones**. Haga doble clic en el grupo de aplicaciones para ver más detalles.

![Propiedades de grupo de la aplicación](./media/OPSetup_05_ApplicatioGroupProperties.png)

Finalmente, para una comprobación de estado, asegúrese de que puede acceder a la dirección URL de la configuración OpenID de ADFS en un nodo de Service Fabric del tipo **AOSNodeType** navegando hasta `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` en un explorador web. Si recibe un mensaje que indica que el sitio no es seguro, no ha agregado su certificado SSL de ADFS al almacén de entidades de certificación raíz de confianza. Este paso se describe en la guía de implementación de ADFS. Si accede correctamente a la dirección URL, se devuelve un archivo JavaScript Object Notation (JSON) que contiene la configuración de ADFS, y verá que la dirección URL de ADFS es de confianza.

Con esto, la configuración de la infraestructura está completa. Las siguientes secciones describen cómo navegar hasta [LCS](https://lcs.dynamics.com) para configurar su conector e implementar su entorno Dynamics 365 for Finance and Operations.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Configure el conector instalar y el agente local

1. Inicie sesión en [LCS](https://lcs.dynamics.com/) y abra el proyecto de implementación local.
2. En el menú de hamburguesa, haga clic en **Configuración del proyecto**.

    ![Comando de configuración del proyecto](./media/OPSetup_06_ProjectSettings.png)

3. Haga clic en **Conector de On-Premises**.
4. Haga clic en **Agregar** para crear un nuevo conector
5. En la pestaña **Configurar infraestructura del host**, descargue el instalador del agente.

    ![Descargue el botón del instalador del agente en el pestaña Configurar infraestructura del host](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Compruebe que es archivo zip está desbloqueado. Haga clic con el botón secundario en el archivo **Propiedades** y luego seleccione **Desbloquear**.
7. Descomprima el instalador del agente en uno de los nodos de Service Fabrice del tipo **OrchestratorType** .
8. En la pestaña **Configurar agente**, especifique los parámetros de configuración.
9. Guarde la configuración y luego haga clic en **Descargue configuraciones** para descargar el archivo de configuración localagent-config.json.

    ![Descargue el botón de configuración en la pestaña Configurar agente](./media/OPSetup_08_DownloadConfigurations.png)

10. Copie el archivo localagent-config.json en el equipo en el que se encuentra el paquete del instalador del agente.
11. En una ventana de indicación de comando, ejecute el siguiente comando navegando hasta la carpeta que contiene el instalador del agente.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > El usuario que ejecute este comando debe tener permisos **db\_owner** en la base de datos OrchestratorData.
    
12. Una vez que el agente local esté instalado correctamente, vaya de nuevo a su conector de On-Premises en LCS.
13. En la pestaña **Validar configuración**, haga clic en el botón **Agente de mensaje** . Esto probará la conectividad LCS de su agente local. Cuando la conexión se establezca con éxito, la página tendrá el siguiente gráfico.

     ![Validar agente](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Implemente su entorno Dynamics 365 for Finance and Operations (local)

1. Vaya al proyecto local en LCS, vaya **Entorno**, **Espacio aislado** y haga clic en **Configurar**
2. Seleccione la **Topología de entorno** y vaya al ayudante para iniciar su implementación.
3. El agente local recogerá la solicitud de implementación, pondrá en marcha la implementación y volverá a comunicarse con LCS cuando esté listo.

