---
title: Crear un perfil de funcionalidad comercial
description: Este tema describe cómo crear un perfil de funcionalidad en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b8d481597485775796290f61de19ef7682cb9f43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792007"
---
# <a name="create-a-retail-functionality-profile"></a>Crear un perfil de funcionalidad comercial

[!include [banner](includes/banner.md)]

Este tema describe cómo crear un perfil de funcionalidad en Microsoft Dynamics 365 Commerce.

El perfil de funcionalidad comercial proporciona varias configuraciones utilizadas para los canales en línea. Cada canal debe especificar un perfil de funcionalidad.

## <a name="create-a-functionality-profile"></a>Crear un perfil de funcionalidad

Para crear un perfil de funcionalidad, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Configuración de canal \> Perfiles de PDV \> Perfiles de funcionalidad**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Perfil**, introduzca un id. para el perfil ("FN006" en la imagen de ejemplo que se muestra a continuación).
1. En el campo **Descripción**, introduzca un valor ("Perfil de Adventure Works" en la imagen de ejemplo que se muestra a continuación).
1. En la sección **General**, seleccione un país para la configuración regional **ISO**.
1. En la sección **General**, modifique otros ajustes, según sea necesario.
1. En la sección **General**, seleccione un **Id. de perfil de recibo** para recibos por correo electrónico.
1. En la sección **Funciones**, modifique la configuración, según sea necesario.
1. En la sección **Importe**, modifique la configuración según sea necesario.
1. En la sección **Códigos de información**, modifique la configuración, según sea necesario.
1. En la sección **Numeración del recibo**, modifique la configuración, según sea necesario. 
  
La siguiente imagen muestra un perfil de funcionalidad de ejemplo.
  
![Ejemplo de perfil de funcionalidad](media/retail-functionality-profile.png)

## <a name="additional-resources"></a>Recursos adicionales

[Códigos de información y grupos de códigos de información](info-codes-retail.md)           

[Crear nueva libreta de direcciones](new-address-book.md) 

[Visión general del diseño de pantalla](pos-screen-layouts.md)       

[Instalar y configurar Retail Hardware Station](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
