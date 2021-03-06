---
title: Requisitos del sistema
description: Este artículo describe los requisitos de Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f86cd60466661c87d762f2e2f0765b92351ee2b8
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053596"
---
# <a name="system-requirements"></a>Requisitos del sistema

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe los requisitos de Microsoft Dynamics 365 Human Resources. También describe los países y regiones donde Human Resources está disponible, además de información sobre idiomas y ubicación para los datos de Human Resources.

## <a name="supported-web-browsers"></a>Exploradores web compatibles

Human Resources se puede ejecutar en cualquiera de los siguientes exploradores web que se ejecutan en sistemas operativos especificados: 

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
> * Human Resources está diseñado para redes con latencia de 250-300 milisegundos (ms) o menos. Esta es la latencia de un cliente de explorador al centro de datos de Microsoft Azure que aloja Human Resources. Se recomienda que pruebe la latencia de red en [www.azurespeed.com](https://www.azurespeed.com "Test de latencia de Azure").
> * Los requisitos de ancho de banda de Human Resources dependen de su situación. La mayoría de las situaciones habituales requieren un ancho de banda de más de 50 kilobytes por segundo (Kbps).
> 
> [!WARNING]
> No calcule los requisitos del ancho de banda de una ubicación del cliente multiplicando el número de usuarios por los requisitos mínimos del ancho de banda. El uso simultáneo de una ubicación determinada es muy difícil de calcular. Para los clientes que estén preocupados por los requisitos del ancho de banda, use una versión de prueba de Human Resources.

## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office admitidas

* Para ejecutar los complementos de Microsoft Excel y Word, es necesario tener instalado Microsoft Office 2016 para Windows o Mac. Para obtener más información acerca de los requisitos de la versión, consulte [Solución de problemas de la integración de Office](../fin-ops-core/dev-itpro/office-integration/office-integration-troubleshooting.md "Solución de problemas de la integración con Office").
* Para ver los documentos que se generan mediante la funcionalidad de exportación a Excel o exportación a Word, debe tener instalado Microsoft Office 2007 o una versión posterior.

## <a name="regional-availability-languages-and-localization"></a>Disponibilidad, idiomas, y localización regional

Puede descargar un archivo PDF de países, las regiones e idiomas compatibles con Human Resources en [Disponibilidad internacional de Microsoft Dynamics 365](/dynamics365/get-started/availability). 

> [!NOTE]
> Aunque la interfaz de usuario se encuentre en otros idiomas, todos los datos de usuario se almacenan en el idioma en el que se introdujeron. Puede crear mensajes de correo electrónico y plantillas en otros idiomas, pero los datos como información de programación solo está disponible en inglés en este momento.

Si es desarrollador de software y está interesado en crear país o personalizaciones específicas de una región, o en crear una solución de un país o región no compatible actualmente con Microsoft, consulte [Globalización](/dynamics365/unified-operations/dev-itpro/lcs-solutions/country-region).


[!INCLUDE[footer-include](../includes/footer-banner.md)]