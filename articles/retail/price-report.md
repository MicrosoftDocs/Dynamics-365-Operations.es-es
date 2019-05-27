---
title: Informes de precio comercial
description: Este tema proporciona una visión general de la función del informe de precio que pueda utilizar para ver los próximos cambios de precio para los productos.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 72f4d248f3ac49bbfd8e5a7a12352d92b89bb0eb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564956"
---
# <a name="retail-price-reports"></a>Informes de precio comercial

[!include [banner](includes/banner.md)]


Para proporcionar precios competitivos a sus clientes, los minoristas cambian a menudo precios de los productos. Los encargados de la tienda desean la habilidad de tener acceso a cambios de precio recientes o próximos de modo que puedan planificar los recursos requeridos para actualizar las etiquetas de precio presentadas en las estanterías de una tienda. Con el lanzamiento 10.0 de Dynamics 365 for Retail un encargado de tienda puede abrir el informe **Precio** yendo a **Todas las tiendas al por menor \> Almacén \> Informe de precio** y ver los precios actualizados de los productos asociados a la tienda. 

Para habilitar el informe de precio, el parámetro **Informe de precio para tienda comercial** se debe activar. Este parámetro está en la pestaña **Parámetros de ventas \> Descuentos \> Varios**. Abriendo la página **Informe de precio** aparece un cuadro de diálogo con distintas configuraciones. Las configuraciones disponibles se muestran a continuación.

| Configuración | Descripción |
|---|---|
| Desde / hasta fecha| El intervalo de fechas para el que el informe del precio se va a producir. La duración se limita actualmente en 7 días. |
| Canal| La tienda minorista para la que se va a producir el informe del precio. |
| Mostrar productos con inventario disponible| Establecer esto en **Sí** mostrará los precios para solo los productos que tiene actualmente inventario físico disponible en la tienda. |
| Mostrar precios de las variantes | Establecer esto en **Sí** mostrará los precios de variantes junto con los productos maestros. Éste solo debe ser **Activado** si tiene precios específicos de variantes, porque el número de filas puede crecer mucho. En versiones futuras, habilitaremos los precios basados en dimensiones de modo que el encargado de tienda puede elegir las dimensiones para las que los precios deben mostrarse. |
| Mostrar productos con cambios de precio | Establecer esto en **Sí** mostrará los índices por solo las fechas en las que se ha cambiado el precio. El precio para *un día antes* seleccionado **Desde fecha** se mostrará siempre, de modo que el encargado de tienda pueda identificar con facilidad los productos que no han cambiado los precios durante la duración completa seleccionada, y también puede ver el precio actual. |

Después de que se cree el informe, el archivo de Excel se puede descargar para usar cualquier filtro necesario. El informe del precio se puede usar para comprobar los precios históricos de los productos por últimas fechas.
