---
title: Requisitos del sistema
description: "Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, para implementaciones locales y en la nube."
author: sericks007
manager: AnnBe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 871ba89973f6af341c536f67db056bebb54600b3
ms.contentlocale: es-es
ms.lasthandoff: 07/25/2017

---

# <a name="system-requirements"></a>Requisitos del sistema

[!include[banner](../includes/banner.md)]


Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, para implementaciones locales y en la nube. Antes de instalar Finance and Operations, si es necesario, compruebe que el sistema con el que trabaja cumple o supera los requisitos mínimos de red, hardware y software.


## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office compatibles
Las siguientes aplicaciones de Office se admiten en implementaciones locales y en la nube de Finance and Operations.
-   Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac. Para obtener más información acerca de los requisitos de la versión, consulte [la solución de problemas de la integración de Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.

# <a name="system-requirements-specific-to-cloud-deployments"></a>Requisitos del sistema específicos de implementaciones en la nube
## <a name="network-requirements"></a>Requisitos de red
-   Finance and Operations está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos. Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Finance and Operations. Se recomienda que pruebe la latencia de red en <http://www.azurespeed.com>.
-   Los requisitos del ancho de banda para Dynamics 365 for Finance and Operations dependen de su caso. La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps). Sin embargo, para las situaciones con requisitos de carga elevados, como los espacios de trabajo o las situaciones que implican una personalización amplia, se recomienda más ancho de banda.

En general, Finance and Operations está optimizado para Internet. El número de acciones de ida y vuelta de un cliente de explorador al centro de datos de Azure es muy pequeño y se comprime la carga completa. 

> [!WARNING]
> No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es muy difícil de calcular. Para los clientes que están preocupados por los requisitos del ancho de banda, use una versión preliminar de Finance and Operations.

## <a name="net-framework-requirements"></a>Requisitos de .NET Framework
Finance and Operations requiere la versión 4.6.2 de .NET Framework para todas las aplicaciones de un solo clic como el agente de ruta del documento. Para obtener instrucciones de instalación, consulte [Instalación de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-web-browsers"></a>Exploradores web compatibles
La aplicación web se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:


-   Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
-   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
-   Google Chrome (la versión disponible publicada más recientemente) en Windows 10, Windows 8.1, Windows 8, Windows 7 o la tableta Google Nexus 10
-   Apple Safari (la versión disponible publicada más recientemente) en Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) o 10.12 (Sierra) o Apple iPad

Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software. 

> [!NOTE]
> -   Para tomar las imágenes generadas en el Grabador de tareas e incluirlas en los documentos generados por Microsoft Word, debe tener una versión preliminar de una extensión de Chrome instalada. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
> -   El editor de flujo de trabajo se inicia como aplicación ClickOnce. Solo Microsoft Edge y Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnce. La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.
> -   El Diseñador de informes para informes financieros se inicia como aplicación ClickOnce. Requiere un sistema operativo compatible de 64 bits. Si está usando Chrome, debe instalar una extensión ClickOnce para descargar el cliente del diseñador de informes. Si está usando Chrome en modo incógnito, asegúrese de que la extensión ClickOnce está también activada para el modo incógnito.
> -   Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Exploradores web admitidos para Retail Cloud POS

Retail Cloud POS se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:

-   Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
-   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
-   Chrome (la versión disponible publicada recientemente) en Windows 10, Windows 8.1 o Windows 7

## <a name="retail-modern-pos-requirements"></a>Requisitos de Retail Modern POS
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   Retail Modern POS es una aplicación de 32 bits, pero se ejecutará en arquitecturas de x86 y de x64.
-   Retail Modern POS solo se admite en las ediciones Pro, Enterprise y Enterprise Long Term Servicing Branch (LTSB) de Windows 10.

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

-   La resolución compatible mínima es 1280 × 1024.
-   El equipo donde se ejecuta Retail Modern POS debe cumplir estos requisitos:
    -   Es necesario, como mínimo, un procesador de doble núcleo que se ejecute como mínimo a 2 gigahercios (GHz).
    -   Es necesario, como mínimo, 3 gigabytes (GB) de RAM.
    -   Debe tener acceso a Internet.

