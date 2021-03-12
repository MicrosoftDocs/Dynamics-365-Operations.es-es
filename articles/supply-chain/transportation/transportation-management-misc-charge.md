---
title: Gastos varios de gestión de transporte
description: Este tema explica cómo los cargos generados por el transporte deben asociarse con un código de cargo.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cb503072fb76e04aa01ff2d231c756eeb244c65a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004711"
---
# <a name="transportation-management-miscellaneous-charges"></a>Gastos varios de gestión de transporte

[!include [banner](../includes/banner.md)]

Como sucede con los cargos varios, los cargos generados por el transporte deben asociarse con un código de cargo. De lo contrario, no se volverán a agregar al pedido como un cargo diverso. El **Código de cargos** determina cómo se contabiliza el cargo en relación con el pedido y la línea de pedido donde se agrega.

Vaya a **Gestión de transporte > Configuración > Clasificación > Cargos varios** para definir los criterios de calificación que determinan cuándo un **Código de cargos** se aplica a un cargo.

Debe tener al menos una configuración para cada ajuste correspondiente de **Módulo de cargas** (*Cliente* y *Vendedor*) donde **Tipo de cargos varios** se establece en *Ninguno*. Si falta, los cargos varios *no* se agregan al pedido.
