---
title: Amortizar los costes constantes para un artículo fabricado
description: Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante.
author: JennySong-SH
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: d466395859e19874183691e697c8aca3a774d359
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675414"
---
# <a name="amortize-constant-costs-for-a-manufactured-item"></a>Amortizar los costes constantes para un artículo fabricado

[!include [banner](../includes/banner.md)]

Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante. 

El concepto de tamaño del lote de gestión de costes se usa para amortizar estos costes constantes en el coste calculado de un artículo fabricado. Este concepto tiene varios sinónimos, uno de los cuales es el tamaño del lote de contabilidad. El concepto de costes constantes de amortización también tiene varios sinónimos, uno de los cuales es el de costes constantes proporcionales.

La cantidad del tamaño del lote de gestión de costes para un artículo fabricado se usa en un cálculo de lista de materiales (L. MAT). La cantidad depende de cómo se inicia y realiza el cálculo de L. MAT, tal como se muestra a continuación:

-   La cantidad de cálculo predeterminada en un cálculo de L. MAT de un producto: la cantidad de pedido estándar del artículo para inventario funciona como el tamaño de lote de gestión de costes, pero el valor predeterminado debe ser una cantidad superior para reflejar la cantidad del pedido múltiple del artículo. La cantidad y el múltiplo de pedido estándar del artículo se pueden definir en su configuración de pedido predeterminada o en la configuración específica del pedido.
-   Cantidad de cálculo especificada en el cálculo de L. MAT de un artículo: la cantidad de cálculo especificada actúa como tamaño de lote de gestión de costes para el artículo. La cantidad del cálculo usa inicialmente la cantidad del pedido estándar del artículo; sin embargo, puede reemplazar manualmente los valores predeterminados. La cantidad de cálculo especificada representa el tamaño de lote de gestión de costes para el artículo especificado, y para componentes fabricados con un tipo de producción de línea de L. MAT. Esto se debe a que se supone que el componente va a producirse en la cantidad exacta. El tamaño de lote de gestión de costes para otros componentes fabricados que tengan un tipo de línea de L. MAT de artículo reflejará su cantidad de pedido estándar.
-   Cantidad de cálculo de "hacer para pedir" especificada en el cálculo de L. MAT de un artículo: la cantidad de cálculo especificada actúa como el tamaño de lote de gestión de costes para el artículo y sus componentes fabricados cuando los cálculos de L. MAT usan un modo de expansión de "hacer para pedir". Se supone que va a producir los componentes fabricados en la cantidad exacta, al igual que un componente fabricado con un tipo de línea de L. MAT de producción.
-   Cantidad de cálculo especificada en el cálculo de L. MAT específico de un pedido: un cálculo de L. MAT específico de un pedido se puede realizar para una línea de artículo de un pedido de ventas, un presupuesto de ventas o un pedido de servicio. La cantidad de cálculo especificada utiliza la cantidad del artículo de línea de origen, pero la cantidad predeterminada se puede omitir. Puede seleccionar si el cálculo de L. MAT específico del pedido utiliza un modo de expansión de "hacer para pedir" o multinivel.

El importe calculado de los costes constantes amortizados de un artículo se denomina gastos.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]