## <a name="retail-hardware-station-requirements"></a>Requisitos de Retail hardware station
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   Retail hardware station es una aplicación de 32 bits, pero se ejecutará en arquitecturas de x86 y de x64.
-   Retail hardware station se admite en los sistemas operativos siguientes:
    -   Las ediciones Professional, Enterprise y Ultimate de Windows 7 
    
    > [!NOTE]
    > Windows 7 solo se admite si Internet Explorer 11 está instalado manualmente en el sistema.

    -   Las ediciones Professional, Enterprise y Embedded de Windows 8.1 Update 1
    -   Ediciones Pro, Enterprise y Enterprise LTSB de Windows 10

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

El equipo debe cumplir todos los requisitos del sistema para instalar y usar los siguientes elementos:

-   Servicios de Internet Information Server (IIS)
-   Hardware de terceros

## <a name="retail-store-scale-unit-requirements"></a>Requisitos de Retail Store Scale Unit
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   Retail Store Scale Unit es una aplicación de 32 bits, pero se ejecutará en arquitecturas de x86 y de x64.
-   Retail Store Scale Unit se admite en los sistemas operativos siguientes:
    -   Las ediciones Professional, Enterprise y Ultimate de Windows 7
    -   Las ediciones Professional, Enterprise y Embedded de Windows 8.1 Update 1
    -   Ediciones Pro, Enterprise y Enterprise LTSB de Windows 10

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

-   4 GB de RAM
-   Velocidad de CPU pico de 1,6 GHz por núcleo (dos núcleos como mínimo).
-   Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio).

### <a name="recommended-system-requirements"></a>Requisitos del sistema recomendados

-   6 GB de RAM
-   Velocidad de CPU pico de 2,4 GHz i7 por núcleo (se recomiendan cuatro núcleos).
-   Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio).

## <a name="connector-requirements"></a>Requisitos de Connector
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   El Connector para Microsoft Dynamics AX tiene dos instaladores independientes, el **Servicio de Connector de Servidor Async** y el **Servicio en tiempo real para Dynamics AX 2012 R3**.
-   Ambos componentes son aplicaciones de 32 bits, pero funcionan en arquitecturas x86 y x64.
-   Ambos componentes son compatibles con los sistemas operativos siguientes:
    -   Las ediciones Professional, Enterprise y Ultimate de Windows 7
    -   Las ediciones Professional, Enterprise y Embedded de Windows 8.1 Update 1
    -   Ediciones Pro, Enterprise y Enterprise LTSB de Windows 10
    -   Windows Server 2012 R2, Windows Server 2016

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

-   2 GB de RAM, aunque se recomiendan 4 GB de RAM
-   Velocidad de CPU pico de 1,6 GHz por núcleo (dos núcleos como mínimo).
-   Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio).

## <a name="requirements-for-development-on-local-vms"></a>Requisitos de desarrollo en VM locales
Para obtener información acerca de los requisitos de desarrollo en las máquinas virtuales locales (VM), consulte [la ejecución de VM en las instalaciones](../dev-tools/access-instances.md).

# <a name="system-requirements-for-on-premises-deployments"></a>Requisitos del sistema para implementaciones locales

## <a name="network-requirements"></a>Requisitos de red
Finance and Operations (local) puede funcionar en redes que usan la versión 4 del protocolo de Internet (IPv4) o la versión 6 del protocolo de Internet (IPv6). Tenga en cuenta el entorno de red al planificar su sistema y siga las siguientes instrucciones.

### <a name="network-response-time"></a>Tiempo de respuesta de la red
La siguiente tabla enumera los requisitos mínimos de red para la conexión entre el explorador web y Application Object Server (AOS), y para la conexión entre el AOS y la base de datos en un sistema local.

| Valor     | Explorador web a AOS | AOS a base de datos                                            |
|-----------|--------------------|------------------------------------------------------------|
| Ancho de banda | 50 Kbps por usuario   | 100 Mbps                                                   |
| Latencia   | < 250-300 ms       | < 1 ms (solo LAN). El AOS y la base de datos tienen que ubicarse en el mismo lado. |

