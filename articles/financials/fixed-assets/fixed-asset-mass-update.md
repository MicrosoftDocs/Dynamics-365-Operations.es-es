---
title: Actualización masiva de activos fijos
description: Si utiliza libros, puede modificar las convenciones de depreciación de grupos de activos que forman parte del mismo libro.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 30b9aaaabcac09c9147c350422924a23f785c0ce
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840418"
---
# <a name="fixed-asset-mass-update"></a>Actualización masiva de activos fijos

[!include [banner](../includes/banner.md)]

Si utiliza libros, puede modificar las convenciones de depreciación de grupos de activos que forman parte del mismo libro.

Por ejemplo, si se encuentra en los Estados Unidos y ha puesto más de un 40 por ciento de sus activos en servicio durante el cuarto trimestre del año, deberá utilizar la convención de depreciación de mitad del trimestre. Puede utilizar el proceso de actualización masiva para modificar todos los activos a los que se deba aplicar la nueva convención de depreciación 

Cuando se actualiza la convención de depreciación de los activos, se eliminan todas las transacciones de depreciación que existan para dichos activos. Eliminará también todas las transacciones para los ajustes de depreciación, las transacciones para la depreciación de bonificación y las transacciones para la depreciación extraordinaria para dichos activos. 

Para actualizar la convención de amortizaciones para los activos que se han sido cancelado, primero debe eliminar las transacciones de cancelación existentes. También deben eliminar todas las transacciones que se han generado debido al proceso de cancelación. 

Tras actualizar la convención de depreciación de los activos, puede procesar la depreciación y depreciación extraordinaria de cada activo. También puede realizar los ajustes manuales de depreciación, si se requieren.





