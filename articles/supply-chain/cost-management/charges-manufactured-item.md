---
title: Visualización de los gastos para un artículo fabricado
description: Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante.
author: JennySong-SH
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: f97495488dbbe504a5e79ef7f65fa97eb287d17b
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675442"
---
# <a name="display-charges-for-a-manufactured-item"></a>Visualización de los gastos para un artículo fabricado

[!include [banner](../includes/banner.md)]

Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante.

El importe calculado de los gastos del artículo se puede mostrar con los costes unitarios del artículo. No obstante, los gastos se muestran en ocasiones en campos diferentes, y no se incluyen en los costes unitarios del artículo. Cuando los gastos aparecen en campos diferentes, uno de los campos muestra el importe total de los gastos totales y el otro campo muestra el tamaño del lote de costes que se utiliza para amortizar el importe. La página Precio de artículo, por ejemplo, muestra los gastos en dos campos diferentes. Sin embargo, la página Completado muestra el coste total por unidad del artículo y los costes amortizados se incluyen en los costes unitarios.

Los gastos de un artículo fabricado se incluyen siempre en el coste unitario del artículo con el fin de calcular los costes estándar. De forma opcional, pueden incluirse para calcular los costes planificados. La directiva de la versión de gestión de costes exige incluir los gastos en el coste de un artículo fabricado. Cuando se activa el registro de costes de un artículo, deberá actualizar los gastos de la información del coste base del artículo que se muestra en la página Precio de artículo. Los gastos se muestran en dos campos distintos, y no se incluyen en el coste unitario del artículo. Cada activación actualiza la información del coste base del artículo, a pesar de que la activación refleje sitios diferentes. De ahí que la información de coste base deba considerarse como información de referencia.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]