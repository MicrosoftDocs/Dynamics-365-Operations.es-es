---
title: Requisitos del sistema de Talent y directiva de actualización
description: Este tema muestra los requisitos de Dynamics 365 for Talent. También se describe la directiva de actualización.
author: andreabichsel
manager: AnnBe
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6c881bf25e7145228ccf7ef73a7ef3637c115a49
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741784"
---
# <a name="talent-system-requirements-and-update-policy"></a>Requisitos del sistema de Talent y directiva de actualización

[!include [banner](includes/banner.md)]

Este tema describe los requisitos para Microsoft Dynamics 365 for Talent, incluido Attract, Onboard y Core HR. También describe los países y regiones donde Talent está disponible, además de información sobre idiomas y ubicación para los datos de Talent. Además, este tema proporciona la actualización de la directiva de Talent.

## <a name="supported-web-browsers"></a>Exploradores web compatibles

La aplicación web de Microsoft Dynamics 365 for Talent se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados: 

*   Microsoft Edge (la versión disponible publicada más recientemente) en Windows 10
*   Internet Explorer 11 en Windows 10, Windows 8.1 o Windows 7
*   Google Chrome (la última versión disponible públicamente)
*   Apple Safari (la última versión disponible públicamente)

Para buscar la versión más reciente para cada explorador web, vaya al sitio web del fabricante de software. 

> [!NOTE]
> * Para tomar las imágenes generadas en el Grabador de tareas y incluirlas en los documentos de Microsoft Word, debe tener una extensión de Chrome instalada. 
> * El editor de flujo de trabajo se inicia como aplicación ClickOnce. Sólo Microsoft Edge e Internet Explorer (en una versión compatible de Microsoft Windows) admiten aplicaciones ClickOnces. La aplicación ClickOnce del editor de flujo de trabajo requiere un sistema operativo compatible de 64 bits.
> * Para obtener una vista previa de los archivos PDF, se recomienda que use exploradores modernos como Microsoft Edge (la última versión disponible para el público) en Windows 10, o Google Chrome (la última versión disponible para el público) en tabletas con Windows 10, Windows 8.1, Windows 8, Windows 7, o Google Nexus 10.
>   Requisitos de red
> * Dynamics 365 for Talent está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos. Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Dynamics 365 for Talent. Se recomienda que pruebe la latencia de red en [www.azurespeed.com](https://www.azurespeed.com "Prueba de latencia de Azure").
> * Los requisitos de ancho de banda de Dynamics 365 for Talent dependen de su situación. La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps).
> 
> [!WARNING]
> No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es muy difícil de calcular. Para los clientes que estén preocupados por los requisitos del ancho de banda, use una versión de prueba de Dynamics 365 for Talent.

## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office admitidas

* Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac. Para obtener más información acerca de los requisitos de la versión, consulte la [Solución de problemas de la integración de Office](../dev-itpro/office-integration/office-integration-troubleshooting.md "Solución de problemas de la integración de Office").
* Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.

## <a name="regional-availability-languages-and-localization"></a>Disponibilidad, idiomas, y localización regional

Puede descargar un archivo PDF de países, las regiones e idiomas compatibles con Talent en [Disponibilidad internacional de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability). 

> [!NOTE]
> Aunque la interfaz de usuario se encuentre en otros idiomas, todos los datos de usuario se almacenan en el idioma en el que se introdujeron. Puede crear mensajes de correo electrónico y plantillas en otros idiomas, pero los datos como información de programación solo está disponible en inglés en este momento.

Si es desarrollador de software y está interesado en crear país o personalizaciones específicas de una región, o en crear una solución de un país o región no compatible actualmente con Microsoft, consulte [Globalización](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).

## <a name="update-policy"></a>Directiva de actualización

Microsoft Dynamics 365 for Talent se mantiene como oferta de nube. Las actualizaciones de Dynamics 365 for Talent son continuas y Microsoft las aplica automáticamente.

Las actualizaciones se lanzan en una cadencia regular, las actualizaciones y se crearán a todos los entornos. Dynamics 365 for Talent es admitido por la directiva [Soporte técnico del ciclo de vida de Microsoft](https://support.microsoft.com/gp/lifecycle#gp/OSSLpolicy "Soporte técnico del ciclo de vida de Microsoft"), que proporciona directrices coherentes y fiables para la disponibilidad de asistencia técnica.
