---
title: Requisitos del sistema
description: "Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 724ee7ec29f8a9c4e8cc0b244193cd6c83c37f03
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# <a name="system-requirements"></a>Requisitos del sistema

[!include[banner](../includes/banner.md)]


Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

<a name="supported-web-browsers"></a>Exploradores web compatibles
----------------------

La aplicación web se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:

-   Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
-   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
-   Google Chrome (la versión disponible publicada más recientemente) en Windows 10, Windows 8.1, Windows 8, Windows 7 o la tableta Google Nexus 10
-   Apple Safari (la versión disponible publicada más recientemente) en Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) o 10.12 (Sierra) o Apple iPad

Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software. 

**Notas:**

-   Para tomar las imágenes generadas en el Grabador de tareas e incluirlas en los documentos generados por Microsoft Word, debe tener una versión preliminar de una extensión de Chrome instalada. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/unified-operations/dev-itpro/user-interface/task-recorder).-->
-   El editor de flujo de trabajo se inicia como aplicación ClickOnce. Solo Microsoft Edge y Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnce. La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.
-   El Diseñador de informes para informes financieros se inicia como aplicación ClickOnce. Requiere un sistema operativo compatible de 64 bits. Si está usando Chrome, debe instalar una extensión ClickOnce para descargar el cliente del diseñador de informes. Si está usando Chrome en modo incógnito, asegúrese de que la extensión ClickOnce está también activada para el modo incógnito.
-   Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.


### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Exploradores web admitidos para Retail Cloud POS

Retail Cloud POS se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados:

-   Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
-   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
-   Chrome (la versión disponible publicada recientemente) en Windows 10, Windows 8.1 o Windows 7

## <a name="network-requirements"></a>Requisitos de red
-   Dynamics 365 for Finance and Operations, Enterprise Edition está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos. Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Finance and Operations. Se recomienda que pruebe la latencia de red en <http://www.azurespeed.com>.
-   Los requisitos de ancho de banda dependen de su situación. La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps). Sin embargo, para las situaciones con requisitos de carga elevados, como los espacios de trabajo o las situaciones que implican una personalización amplia, se recomienda más ancho de banda.

En general, Finance and Operations está optimizado para Internet. El número de acciones de ida y vuelta de un cliente de explorador al centro de datos de Azure es pequeño y se comprime la carga completa. 

**Advertencia**: No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es difícil de calcular. Para los clientes que están preocupados por los requisitos del ancho de banda, use una versión preliminar de Finance and Operations.

## <a name="net-framework-requirements"></a>Requisitos de .NET Framework
Requiere la versión 4.6.2 de .NET Framework para todas las aplicaciones ClickOnce, como el agente de ruta del documento. Para obtener instrucciones de instalación, consulte [Instalación de .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office compatibles
-   Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac. Para obtener más información acerca de los requisitos de la versión, consulte [la solución de problemas de la integración de Office](/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.

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
    -   Ediciones Professional, Enterprise y Ultimate de Windows 7 **Nota:** Se admite Windows 7 solo si Internet Explorer 11 está instalado manualmente en el sistema.
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

<a name="see-also"></a>Consulte también
--------

[Obtenga una copia de evaluacion de Dynamics 365 for Finance and Operations, Enterprise Edition](/dynamics365/unified-operations/dev-itpro/dev-tools/get-evaluation-copy)





