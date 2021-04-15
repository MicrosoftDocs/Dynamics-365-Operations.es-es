---
title: Crear un perfil de funcionalidad en línea
description: Este tema describe cómo crear un perfil de funcionalidad en línea en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: be78b92858979b8bb009a4699eff96379ef7cef3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791111"
---
# <a name="create-an-online-functionality-profile"></a>Crear un perfil de funcionalidad en línea

[!include [banner](includes/banner.md)]

Este tema presenta una visión general de la configuración de un perfil de funcionalidad en línea para Microsoft Microsoft Dynamics 365 Commerce.

El perfil de funcionalidad en línea proporciona varias configuraciones utilizadas para los canales en línea. Cada canal en línea debe especificar un perfil de funcionalidad en línea.

## <a name="create-an-online-functionality-profile"></a>Crear un perfil de funcionalidad en línea

El siguiente procedimiento explica cómo crear un perfil de funcionalidad en línea desde la aplicación Commerce Headquarters.

1. En el panel de navegación, vaya a **Módulos \> Configuración de canal \> Configuración de la tienda en línea \> Perfiles de funcionalidad**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Perfil**, introduzca un id. para el perfil.
1. En el campo **Descripción**, introduzca un valor ("Perfil de Adventure Works" en la imagen de ejemplo que se muestra a continuación).
1. En la sección **Funciones**, modifique la configuración de **CARRO**, **CLIENTES COMERCIALES** o **FINALIZAR COMPRA**, según sea necesario.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra un perfil de funcionalidad en línea de ejemplo.
  
![Ejemplo de perfil de funcionalidad en línea](media/online-functionality-profile.png)

## <a name="functions"></a>Funciones

- **Productos agregados**: cuando está habilitada, esta función permite que el carro actualice la cantidad cuando se agrega el mismo artículo varias veces.
- **Permitir finalizar compra sin pagos**: cuando está habilitada, esta función maneja el escenario cuando los artículos agregados al carro tienen un precio 0,00 $.
- **Crear cliente en modo asincrónico**: esta es una configuración heredada aplicable a canales de comercio electrónico de terceros y no es aplicable al sitio de comercio electrónico de Dynamics 365.

## <a name="additional-resources"></a>Recursos adicionales

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Configurar un canal en línea](channel-setup-online.md)

[Configurar un canal comercial](channel-setup-retail.md)

[Configurar un canal de centro de llamadas](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
