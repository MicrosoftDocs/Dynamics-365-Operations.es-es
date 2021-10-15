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
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 776c73b1a29666e393bed7c40059a578fe86cb0d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576193"
---
# <a name="transportation-management-miscellaneous-charges"></a>Gastos varios de gestión de transporte

[!include [banner](../includes/banner.md)]

Como sucede con los cargos varios, los cargos generados por el transporte deben asociarse con un código de cargo. De lo contrario, no se volverán a agregar al pedido como un cargo diverso. El **Código de cargos** determina cómo se contabiliza el cargo en relación con el pedido y la línea de pedido donde se agrega.

Vaya a **Gestión de transporte > Configuración > Clasificación > Cargos varios** para definir los criterios de calificación que determinan cuándo un **Código de cargos** se aplica a un cargo.

Debe tener al menos una configuración para cada ajuste correspondiente de **Módulo de cargas** (*Cliente* y *Vendedor*) donde **Tipo de cargos varios** se establece en *Ninguno*. Si falta, los cargos varios *no* se agregan al pedido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]