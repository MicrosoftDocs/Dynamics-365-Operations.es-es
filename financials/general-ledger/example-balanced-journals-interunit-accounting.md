---
title: "Diarios equilibrio para las estadísticas de interunit"
description: "Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 8b6fda79222905b0df211a0b944aca9e4dc76850
ms.lasthandoff: 03/31/2017


---

# <a name="balanced-journals-for-interunit-accounting"></a>Diarios equilibrio para las estadísticas de interunit

Este artículo muestra cómo se compensa automáticamente un diario cuando se selecciona una dimensión financiera de equilibrio en la página Libro mayor. 

Si los asientos contables no se equilibran en el nivel de los valores de la dimensión financiera, se crean automáticamente asientos contables adicionales para equilibrar el diario. Estos asientos contables usan los tipos de registro **Interunidad: débito** y** Interunidad: crédito** de la página **Cuentas para transacciones automáticas** para determinar la cuenta principal. Por ejemplo, Sucursal, que es el segundo segmento de la cuenta contable, se selecciona como dimensión financiera de compensación y los asientos contables siguientes que se van a crear.

|                      |           |
|----------------------|-----------|
| 6100 – MSP – unidades organizativas\_256 | 100,00 DR |
| 6100 – NY – unidades organizativas\_249  | 100,00 DR |
| 2100 – MSP – unidades organizativas\_256 | 200,00 CR |

En este caso, se determinan los saldos siguientes:

-   Para la sucursal MSP = 100,00 CR
-   Para la sucursal NY = 100,00 DR

Por lo tanto, los siguientes asientos contables se crean automáticamente para equilibrar el diario en el nivel de los valores de la dimensión financiera.

|                                   |           |
|-----------------------------------|-----------|
| Débito () de Interunit – MSP – Unidad organizativa\_256 | 100,00 DR |
| Crédito () de Interunit – NY – Unidad organizativa\_249 | 100,00 CR |




