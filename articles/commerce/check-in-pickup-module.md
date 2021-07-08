---
title: Módulo de registro para recogida
description: En este tema se describe el módulo de registro para recogida y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0baa922afc72778dd6e4836398a280cbe6abaec2
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270592"
---
# <a name="check-in-for-pickup-module"></a>Módulo de registro para recogida

[!include [banner](includes/banner.md)]

En este tema se describe el módulo de registro para recogida y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.

El módulo de registro para recogida proporciona una página de confirmación para los clientes que utilizan las capacidades de recepción de clientes de Dynamics 365 Commerce para notificar a una tienda sobre su llegada. El módulo de registro para recogida también le permite configurar un formulario que recopila información adicional de los clientes para facilitar la entrega del pedido. Esta información incluye el número de la plaza de estacionamiento del cliente y la marca y modelo de su vehículo. 

## <a name="module-properties"></a>Propiedades del módulo

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Texto de confirmación | Cadena de texto | Contenido del título que aparece en la página de confirmación de registro. |
| Mostrar código QR | **Verdadero** o **Falso** | Cuando esta propiedad se establece en **Verdadero**, la página de confirmación de registro muestra un código QR que representa el id. de confirmación del pedido. |
| Título de información adicional | Cadena de texto | Contenido del encabezado que aparece cuando se han configurado campos de información adicional. |
| Claves de información adicional | Par id. de recurso/valor de recurso | Cada clave crea un campo de formulario y una etiqueta asociada que se utilizan para recopilar información adicional de los clientes. |
| Claves de información adicional \> id. de recurso | Cadena de texto | Cada clave de información crea un campo de formulario y una etiqueta asociada que se utilizan para recopilar información adicional de los clientes. Esta propiedad identifica la clave de información adicional. En la tarea que se crea en el punto de venta (PDV), el valor de esta propiedad se muestra como la etiqueta en el campo de instrucciones. |
| Claves de información adicional \> Valor de recurso | Cadena de texto | La etiqueta del campo de texto en la tarea en el PDV. |
| Claves de información adicional \> Necesarias | **Verdadero** o **Falso** | Esta propiedad especifica si los clientes deben completar el campo del formulario antes de poder continuar. Cuando esta propiedad se establece en **Verdadero**, se muestra un asterisco junto a la etiqueta del formulario y se realiza una verificación de NULL para evitar que los clientes continúen si no se introduce ningún valor. |

## <a name="add-the-check-in-for-pickup-module-to-a-page"></a>Agregar el módulo de registro para recogida en una página

El módulo de registro para recogida debe agregarse a la nueva página que crea para la confirmación del registro. Esa página servirá como experiencia de confirmación de registro para los clientes que seleccionen el vínculo o botón **Estoy aquí** en su correo electrónico. 

## <a name="configure-the-additional-information-form"></a>Configurar el formulario de información adicional

De forma predeterminada, si no se configuran claves de información adicional, el módulo muestra a los clientes la página de confirmación de registro. A medida que se muestra la confirmación del registro, se crea una tarea en el PDV donde se está recogiendo el pedido.

Cuando se configuran una o más claves de información adicional, primero se solicita a los clientes que introduzcan información. Cuando seleccionan **Enviar**, se les muestra la confirmación de registro y se crea una tarea en el PDV. 

## <a name="additional-resources"></a>Recursos adicionales

[Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)](enable-customer-check-in.md)
