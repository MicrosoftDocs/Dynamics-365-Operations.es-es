---
title: Diarios equilibrados para la contabilidad interunidad
description: Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e84d96b5467b38e07a9ed31f142c27b638289284
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447492"
---
# <a name="balanced-journals-for-interunit-accounting"></a>Diarios equilibrados para la contabilidad interunidad

[!include [banner](../includes/banner.md)]

Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor. 

Si los asientos contables no se equilibran en el nivel de los valores de la dimensión financiera, se crean automáticamente asientos contables adicionales para equilibrar el diario. Estos asientos contables usan los tipos de registro **Interunidad: débito** y **Interunidad: crédito** de la página **Cuentas para transacciones automáticas** para determinar la cuenta principal. Por ejemplo, Unidad de negocio, que es el segundo segmento de la cuenta contable, se selecciona como dimensión financiera de compensación y los asientos contables siguientes que se van a crear.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100,00 DR |
| 6100 – NY – OU\_249  | 100,00 DR |
| 2100 – MSP – OU\_256 | 200,00 CR |

En este caso, se determinan los saldos siguientes:

-   Para Unidad de negocio MSP = 100.00 CR
-   Para Unidad de negocio NY = 100.00 DR

Por lo tanto, los siguientes asientos contables se crean automáticamente para equilibrar el diario en el nivel de los valores de la dimensión financiera.

|                                   |           |
|-----------------------------------|-----------|
| (Interunidad: débito): MSP: OU\_256 | 100,00 DR |
| (Interunidad: crédito): NY: OU\_249 | 100,00 CR |





