---
title: Requisitos del sistema para implementaciones locales
description: "Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, para implementaciones locales."
author: kfend
manager: AnnBe
ms.date: 08/02/2017
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
ms.author: kfend
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 5230911e1febc66b294f1331846373a472789adf
ms.openlocfilehash: 721c5851cd399398a8dcec5ae110b97a4f17ae0a
ms.contentlocale: es-es
ms.lasthandoff: 08/04/2017

---

# <a name="system-requirements-for-on-premises-deployments"></a>Requisitos del sistema para implementaciones locales

[!include[banner](../includes/banner.md)]

Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, para implementaciones locales. Antes de instalar Finance and Operations, si es necesario, compruebe que el sistema con el que trabaja cumple o supera los requisitos mínimos de red, hardware y software.

## <a name="network-requirements"></a>Requisitos de red
Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (local) puede trabajar en las redes que usan la versión 4 (IPv4) del protocolo de Internet o la versión 6 (IPv6) del protocolo de Internet . Tenga en cuenta el entorno de red al planificar su sistema y siga las siguientes instrucciones.

### <a name="network-response-time"></a>Tiempo de respuesta de la red
La siguiente tabla enumera los requisitos mínimos de red para la conexión entre el explorador web y Application Object Server (AOS), y para la conexión entre el AOS y la base de datos en un sistema local.

| Valor     | Explorador web a AOS                      | AOS a base de datos |
|-----------|-----------------------------------------|------------------------------------------------------------------------------------------|
| Ancho de banda | 50 kilobytes por segundo (KBps) por usuario | 100 megabytes por segundo (MBps) |
| Latencia   | Menor de 250-300 milisegundos de (ms)     | Menor de 1 ms (red de área local [LAN] únicamente). El AOS y la base de datos tienen que ubicarse en el mismo lado. |

- Finance and Operations (local) está diseñado para redes que tengan una latencia de 250-300 milisegundos (ms) o menos. Esta latencia es la latencia de un cliente de explorador al centro de datos que aloja Finance and Operations.
- Los requisitos del ancho de banda para Finance and Operations (local) dependen de su caso. Las situaciones habituales requieren un ancho de banda de más de 50 KBps entre el explorador y el servidor de Finance and Operations. Sin embargo, recomendamos más ancho de banda para las situaciones con requisitos de carga elevados, como los espacios de trabajo o las situaciones que implican una personalización amplia. La cantidad específica de ancho de banda depende de uso.

No se admiten implementaciones en las que el AOS y la base de datos de Microsoft SQL Server están en distintos centros de datos. El AOS y la base de datos SQL Server tienen que ubicarse en el mismo lado. 

En general, Finance and Operations está optimizado para reducir recorridos de ida y vuelta del explorador al servidor. El número de recorridos de ida y vuelta de un cliente de explorador al centro de datos es de cero o uno para cada interacción del usuario, y se comprime la carga.

> [!WARNING]
> No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es muy difícil de calcular. Le recomendamos que use una simulación de la vida real frente a un entorno de no producción de Finance and Operations como el mejor medidor de rendimiento para su caso específico. 

### <a name="lan-environments"></a>Entornos LAN
En entornos de red LAN, Escritorio Remoto de Microsoft en Microsoft Windows Server no es necesario para conectarse a Finance and Operations. Sin embargo, el Escritorio Remoto puede que sea necesario para las operaciones en las máquinas virtuales (MV) que conforman las implementaciones de servidor.

### <a name="wan-environments"></a>Entornos WAN
En los entornos de red de área amplia (WAN), el Escritorio Remoto en Windows Server no es necesario para conectarse a Finance and Operations.

### <a name="internet-connectivity-requirements"></a>Requisitos de conectividad a Internet
Finance and Operations (local) no requiere conectividad a Internet desde las estaciones de trabajo del usuario. Sin embargo, algunas funciones no estarán disponibles si no hay conectividad a Internet.

