---
title: Restricciones en versiones de gestión de costes para costes estándar
description: Este artículo describe las restricciones que se aplican una versión de gestión de costes para costes estándar.
author: JennySong-SH
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8c5c00ae8952e2c80d97d039271a6f5c63e9a72f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867996"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>Restricciones en versiones de gestión de costes para costes estándar

[!include [banner](../includes/banner.md)]

Este artículo describe las restricciones que se aplican una versión de gestión de costes para costes estándar. 

Las siguientes restricciones ayudan garantizar el cumplimiento de los principios de gestión de costes estándar:

-  Los gastos deben incluirse en el coste de un artículo. Los gastos de un artículo fabricado representan los costes constantes amortizados de la lista de materiales (L. MAT.) y la información de ruta, Por tanto, los gastos deben incluirse en el coste unitario. Los gastos de los artículos fabricados se incluirán también en el coste unitario.

-  El cálculo de costes estándar de los artículos fabricados debe basarse en los registros de costes de la versión de gestión de costes estándar. Solo se pueden utilizar otros orígenes de datos de costes con una versión de gestión de costes para costes planificados, como acuerdos comerciales de precios de compra de artículos adquiridos. Los otros orígenes de datos de costes están definidos por el grupo de cálculo de L. MAT.

-  Los cálculos de L. MAT. deben ejecutarse en un modo de expansión de un único nivel.

Los datos de costes estándar de un artículo pueden copiarse en otra versión de gestión de costes que incluya costes estándar o costes planificados. Sin embargo, los datos de costes planificados de un artículo no pueden copiarse en una versión de costes que incluya costes estándar, debido a que las restricciones que se describen anteriormente en este artículo no se aplican a los costes planificados.

## <a name="related-articles"></a>Artículos relacionados

[Visión general de las versiones de gestión de costes](costing-versions.md)

[Actualizar costes estándar en un entorno de no fabricación](update-standard-costs-non-manufacturing-environment.md)

[Preparar el mantenimiento de los costes estándar de artículos fabricados](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]