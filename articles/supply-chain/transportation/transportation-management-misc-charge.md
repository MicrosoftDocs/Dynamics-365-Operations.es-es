---
title: Gastos varios de gestión de transporte
description: Este tema explica cómo los cargos generados por el transporte deben asociarse con un código de cargo.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 53c25f204e98a911e9697f5bb950706555749a55
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828331"
---
# <a name="transportation-management-miscellaneous-charges"></a>Gastos varios de gestión de transporte

[!include [banner](../includes/banner.md)]

Como sucede con los cargos varios, los cargos generados por el transporte deben asociarse con un código de cargo. De lo contrario, no se volverán a agregar al pedido como un cargo diverso. El **Código de cargos** determina cómo se contabiliza el cargo en relación con el pedido y la línea de pedido donde se agrega.

Vaya a **Gestión de transporte > Configuración > Clasificación > Cargos varios** para definir los criterios de calificación que determinan cuándo un **Código de cargos** se aplica a un cargo.

Debe tener al menos una configuración para cada ajuste correspondiente de **Módulo de cargas** (*Cliente* y *Vendedor*) donde **Tipo de cargos varios** se establece en *Ninguno*. Si falta, los cargos varios *no* se agregan al pedido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]