|                    |   |
|--------------------|---|
| **Cliente de explorador** | Un escenario de intranet sin conectividad a Internet es un punto de diseño para la opción de implementación local. No estarán disponibles algunas funciones que requieren servicios en la nube, como las bibliotecas de la guía de ayuda y tareas en Microsoft Dynamics Lifecycle Services (LCS). |
| **Servidor**         | El nivel de AOS o Microsoft Azure Service Fabric debe poder comunicarse con LCS. El cliente basado en explorador local no requiere acceso a Internet. |
| **Telemetría**      | Puede que los datos de telemetría se pierdan si hay largas interrupciones en la conectividad. Las interrupciones en la conectividad a LCS no afectan a la funcionalidad de las aplicaciones locales. |
| **LCS**            | La conectividad a LCS es necesaria para la implementación, la implementación del código y las operaciones de mantenimiento. |

## <a name="telemetry-data-transfer-to-the-cloud"></a>Los datos de telemetría se transfieren a la nube
La mayoría de los datos de la telemetría se almacena de forma local y se puede acceder mediante el Visor de eventos en Microsoft Windows. Un pequeño subconjunto de eventos de telemetría se transfiere al proceso de telemetría de Microsoft en la nube para diagnósticos. Los datos del cliente y los datos identificables del usuario no forman parte de los datos de la telemetría enviada a Microsoft. Los nombres de MV se envían a Microsoft para ayudar con la administración y diagnósticos del entorno desde el portal LCS.

## <a name="domain-requirements"></a>Requisitos de dominio
Tenga en cuenta los siguientes requisitos del dominio al instalar Finance and Operations (local):

- Las MV que hospedan componentes de Finance and Operations (local) deben pertenecer a un dominio de Active Directory. Los servicios de dominio de Active Directory (AD DS) deben configurarse en modo nativo.
- MV que ejecutan los componentes de Finance and Operations (local) deben tener acceso entre sí. Este acceso se configura en AD DS. 
- El controlador de dominio debe ser Microsoft Windows Server 2012 R2 o posterior y el nivel funcional del dominio debe ser 2012 R2 o superior

## <a name="hardware-requirements"></a>Requisitos de hardware
Esta sección describe el hardware necesario para ejecutar Finance and Operations (local).

En función de la configuración del sistema, la composición de los datos y las aplicaciones y funciones que decida usar, los requisitos reales de hardware varían. A continuación se muestran algunos de los factores que pueden afectar a la selección del hardware adecuado para Finance and Operations (local):

- El número de transacciones por hora
- El número de usuarios simultáneos

## <a name="minimum-infrastructure-requirements"></a>Requisitos mínimos de la infraestructura
Finance and Operations (local) utiliza Service Fabric para alojar el AOS, el lote, la administración de datos, Management Reporter y los servicios Orchestrator del entorno. Microsoft SQL Server Reporting Services (SSRS) no se aloja en el clúster del Service Fabric.

SQL Server debe tener en una configuración HADRON de alta disponibilidad que tenga al menos dos nodos para el uso de la producción.

La ilustración siguiente muestra el número mínimo recomendado de nodos en el clúster del Service Fabric.

[![Número recomendado de nodos para el clúster del Service Fabric](./media/system-reqs-on-premises-01.png)](./media/system-reqs-on-premises-01.png) 

