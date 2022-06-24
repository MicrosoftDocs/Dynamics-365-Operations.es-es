---
title: Gastos varios de gestión de transporte
description: Este artículo explica cómo los cargos generados por el transporte deben asociarse con un código de cargo.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 8cc4c595d8b61cb9b6c81af4bf7f03faa1a12960
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849224"
---
# <a name="transportation-management-miscellaneous-charges"></a>Gastos varios de gestión de transporte

[!include [banner](../includes/banner.md)]

Como sucede con los cargos varios, los cargos generados por el transporte deben asociarse con un código de cargo. De lo contrario, no se volverán a agregar al pedido como un cargo diverso. El **Código de cargos** determina cómo se contabiliza el cargo en relación con el pedido y la línea de pedido donde se agrega.

Vaya a **Gestión de transporte > Configuración > Clasificación > Cargos varios** para definir los criterios de calificación que determinan cuándo un **Código de cargos** se aplica a un cargo.

Debe tener al menos una configuración para cada ajuste correspondiente de **Módulo de cargas** (*Cliente* y *Vendedor*) donde **Tipo de cargos varios** se establece en *Ninguno*. Si falta, los cargos varios *no* se agregan al pedido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]