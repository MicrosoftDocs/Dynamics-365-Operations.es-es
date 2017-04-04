---
title: Requisitos del sistema
description: "Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 para las operaciones."
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Core
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 9220c093d3f6d6700127c93651db4083be300311
ms.lasthandoff: 03/31/2017


---

# <a name="system-requirements"></a>Requisitos del sistema

Este tema muestra los requisitos del sistema para la versión actual de Microsoft Dynamics 365 para las operaciones.

<a name="supported-web-browsers"></a>Exploradores web compatibles
----------------------

El Microsoft Dynamics 365 para la aplicación Web de las operaciones se puede ejecutar en cualquiera de los exploradores Web que se ejecutan en los sistemas operativos especificados:

-   Microsoft afila (lo más tarde posible público - versión disponible) en Windows 10
-   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
-   Google Cromada (lo más tarde posible público - versión disponible) en la tableta de Windows 10, de Windows 8.1, de Windows 8, de Windows 7, o de Google Nexus 10
-   Apple Safari (lo más tarde posible público - versión disponible) en Mac OS X 10.10 (Yosemite), 10.11 Capitan EL () o 10.12 (Sierra), o iPad de Apple

Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software. **Notas:**

-   Para tomar las imágenes generados en el Grabador de tareas y incluirlas en los documentos de Microsoft Word, debe tener una extensión de Cromada instalada. <!---For instructions about how to install the extension, see [Screenshot Extension setup](/dynamics365/operations/dev-itpro/user-interface/task-recorder).-->
-   El editor de flujo de trabajo se inicia como aplicación ClickOnce. Solo el perímetro y Internet Explorer de Microsoft (en una versión compatible de Microsoft Windows) admiten ClickOnces aplicaciones. La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo de 64 bits.
-   Encienden al Diseñador de informes para el informe financiero como ClickOnce aplicación. Requiere un sistema operativo de 64 bits. Si utiliza Cromada, debe instalar una extensión de ClickOnce para descargar el cliente del diseñador de informes. Si utiliza Cromada con el modo incógnito, asegúrese de que la extensión de ClickOnce también esté habilitada para el modo incógnito.

### <a name="supported-web-browsers-for-retail-cloud-pos"></a>Exploradores web admitidos para Retail Cloud POS

La nube al por menor PDV para Dynamics 365 para las operaciones se puede ejecutar en cualquiera de los exploradores Web que se ejecutan en los sistemas operativos especificados:

-   Microsoft afila (lo más tarde posible público - versión disponible) en Windows 10
-   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
-   Cromada (lo más tarde posible público - versión disponible) en Windows 10, Windows 8.1, 7 o Windows

## <a name="network-requirements"></a>Requisitos de la red
-   La Dynamics 365 para las operaciones está diseñada para las redes con latencia de menos de 150 milisegundos de (ms). Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Dynamics 365 para las operaciones. Se recomienda que pruebe latencia de red en< http://www.azurespeed.com>.
-   Los requisitos del ancho de banda para Dynamics 365 para las operaciones dependen de su situación de ejemplo. La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps). Sin embargo, para las situaciones que con requisitos de carga, como el área de trabajo o situaciones que implican la personalización amplia, se recomienda más ancho de banda.

La Dynamics 365 para las operaciones se optimiza normalmente para Internet. El número de acciones de ida y devolución de un cliente de explorador al centro de datos blanco cielo sea muy pequeño, y se comprimen la carga completa. ** Advirtiendo: ** No calcular requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es muy difícil de calcular. Para los clientes que se tratan acerca de los requisitos del ancho de banda, use una versión preliminar de Dynamics 365 para las operaciones.

## <a name="net-framework-requirements"></a>requisitos de .NET Framework
La Dynamics 365 para las operaciones requiere la versión 4.6.2 de .NET Framework para todos entrada una vez que las aplicaciones, como el agente de rutas del documento. Para obtener instrucciones de instalación, consulte [a instalar .NET Framework] (https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).

## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office compatibles
-   Para ejecutar Microsoft Excel y redactar los complementos, debe tener Microsoft Office 2016 para Windows o Mac instaló. Para obtener más información acerca de los requisitos de la versión, consulte [la solución de problemas] de la integración de la oficina (/dynamics365/operations/dev-itpro/office-integration/office-integration-troubleshooting).
-   Para ver los documentos que se generan mediante la exportación a Excel o exportación para redactar función, debe tener instalado Microsoft Office 2007 o más adelante.

## <a name="retail-modern-pos-requirements"></a>Requisitos modernos al por menor de PDV
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   PDV moderno Retail es una aplicación de 32 bits, pero ejecutará en las arquitecturas de x86 y del x64.
-   PDV moderno al por menor está sólo admite en Windows 10 las ediciones ramificadas de mantenimiento a largo plazo de (LTSB), favorable de la empresa, y de la empresa.

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

-   Resolver compatible el mínimo es 1280 × 1024.
-   El equipo que PDV moderno al por menor ejecuta cumpla con estos requisitos:
    -   Es necesario, el mínimo, un procesador dual-core que ejecute en cualquier menos de 2 gigahercios (GHz).
    -   Es necesario, el mínimo, 3 de gigabytes (GB) de RAM.
    -   Deben tener acceso a Internet.

## <a name="retail-hardware-station-requirements"></a>Requisitos de ventas al por menor de la emisora de hardware
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   La emisora del hardware es una aplicación de 32 bits, pero ejecutará en las arquitecturas de x86 y del x64.
-   La emisora el por menor y se admite hardware en los sistemas operativos siguientes:
    -   Windows 7, Professional empresa y, ediciones últimas ** nota: ** Se admite Windows 7 si Internet Explorer 11 está instalado manualmente en el sistema.
    -   La Windows 8.1 actualiza Professional 1, la empresa, y las ediciones incrustadas
    -   Windows 10 favorables, ediciones de la empresa, y de la empresa LTSB

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

El equipo cumpla con todos los requisitos del sistema para instalar y usar los siguientes elementos:

-   Servicios de Internet Information Server (IIS)
-   Hardware de terceros

## <a name="retail-store-scale-unit-requirements"></a>Requisitos de la unidad de la escala de Retail Store Connect
### <a name="supported-operating-systems"></a>Sistemas operativos admitidos

-   La unidad de la escala de Retail Store Connect es una aplicación de 32 bits, pero ejecutará en las arquitecturas de x86 y del x64.
-   La unidad de la escala de Retail Store Connect se admite en los sistemas operativos siguientes:
    -   Windows 7, Professional empresa y, ediciones últimas
    -   La Windows 8.1 actualiza Professional 1, la empresa, y las ediciones incrustadas
    -   Windows 10 favorables, ediciones de la empresa, y de la empresa LTSB

### <a name="minimum-system-requirements"></a>Requisitos mínimos del sistema

-   4 De RAM GB
-   1.6 De la velocidad CPU de demanda de GHz por base (dos núcleos son el mínimo.)
-   Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio.)

### <a name="recommended-system-requirements"></a>Requisitos del sistema recomendados

-   6 De RAM GB
-   2.4 De la velocidad CPU de demanda de GHz i7 equivalente (o) por la base (se recomiendan cuatro núcleos).
-   Al menos 10 GB de espacio libre (la base de datos del canal puede requerir una gran cantidad de espacio.)

## <a name="requirements-for-development-on-local-vms"></a>Los requisitos del desarrollo en el valor MV local
Para obtener información acerca de los requisitos para el desarrollo en las máquinas virtuales locales (VMs), consulte [el ejecutarse de MV local (/dynamics365/operations/dev-itpro/dev-tools/access-instances] #vm-that-is-running-in-premises).

<a name="see-also"></a>Consulte también
--------

[Obtener una copia de evaluación de Dynamics 365 para las operaciones] (/dynamics365/operations/dev-itpro/dev-tools/get-evaluation-copy)