## <a name="processor-and-ram-requirements"></a>Requisitos del procesador y la RAM
La siguiente tabla muestra el número de procesadores y la cantidad de memoria RAM necesarios para cada uno de los roles que se necesitan para ejecutar esta opción de implementación. Para obtener más información, consulte los requisitos mínimos recomendados para el clúster del Service Fabric independiente en [Planifique y prepare el clúster del Service Fabric independiente](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

> [!NOTE]
> Si se instala otro software de Microsoft en el mismo equipo, el sistema también debe cumplir con los requisitos de hardware para dicho software. Si hay instaladas otras aplicaciones de servidor en el mismo equipo que AOS, le recomendamos que limite esas otras aplicaciones de servidor a 1 gigabyte (GB) de RAM.

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

**Estimaciones de dimensionamiento mínimo para implementaciones de producción y de espacio aislado\***

| Topología                                        | Función                          | Número de instancias |
|-------------------------------------------------|-------------------------------|---------------------|
| Producción                                      | AOS (administración de datos, lote)  | 3                   |
|                                                 | Management Reporter           | 2                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator\*\*              | 3                   |
| Espacio aislado                                         | AOS, administración de datos, lote   | 2                   |
|                                                 | Management Reporter           | 1                   |
|                                                 | SQL Server Reporting Services | 1                   |
|                                                 | Orchestrator                  | 3                   |
| *Topologías de resumen de producción y de espacio aislado* |                               | *16*                |

\* Los números de esta tabla se validan por nuestros clientes de vista previa y se pueden ajustar en función de la retroalimentación de dichos clientes.

\*\* Orchestrator está diseñado como el tipo de nodo principal y también se usará para ejecutar los servicios de Service Fabric.

**Estimaciones iniciales de Back-end SQL Server y AD DS**

<table>
<thead>
<tr>
<th></th>
<th>Función</th>
<th>MV/Instancias</th>
<th>Núcleos</th>
<th>Núcleos totales</th>
<th>Memoria por instancia (GB)</th>
<th>Memoria total (GB)</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan="3"><strong>Infraestructura compartida</strong></td>
<td>SQL Server*</td>
<td>2</td>
<td>8</td>
<td>16</td>
<td>32</td>
<td>64</td>
</tr>
<tr>
<td>Servidor de archivos/red de área de almacenamiento/almacenamiento muy disponible</td>
<td colspan="5"><p>El almacenamiento back-end se debe basar en las unidades de estado sólido (SSDs) en el tiempo de ejecución de la red del área de almacenamiento (SAN).</p>
<p>Las operaciones de tamaño y de entrada-salida por segundo (IOPS) se basan en el tamaño de la carga de trabajo.</p></td>
</tr>
<tr>
<td>Active Directory</td>
<td>3</td>
<td>4</td>
<td>12</td>
<td>16</td>
<td>48</td>
</tr>
<tr>
<td><em>Resumen para la infraestructura compartida</em></td>
<td></td>
<td><em>5</em></td>
<td></td>
<td><em>28</em></td>
<td></td>
<td><em>112</em></td>
</tr>
</tbody>
</table>

\*Los tamaños de SQL Server son muy dependientes de las cargas de trabajo. Para obtener más información, consulte [Tamaño del hardware para entornos locales](hardware-sizing-on-premises-environments.md).

## <a name="storage"></a>Almacenamiento

- **AOS** – Finance and Operations (local) utiliza un Server Message Block (SMB) 3.0 compartido para almacenar datos no estructurados. Para obtener más información, consulte [Storage Spaces Direct en Windows Server 2016](/windows-server/storage/storage-spaces/storage-spaces-direct-overview).
- **SQL** – Son viables las siguientes opciones:

    - Una configuración muy disponible de SSD
    - Un SAN que se optimiza para los rendimiento de procesamiento de transacciones en línea (OLTP)
    - Almacenamiento de conexión directa (DAS) de alto rendimiento 

- **SQL Server y administración de datos IOPS** - El almacenamiento para la administración de datos y SQL Server debe tener al menos 2000 (IOPS). Las IOPS de producción dependen de muchos factores. Para obtener más información, consulte [Tamaño del hardware para entornos locales](hardware-sizing-on-premises-environments.md).
- **IOP DE MV** – Cada MV debe tener al menos 100 IOP de devaluación.

## <a name="virtual-host-requirements"></a>Requisitos de host virtual
Al configurar los alojamientos virtuales para el entorno Finance and Operations (local), consulte las directrices en: [Planifique y prepare el clúster del Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation) y [Describir un clúster del Service Fabric](/azure/service-fabric/service-fabric-cluster-resource-manager-cluster-description). Cada host virtual debe tener suficientes núcleos para la infraestructura que se está dimensionando. Son posibles múltiples configuraciones avanzadas, donde SQL Server reside en el hardware físico pero todo lo demás se virtualiza. Si se virtualiza SQL Server, el subsistema del disco debe ser un SAN rápido o el equivalente. En todos los casos, asegúrese de que la configuración básica del host virtual es redundante y de alta disponibilidad. En todos los casos, cuando se usa la virtualización, se deben tomar instantáneas de MV.

## <a name="software-requirements-for-all-server-computers"></a>Requisitos de software para todos los equipos del servidor
El siguiente software debe estar presente en un equipo antes de que se pueda instalar cualquier componente de Finance and Operations (local):

- La versión 4.5.1 o superior de Microsoft .NET Framework
- Service Fabric

Para obtener más información, consulte [Planifique y prepare el clúster del Service Fabric](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="supported-server-operating-systems"></a>Sistemas operativos de servidor compatibles
La siguiente tabla muestra los sistemas operativos del servidor compatibles con componentes de Finance and Operations.

| Sistema operativo                                     | Notas |
|------------------------------------------------------|-------|
| Microsoft Windows Server 2016 Datacenter o Standard | Estos requisitos son para la base de datos y el clúster del Service Fabric que aloja el AOS. |

## <a name="software-requirements-for-database-servers"></a>Requisitos de software para servidores de base de datos

- SQL Server 2016 solo admite versiones de 64 bits.
- En un entorno de producción, le recomendamos que instale la actualización acumulativa (CU) más recientes para la versión de SQL Server que esté usando.
- Finance and Operations (local) admite intercalaciones Unicode que no distingan entre mayúsculas y minúsculas ni ancho, y que distingan acentos y tipos de kana. La intercalación debe coincidir con la configuración regional de Windows de los equipos que ejecuten instancias del AOS. Si configura una instalación nueva, le recomendamos que seleccione una intercalación de Windows en lugar de una intercalación de SQL Server. Para obtener más información sobre cómo seleccionar una intercalación para una base de datos de SQL Server, consulte la [Documentación de SQL Server](/sql/sql-server/sql-server-technical-documentation).

La siguiente tabla muestra las versiones de SQL Server compatibles con las bases de datos de Finance and Operations. Para obtener más información, consulte los requisitos mínimos de hardware para [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-2016).

| Requisito                                                      | Notas |
|------------------------------------------------------------------|-------|
| Microsoft SQL Server 2016 Standard Edition o Enterprise Edition | Para los requisitos de hardware de SQL Server 2016, consulte [Requisitos de hardware y de software para instalar SQL Server 2016](/sql/sql-server/install/hardware-and-software-requirements-for-installing-sql-server). |

## <a name="software-requirements-for-client-computers"></a>Requisitos de software para todos los equipos cliente
La aplicación web de Finance and Operations se puede ejecutar en cualquier dispositivo que tenga un explorador web compatible con HTML 5.0. Estas son algunas de las combinaciones específicas de dispositivo/explorador que Microsoft ha confirmado:

- Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
- Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
- Google Chrome (la versión disponible publicada más recientemente) en Windows 10, Windows 8.1, Windows 8, Windows 7 o la tableta Google Nexus 10
- Apple Safari (la versión disponible publicada más recientemente) en Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) o 10.12 (Sierra) o Apple iPad

## <a name="software-requirements-for-active-directory-federation-services"></a>Requisitos de software para Active Directory Federation Services 
se requiere Active Directory Federation Services (ADFS) en Windows Server 2016.

El controlador de dominio debe ser Windows Server 2012 R2 o posterior y el nivel funcional del dominio debe ser 2012 R2 o superior Para obtener más información acerca de los niveles funcionales, consulte las siguientes páginas:

- [Cuáles son niveles funcionales de Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
- [Comprender los niveles funcionales de Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)

## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office compatibles
Las siguientes aplicaciones de Microsoft Office se admiten en implementaciones locales y en la nube de Finance and Operations:

-   Para ejecutar los complementos de Microsoft Excel y Microsoft Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac. Para obtener más información acerca de los requisitos de la versión, consulte [Solucionador de problemas de integración de Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.
 
## <a name="hardware-and-software-requirements-for-retail-components"></a>Requisitos de hardware y software para componentes de Retail
Actualmente, Finance and Operations (local) no incluye los componentes de Retail.

