---
title: Instalar el tema de Adventure Works
description: Este tema describe cómo instalar el tema Adventure Works en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ad704c6c3b95abcfd52e449a0ffbb4b82b236498ae8d2775c4e65811de3ef503
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763845"
---
# <a name="install-the-adventure-works-theme"></a>Instalar el tema de Adventure Works

[!include [banner](includes/banner.md)]

Este tema describe cómo instalar el tema Adventure Works en Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> El tema de Adventure Works y los módulos están disponibles a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce. Están disponibles en Microsoft AppSource.

## <a name="prerequisites"></a>Requisitos previos

Antes de instalar el tema Adventure Works, debe tener un entorno Dynamics 365 Commerce (Commerce versión 10.0.20 o posterior) que incluya Retail Cloud Scale Unit (RCSU), el kit de desarrollo de software en línea (SDK) de Commerce y la biblioteca del módulo de Commerce. Para obtener información sobre cómo instalar el SDK de Commerce y la biblioteca de módulos, consulte [Actualizaciones de biblioteca de módulos y SDK](e-commerce-extensibility/sdk-updates.md). 

## <a name="installation-steps"></a>Pasos de instalación

### <a name="install-the-adventure-works-theme-in-your-application"></a>Instale el tema Adventure Works en su aplicación

El paquete de temas Adventure Works está disponible en la fuente **dynamics365-commerce**, como **@msdyn365-commerce-theme / adventureworks-theme-kit**. Sin embargo, aunque el paquete de temas de Adventure Works es parte de esa fuente, está en un espacio de nombres diferente. Por lo tanto, debe seguir estos pasos para agregar entradas de registro para el espacio de nombres.

1. Actualice el archivo **.npmrc** para que incluya la siguiente entrada de registro (si la entrada aún no está incluida):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Actualice el archivo **.yarnrc** para que incluya la siguiente entrada de registro (si la entrada aún no está incluida):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Para instalar el paquete en su entorno local, ejecute el siguiente comando desde el símbolo del sistema. Este comando actualiza automáticamente el archivo package.json para que incluya la dependencia.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit`

En el archivo **package.json**, debe actualizar la versión del tema a una versión específica.

> [!IMPORTANT]
> - La versión del tema debe coincidir con la versión de la biblioteca del módulo para garantizar que todas las funciones funcionen como se espera. 
> - La versión mínima para la biblioteca del módulo de Comercio y el SDK debe ser 10.0.20 (9.31). 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Agregue los archivos de fuentes para el tema Adventure Works

Una vez que el tema Adventure Works está instalado en su aplicación, debe agregar los archivos de fuentes necesarios para ello. Para completar este paso, copie todos los archivos de fuentes de **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** a la ruta del directorio público de la aplicación asociada **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Configure los recursos para el tema Adventure Works

El siguiente paso es actualizar el recurso predeterminado requerido para el tema. Para completar este paso, copie el contenido del archivo global.json en **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\resources\modules** al archivo global.json de la aplicación de partner en **\src\resources\modules**. Si el directorio de destino **\src\rresources** no existe, se puede copiar en su totalidad desde el directorio de origen **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** al directorio **\src**.

### <a name="pull-updates-and-validate-the-theme"></a>Extraiga actualizaciones y valide el tema

Para obtener información sobre cómo extraer el SDK más reciente, la biblioteca de módulos y otras actualizaciones de dependencia, consulte la sección "Extraer actualizaciones" de [Actualizaciones de biblioteca de módulos y SDK](e-commerce-extensibility/sdk-updates.md#pull-updates).

Una vez que se eliminan las dependencias más recientes, puede ejecutar el comando **comenzar hilo** para iniciar el servidor Node en su entorno de desarrollo y probar el nuevo tema de Adventure Works. Examine la aplicación localmente mediante el parámetro de cadena de consulta `?theme=adventureworks` (por ejemplo, `https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>Recursos adicionales

[Tema de Adventure Works](adventure-works-theme.md)

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Actualizaciones de SDK y bibliotecas de módulos](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
