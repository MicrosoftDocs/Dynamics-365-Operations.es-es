---
title: Programación maestra de empresas vinculadas
description: Este tema explica la programación maestra de empresas vinculadas
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 02d1a3675cfe30f2e72237f69509398122d17f05
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671881"
---
# <a name="intercompany-master-scheduling"></a>Programación maestra de empresas vinculadas

[!include [banner](../../includes/banner.md)]

La programación maestra de empresas vinculadas es el medio por el que se calculan los requisitos y se generan los pedidos de empresas vinculadas planificados de varias empresas internas. La programación maestra de empresas vinculadas se realiza sobre el número de iteraciones especificado. Para habilitar Microsoft Dynamics 365 Supply Chain Management para que realice la programación maestra de empresas vinculadas, debe configurar la programación maestra en cada empresa vinculada. Esto conlleva un varias iteraciones en las que Microsoft Dynamics 365 Supply Chain Management crea automáticamente un pedido de compra de empresas vinculadas, lo cual, a su vez, conduce a la creación automática de un pedido de ventas de empresas vinculadas, que de nuevo conduce a nuevas demandas.

El plan maestro de empresas vinculadas y el pedido de programación de empresas vinculadas se configuran en los parámetros de **Planificación maestra** de cada una de las empresas vinculadas.

Para extender la demanda a la cadena de empresas vinculadas, debe establecer los parámetros para garantizar que se pongan en firme automáticamente los pedidos de compra planificados, es decir, los pedidos no se pueden modificar en términos de hora o cantidad. Configure el **Límite de tiempo de puesta en firme** en el grupo de Cobertura, o en el **Límite de tiempo de puesta en firme** en el plan maestro. Si no se ha configurado ningún **Límite de tiempo de puesta en firme**, no se crea automáticamente ningún pedido de compra de empresas vinculadas. Solo la primera ejecución de la programación maestra da como resultado órdenes planificadas. Sin embargo, dado que no se crea ningún pedido de compra de empresas vinculadas, no se crea ningún pedido de venta de empresas vinculadas y, por lo tanto, no se crean más pedidos de compra de empresas vinculadas, etc.

Al iniciar la programación maestra de empresas vinculadas, Microsoft Dynamics 365 Supply Chain Management realiza una programación maestra en cada empresa vinculada, a continuación, realiza una segunda programación maestra en cada empresa vinculada y, así, sucesivamente, hasta que se alcanza el número de iteraciones especificado. Se permite un máximo de 30 iteraciones, pero cuantas más iteraciones seleccione, mayor será la programación que conlleve.

Dado que la programación maestra en las empresas la controla la secuencia de programación de empresas vinculadas (es decir, el orden en el que el programa prioriza las programaciones maestras entre cada empresa vinculada), puede iniciar la programación maestra de empresas vinculadas desde cualquier empresa vinculada. Debido a que la secuencia de programación de empresas vinculadas determina el orden en que se realiza la programación maestra en las empresas, no es importante dónde se inicia la programación maestra de empresas vinculadas. En cada iteración, la empresa actual se ejecuta en último lugar.

> [!NOTE]
> La mejor práctica consiste en permitir la iniciación de la programación maestra de empresas vinculadas desde una empresa de Microsoft Dynamics 365 Supply Chain Management.

En la página **Programación maestra de empresas vinculadas**, puede iniciar una secuencia de programación maestra, que ejecuta una programación maestra la primera vez con el principio para actualizar el cálculo de requisitos que ha seleccionado para la primera iteración de todas las empresas vinculadas. Las iteraciones posteriores utilizan el principio secundario que seleccione para la siguiente iteración y este principio se aplica hasta que se alcance el número de iteraciones que haya especificado.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
