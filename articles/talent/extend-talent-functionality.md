---
title: Extender la funcionalidad de Microsoft Dynamics 365 for Talent
description: "Si ha creado alguna aplicación de Microsoft PowerApps, puede iniciarla desde los vínculos de Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 03/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 51eb4288f5b6c732755007c1dcd8c4db090ccc0a
ms.contentlocale: es-es
ms.lasthandoff: 03/08/2018

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>Extender la funcionalidad de Microsoft Dynamics 365 for Talent

[!include [banner](includes/banner.md)]

Si ha creado alguna aplicación de Microsoft PowerApps, puede iniciarla desde los vínculos de Microsoft Dynamics 365 for Talent. Para configurar el acceso a sus aplicaciones, deberá configurar información en Talent en una página de configuración que pueda abrir desde el espacio de trabajo **Administración del sistema**.

## <a name="configuring-embedded-powerapps-within-talent"></a>Combinación de aplicaciones de PowerApps incrustadas en Talent
Use la página **Establecer aplicaciones incrustadas de Microsoft PowerApps** para configurar las páginas de Talent para iniciar aplicaciones de PowerApps. Para abrir la página **Establecer aplicaciones incrustadas de Microsoft PowerApps**, abra el área trabajo **Administración del sistema** y después abra la ficha **Vínculos**. Seleccione **Microsoft PowerApps** del grupo **Configuración**. 

La siguiente información se introduce o se establece en esta página: 

 -  Un nombre descriptivo o un identificador para cada aplicación de PowerApps.
 -  Un identificador único (GUID) para cada aplicación que agregue a una página de Talent. El identificador de la aplicación disponible en el sitio de PowerApps [powerapps.com](http://powerapps.com/). 
 -  La página desde la que los usuarios pueden abrir una aplicación o un informe. No todas las páginas de Talent admiten aplicaciones de PowerApps ni informes de Power BI incrustados. 

 > [!NOTE]
 >  Especifique el nombre interno de la página, en lugar del nombre para mostrar que aparece en la parte superior de la página. Para buscar el nombre interno, abra la página cuyo nombre interno necesita y haga clic con el botón secundario en cualquier lugar de la página. Cuando el menú se abra, mantenga el mouse sobre el elemento **Información del formulario**. El nombre del formulario interno aparece junto al elemento **Información del formulario** del menú.
 
-   Especifique el control de formulario desde el que la aplicación puede recuperar datos de contexto. Por ejemplo, una solicitud puede usar los datos de un trabajador. Si especifica la página **Trabajador** en el campo **Contexto**, la página **Trabajador** se abrirá al iniciar la aplicación. Una entrada en el **Campo de contexto** es opcional. 
-   Configure el tamaño del cuadro de diálogo en el que la aplicación de PowerApps se ejecutará. Los cuadros de diálogo se designan como “pequeño “o “grande” para optimizar la interfaz de usuario cuando su aplicación se ejecuta en un teléfono o un dispositivo mayor, respectivamente. 


También puede especificar para qué entidades jurídicas una aplicación estará disponible, o bien ponerla a disposición todas las entidades jurídicas. De forma predeterminada, sus aplicaciones de PowerApps están disponibles para todas las entidades jurídicas.

## <a name="opening-an-application"></a>Abrir una aplicación
Cuando haya configurado las aplicaciones incrustadas de PowerApps, se agregarán vínculos a las aplicaciones que ha especificado en las páginas de Talent. Haga clic en un vínculo para abrir una aplicación. 