- Finance and Operations (local) está diseñado para redes que tengan una latencia de 250-300 milisegundos (ms) o menos. Esta latencia es la latencia de un cliente de explorador al centro de datos que aloja Finance and Operations.
- Los requisitos del ancho de banda para Finance and Operations (local) dependen de su caso. Las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps) entre el explorador y el servidor de Finance and Operations. Sin embargo, para las situaciones con requisitos de carga elevados, como los espacios de trabajo o las situaciones que implican una personalización amplia, se recomienda un mayor ancho de banda y depende del uso.
No se admiten implementaciones en las que el AOS y la base de datos SQL Server están en distintos centros de datos. El AOS y la base de datos de SQL Server tienen que ubicarse en el mismo lado. En general, Finance and Operations está optimizado para reducir recorridos de ida y vuelta del explorador al servidor. El número de recorridos de ida y vuelta de un cliente de explorador al centro de datos es de cero o uno para cada interacción del usuario, y se comprime la carga.

> [!WARNING]
> No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es muy difícil de calcular. Le recomendamos que use una simulación de la vida real frente a un entorno de no producción de Finance and Operations como el mejor medidor de rendimiento para su caso específico. 

### <a name="lan-environments"></a>Entornos LAN
En entornos de red de área local (LAN), Microsoft Remote Desktop en Microsoft Windows Server no es necesario para conectarse a Finance and Operations. Sin embargo, puede que sea necesario para las operaciones de mantenimiento en las MV que conforman las implementaciones de servidor.

### <a name="wan-environments"></a>Entornos WAN
En los entornos de red de área amplia (WAN), Remote Desktop en Windows Server no es necesario para conectarse a Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Requisitos de conectividad a Internet
Finance and Operations (local) no requiere conectividad a Internet de las estaciones de trabajo del usuario final. Sin embargo, algunas funciones no estarán disponibles sin conectividad a Internet.

| Cliente de explorador | Un escenario de intranet sin conectividad a Internet es un punto de diseño para la opción de implementación local. No estarán disponibles algunas funciones que requieren servicios en la nube, como las bibliotecas de la guía de ayuda y tareas en LCS. |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Servidor         | El nivel de AOS o Service Fabric debe poder comunicarse con LCS. El cliente basado en explorador local no requiere acceso a Internet.                                                                                |
| Telemetría      | Puede que los datos de telemetría se pierdan si hay largas interrupciones en la conectividad. Las interrupciones en la conectividad a LCS no afectan a la funcionalidad de las aplicaciones locales.                                                |
| LCS            | La conectividad a LCS es necesaria para la implementación, la implementación del código y las operaciones de mantenimiento.                                                                                                                                 |
## <a name="telemetry-data-transfer-to-the-cloud"></a>Los datos de telemetría se transfieren a la nube
La mayoría de la telemetría se almacena de forma local y se puede acceder mediante el Visor de eventos en Microsoft Windows. Un pequeño subconjunto de eventos de telemetría se transfiere al proceso de telemetría de Microsoft en la nube para diagnósticos. Los datos del cliente y los datos identificables del usuario final no forman parte de la telemetría enviada a Microsoft. Los nombres de MV se envían a Microsoft para ayudar en la administración y diagnósticos del entorno desde el portal LCS.

## <a name="domain-requirements"></a>Requisitos de dominio
Tenga en cuenta los siguientes requisitos del dominio al instalar Finance and Operations (local):

- Las máquinas virtuales que hospedan componentes de Finance and Operations (local) deben pertenecer a un dominio de Active Directory. Los servicios de dominio de Active Directory (AD DS) deben configurarse en modo nativo.
- Las máquinas virtuales que ejecutan componentes de Finance and Operations (local) deben tener acceso entre sí a los servicios de dominio de Active Directory configurados. 
- El controlador de dominio debe ejecutarse en Microsoft Windows Server 2016.

## <a name="hardware-requirements"></a>Requisitos de hardware
Esta sección describe el hardware necesario para ejecutar Finance and Operations (local).
En función de la configuración del sistema, la composición de los datos y las aplicaciones y funciones que decida usar, los requisitos reales de hardware variarán. A continuación se muestran algunos de los factores que podrían afectar a la selección del hardware adecuado para Finance and Operations (local):

