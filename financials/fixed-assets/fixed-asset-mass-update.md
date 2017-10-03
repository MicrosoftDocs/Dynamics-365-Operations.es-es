---
title: "Actualización masiva de activos fijos"
description: "Si utiliza libros, puede modificar las convenciones de depreciación de grupos de activos que forman parte del mismo libro."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a16bae8f13dd53b5bbe380f03f6ca399bd6dbd9a
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-asset-mass-update"></a>Actualización masiva de activos fijos

[!include[banner](../includes/banner.md)]


Si utiliza libros, puede modificar las convenciones de depreciación de grupos de activos que forman parte del mismo libro.

Por ejemplo, si se encuentra en los Estados Unidos y ha puesto más de un 40 por ciento de sus activos en servicio durante el cuarto trimestre del año, deberá utilizar la convención de depreciación de mitad del trimestre. Puede utilizar el proceso de actualización masiva para modificar todos los activos a los que se deba aplicar la nueva convención de depreciación 

Cuando se actualiza la convención de depreciación de los activos, se eliminan todas las transacciones de depreciación que existan para dichos activos. Eliminará también todas las transacciones para los ajustes de depreciación, las transacciones para la depreciación de bonificación y las transacciones para la depreciación extraordinaria para dichos activos. 

Para actualizar la convención de amortizaciones para los activos que se han sido cancelado, primero debe eliminar las transacciones de cancelación existentes. También deben eliminar todas las transacciones que se han generado debido al proceso de cancelación. 

Tras actualizar la convención de depreciación de los activos, puede procesar la depreciación y depreciación extraordinaria de cada activo. También puede realizar los ajustes manuales de depreciación, si se requieren.






