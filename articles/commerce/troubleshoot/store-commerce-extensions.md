---
title: Solucionar problemas de la extensión Store Commerce
description: Este artículo explica cómo solucionar problemas de extensión en la aplicación Store Commerce de Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 06/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1a2d6a68b7556d8b4d05529efd90f9e66f0c5925
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269791"
---
# <a name="troubleshoot-store-commerce-extension-issues"></a>Solucionar problemas de la extensión Store Commerce

[!include [banner](../includes/banner.md)]

Este artículo explica cómo solucionar problemas de extensión en la aplicación Store Commerce de Microsoft Dynamics 365 Commerce.

## <a name="extensions-packages-arent-loaded"></a>Los paquetes de extensiones no están cargados

### <a name="extensions-packages-dont-appear-on-the-pos--settings-page"></a>Los paquetes de extensiones no aparecen en la página PDV \> Configuración

Es posible que los disparadores de Commerce runtime (CRT) no se hayan actualizado para incluir el paquete de extensión o que no estén implementados. Para más información, vea [Extensibilidad y disparadores de Commerce Runtime (CRT)](../dev-itpro/commerce-runtime-extensibility-trigger.md).

### <a name="extensions-packages-appear-on-the-pos--settings-page-but-the-manifest-isnt-loaded"></a>Los paquetes de extensiones aparecen en la página PDV \> Configuración, pero el manifiesto no está cargado

Confirme que los paquetes de extensiones existen en la carpeta **C:\\Archivos de programa\\Microsoft Dynamics 365\\10.0\\Store Commerce\\Extensions**. Si los paquetes existen, debe haber una carpeta **PDV** allí que contiene el manifiesto.

Si no hay una carpeta **PDV**, confirme que el proyecto de Store Commerce hace referencia correctamente al proyecto de extensión de punto de venta (PDV). Valide la ruta de referencia del proyecto y asegúrese de que exista. 

En la siguiente ilustración de ejemplo, el proyecto del instalador tiene problemas con el proyecto de extensión al que se hace referencia.

![La referencia del proyecto del instalador de Store Commerce no es válida.](media/ReferenceNotValid.png)

Si la referencia para el proyecto de extensión se agrega correctamente, no habrá ningún problema de dependencia o advertencia en el proyecto del instalador, como se muestra en la siguiente ilustración de ejemplo.

![La referencia del proyecto del instalador de Store Commerce es válida.](media/ReferenceValid.png)
