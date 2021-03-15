---
title: Actualizar costes estándar en un entorno de no fabricación
description: Este artículo proporciona orientación para actualizar los costes estándar en un entorno de no fabricación.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bb4437078b2fd17a4edc6a66567da8c1741813f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983784"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Actualizar costes estándar en un entorno de no fabricación

[!include [banner](../includes/banner.md)]

Este artículo proporciona orientación para actualizar los costes estándar en un entorno de no fabricación.

En las directrices siguientes se supone que se usa el enfoque de dos versiones para actualizar el coste estándar. En este enfoque, una versión de gestión de costes contiene los costes estándar que se definieron originalmente para el período congelado y la segunda versión de gestión de costes contiene las actualizaciones incrementales. Cada actualización se especifica como un registro de coste incluido en la segunda versión de gestión de costes y, finalmente, se activa. El enfoque alternativo de una versión utiliza el conjunto de costes estándar que se definió originalmente. El enfoque de dos versiones requiere que defina una segunda versión de gestión de costes. Esta son las instrucciones para definir esta versión de gestión de costes:

-   Asigne un tipo de gestión de costes de **Costes estándar**.
-   Asigne un identificador significativo que indique el contenido de la versión de gestión de costes como, por ejemplo, **2016-ACTUALIZACIONES**.
-   Asegúrese de que el contenido incluya registros de costes.
-   Permita la entrada de registros de costes para todos los sitios. Si especifica un sitio, los registros de costes se pueden especificar solo para ese sitio.
-   Indique un principio de reserva igual a **Ninguno**. El principio de reserva solo se aplica a los cálculos de coste para artículos fabricados.

Para corregir, ajustar o actualizar costes estándar para nuevos artículos, siga estos pasos:

1.  Utilice la página **Configuración de la versión de** **gestión de costes** para permitir la entrada de datos de coste en la segunda versión de gestión de costes. También puede evitar la activación de costes pendientes, de modo que la activación se permita después de que los costes pendientes se hayan definido completa y detalladamente. También puede especificar de forma opcional una fecha en el campo **Fecha inicial**. Como regla general, use la fecha que represente en la que desea habilitar las actualizaciones incrementales. Como método alternativo, deje el campo **Fecha inicial** en blanco para la versión de gestión de costes y, a continuación, indique una fecha en el campo **Fecha inicial** para cada registro de coste.
2.  Utilice la página **Precio de artículo** para especificar las actualizaciones como registros de coste del artículo incluidos en la segunda versión de gestión de costes.
3.  Utilice el informe **Precios del artículo** para comprobar si los registros de costes de artículos incluidos en la segunda versión de gestión de costes están completos y son precisos.
4.  Utilice la página **Mantenimiento de la versión de gestión de costes** para modificar el indicador de bloqueo y permitir la activación de los registros de costes pendientes incluidos en la segunda versión de gestión de costes.
5.  Use la página **Activar precios** (que se abre desde la página **Mantenimiento de la versión de gestión de costes**) para activar todos los registros de costes de artículos pendientes que se incluyen en la segunda versión de gestión de costes. También puede activar los registros de costes pendientes para los artículos individuales haciendo clic en la página **Activar precios pendientes** de la página **Precio de artículo**.
6.  Para impedir la actualización posterior de los datos, use la página **Configuración de la versión de gestión de costes** para modificar los indicadores de bloqueo incluidos en la segunda versión de gestión de costes. Las directivas de bloqueo impedirán la entrada de nuevos costes pendientes y la activación de costes pendientes.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]