- El número de transacciones por hora.
- El número de usuarios simultáneos.

## <a name="minimum-infrastructure-requirements"></a>Requisitos mínimos de la infraestructura
Finance and Operations (local) utiliza Microsoft Azure Service Fabric para alojar el AOS, el lote, la administración de datos, Management Reporter y los servicios Orchestrator del entorno. Microsoft SQL Server Reporting Services (SSRS) no se alojan en el clúster del Service Fabric.
SQL Server debe configurarse en una configuración HADRON de alta disponibilidad que tenga al menos dos nodos para el uso de la producción.
La ilustración siguiente muestra el número mínimo recomendado de nodos en el clúster del Service Fabric.

[![número recomendado de nodos para el clúster del Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Requisitos del procesador y la RAM
La siguiente tabla muestra el número de procesadores y la cantidad de memoria de acceso aleatorio (RAM) necesarios para cada uno de los roles para ejecutar esta opción de implementación. Para obtener más información, consulte los requisitos mínimos recomendados para el clúster del Service Fabric independiente, [Planifique y prepare el clúster del Service Fabric independiente](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Si se instala otro software de Microsoft en el mismo equipo, el sistema también debe cumplir con los requisitos de hardware para dicho software. Le recomendamos que limite otras aplicaciones de servidor en el mismo equipo que AOS a 1 gigabyte (GB) de RAM.

**Dimensionamiento por rol y tipo de topología**

| Topología   | Rol (tipo de nodo)              | Núcleos de procesador recomendados | Memoria recomendada (GB) |
|------------|-------------------------------|-----------------------------|-------------------------|
| Producción | AOS, administración de datos, lote   | 8                           | 24                      |
|            | Management Reporter           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |
| Espacio aislado    | AOS, administración de datos, lote   | 4                           | 24                      |
|            | Management Reporter           | 4                           | 16                      |
|            | SQL Server Reporting Services | 4                           | 16                      |
|            | Orchestrator                  | 4                           | 16                      |

**Estimaciones de dimensionamiento mínimo para implementaciones de producción y de espacio aislado**\*

| Topología                                  | Función                          | Número de instancias |
|-------------------------------------------|-------------------------------|---------------------|
| Producción                                | AOS (administración de datos, lote)  | 3                   |
|                                           | Management Reporter           | 2                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Orchestrator\*\*                | 3                   |
| Espacio aislado                                   | AOS, administración de datos, lote   | 2                   |
|                                           | Management Reporter           | 1                   |
|                                           | SQL Server Reporting Services | 1                   |
|                                           | Orchestrator                  | 3                   |
| *Topologías de resumen de producción y de espacio aislado* |                               | 16                  |

\*Nuestros clientes de vista previa validan estos números y se pueden ajustar según sea necesario en función de esa realimentación.

\*\*Orchestrator está diseñado como el tipo de nodo principal y también se usará para ejecutar los servicios de Service Fabric.

**Estimaciones iniciales de Backend SQL Server y AD**

[![Estimaciones iniciales de Backend SQL Server y AD](./media/system-reqs-on-premises-02.PNG)](./media/system-reqs-on-premises-02.PNG) 

\*Los tamaños de SQL Server son muy dependientes de las cargas de trabajo. Para obtener más información, consulte la sección [Tamaño del hardware para entornos locales](#Hardware-sizing-for-on-premises-environments).

## <a name="storage"></a>Almacenamiento

- **AOS** - Finance and Operatiosn (local) utilizará un recurso compartido Server Message Block (SMB) 3.0 para almacenar datos no estructurados. Para obtener más información, consulte [Storage Spaces Direct en Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** - Opciones viables:
    - Una configuración de unidad de estado sólido (SSD) de alta disponibilidad.
    - Una red de aŕea de almacenamiento (SAN) optimizada para el rendimiento de los OLTP.
    - Almacenamiento de conexión directa (DAS) de alto rendimiento 
- **IOPS para SQL y administración de datos** - El almacenamiento para la administración de datos y SQL Server debe tener al menos 2000 operaciones de entrada/salida por segundo (IOPS). Las IOPS de producción dependen de muchos factores. Para obtener más información, consulte la sección "Tamaño del hardware para entornos locales". 
- **IOPS de la máquina virtual** - Cada máquina virtual debe tener al menos 100 IOPS de escritura.

## <a name="virtual-host-requirements"></a>Requisitos de host virtual
Al configurar los host virtuales para un entorno Finance and Operations (local), haga referencia a las siguientes directrices: [Planifique y prepare el clúster del Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) y [Describir un clúster del Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Cada host virtual debe tener suficientes núcleos para la infraestructura que se está dimensionando. Son posibles múltiples configuraciones avanzadas, donde SQL Server reside en el hardware físico pero todo lo demás se virtualiza. Si se virtualiza SQL Server, el subsistema del disco debe ser un SAN rápido o el equivalente. En todos los casos, asegúrese de que la configuración básica del host virtual es redundante y de alta disponibilidad. En todos los casos, cuando se usa la virtualización, se deben tomar instantáneas de MV.

## <a name="software-requirements-for-all-server-computers"></a>Requisitos de software para todos los equipos del servidor
El siguiente software debe estar presente en un equipo antes de que se pueda instalar cualquier componente de Finance and Operations (local):

- Microsoft .NET Framework 4.5.1 o superior
- Para obtener más información sobre el Service Fabric, consulte [Planifique y prepare el clúster del Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Sistemas operativos de servidor compatibles
La siguiente tabla muestra los sistemas operativos del servidor compatibles con componentes de Finance and Operations.

| Sistema operativo                                     | Notas                                                                                  |
|------------------------------------------------------|----------------------------------------------------------------------------------------|
| Microsoft Windows Server 2016 Datacenter o Standard | Estos requisitos son para la base de datos y el clúster del Service Fabric que aloja el AOS. |

## <a name="software-requirements-for-database-servers"></a>Requisitos de software para servidores de base de datos

- SQL Server 2016 solo admite versiones de 64 bits.
- En un entorno de producción, le recomendamos que instale la actualización acumulativa (CU) más recientes para la versión de SQL Server que esté usando.
- Finance and Operations (local) admite intercalaciones Unicode que no distingan entre mayúsculas y minúsculas ni ancho, y que distingan acentos y tipos de kana. La intercalación debe coincidir con la configuración regional de Windows de los equipos que ejecuten instancias del AOS. Si configura una instalación nueva, le recomendamos que seleccione una intercalación de Windows en lugar de una intercalación de SQL Server. Para obtener más información sobre cómo seleccionar una intercalación para una base de datos de SQL Server, consulte la [Documentación de SQL Server](/sql/sql-server/sql-server-technical-documentation).
La siguiente tabla muestra las versiones de SQL Server compatibles con las bases de datos de Finance and Operations. Para obtener más información, consulte los requisitos mínimos de hardware para [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Requisito                                                      | Notas                                                                                                                     |
|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Microsoft SQL Server 2016 Standard Edition o Enterprise Edition | Para los requisitos de hardware de SQL Server 2016, consulte [Requisitos de hardware y de software para instalar SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>Requisitos de software para todos los equipos cliente
La aplicación web de Finance and Operations se puede ejecutar en cualquier dispositivo con un explorador web compatible con HTML5.0. Entre las combinaciones específicas de dispositivo/explorador que Microsoft ha confirmado se incluyen:

- Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
- Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
- Google Chrome (la versión disponible publicada más recientemente) en Windows 10, Windows 8.1, Windows 8, Windows 7 o la tableta Google Nexus 10
- Apple Safari (la versión disponible publicada más recientemente) en Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) o 10.12 (Sierra) o Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Requisitos de software para Active Directory Federation Services 
Active Directory Federation Services (ADFS) en Windows Server 2016

El controlador de dominio debe ser Windows Server 2012 R2 o posteriormente con un nivel funcional de dominio de 2012 R2 o superior

Para obtener más información acerca de los niveles funcionales, consulte: 
- [Cuáles son niveles funcionales de Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Comprender los niveles funcionales de Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Requisitos de hardware y software para componentes de Retail
Finance and Operations (local) no incluye los componentes de Retail en este momento.

<a name="see-also"></a>Consulte también
--------

[Obtenga una copia de evaluacion de Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)

