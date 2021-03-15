---
title: Configurar un canal para usar una jerarquía de navegación de canales
description: En este tema se describe cómo configurar un canal para usar una jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3dcba743e6557b1bd366ac79ecb49ead831dceb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001034"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Configurar un canal para usar una jerarquía de navegación de canales


[!include [banner](includes/banner.md)]

En este tema se describe cómo configurar un canal para usar una jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Las jerarquías de navegación de canales organizan los productos en categorías para que los productos se puedan examinar en un sitio de comercio electrónico o en puntos de venta (PDV). Los canales comerciales y en línea deben configurarse con jerarquías de navegación de canales.

## <a name="configure-the-channel"></a>Configurar el canal

Para configurar un canal de forma que use una jerarquía de navegación de canales, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.
1. Seleccione el canal que desea configurar.
1. En el panel de acciones, seleccione **Establecer metadatos de atributos**.
1. En la lista desplegable **Jerarquía de categorías**, seleccione la jerarquía de navegación de canales apropiada.
1. En el panel de acciones, seleccione **Guardar**.
1. En **Grupo de atributos**, agregue los grupos de atributos que serán atributos globales para todos los nodos.

La siguiente imagen muestra cómo se configura un canal para usar una jerarquía de navegación de canales.

![Ejemplo de configuración de canal](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Configurar metadatos de atributos

Establecer los metadatos de atributos permitirá configurar los atributos en cada nodo.

Para establecer metadatos de atributos, siga estos pasos.

1. En el panel de acciones, seleccione **Establecer metadatos de atributos**.
1. Para cada nodo, seleccione **Atributos de producto del canal**.
1. Establezca **Mostrar atributo en el canal** en **Sí** y **Se puede refinar** en **Sí** para habilitar los refinadores en ese canal.
1. Después de configurar cada nodo como desee, en el **Panel de acciones**, seleccione el botón **Guardar** para guardar.
1. Selecciona la **X** en la esquina superior derecha para salir de esta pantalla y volver a la página **Categorías de canal y atributos de producto**.

La siguiente imagen muestra un conjunto de ejemplos de atributos de producto de canal configurados en un nodo de categoría de canal.

![Atributos de canal en un nodo de categoría de canal](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Publicar cambios

Para que los cambios surtan efecto debe publicarlos.

Para publicar cambios, siga estos pasos.

1. En el panel de acciones, seleccione **Publicar actualizaciones de canal**.
1. En el panel **Publicar actualizaciones de canal**, seleccione **Aceptar**.

La siguiente imagen muestra cómo publicar actualizaciones de canal.

![Publicar actualizaciones de canal](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>Recursos adicionales

[Crear una jerarquía de navegación de canales](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]